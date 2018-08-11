DXVK provides a Vulkan-based compatibility layer for DXGI and D3D11, which may be used to run 3D applications on Linux using Wine.

## Feature support
DXVK aims to provide support for D3D11, feature level 11_0.

Features that are still missing:
- Predication (Work in Progress)
- Stream output

## Performance considerations
Depending on the game and your hardware configuration, performance with DXVK can be expected to be between 50% and 70% of native Windows performance.

In order to get the best results, the following steps are recommended:
- Use an [esync](https://github.com/zfigura/wine/tree/esync)-enabled wine build, which dramatically reduces CPU overhead in some games. Lutris may offer such builds out of the box, and for Arch Linux, a PKGBUILD is available [here](https://github.com/Tk-Glitch/PKGBUILDS).
- Set the CPU frequency governor to `performance`