## AMD RADV ([#252](https://github.com/doitsujin/dxvk/issues/252))
- **Recommended driver version:** 18.2.3 or newer. Games that use Stream Output require Mesa 18.3.
- **Note:** LLVM 6 can cause additional issues, such as GPU hangs or rendering bugs, which do not occur with newer LLVM versions. Please use LLVM 7.0 or 8.0-svn if possible.

## Nvidia ([#267](https://github.com/doitsujin/dxvk/issues/267))
- **Recommended driver version:** 396.54
- For Stream Output support and best performance, use 396.54.**09**

## Intel ANV
- Rarely tested. Please use `mesa-git` when testing this driver, and report any issues you run into.

## AMDVLK ([#578](https://github.com/doitsujin/dxvk/issues/578))
- Make sure to run the latest version available. Before reporting issues with this driver, please confirm that the same issue also exists on the RADV driver.

## AMDGPU PRO
- The Vulkan driver version shipping with the 18.30 driver package is outdated and will not work with DXVK.

## Windows drivers
- Unsupported. Any issues that are exclusive to Windows will be ignored.