# Configuration
Some applications may require quirks in order to run or improve performance. While DXVK enables some of them by default if necessary, they can be overridden by using a configuration file. **Note that overriding the default options may cause issues!**

## Configuration file
By default, DXVK will try to load `dxvk.conf` from the current working directory, i.e. the directory where the log files will be created. This is usually the same directory where the game exe is located.

In order to change the configuration file path, set the environment variable `DXVK_CONFIG_FILE`, e.g.:
```
DXVK_CONFIG_FILE=/home/xxx/dxvk.conf
```

## Example configuration
The following configuration example documents all the options that are currently available, and leaves them to their default values. Uncomment an option by removing the `#` in order to override it.
```
# Create the VkSurface on the first call to IDXGISwapChain::Present,
# rather than when creating the swap chain. Some games that start
# rendering with a different graphics API may require this option,
# or otherwise the window may stay black.
# 
# Supported values: True, False
# 
# Enabled by default for:
# - Frostpunk

# dxgi.deferSurfaceCreation = False


# Return S_OK from IDXGIDevice::CheckInterfaceSupport when querying
# support for a Direct3D 10 COM interface. Some games require this
# in order to start up, others may break when this option is set.
# 
# Supported values: True, False
# 
# Enabled by default for:
# - World of Warcraft

# dxgi.fakeDx10Support = False


# Enforce a stricter maximum frame latency. Overrides the application
# setting specified by calling IDXGIDevice::SetMaximumFrameLatency.
# Setting this to 0 will have no effect.
# 
# Supported values : 0 - 16

# dxgi.maxFrameLatency = 0


# Handle D3D11_MAP_FLAG_DO_NOT_WAIT correctly when D3D11DeviceContext::Map()
# is called. Enabling this can potentially improve performance, but breaks
# games which do not expect Map() to return an error despite using the flag.
# 
# Supported values: True, False
#
# Enabled by default for:
# - Dishonored 2
# - Far Cry 5

# d3d11.allowMapFlagNoWait = False


# Fake Stream Output support. This reports a success code to applications
# calling CreateGeometryShaderWithStreamOutput, even if the device does
# not actually support transform feedback. Allows some games to run that
# would otherwise crash or show an error message.
#
# Supported values: True, False
#
# Enabled by default for:
# - F1 2015
# - Final Fantasy XV
# - Mafia 3
# - Overwatch

# d3d11.fakeStreamOutSupport = False
```