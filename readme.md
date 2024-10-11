## OpenCore Configuration - B550 x RX550 x R7 5700X

## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | [AMD Ryzen™ 7 5700X 4.6GHz](https://www.amd.com/en/support/downloads/drivers.html/processors/ryzen/ryzen-5000-series/amd-ryzen-7-5700x.html) (Vermeer) |
| Motherboard | [Asus TUF Gaming B550M-Plus](https://www.asus.com/motherboards-components/motherboards/tuf-gaming/tuf-gaming-b550m-plus/) |
| RAM | [16GB Lexar DDR4 3200MHz](https://www.lexar.com/product/lexar-ddr4-3200-udimm-desktop-memory/) |
| Audio | ALC1220 |
| GPU | [Asus Phoenix RX 550 4GB](https://www.asus.com/motherboards-components/graphics-cards/phoenix/ph-rx550-4g-evo/) (Lexa) |
| Ethernet | RTL8125 2.5GbE |
| WiFi Adapter | [TP-Link WN823N V3](https://www.tp-link.com/bd/home-networking/adapter/tl-wn823n/v3/) (RTL8192E)|
| Storage (SATA) | 1x Western Digital 1TB HDD |
| Storage (NVMe) | 1x Western Digital 240GB M.2 NVMe |

## Bootloader
| **Bootloader** | **Version** |
| -------------- | ----------- |
|    OpenCore    |    1.0.2    |

## Requirements
- [OpenCore](https://github.com/acidanthera/OpenCorePkg/releases)

### Kexts
- [Lilu](https://github.com/acidanthera/Lilu/releases)
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases)
- [Kernel Patch](https://github.com/AMD-OSX/AMD_Vanilla)
- [AppleALC](https://github.com/acidanthera/AppleALC/releases)
- [VoodooHDA](https://sourceforge.net/projects/voodoohda/)
- [LucyRTL8125Ethernet](https://www.insanelymac.com/forum/files/file/1004-lucyrtl8125ethernet/)
- [USBMap] is included.

N.B Don't enable AppleALC and VoodooHDA together.

### Optional
- [SMCAMDProcessor](https://github.com/trulyspinach/SMCAMDProcessor/releases)
- [SMCRadeonSensors](https://github.com/ChefKissInc/SMCRadeonSensors/releases)
- [AppleMCEReporterDisabler](https://github.com/acidanthera/bugtracker/files/3703498/AppleMCEReporterDisabler.kext.zip)
- [NVMeFix](https://github.com/acidanthera/NVMeFix/releases)
- [SATA-Unsupported](https://github.com/khronokernel/Legacy-Kexts/blob/master/Injectors/Zip/SATA-unsupported.kext.zip)
- [RestrictEvents](https://github.com/acidanthera/RestrictEvents/releases)
- [FeatureUnlock](https://github.com/acidanthera/FeatureUnlock/releases)

### ACPI
- SSDT-EC : Disable Embedded Controller and create fake one.
- SSDT-GPU-SPOOF : Spoof Unsupported GPU.
- SSDT-PLUG-ALT : PluginType.
- SSDT-SBUS-MCHC : Fix AMD SMBus.
- SSDT-USBX : Inject missing/required USB power properties.

## Extras
- [Lilu & Friends](https://github.com/corpnewt/Lilu-and-Friends) Update kexts
- [Hackintool](https://github.com/benbaker76/Hackintool/releases)
- [USBWiFiAdapter](https://github.com/chris1111/Wireless-USB-OC-Big-Sur-Adapter/releases) requires [csr-active-config = "03080000"] in NVRAM
- [ProperTree](https://github.com/corpnewt/ProperTree/releases)
- [gibMacOS](https://github.com/corpnewt/gibMacOS) & [gibMacRecovery](https://github.com/corpnewt/gibMacRecovery) & [Unplugged](https://github.com/corpnewt/UnPlugged/blob/main/UnPlugged.command)
- [For WiFi & Bluetooth](https://dortania.github.io/OpenCore-Install-Guide/ktext.html#wifi-and-bluetooth)

### Cosmetics
- [GUI & Sound](https://dortania.github.io/OpenCore-Post-Install/cosmetic/gui.html#setting-up-opencore-s-gui)
- [Fixing MacPro7,1 Memory Errors](https://dortania.github.io/OpenCore-Post-Install/universal/memory.html)

## Things not working
- Audio on macOS Sequoia (AMD AppleALC issue) can be solved by using VoodooHDA FOR NOW!
- AirDrop (Not yet).
- WiFi (The adapter shows up as Ethernet). Need an intel LAN card.
- Bluetooth. I mean it should work but I haven't tried adding bluetooth, might do it later.
- Hypervisor.framework (VirtualBox and XCode iOS emulator works).
- Android Studio emulator (Can be replaced with Genymotion).
- Discord Krisp Noise Supression & Adobe Softwares (AMD issue). Use AMDHelper or AMDFriend.

**Thanks to everyone for supporting this project**
