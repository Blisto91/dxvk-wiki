## AMD RADV
- Developing and testing is mostly done on stable revisions of Mesa / RADV.
- **Version 17.3.2** and older: Some games may fail to render certain geometry, crash, or cause GPU hangs due to a [bug](https://bugs.freedesktop.org/show_bug.cgi?id=104677) related to vertex input. **Workaround:** Use mesa-git.
- **Version 17.3.99**: Games may not render shadows correctly. **Workaround:** `export RADV_DEBUG=nohiz`

## AMD amdvlk
- Crashes in the shader compiler. **Reason:** Unknown.

## Intel ANV
- Does not support depth bounds, which are currently listed as a required feature. Workaround possible.
- Does not support `shaderStorageImageReadWithoutFormat`, which is required for Unordered Access views.

## Nvidia
- Crashes in the shader compiler. **Reason:** Unknown.