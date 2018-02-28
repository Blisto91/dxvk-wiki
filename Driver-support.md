## AMD RADV
- Development and testing mostly happens on stable revisions of Mesa / RADV.
- **Version 17.3.3** and older: Some games may fail to render certain geometry, crash, or cause GPU hangs due to a [bug](https://bugs.freedesktop.org/show_bug.cgi?id=104677) related to vertex input. **Workaround:** Use mesa-git.
- **Version 17.3.3** and newer: Games may not render shadows correctly or may not render anything at all. **Workaround:** `export RADV_DEBUG=nohiz`
- **Vega GPUs:** May encounter freezes due to a driver bug. **Workaround:** Use mesa-git.

## AMD amdvlk
- Sometimes crashes in the shader compiler. **Reason:** Possibly bugs in the DXBC->SPIR-V translation.
- Incorrect rendering in some games. **Reason:** Unknown.

## Intel ANV
- Does not support `shaderStorageImageReadWithoutFormat`, which is required for Unordered Access views.

## Nvidia
- Frequently crashes in the shader compiler. Try `export DXVK_SHADER_OPTIMIZE=1` until the issue is fixed.