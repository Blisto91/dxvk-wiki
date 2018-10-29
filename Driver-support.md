## AMD RADV ([#252](https://github.com/doitsujin/dxvk/issues/252))
- **Recommended driver version:** 18.2.3 or newer.
- For Stream Output support, use Mesa 18.3-git.
- **Note:** LLVM 6 can cause additional issues, such as GPU hangs or rendering bugs, which do not occur with newer LLVM versions. Please use LLVM 7.0 or 8.0-svn if possible.

## Nvidia ([#267](https://github.com/doitsujin/dxvk/issues/267))
- **Recommended driver version:** 396.54
- For Stream Output support and best performance, use 396.54.**09**

## Intel ANV
- **Recommended driver version:** 18.2 or newer.

## AMDVLK ([#578](https://github.com/doitsujin/dxvk/issues/578))
- Make sure to run the latest version available. When reporting issues, please also test whether the same issue can be experienced on RADV.

## AMDGPU PRO
- The Vulkan driver version shipping with the 18.40 driver package is outdated and will not work with DXVK.

## Windows drivers
- Unsupported. Any issues that are exclusive to Windows will be ignored.