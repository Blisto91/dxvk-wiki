## AMD RADV
- Development and testing mostly happens on stable revisions of Mesa / RADV.
- **Version 17.3.3** and older: Some games may fail to render certain geometry, crash, or cause GPU hangs due to a [bug](https://bugs.freedesktop.org/show_bug.cgi?id=104677) related to vertex input. **Workaround:** Use mesa-git.
- **Version 17.3.3** and newer: Games may not render shadows correctly or may not render anything at all. **Workaround:** `export RADV_DEBUG=nohiz`
- **Vega GPUs:** Freezes.

## AMD amdvlk
- Crashes in the shader compiler. **Reason:** Unknown.
- Incorrect rendering in some games. **Reason:** Unknown.

## Intel ANV
- Does not support depth bounds, which are currently listed as a required feature. Workaround possible.
- Does not support `shaderStorageImageReadWithoutFormat`, which is required for Unordered Access views.

## Nvidia
- Crashes in the shader compiler. **Reason:** Unknown.