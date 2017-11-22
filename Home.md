# DXVK
Provides a Vulkan-based implementation of DXGI and D3D11 in order to run 3D applications on Linux using Wine.

## Feature support
DXVK aims to provide support for D3D11, feature level 11_0.

Currently implemented D3D11 features:
- Device and immediate context creation

Currently implemented in the backend, but not wired up to D3D11 and DXGI yet:
- Swap chain
- Shader creation
- Buffer and image creation
- Graphics pipeline state objects
- Draw and dispatch calls

Short- and mid-term goals are listed in the [Roadmap](https://github.com/doitsujin/dxvk/wiki/Roadmap).