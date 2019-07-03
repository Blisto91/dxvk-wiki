## Compilation
### Mingw Version
Make sure you're using at least mingw-gcc 7.0. Older versions are unsupported.

### Threading support
DXVK requires threading support from your mingw-w64 build environment. If you are missing this, you may see "error: 'mutex' is not a member of 'std'". On Debian and Ubuntu, this can usually be resolved by using the posix alternate, which supports threading. For example, choose the posix alternate from these commands (use i686 for 32-bit):

```
update-alternatives --config x86_64-w64-mingw32-gcc
update-alternatives --config x86_64-w64-mingw32-g++
```

On gentoo: see https://github.com/doitsujin/dxvk/issues/184

## Crashes
First, look for the dxvk log files called `game_d3d11.log` and `game_dxgi.log` that should be in the same directory as the game executable. If you can't find these log files, that means dxvk wasn't used and you probably made a mistake in setting up dxvk or the game didn't use d3d11.

Second, run the game with wined3d: `WINEDLLOVERRIDES="d3d11,dxgi=b" wine game.exe` . If the game crashes in the exact same manner as dxvk, it is most likely not a dxvk bug.

### Unimplemented function: d3dx11_43...
If you see errors related to any of the `d3dx` libraries, install the native version of that library using winetricks, e.g. `d3dx11_43`. These functions are not part of D3D11, and please **do not** report any issues related to them to the DXVK bug tracker.


### 32-bit games

32-bit games often run out of address space and will crash as a result. This is an inherent limitation of DXVK and cannot be fixed. Use wined3d for 32-bit games instead.

### Steam / Uplay overlay

In some cases, overlays are responsible for crashes. Make sure you have them disabled if you run into trouble.

### Vulkan errors
If you see `DxvkInstance: Failed to create instance` in the dxgi log file, there's something wrong with your vulkan setup. 

You'll need at least wine 3.6, built with vulkan support. Playonlinux and some distros' wine builds do not have vulkan support.

Next, make sure you've got vulkan libraries installed on your system.

On ubuntu: `sudo apt-get install libvulkan1 libvulkan1:i386`

On arch linux: `sudo pacman -S vulkan-icd-loader lib32-vulkan-icd-loader`

If you're on AMD, you'll also need to install the vulkan driver separately.

On ubuntu: `sudo apt-get install mesa-vulkan-drivers mesa-vulkan-drivers:i386`

On arch linux: `sudo pacman -S vulkan-radeon lib32-vulkan-radeon`

### Conflicting drivers
If you've got `DxvkSurface::createSurface: Surface not supported by device` and messages about both Intel HD graphics and your dedicated graphics card in the dxgi log, your integrated graphics drivers might be causing issues. Run your game with `VK_ICD_FILENAMES=/usr/share/vulkan/icd.d/radeon_icd.x86_64.json` for AMD 64 bit or with `VK_ICD_FILENAMES=/usr/share/vulkan/icd.d/nvidia_icd.json` for nvidia.

### GPU hangs
Games hanging the entire system is a somewhat common occurence on AMD cards. These are driver issues that will be fixed in future releases. Using the latest mesa-git with the latest llvm-svn may fix your hang. See https://github.com/doitsujin/dxvk/issues/252

### NVAPI
Some games may use `nvapi.dll` or `nvapi64.dll` when detecting an Nvidia GPU. The wine-staging implementation of these DLLs does not work with DXVK and should be disabled in winecfg, or otherwise games may crash or suffer from visual issues.

Some games assume that `nvapi` is present regardless. In this case, spoofing an AMD GPU using the `dxgi.customVendorId` configuration option may help.

### Overwatch is broken
Yes, this is normal, and each time they fix it, the game comes up with another way to break on DXVK. Debugging this game is next to impossible, so it's unlikely that any issues with this game will get fixed. Use wined3d instead.

## Graphical issues
### Drivers
Take a look at the drivers section and make sure they are up-to-date.

## Errors about missing D3D11 support
In this case, it is likely that DXVK fails to load. Possible reasons include:
- DXVK is not set up correctly and the game does not find the DLLs. Make sure to set up **both** 64-bit and 32-bit DXVK in the same Wine prefix.
- No Vulkan loader or driver is installed for the target architecture. Make sure to install both the respective 64-bit and 32-bit packages.
- Your [Vulkan driver](https://github.com/doitsujin/dxvk/wiki/Driver-support) is outdatd, or your hardware/driver does not support the necessary set of features and extensions.

**Note:** Some games, such as World of Warcraft, may work when setting `dxgi.fakeDx10Support = True` in the DXVK configuration file for the game.

## Performance

When experiencing unexpectedly low performance, try setting the CPU governor to `performance`. This is a general recommendation for native OpenGL and Vulkan games as well.

Multithreaded games often perform poorly on CPUs with more than four logical cores with a standard wine build. A workaround is to use an esync-patched wine build.

### Xwayland issues
When running DXVK on Xwayland, even with disabled Vsync, frame rates are capped to the display refresh rate. This is an Xwayland limitation and can be worked by enabling triple buffering in `dxvk.conf`:
```
dxgi.numBackBuffers = 3
```

## Reporting an issue
First off, make sure the issue you're experiencing has not yet been reported by someone else.

### Audio issues
DXVK does not interact with audio and audio issues are most likely not dxvk related. In general running `winetricks xact` fixes a lot of audio issues in wine.

### Input issues
While DXVK is not involved in handling mouse or keyboard input in any way, a lot of games seem to have issues which do not occur with wined3d. The reason for this is unknown, but lies likely within DXVK's implementation of `IDXGISwapChain`.

### Validation layers
It might be useful to run the game with `WINEDEBUG=-all VK_INSTANCE_LAYERS=VK_LAYER_LUNARG_standard_validation wine game.exe` and attach the terminal output to your issue. This requires the `vulkan-validation-layers` package on arch linux to be installed.

### Apitrace
If you're opening an issue and you're having issues with making an apitrace, put [these DLLs]( https://www.dropbox.com/sh/o769ius47wpu3pw/AABYFKQFFNsCsosXhl7_HReDa?dl=0) into the directory where `yourgame.exe` is located. This will create a file `yourgame.trace` without requiring further interaction.