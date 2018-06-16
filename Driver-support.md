## AMD RADV
- **GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252)). Most of these issues have been resolved in Mesa 18.1.2.
- **Version 18.0** and older: Not supported. Several important bugs that affect DXVK have been fixed in 18.1 and later.

## Nvidia
- **396.24.0** and older: Not supported, please use at least 396.24.**02**.
- **Do not** set `__GL_NextGenCompiler=0` for regular use.
- Some games may freeze at high frame rates. **Workaround:** Disable *Allow Flipping* in the Nvidia driver settings.

## Intel ANV
- Mostly untested, expect issues.

## AMD amdvlk / AMDGPU-PRO
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.