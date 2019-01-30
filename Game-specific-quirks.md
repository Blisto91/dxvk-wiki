### Frostbite Engine games

Frostbite Engine has issues when Nvidia GPUs are reported as AMD GPUs, as is the default for DXVK due to common performance issues related to nvapi in other engines. This can be solved by disabling the nvapi workaround:
```
# Actually report Nvidia GPUs as Nvidia
dxgi.nvapiHack = False
```
