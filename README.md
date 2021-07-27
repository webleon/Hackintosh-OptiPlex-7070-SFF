# Hackintosh-OptiPlex-7070-SFF
**Opencore Bootloader 0.7.1. Tested on Big Sur 11.5.1**

<img src=https://raw.githubusercontent.com/webleon/Hackintosh-OptiPlex-7070-SFF/master/images/about0727.png width=640px />

![](https://raw.githubusercontent.com/webleon/Hackintosh-OptiPlex-7070-SFF/master/images/about0727.png)

## Introdution
This is the Hackintosh EFI Folder for Dell OptiPlex 7070 Small Form Factor. The configuration settings support MacOS Catalina and Big Sur. 
Because deep sleep will cause a kernel panic, I blocked sleep in BIOS. 

I'm using a iMac 19,1 SMBIOS to improve performance with dedicate GPU. If you only using the intergrated iGPU, set SMBIOS to Macmini 8,1 will avoid most of the issues with video. 

You will have to [**generate a new SMIBIOS**](https://github.com/corpnewt/GenSMBIOS) before login to your iCloud account.


## Hardware Specs
* **Desktop Computer**: [Dell OptiPlex 7070 Small Form Factor](https://www.dell.com/tc/business/p/optiplex-7070-desktop/pd) 
* **CPU**: ~~[Intel® Core™ i7-9700](https://ark.intel.com/content/www/us/en/ark/products/191792/intel-core-i7-9700-processor-12m-cache-up-to-4-70-ghz.html)~~ [Intel® Core™ i7-9900](https://ark.intel.com/content/www/us/en/ark/products/191789/intel-core-i9-9900-processor-16m-cache-up-to-5-00-ghz.html)
* **iGPU**: Intel® UHD Graphics 630
* **GPU**: Radeon™ RX 560 (low profile)
* **RAM**: 64GB DDR4 2666 Daul Channel
* **HDD**: TOSHIBA RC500 NVMe SSD 500G
* **LAN**: Realtek RTL8125B / Intel I219LM7
* **Wi-Fi & Bluetooth**: BCM943602CS with NGFF Adapter


## Working
* CPU Turbo Boost & Thermal Throttling
* Radeon™ RX 560 & iGPU acceleration
* ALC 255 audio
* All USB Ports
* LAN & Wireless Network
* Airdrop & Airplay
* Sleep & Wakeup


## Not working
* 


## BIOS Settings
* General → Advanced Boot Options: ***uncheck***
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ Enable: ***Disabled***
* ~~Power Management → Block Sleep: ***check***~~
* Virtualization Support → VT for Direct I/O: ***uncheck***


## BIOS Settings via GRUB (Optional)
* Set Pre-Allocated DVMT to 64M: 
***setup_var 0x8DC 0x02***
* Disable CFG lock: 
***setup_var 0x5BE 0x00***


## Changelog

**2021-07-27**
* Updated bootloader to Opencore 0.7.1
* Updated the KEXTs to the latest version
* Fixed Sleep/Wakeup issue. Now it's no need to block sleep in the BIOS

**2021-05-16**
* Fixed UHD 630 Acceleration 

**2021-05-08**
* Fixed USB on Big Sur 11.3.1 by mapping USB Ports 

**2021-04-24**
* Updated bootloader to Opencore 0.6.8
* Added lucyRTL8125Ethernet.kext

**2020-11-15**
* Changed bootloader to Opencore 0.6.3
* Installed a dedicate GPU RX560, changed SMBIOS to iMac 19,1
* ALC255 Audio didn't work with default OC configuration caused by IRQ conflicts. These has been patched with [SSDTTime](https://github.com/corpnewt/SSDTTime) 

**2020-03-27**
* Updated MacOS to Catalina 10.15.4
