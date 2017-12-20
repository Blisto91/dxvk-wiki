# DXVK
Provides a Vulkan-based implementation of DXGI and D3D11 in order to run 3D applications on Linux using Wine.

## Feature support
DXVK aims to provide support for D3D11, feature level 11_0.

As of 2017-12-18, DXVK is able to render all fourteen Direct3D Tutorials and a few other samples from the [Microsoft SDK](https://github.com/walbourn/directx-sdk-samples/tree/master/) correctly:

Currently supported D3D11 features include:
- Simple vertex, pixel and geometry shaders
- Vertex buffers and index buffers
- Constant buffers
- 2D color and depth textures
- Non-indirect draw calls
- State objects (blending etc.)

Short- and mid-term goals are listed in the [Roadmap](https://github.com/doitsujin/dxvk/wiki/Roadmap).

## Screenshots
![Cascading Shadow Map demo](http://s1.bild.me/bilder/110417/3869421Bildschirmfoto-355.png)

_Cascading shadow map demo from the Microsoft SDK, running on the open-source RADV Vulkan driver on an AMD RX 480._