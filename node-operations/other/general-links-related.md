# General Links Related To Node Operations/System Admin
[SYS ADMIN](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#sys-admin)

[REALTEK DRIVERS](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#realtek-driver)

[HARDWARE FIREWALL & NETWORK MONITORING](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#hardware-firewall--network-monitoring)
- [Open-Source Software Firewall](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#open-source-softtware-firewall)
- [Micro-PCs With Dual-LAN](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#micro-pcs-with-dual-lan)

[RAID](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#raid)
- [mdadm - Linux built-in](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#mdadm-linux-built-in)
- [RAID Controllers](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#raid-controllers)
- [Non-RAID Expansion](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#non-raid-expansion)

### SYS ADMIN
- [**AMD DASH**](https://deviceon.gitbook.io/docs/out-of-band/amd-dash) - administration tool

### REALTEK DRIVER
- for Realtek RTL8125 2.5GbE
  ```
  As of 25 April 2025 it is recommended to not use Realtek drivers for the hardwired (non-wireless) on Linux nodes having this hardware 
  ```
- realtek driver website
    ```
    https://www.realtek.com/Download/Index?cate_id=194&menu_id=297
    ```
- linux github repo for realtek wireless driver (good)    
    ```
    https://github.com/torvalds/linux/blob/master/drivers/net/wireless/realtek/rtw89/rtw8922ae.c
    ```

---

### HARDWARE FIREWALL & NETWORK MONITORING
```
The idea with these is to create a PFSense/HW-Firewall/Traffic-Monitoring appliance that all service devices (servers, nodes, web-hosting, etc.) must pass through
```
#### OPEN-SOURCE SOFTTWARE FIREWALL
- [Pfsense](https://www.pfsense.org/)

#### MICRO PCs WITH DUAL LAN
- [ASRock - #1 -- website](https://www.asrockind.com/en-gb/4X4%20BOX-7640U)
- [ASRock - #2 - PDF](https://download.asrock.com/IPC/Download/e-catalog/4X4%20BOX-7640U.pdf)


--- 

### RAID

#### mdadm (Linux built-in)
- [Native RAID on Ubuntu Linux](https://www.digitalocean.com/community/tutorials/how-to-create-raid-arrays-with-mdadm-on-ubuntu)
- [Manage RAID arrays on Ubuntu Linux](https://www.digitalocean.com/community/tutorials/how-to-manage-raid-arrays-with-mdadm-on-ubuntu-22-04)
- [Cache'ing Linux RAID](https://www.kernel.org/doc/Documentation/md/raid5-cache.txt)

#### RAID CONTROLLERS
- [ASUS Hyper M.2 x16 Gen5 Card - PCIe5.0/4.0 - 4x NVME - 290mm length](https://www.amazon.com/ASUS-M-2-Supports-Platform-Functions/dp/B0CKH9FWRQ?crid=2G1W2V933FEIO&dib=eyJ2IjoiMSJ9.qNQARfaFbc0SaeyR1CDzXedrOJCOUDVGZ3F0aJpXrDvZ9GnWunyFea9NNxPTZtKgDqHmiHZG6Ye0YirNjZ6Wd67CgyfoHLCqbn8Y7QgTpkWgN3tlpctyyG49bW-hiMsdjRHeBy7Foq3RQjM5kXbs1_1OY0o2YMb_6MJeH1gj2OqcxKPAsOBTIMNPfyw5EZjZXal20C3gX2mm3eGWcE0DMcFmu7YQiB1_mfbEn-ay8aM.J_HndkmCyNAYjIuoeXBPNLKGoYQZ7EzkxJYRXSyX7Mc&dib_tag=se&keywords=pci-e+5.0+RAID+controller&qid=1744919998&sprefix=pci-e+5.0+raid+controller%2Caps%2C126&sr=8-3&ufe=app_do%3Aamzn1.fos.9fe8cbfa-bf43-43d1-a707-3f4e65a4b666)
  - [mfg website](https://www.asus.com/motherboards-components/motherboards/accessories/hyper-m-2-x16-gen5-card/techspec/)
- [16 SAS RAID Controller - PCIe](https://www.amazon.com/SVNXINGTII-SAS9305-16i-SATA-9305-16i-8643/dp/B0CMX9QPZK?crid=2G1W2V933FEIO&dib=eyJ2IjoiMSJ9.qNQARfaFbc0SaeyR1CDzXedrOJCOUDVGZ3F0aJpXrDvZ9GnWunyFea9NNxPTZtKgDqHmiHZG6Ye0YirNjZ6Wd67CgyfoHLCqbn8Y7QgTpkWgN3tlpctyyG49bW-hiMsdjRHeBy7Foq3RQjM5kXbs1_1OY0o2YMb_6MJeH1gj2OqcxKPAsOBTIMNPfyw5EZjZXal20C3gX2mm3eGWcE0DMcFmu7YQiB1_mfbEn-ay8aM.J_HndkmCyNAYjIuoeXBPNLKGoYQZ7EzkxJYRXSyX7Mc&dib_tag=se&keywords=pci-e%2B5.0%2BRAID%2Bcontroller&qid=1744919998&sprefix=pci-e%2B5.0%2Braid%2Bcontroller%2Caps%2C126&sr=8-5&th=1) 

#### NON-RAID EXPANSION
- [M2 slot SATA expansion controller - PCIe 3.0](https://www.amazon.com/SilverStone-Technology-ECS07-Expansion-SST-ECS07/dp/B0B8TV1QRG?crid=1ZZKVH5MM31Q0&dib=eyJ2IjoiMSJ9.O2X4ymdodbBMJGiHD4Psuocthj1rLj4ZUZH3fTlaL9dvyugduZ2zhceWN9zUEQBD4eanIQEWkZZb-AjLvaFyckB4acwxlotzo-n0bDV42ReBZXdmSb2mX1_NIj07HP_Tk2EnDLyR9CkicGl46yIQLunMhd76m_-bifvwz3TLE0I7QSYMCGkV80PhO17s8nuEOt2gLhxVgc9lK-2CMzIFAkoly4aIN5YdP41o3FYDgro.YNdgCApM2nS6_wEs8R4has1r-uXnDAZq-NNbTE51e34&dib_tag=se&keywords=%22raid+6%22+SAS+SATA+NVME+controller+%22gen+5%22&qid=1744920779&sprefix=raid+6+sas+sata+nvme+controller+gen+5+%2Caps%2C543&sr=8-6&ufe=app_do%3Aamzn1.fos.9fe8cbfa-bf43-43d1-a707-3f4e65a4b666)
- 

