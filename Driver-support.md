## AMD RADV
- **Frequent GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252))
- **Version 17.3** and older: Not supported. Several important bugs that affect DXVK have been fixed in 18.0 and recent development branches (18.1).

## Nvidia
- Occational crashes in the shader compiler. **Reason:** Driver issues and bugs in the DXBC->SPIR-V translation.

## Intel ANV
- Mostly untested, expect issues.

## AMD amdvlk
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.