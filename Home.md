DXVK provides a Vulkan-based translation layer for D3D9, D3D10 and D3D11, which can be used on Linux with Wine.

## D3D11 Feature support
DXVK aims to provide support for D3D11, feature level 11_1, and D3D10, feature level 10_1.

Currently unsupported features:
- D3D11: Shared Resources.
- D3D11: Class linkage.
- D3D11: Predication. Currently disabled due to implementation issues.
- D3D11: Arbitrary sampler border colors, due to lack of Vulkan support for this feature.
- D3D11.1: Target-independent rasterization (behaves incorrectly; no MSAA16x support).
- D3D11.1: YUV and other multi-planar formats.
- D3D11.2: Tiled resources (optional).
- D3D11.3: Conservative Rasterization (optional).
- D3D11.3: Rasterizer Ordered Views (optional).
- D3D11.4: D3D12 interop.

## Performance considerations
In order to get the best results, the following steps are recommended:
- Use an [esync](https://github.com/zfigura/wine/tree/esync)-enabled wine build, which dramatically reduces CPU overhead in some games. Lutris may offer such builds out of the box, and for Arch Linux, a PKGBUILD is available [here](https://github.com/Tk-Glitch/PKGBUILDS). Set `WINEESYNC=1` to enable esync.
- Try setting `WINEDEBUG=-all` and `DXVK_LOG_LEVEL=none` in games that generate a lot of log messages.
- Set the CPU frequency governor to `performance` or `schedutil` on AMD and older Intel CPUs.
- Disable desktop effects on your compositor, as that can lead to severe stuttering issues when games are GPU-bound.

## Development builds
Up-to-date builds can be found [here](https://git.froggi.es/doitsujin/dxvk/pipelines?scope=finished&page=1).