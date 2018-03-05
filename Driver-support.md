## AMD RADV
- Development and testing mostly happens on stable revisions of Mesa / RADV.
- **Version 17.3.3** and newer: Games may not render shadows correctly or may not render anything at all. **Workaround:** `export RADV_DEBUG=nohiz`

## AMD amdvlk
- Sometimes crashes in the shader compiler. **Reason:** Possibly bugs in the DXBC->SPIR-V translation.
- Incorrect rendering in some games. **Reason:** Unknown.

## Intel ANV
- Does not support `shaderStorageImageReadWithoutFormat`, which is required for Unordered Access views.

## Nvidia
- Occational crashes in the shader compiler. **Reason:** Driver issues and bugs in the DXBC->SPIR-V translation.
- Kepler cards (GTX 600 and 700 series cards) do not expose feature level `11_0` due to missing support for `shaderStorageImageReadWithoutFormat`.