## AMD RADV
- **GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252))
- **Version 18.0** and older: Not supported. Several important bugs that affect DXVK have been fixed in 18.1 and later.

## Nvidia
- **390.xx** and older: Not supported, please use at least 396.18.07.
- **Do not** set `__GL_NextGenCompiler=0`.

## Intel ANV
- Mostly untested, expect issues.

## AMD amdvlk
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.