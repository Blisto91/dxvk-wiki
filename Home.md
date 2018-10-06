DXVK provides a Vulkan-based translation layer for DXGI, D3D10 and D3D11, which can be used on Linux with Wine.

## Feature support
DXVK aims to provide support for D3D11, feature level 11_1, and D3D10, feature level 10_1.

Features that are still missing:
- Predication (On hold)
- Stream output (Work in Progress)

## Performance considerations
In order to get the best results, the following steps are recommended:
- Use an [esync](https://github.com/zfigura/wine/tree/esync)-enabled wine build, which dramatically reduces CPU overhead in some games. Lutris may offer such builds out of the box, and for Arch Linux, a PKGBUILD is available [here](https://github.com/Tk-Glitch/PKGBUILDS).
- Set the CPU frequency governor to `performance` on AMD and older Intel CPUs.
- Disable your compositor, as that can lead to severe stuttering issues when games are GPU-bound.