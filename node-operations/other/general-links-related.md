# General Links Related To Node Operations/System Admin
1. [SYS ADMIN](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#sys-admin)
2. [NICs](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#nics)
2. [REALTEK DRIVERS](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#realtek-driver)
3. [FIREWALL](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#firewall)
    - [Open-Source Software Firewall](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#open-source-softtware-firewall)
    - [Micro-PCs With Dual-LAN](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#micro-pcs-with-dual-lan)
4. [RAID](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#raid)
    - [mdadm - Linux built-in](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#mdadm-linux-built-in)
    - [RAID Controllers](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#raid-controllers)
    - [Non-RAID Expansion](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#non-raid-expansion)
5. [CEPH](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#ceph)
    - [links](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#links)
    - [guides](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#guides)
6. [UNRAID](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#unraid)
7. [Intrustion Detection, Packet Sniffers, pen-testing, OSINT](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/other/general-links-related.md#itrusion-detection-packet-sniffer-pen-testing-osint)

### LIST OF INTERFACE SPEEDS
- [wiki](https://en.wikipedia.org/wiki/List_of_interface_bit_rates)

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

### NICs
- [list#1](https://forums.servethehome.com/index.php?threads/list-of-nics-and-their-equivalent-oem-parts.20974)
- [counterfeit](https://forums.servethehome.com/index.php?threads/comparison-intel-i350-t4-genuine-vs-fake.6917/)
- [Intel i225/226 Issues](https://www.techpowerup.com/forums/threads/quad-port-802-3bz-2-5g-5g-nic-recommendation.336544/)

#### standards ([802.3](https://en.wikipedia.org/wiki/IEEE_802.3))
- 802.3ab - 1G BASE-T over twisted-pair
- 802.3bz - 2.5/5G BASE-T over twisted-pair
- 802.3an - 10G BASE-T over UTP

#### old board available ports
- 1x pci-e 2.0 x16
- 1x pci-e x1
- 2x pci 2.2
- 6x SATA-2

#### new board available ports
- 1x pci-e 4.0 x8 (with NVME m2B, m2C filled, otherwwise x16) - CPU
- 0x pci-e 4.0 x4 (with NVME m2d, otherwise x4) - chipset
- 1x pci-e 3.0 x2 - chipset
- 4x SATA-3 - chipset

#### pci 2.2
- pin out: ` `
  - ends at
- throughput: `2.133 Gbit/s`
- [wiki article](https://en.wikipedia.org/wiki/Peripheral_Component_Interconnect)

#### pci-e x1
- pin out: `11 + 7`
  - ends at 18
- throughput: `2.5 Gbit/s`
- **one full-duplex transmit lane - lane 0** 
- [wiki article](https://en.wikipedia.org/wiki/PCI_Express#Comparison_table)

#### pci-e 1.0 x4
- pin out: `11 + 21`
  - ends at 32
- throughput: `10 Gbit/s`
- [Intel Pro - 4-port](https://www.amazon.com/Intel-1000-Quad-Adapter-EXPI9404PTL/dp/B00GS0RFUY?crid=8KE88EJ3AO15&dib=eyJ2IjoiMSJ9.mCXEUzQ5oQdkMQicUEk5SWSy3CuWr2cS77OPW6sZ1f2Ra3uh7Ug69autGaTveamEXIzOMo1joIi6lmWBUNA1bzUJatQ4Ae-KEcluHBid4DjbsZ8L_CwprrGRRXx0CgABiwi2FIqpuLULEg7kChGWN4ZiI9pIJlwjbRB_pqsE1iaPhC0Egdqtqmv20AA6dzqfoJEErFWfILCh_rv3NY8goQ0BEHY2OTcnLKHNZXwZREbppaLRfW4IHqla3hb8Zr1lz0ZP4NIAJnU3mlkBPvlSZkvHTj1mVoc7-iliyaXQKUg.piB4QBX8j23xeWRpyCsrZR68PaUU4rrTUwW1w72dSlA&dib_tag=se&keywords=%22pcie+x1%22+network+dell&qid=1746797294&s=electronics&sprefix=pcie+x1+network+dell%2Celectronics%2C81&sr=1-12)
- [Dell YGCV4 Broadcom 5719 Quad Port 1Gbe Network PCI-E Ethernet Adapter - TMGR6](https://www.amazon.com/Dell-Broadcom-Network-Ethernet-Adapter/dp/B07SZ26NKR?crid=8KE88EJ3AO15&dib=eyJ2IjoiMSJ9.mCXEUzQ5oQdkMQicUEk5SWSy3CuWr2cS77OPW6sZ1f2Ra3uh7Ug69autGaTveamEXIzOMo1joIi6lmWBUNA1bzUJatQ4Ae-KEcluHBid4DjbsZ8L_CwprrGRRXx0CgABiwi2FIqpuLULEg7kChGWN4ZiI9pIJlwjbRB_pqsE1iaPhC0Egdqtqmv20AA6dzqfoJEErFWfILCh_rv3NY8goQ0BEHY2OTcnLKHNZXwZREbppaLRfW4IHqla3hb8Zr1lz0ZP4NIAJnU3mlkBPvlSZkvHTj1mVoc7-iliyaXQKUg.piB4QBX8j23xeWRpyCsrZR68PaUU4rrTUwW1w72dSlA&dib_tag=se&keywords=%22pcie+x1%22+network+dell&qid=1746797294&s=electronics&sprefix=pcie+x1+network+dell%2Celectronics%2C81&sr=1-10#averageCustomerReviewsAnchor)
- [Intel PRO/1000 PT Quad Port Server Adapter](https://www.amazon.com/Intel-1000-Quad-Server-Adapter/dp/B000JLF4FG?crid=LP2XMYKVH71V&dib=eyJ2IjoiMSJ9.zG7ccp_K3iC46DwYqyRmv2JleLxn5ReSasg8dXkyXQavp08mASvmrFiA0Mjm7WpgBqxPWDPJrM17MRBASb1C2_qW_nJ3SG99vgYueNEUz1I.bNKIxZqM6fCoMm6wSHKE0N_wknZhX0AKjw9xvCuL-R8&dib_tag=se&keywords=EXPI9404PT&qid=1746713375&s=electronics&sprefix=expi9404pt%2Celectronics%2C297&sr=1-1#averageCustomerReviewsAnchor)

#### pci-e 2.x x4
- pin out: `11 + 21`
  - ends at 32
- throughput: `20 Gbit/s` 
- [4-port Intel - i350-t4](https://www.cdw.com/product/intel-ethernet-server-adapter-i350-t4-network-adapter-pcie-2.1-x4-gig/3522854)
- [broadcom bcm5719 - 4-port](https://www.cdw.com/product/broadcom-bcm5719-network-adapter-pcie-2.0-x4-gigabit-ethernet-x-4/7071661?pfm=srh)
- [Dell 0HM9JY Quad Port PCI-E NIC](https://www.amazon.com/Dell-0HM9JY-Quard-Port-PCI/dp/B00I8C5VCY?dib=eyJ2IjoiMSJ9.hCecwLjkBD-cpBkqeUO_2eX5ZICMiBjfwv75MNHdcQPefYECAVFDSFcZW8Z8tIzuRm0ocajGNIMIQk-MwzQO2R80lK9X6aBykrYrEfB2st4.mJBO4-bzPJpboLDL5KKHipYnvuq4847m-AURM1hZS9I&dib_tag=se&keywords=%22pcie+2.0%22+%224x+rj45%22&qid=1746803197&s=pc&sr=1-4)

#### pci-e 2.0 x16
- pin out: `11 + 71`
  - ends at 82
- throughput: `80 Gbit/s`

#### pci-e 4.0 x8
- pin out: `11 + 38`
  - ends at 49
- throughput: `80 Gbit/s` - ??



---

### FIREWALL
```
The idea with these is to create a PFSense/HW-Firewall/Traffic-Monitoring appliance that all service devices (servers, nodes, web-hosting, etc.) must pass through
```
#### OPEN-SOURCE SOFTTWARE FIREWALL
- [OPNsense v. PfSense: Which one? via `XDA-Developers`](https://www.xda-developers.com/should-you-use-opnsense-or-pfsense-in-your-home-lab/)
- [pfsense Repo](https://github.com/pfsense/pfsense)
  - [Download - reqs account registration](https://www.pfsense.org/download/)
- Installation Links & Tutorials
    - [`pfsense` - Budget 10gbe Install](https://drakeor.com/2021/04/14/setting-up-pfsense-as-a-router/)
- []

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


#### DRIVES
- nvme - PNY, Samsung
- ssd - Samsung
- hdd - seagate exos x18+ & iron wolf pro

---

### CEPH
#### LINKS
- [ceph OSD creation using a partition](https://forum.proxmox.com/threads/ceph-osd-creation-using-a-partition.58170/)
- [8. Deploy Hyper-Converged Ceph Cluster - `ProxMox`](https://pve.proxmox.com/pve-docs/pve-admin-guide.html#chapter_pveceph)
- [Ceph - Hardware Recommendations](https://docs.ceph.com/docs/nautilus/start/hardware-recommendations/)

#### GUIDES
- [Distributed file storage with a Ceph cluster on Raspberry Pi](https://www.hackster.io/shahizat/distributed-file-storage-with-a-ceph-cluster-on-raspberry-pi-f8158e)
- [Tutorial: Using Ceph Distributed Storage Cluster on Bare Metal Cloud Services](https://blogs.oracle.com/cloud-infrastructure/post/tutorial-using-ceph-distributed-storage-cluster-on-bare-metal-cloud-services)
- [Distributed Storage with CEPH](https://blog.miguens.one/posts/2021/06/distributed-storage-with-ceph/)

---

### UNRAID
- [FAQ](https://forums.unraid.net/topic/46802-faq-for-unraid-v6/#findComment-511923)

---

### ITRUSION DETECTION, PACKET SNIFFER, PEN-TESTING, OSINT
- [Snort - `owned by Cisco`](https://www.snort.org/downloads/#rule-downloads) • [Documentation](https://www.snort.org/documents)
- [Wireshark - `by Wireshark Foundation`](https://www.wireshark.org/download.html)
- [2025's Top OSINT Tools](https://hackread.com/2025-top-osint-tools-take-on-open-source-intel/)
