# Roadmap

## Immediate goals
Implement enough functionality to run _Tomb Raider (2013)_ and _Nier: Automata_:
- Fix handling of unbound D3D11 resources **(in progress)**
- Implement query objects **(started)**
- Rewrite DXGI parts that use SDL using pure win32 APIs **(done)**

## Mid-term goals
- Refactor D3D11 and DXGI classes to use COM properly

## Further down the road
- Implement Geometry Shaders **(started)**
- Implement Stream Output
- Implement Tessellation Shaders

## Only if needed
- Shader class linkage. Wine seems to be doing well without it.

## Completed
- Implement enough D3D11 and DXGI features to run the [tutorials](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11Tutorials) from the Microsoft SDK. **(done 12-2017)**
- Implement enough functionality to run more advanced [tutorials](https://github.com/walbourn/directx-sdk-samples/tree/master/Direct3D11TutorialsFX11) from the Microsoft SDK. **(done 12-2017)**
