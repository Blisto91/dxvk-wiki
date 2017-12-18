# Roadmap
In the early stages, development will focus around features required to run basic D3D11 samples. When the project is more advanced, priorities may shift to getting actual games to work.

## Immediate goals
Implement enough functionality to run more advanced [tutorials](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11TutorialsFX11) from the Microsoft SDK.
- Implement textures and shader resources **(in progress)**
- Implement pipeline states (blending, etc.) **(done)**

## Mid-term goals
- Implement UAVs
- Implement compute shaders
- Implement query objects
- Optimize D3D11 resource mapping to avoid synchronization **(in progress)**
- Refactor D3D11 and DXGI classes to use COM properly
- Rewrite DXGI parts that use SDL using pure win32 APIs

## Further down the road
- Implement Geometry Shaders **(started)**
- Implement Stream Output
- Implement Tessellation Shaders

## Only if needed
- Shader class linkage. Wine seems to be doing well without it.

## Completed
- Implement enough D3D11 and DXGI features to run the [tutorials](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11Tutorials) from the Microsoft SDK. **(done 12-2017)**
