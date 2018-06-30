## AMD RADV
- **GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252)). Most of these issues have been resolved in Mesa 18.1.2.
- **Minimum driver version:** 18.1.2

## Nvidia
- **Minimum driver version:** 396.24.**02**.
- **Do not** set `__GL_NextGenCompiler=0` for regular use.
- Some games may freeze at high frame rates. **Workaround:** Disable *Allow Flipping* in the Nvidia driver settings.

## Intel ANV
- Rarely tested, please report any issues you run into with this driver.

## AMD amdvlk / AMDGPU-PRO
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.