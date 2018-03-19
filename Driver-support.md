## AMD RADV
- **Frequent GPU hangs** can be experienced when using LLVM 6.0.0 or newer.
- **Version 17.3** and older: Not supported. Several important bugs that affect DXVK have been fixed in more recent development branches (18.0 and 18.1).
- **Vega GPUs:** Not supported, and any issues with Vega GPUs will be ignored. Use wined3d instead.

## Nvidia
- Occational crashes in the shader compiler. **Reason:** Driver issues and bugs in the DXBC->SPIR-V translation.
- Kepler cards (GTX 600 and 700 series) do not expose feature level `11_0` due to missing support for `shaderStorageImageReadWithoutFormat`.

## Intel ANV
- Does not support `shaderStorageImageReadWithoutFormat`, which is required for Unordered Access views.

## AMD amdvlk
- Not supported, and any issues with this driver will be ignored. Use RADV on AMD cards instead.