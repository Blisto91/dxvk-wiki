# DXVK
Provides a Vulkan-based implementation of DXGI and D3D11 in order to run 3D applications on Linux using Wine.

## Feature support
DXVK aims to provide support for D3D11, feature level 11_0.

As of 2017-12-10, DXVK is able to render the first seven [tutorials](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11Tutorials) from the Microsoft SDK correctly.

Currently supported D3D11 features include:
- Simple vertex and pixel shaders
- Vertex buffers and index buffers
- Constant buffers
- Basic 2D textures
- Non-indirect draw calls

Short- and mid-term goals are listed in the [Roadmap](https://github.com/doitsujin/dxvk/wiki/Roadmap).