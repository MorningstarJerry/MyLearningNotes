# Win10 Hyper-V

https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v

## Enable & Disable With powershell

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All

Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Hypervisor
```

# VitualBox 启动后 docker desktop 无法启动Hyper-V 方案

https://d3v.one/windows-10-changing-hyper-v-support-at-boot-time/

