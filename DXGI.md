Starting with wine 4.0 and DXVK 0.95, it is possible to use Wine's own DXGI implementation instead of the one provided by DXVK.

### Advantages
Using wine's DXGI implementation allows **vkd3d** to work for D3D12 games, while DXVK can still be used with D3D11 (e.g. World of Warcraft). This is not possible when using the implementation provided by DXVK.

### Issues
Some of the [configuration](https://github.com/doitsujin/dxvk/wiki/Configuration) options only work when using DXVK's DXGI implementation and will **not** have any effect when using Wine's implementation:
```
dxgi.customDeviceId
dxgi.customVendorId
dxgi.maxDeviceMemory
dxgi.maxSharedMemory
dxgi.nvapiHack
d3d10.enable
```

It is therefore recommended to use DXVK's DXGI implementation for the following games:
- **Most Unreal Engine 4 titles**
- Assassin's Creed Syndicate
- Elite Dangerous
- The Vanishing of Ethan Carter Redux
- Far Cry 3 (and Blood Dragon)
- Far Cry 4
- Call of Duty World War 2
- Need for Speed 2015
- Mass Effect Andromeda
