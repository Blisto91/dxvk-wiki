## AMD RADV
- **GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252)). Most of these issues have been resolved in Mesa 18.1.3 and LLVM 7.0-svn.
- **Recommended driver version:** 18.1.3

## Nvidia
- **Recommended driver version:** 396.24.**10** (396.24.0 will not work)
- **Do not** set `__GL_NextGenCompiler=0` for regular use.

## Intel ANV
- Rarely tested. Please use `mesa-git` when testing this driver, and report any issues you run into.

## AMD amdvlk / AMDGPU-PRO
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.