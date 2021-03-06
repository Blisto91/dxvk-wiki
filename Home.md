DXVK provides a Vulkan-based translation layer for D3D9, D3D10 and D3D11, which can be used on Linux with Wine.

## D3D11 Feature support
DXVK aims to provide support for D3D11, feature level 11_1, and D3D10, feature level 10_1.

Currently unsupported features:
- D3D11: Class linkage.
- D3D11: Predication.
- D3D11.1: Target-independent rasterization (behaves incorrectly; no MSAA16x support).
- D3D11.2: Tiled resources (optional).
- D3D11.3: Rasterizer Ordered Views (optional).
- D3D11.4: D3D12 interop.

Shared Resources are partially supported, with the following restrictions:
- Proton patches are required.
- Only 2D textures are currently supported, shared fences are not.
- Only D3D9 and D3D11 are supported. Sharing resources with Vulkan or D3D12 will not work.
- `IDXGIKeyedMutex` is unsupported due to extremely poor documentation.
- This does not and will never work **at all** on Windows.

## Performance considerations
In order to get the best results, the following steps are recommended:
- Use an [esync](https://github.com/zfigura/wine/tree/esync)-enabled wine build, which dramatically reduces CPU overhead in some games. Lutris may offer such builds out of the box, and for Arch Linux, a PKGBUILD is available [here](https://github.com/Tk-Glitch/PKGBUILDS). Set `WINEESYNC=1` to enable esync.
- Try setting `WINEDEBUG=-all` and `DXVK_LOG_LEVEL=none` in games that generate a lot of log messages.
- Set the CPU frequency governor to `performance` or `schedutil` on AMD and older Intel CPUs.
- Disable desktop effects on your compositor, as that can lead to severe stuttering issues when games are GPU-bound.

## Development builds
Up-to-date builds can be found [here](https://github.com/doitsujin/dxvk/actions/workflows/artifacts.yml?query=branch%3Amaster).