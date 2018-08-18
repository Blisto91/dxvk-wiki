## AMD RADV
- **GPU hangs** can be experienced in some games (see [Issue #252](https://github.com/doitsujin/dxvk/issues/252)). Most of these issues have been resolved in Mesa 18.1.3 and LLVM 7.0-svn.
- **Recommended driver version:** 18.1.3 or newer
- **Note:** LLVM 6 can cause additional issues, such as GPU hangs or rendering bugs, which do not occur with newer LLVM versions. Please use LLVM 7.0-svn if possible.

## Nvidia
- **Recommended driver version:** 396.51 or newer
- **Do not** set `__GL_NextGenCompiler=0` for regular use.

## Intel ANV
- Rarely tested. Please use `mesa-git` when testing this driver, and report any issues you run into.

## AMDVLK
- Rarely tested, but the most recent versions may work for certain games. Before reporting issues with this driver, please confirm that the same issue also exists on the RADV driver.