# Hackintosh UEFI SNB Nvidia
Hackintosh based on UEFI system with Intel Sandy Bridge and a GeForce 210 graphic card. 
**Max OS version: 10.13.6**

## Specifications
- Intel i3 2100
- ASUS P8H61M LX2.0
  - Realtek 8111F
  - VIA VT1708S
- Kingston DDR3 1333Mhz 4GB
- Gainward Nvidia GeForce 210 1GB
- SSD WD Green 120GB (SATA)
- TP Link WN781ND (V2) (PCIe)
  - Based on Qualcomm Atheros AR9485
- Unknown Bluetooth dongle bought on eBay (USB)
  - Based on BCM2046
  - VID 2578 (0x0A12, Cambridge Silicon Radio Ldt.)
  - PID 1 (0x0001)
  
## Files 
This is all important files that I added to EFI.<br>
You can view all folder tree by clicking [here](https://github.com/gabrielecappellaro/hackintosh-uefi-snb-nvidia/Docs/folder-tree.txt).
  
###  Kexts
- ATH9KFixup.kext (for WiFi)
  - ATH9KInjector.kext installed in /L/E
- IOBluetoothFamily.kext (for Bluetooth)
  - Also AppleBluetoothMultitouch.kext, AppleMultitouchDriver.kext and IOBluetoothHID.kext ported from MacOS Yosemite
  - Probably can I patch High Sierra IOBluetoothFamily.kext so can I remove other
- Lilu.kext
- NightShiftUnlocker.kext
  - Enable Night Shift in unsupported SMBIOS (like iMac12,2)
- Realtek RTL8111.kext (for on-board Ethernet)
- USBInjectAll.kext
  - Motherboard hasn't USB declared in ACPI so we can't do a standard map
- VirtualSMC.kext
- VoodooHDA.kext
  - On-board audio isn't natively supported by AppleHDA (and AppleALC.kext)
- WheteverGreen.kext

### SSDTs
- SSDT-EC.aml
- SSDT-GFX0.aml
  - Made by [MacNB](https://www.insanelymac.com/forum/profile/658617-macnb/)
- SSDT-PM.aml
  - Generated by ssdtPRgen due to Intel Sandy/Ivy Bridge CPU
- SSDT-IMEI.aml
  - Get from Dortania ACPI samples

### Drivers
- HFSPlus.efi
- OpenCanopy.efi
- OpenRuntime.efi

## Useful guides
https://dortania.github.io/OpenCore-Install-Guide/
https://dortania.github.io/OpenCore-Post-Install/
https://www.insanelymac.com/forum/topic/344713-solved-opencore-injectnvidia/ (an user with my same problem opened in this days this topic)<br>
https://www.tonymacx86.com/threads/bluetooth-problems.174289/
https://www.reddit.com/r/hackintosh/comments/74rl7w/any_chance_of_getting_this_generic_bt_adapter_to (haven't tried yet)

