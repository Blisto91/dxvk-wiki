The general recommendation to avoid issues is to **keep your drivers up to date** as much as possible, regardless or vendor, in order to reduce the risk of running into driver bugs.

## AMD drivers
**RADV**: Preferred and our primary development target, generally provides the best compatibility and performance. Version **21.2** or later recommended.

**AMDVLK**: We do not regularly test this driver. Compatbility is good, but performance may be low in some games and shader compile stutter is extreme.

**AMD Proprietary**: We do not regularly test this driver. Compatibility is mediocre, but in some games this driver *may* provide the best performance on certain GPU architectures.

## Nvidia drivers
Driver version **495.46** or later recommended. Compatibility is very good, but performance is unlikely to be competitive with Windows D3D11 drivers.

GPUs that no longer enjoy active driver support and are limited to 470 drivers *may* work, but we cannot provide support for issues specific to these drivers.

## Intel drivers
**ANV**: Generally capable of running DXVK, but may have issues. Always keep up to date.

**Windows**: Don't even try.

## Windows
While using DXVK on Windows may work, we do not and cannot offically support it. Many games will work just fine on a bare-bones Windows setup, there are many reasons for this not to work that are outside our control, including but not limited to:
- Third-party software interfering, especially any sort of overlay that may be integrated into game launchers
- Third-party Vulkan layers interfering even when the corresponding software is not running, sometimes seen with the RTSS performance overlay
- Tight integration of vendor-specific libraries such as NVAPI, AMDAGS, Ansel etc., which will fail to initialize with DXVK and not all games handle this gracefully
- Anti-cheat systems, or weird DLL loading mechanisms where the game loads some libraries from System32 and some from the install directory
- Broken or incomplete driver installs on laptops and other pre-built systems
- Slight inaccuracies in our DXGI implementation that are extremely hard to figure out and fix due to the lack of documentation