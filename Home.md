# DXVK
Provides a Vulkan-based compatibility layer for DXGI and D3D11, which may be used to run 3D applications on Linux using Wine.

## Feature support
DXVK aims to provide support for D3D11, feature level 11_0.

Features that are still missing:
- Tessellation
- Stream output
- Queries

Features that are present, but still incomplete:
- Resource copies and resolve operations
- Unordered Access Views, esp. append/consume buffers
- Shader support, esp. system values
- Swap chain management, esp. fullscreen mode

Short- and mid-term goals are listed in the [Roadmap](https://github.com/doitsujin/dxvk/wiki/Roadmap).

## Screenshots
![Nier Automata](http://s1.bild.me/bilder/110417/8983866Screenshot_20180102_202827.png)

_Nier: Automata as of 2018-01-02, on an AMD A10-7350B mobile APU. The game is not yet playable._

![Cascading Shadow Map demo](http://s1.bild.me/bilder/110417/3869421Bildschirmfoto-355.png)

_Cascading shadow map demo from the Microsoft SDK, running on the open-source RADV Vulkan driver on an AMD RX 480._