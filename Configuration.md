Some applications may require quirks in order to run or improve performance. While DXVK enables some of them by default if necessary, they can be overridden by using a configuration file.

**Note that overriding the default options is usually not necessary and may cause issues!**

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


# Enforce a stricter maximum frame latency. Overrides the application
# setting specified by calling IDXGIDevice::SetMaximumFrameLatency.
# Setting this to 0 will have no effect.
# 
# Supported values : 0 - 16

# dxgi.maxFrameLatency = 0


# Override PCI vendor and device IDs reported to the application. Can
# cause the app to adjust behaviour depending on the selected values.
#
# Supported values: Any four-digit hex number.

# dxgi.customDeviceId = 0000
# dxgi.customVendorId = 0000


# Override maximum amount of device memory and shared system memory
# reported to the application. This may fix texture streaming issues
# in games that do not support cards with large amounts of VRAM.
#
# Supported values: Any number in Megabytes.
#
# Enabled by default for:
# - Life is Feudal MMO: 4095

# dxgi.maxDeviceMemory = 0
# dxgi.maxSharedMemory = 0


# Override back buffer count for the Vulkan swap chain.
# Setting this to 0 or less will have no effect.
#
# Supported values: Any number greater than or equal to 2.

# dxgi.numBackBuffers = 0


# Overrides synchronization interval (Vsync) for presentation.
# Setting this to 0 disables vertical synchronization entirely.
# A positive value 'n' will enable Vsync and repeat the same
# image n times, and a negative value will have no effect.
#
# Supported values: Any non-negative number

# dxgi.syncInterval = -1


# Overrides present mode for vertical synchronization
# 
# Supported values are:
# - 0: FIFO (default)
# - 1: MAILBOX (allows higher frame rates than refresh rate)

# dxgi.syncMode = 0


# Enables or dsables d3d10 support.
# 
# Supported values: True, False

# d3d10.enable = True


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


# Override the maximum feature level that a D3D11 device can be created
# with. Setting this to a higher value may allow some applications to run
# that would otherwise fail to create a D3D11 device.
#
# Supported values: 9_1, 9_2, 9_3, 10_0, 10_1, 11_0, 11_1

# d3d11.maxFeatureLevel = 11_1


# Overrides the maximum allowed tessellation factor. This can be used to
# improve performance in titles which overuse tessellation.
# 
# Supported values: Any number between 8 and 64

# d3d11.maxTessFactor = 0


# Overrides anisotropic filtering for all samplers. Set this to a positive
# value to enable AF for all samplers in the game, or to 0 in order to
# disable AF entirely. Negative values will have no effect.
# 
# Supported values: Any number between 0 and 16

# d3d11.samplerAnisotropy = -1


# Allow allocating more device memory from a Vulkan heap than the heap
# provides. May in some cases improve performance in low-memory conditions.
#
# Supported values: True, False

# dxvk.allowMemoryOvercommit = False


# Sets number of pipeline compiler threads.
# 
# Supported values:
# - 0 to automatically determine the number of threads to use
# - any positive number to enforce the thread count

# dxvk.numCompilerThreads = 0



# Toggles raw SSBO usage
# 
# Uses storage buffers to implement raw and structured buffer
# views. Enabled by default on hardware which has a storage
# buffer offset alignment requirement of 4 Bytes (e.g. AMD).
# 
# Supported values:
# - Auto: Don't change the default
# - True, False: Always enable / disable

# dxvk.useRawSsbo = Auto



# Toggles early discard
# 
# Uses subgroup operations to determine whether it is safe to
# discard fragments before the end of a fragment shader. This
# is enabled by default on all drivers except RADV and Nvidia.
# 
# Supported values:
# - Auto: Don't change the default
# - True, False: Always enable / disable

# dxvk.useEarlyDiscard = Auto
```