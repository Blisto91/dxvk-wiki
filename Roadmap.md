# Roadmap
In the early stages, development will focus around features required to run basic D3D11 samples. When the project is more advanced, priorities may shift to getting actual games to work.

## Immediate goals
- Implement enough D3D11 and DXGI features to run the [tutorials](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11Tutorials) from the Microsoft SDK.
  - DXVK: implement proper graphics pipeline support **(done)**
  - DXVK: implement uniform buffers and uniform texel buffers **(done)**
  - DXVK: implement textures **(in progress)**
  - DXGI: Implement DxgiSwapChain **(done)**
  - DXGI: Bump DxgiFactory to IDXGIFactory1 **(done)**
  - DXBC: Support basic vertex and pixel shaders **(in progress)**
  - D3D11: Wire up required features to DXVK **(in progress)**

## Mid-term goals
- Implement textures and shader resources **(in progress)**
- Implement pipeline states (blending, etc.) **(in progress)**
- Implement UAVs
- Implement compute shaders
- Implement query objects
- Refactor D3D11 and DXGI classes to use COM properly
- Rewrite memory allocator to sub-allocate from larger pools
- Don't synchronize immediately after command submission

## Further down the road
- Implement Geometry Shaders and Stream Output
- Implement Tessellation Shaders

## Only if needed
- Shader class linkage. Wine seems to be doing well without it.