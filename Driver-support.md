## AMD RADV
- **Frequent GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252))
- **Version 17.3** and older: Not supported. Several important bugs that affect DXVK have been fixed in 18.0 and recent development branches (18.1).

## Nvidia
- **387.xx** and older: Not supported, please use a newer driver.
- **390.xx**: Occational crashes in the shader compiler caused by driver issues and bugs in the DXBC->SPIR-V translation.
- **396.18**: Poor performance and visual issues in some games (see [Issue #267](https://github.com/doitsujin/dxvk/issues/267)).

## Intel ANV
- Mostly untested, expect issues.

## AMD amdvlk
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.