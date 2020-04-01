# Hackintosh-OptiPlex-7070-SFF
**Only tested on Clover EFI bootloader.**

**2020-03-27**
* Update MacOS to Catalina 10.15.4

## Introdution
This is the Hackintosh EFI Folder for Dell OptiPlex 7070 Small Form Factor. The configuration settings support MacOS Catalina 10.15.3 with resolution up to 3840 x 2160. Because deep sleep will cause a kernel panic and the screens will display all green or black, so I blocked sleep in BIOS. You will have to **generate a new serial and SmUUID** before login to your iCloud account.

## Hardware Specs
* **Desktop Computer**: [Dell OptiPlex 7070 Small Form Factor](https://www.dell.com/tc/business/p/optiplex-7070-desktop/pd) 
* **CPU**: [Intel® Core™ i7-9700](https://ark.intel.com/content/www/us/en/ark/products/191792/intel-core-i7-9700-processor-12m-cache-up-to-4-70-ghz.html)
* **iGPU**: Intel® UHD Graphics 630
* **RAM**: 64GB DDR4 2666 Daul Channel
* **HDD**: TOSHIBA RC500 NVMe SSD 500G
* **Wi-Fi & Bluetooth**: BCM943602CS with NGFF Adapter

## What Works
* CPU Turbo Boost & Thermal Throttling
* Integrated Graphics with acceleration
* Daul monitor output at 3840 x 2160
* Integrated Audio Output (front/rear)
* All USB Ports
* LAN & Wireless Network
* Airdrop & Airplay
* Partly Sleep & Wakeup

## BIOS Settings
* General → Advanced Boot Options: ***uncheck***
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ Enable: ***Disabled***
* Power Management → Block Sleep: ***check***
* Virtualization Support → VT for Direct I/O: ***uncheck***

## BIOS Settings via GRUB (Optional)
* Set Pre-Allocated DVMT to 64M: 
***setup_var 0x8DC 0x02***
* Disable CFG lock: 
***setup_var 0x5BE 0x00***
