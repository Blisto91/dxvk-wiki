# Roadmap
In the early stages, development will focus around features required to run basic D3D11 samples. When the project is more advanced, priorities may shift to getting actual games to work.

## Immediate goals
- Implement enough D3D11 and DXGI features to run the [tutorial samples](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11Tutorials) from the Microsoft SDK.
  - DXVK: implement proper graphics pipeline support
  - DXVK: implement uniform buffers and uniform texel buffers
  - DXVK: implement textures
  - DXGI: Implement DxgiSwapChain
  - DXGI: Bump DxgiFactory to IDXGIFactory1
  - D3D11: Wire up required features to DXVK

## Mid-term goals
- Implement textures and shader resources
- Implement pipeline states (blending, etc.) 
- Implement UAVs
- Implement compute shaders
- Implement query objects
- Rewrite memory allocator to sub-allocate from larger pools
- Don't synchronize immediately after command submission

## Further down the road
- Implement Geometry Shaders and Stream Output
- Implement Tessellation Shaders

## Only if needed
- Shader class linkage. Wine seems to be doing well without it.