## AMD RADV
- **Frequent GPU hangs** can be experienced when using LLVM 6.0.0 or newer.
- **Version 17.3** and older: Not supported. Several important bugs that affect DXVK have been fixed in 18.0 and recent development branches (18.1).
- **Artifacts** in certain games (e.g. Overwatch, Kingdom Come: Deliverance). **Reason:** Unknown.
- Shader compile times may cause extremely long loading times, and games may freeze for several seconds during gameplay.

## Nvidia
- Occational crashes in the shader compiler. **Reason:** Driver issues and bugs in the DXBC->SPIR-V translation.

## Intel ANV
- Mostly untested, expect issues.

## AMD amdvlk
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.