# Hackintosh 13600k-Asus-B660M-Wifi-Plus

![Thumbnail](Docs/Thumbnail.png)

# Current macOS

Current Version: macOS Ventura 13.3

# Hardware
- CPU: i5-13600k
- Board: Asus B660M Wifi Plus
- RAM: 32 GB (2x16GB) Kingston DDR5 6000Mhz CL32
- GPU: MSI Gaming Trio X 6900 XTX
- PSU: Corsair SF750
- Case: Asus AP201 (Micro-ATX)
- Wifi/BT: BCM94360NG (replaces the preinstalled m.2 Intel AX201)

# Working
- CPU Power Management
- USB Ports
- Sleep/Wake
- Wifi/BT

# Not working
- iGPU UHD770 is not supported by macOS

  # Wifi in macOS Sonoma

With macOS Sonoma, the Broadcom based Wifi cards don't work plug and play anymore. It is a very annoying process now, that you have to repeat after every macOS Update!

General Requirements for Broadcom Wifi in Sonoma: 
- Additional Kexts: ```IO80211FamilyLegacy.kext```, ```IOSkywalkFamily.kext```, ```AMFIPass.kext```. Also these Kexts in a very high priority after Lilu and VirtualSMC.
- Blocking Kexts: ```com.apple.iokit.IOSkywalkFamily```
- Bootarg: ```-amfipassbeta```

To be repeated for every macOS Update: 

1. Disable SecureBoot via config.plist: ```SecureBootModel = Disabled``` and ```DmgLoading = Any```
2. ```Disable SecureBoot``` in BIOS
3. Install the macOS Update
4. Run the OCLP Patcher and start the "Post-install Root Patch".
5. Enable SecureBoot via config.plist: ```SecureBootModel = ```(your SecureBootModel according to here: https://dortania.github.io/OpenCore-Post-Install/universal/security/applesecureboot.html#securebootmodel) and ```DmgLoading = Any```
6. Enable SecureBoot in BIOS again

## Getting the OpenCore Legacy Patcher

Install the newest release from here: https://github.com/dortania/OpenCore-Legacy-Patcher/releases

# USB Port Mapping

![USB Port Mapping](Docs/USB-Mapping.png)
