## AMD RADV ([#252](https://github.com/doitsujin/dxvk/issues/252))
- **Recommended driver version:** 18.3 or newer
- **Note:** LLVM 6.0 can cause additional issues, such as GPU hangs or rendering bugs, which do not occur with newer LLVM versions. Please use LLVM 7.0.0 or 8.0 if possible.
- **Note:** LLVM 7.0.1 reportedly causes GPU hangs in various games that work fine with 7.0.0 or 8.0.

## Nvidia ([#267](https://github.com/doitsujin/dxvk/issues/267))
- **Recommended driver version:** 415.22 or later

## Intel ANV
- **Recommended driver version:** 19.0 or newer

## AMDVLK ([#578](https://github.com/doitsujin/dxvk/issues/578))
- Make sure to run the latest version available. When reporting issues, please also test whether the same issue can be experienced on RADV.

## AMDGPU PRO
- **Recommended driver verson:** 18.50 or newer
- The Vulkan driver version shipping with the 18.40 driver package is outdated and will not work with DXVK.

## Windows drivers
- Unsupported. Any issues that are exclusive to Windows will be ignored.