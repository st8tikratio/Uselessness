# ALL DANDO BUILD NOTES
##### Starting 04 April 2025
###### Includes hardware specific notes
- The below are a compilation of notes that were taken while installing the preprod <br> and mainnet dandeklion nodes. Some are basic, some not so much. If there was <br> and issue it was noted. In the future I will play around with the formatting so that <br> it is more user friendly. Tables will be inserted where it makes sense.
- These notes are as much for me as they are for YOU.
---

## LINUX ISOs
- server [current LTS]
  ```
  https://ubuntu.com/download/server/thank-you?version=24.04.2&architecture=amd64&lts=true
  ```
- desktop [current LTS]
  ```
  https://ubuntu.com/download/desktop/thank-you?version=24.04.2&architecture=amd64&lts=true
  ```

---

## M2TEC MODS
### in progress
- Cardano GraphQL without metadata
  ```
  https://github.com/M2tec/cardano-graphql/tree/feat/no_Meta)
  ```
  - Discord discussion
    ```
    https://discord.com/channels/912354788795109396/1359910909459566814)
    ```

### completed
- typically rolled into the most up-to-date dandelion node container and instructions

---

## DANDELION

### general dandelion syncing specs
- **Uptime: 2 days, 0:41:56**
  ```  
  27.4% swap space; of 40G swap space
  45.3% of memory: of 128G
  25.3% CPU; 16-Core
  682G of drive space; of 1 TB
  22.8ms max CPU_IOWAIT by postgres, postgres, postgres
  ```
### swap file resizing
- change swap file size from 8G to 40G
  - use `docker compose down` if applicable
    ```
    swapon --show
    sudo swapoff -v /swap.img 
    sudo rm -rf /swap.img
    sudo fallocate -l 40G /swap.img 
    sudo chmod 0600 /swap.img 
    sudo mkswap /swap.img 
    sudo swapon 
    sudo reboot now
    ```
### common errors when syncing Cardano
- CPU_IOWAIT
  ```
  2025-04-08 09:01:10 (0:00:12) - CRITICAL on CPU_IOWAIT (Min:3.3 Mean:4.9 Max:7.4): cardano-node, java, conmon
  ```

---

## REQUIRED LINUX INSTALLS

### install git
- install git
  ```
  sudo apt install git
  ```

### inline file editor
- for `nano`
  ```
  which nano
  ```
  **IF NOT OUTPUT**
  ```
  sudo apt install nano
  ```
- to edit file inline
  ```
  nano [filneame]
  ```
  **example**
  ```
  nano .env
  ```
- save changes to file and exit
  ```
  CTRL + S
  CTRL + X
  ```
- exit **without** saving
  ```
  CTRL + X
  n(o)
  ```
- `VIM` is another inline editor; just replace `vim` for `nano`

## SUGGESTED LINUX INSTALLS


## TIPS, TRICKS, USEFUL CMDs

### autocomplete using TAB
- start typing path or directory and hit `TAB` to autcomplete
  - if not autocomplete, hit `TAB` twice for list of 'paths'
  - example
    ```
    ./scripts/dand   -> TAB key  —> ENTER
    ```

### general linux commands
- get help for any command
  ```
  [your command] -h
  ```
  **OR**
  ```
  [your command] --help
  ```
- check to see if an application or package is install
  ```
  which [app or package name]
  ```
- check version of application or package
  ```
  [app or package name] -v
  ```
  **OR**
  ```
  [app or package name] --version
  ```
- to pause (and resume) large outputs
  - pausing
    ```
    CTRL + S
    ```
  - resume
    ```
    CTRL + Q
    ```
- update or upgrade system and applications
  ```
  sudo apt update
  ```
  **then**
  ```
  sudo apt upgrade
  ```



### networking
- check if any `connection` is active
  - ```
    ip -br a
    ```
- check `network map`
  - ```
    namp [your IP addess from (ip -br a)]/24
    ```   

### filesysten information
- to see drive info including usage
  - ```
    df -h
    ```

### adding another drive to node build
- open fstab
  - ```
    sudo nano /etc/fstab
    ```
- copy primary drive information on newline and replace info with new drive info
	- last two digits on line should be 0 and 2
	- find UUID in `Drive Manager` (Linux Desktop 24.04 LTS)

### copy permissions when copying/swapping data across directories or disk
- add this to the larger cli entry
  - ```
    cp -p
    ```

### onboard sensors
- provides insight into system specific temperatures and resource usage
- check if sensors is install
  - ```
    which lm-sensors
    ```
- if nothing returned
  - ```
    sudo apt install lm-sensors
    ```
- to monitor, display and update sensors at 1 second intervals
  - ```
    sudo watch -n 1 -d sensors
    ```
  - change the `1` to any number to monitor for that interval period
    - ```
      i.e. changing `1` to a `5` will change refresh interval to 5 seconds
      ```
- more sensor information
  - **may/may-not** be applicable to dandelion node
  - ```
    from - https://www.hwinfo.com/forum/threads/cpu-temp-sensors-explanation.5597/
    -CPU (onboard sensor): This is either a temperature measured by a dedicated sensor on mainboard located inside the CPU socket (the external CPU temperature) or temperature obtained from internal CPU thermal sensor (i.e. DTS = Digital Thermal Sensor).
    -Core Max: The maximum temperature among all cores in the CPU.
    -CPU (Tctl): This is the T_control temperature available on AMD CPUs only. On several generations before Zen (Ryzen), this is not a reliable representation of the temperature. On AMD Zen series this is the temperature used to control cooling and is a fixed offset from the real CPU temperature. Offset is used mostly on X-series and some Threadripper CPUs; in such case two values are shown: Tctl and Tdie. If no offset is used, then only a single value is shown as Tctl/Tdie, which equals the real temperature.
    -CPU (Tdie): This value is shown in case the CPU uses an offset from Tctl and represents the real temperature (Tdie = Tctl - Tctl_offset).
    -CPU Package: Shown on Intel CPUs represents a 256-millisecond average value (calculated by CPU) of the hottest temperature sensor within the CPU package.
    -CPU Package (TSI): Available on pre-Zen AMD CPUs is the CPU temperature obtained via TSI interface.
    -Core #n (n=any number): Actual temperature of a particular CPU core.
    -CPU IA Cores: Maximum temperature among all computing (x86) cores in CPU (so part of CPU except Uncore and Graphics logic).
    -CPU GT Cores: Temperature of the integrated graphics part of CPU (if present).
    ```
- another possible sensor source
  - ```
    https://www.linux.com/topic/desktop/advanced-lm-sensors-tips-and-tricks-linux-0/
    ```

    
### get hardware identifiers
- LSHW
  - check identifiers for driver updates or other troubleshooting
    - ```
      sudo lshw -short
      ```
  - output should provide information needed
    - use `CTRL + F` toi perform a keyword search on the output
  - can use `-json` or `-html` to get info in particular formats
 
### system overview

- INXI
  - overall system view, neatly organized, more user friendly
    - ```
      which inxi
      ```
	- if no output
    - ```
      sudo apt install inxi
      ```
  - to see system specs, hw names, drivers (user-friendly view)
    - ```
      sudo inxi -Fxz
      ```
- GLANCES
  - system overview with active processes
  - great for monitoring remotely
  - install Glances
    - ```
      sudo apt install glances
      ```
  - THEN
    - ```
      sudo glances
      ```

### change root (main) drive to another drive of equal or greater size
- ***use at own risk***
  - swapping/reinstalling linux due to drive size
    - ```
      https://ubuntuforums.org/showthread.php?t=2471454&p=14078689#post14078689
      ```
  - change boot volume with copying
    - ```
      https://medium.com/@dominikgacek/how-to-move-linux-root-partition-to-another-drive-quickly-31e54fdc9c19
      ```     

---

## NON-NODE SYSTEM INSTALL (MONITORING SYS)
- pgadmin

---

## DOCKER NOTES & COMMANDS
- docker uses project name as folder name
- possible to run multiple pre-prod instances with different variables being entered into `.env` in global variable
  - must not conflict; cannot have two that are both 0, 0; must be 0, 1 **OR** 0, 2

### stop, resume, monitor docker processes
- navigate to docker directory
  - ```
    cd /home/[username]/.../[directory with docker container] 
    ```
- stop docker process
  - ```
    docker compose down
    ```
- resume docker process
  - ```
    docker compose up
    ```
- show and follow docker logs
  - ```
    docker compose logs -f
    ```
- detach command
  - at the end of any docker command above type `space` then `-d` 

---

## DRIVERS
- Linux Kernel Driver Database
  ```
  - https://cateee.net/lkddb/
  - https://github.com/torvalds/linux/blob/master/drivers/
  ```

- NIC(s) drivers for `Aorus 870E Elite Wifi 7`
  - Device-1: `Realtek RTW89_8922AE`
    ```
    - Type: wireless (aka wi-fi)
    - Actions: automatically recognized by Linux Desktop 24.04 LTS
    - Drivers Needed: none
    - Issues: none
    ```
  - Device-2: `Realtek RTL8125 2.5GbE`
    ```
    - Type: hardware; 2.5 GbE
    - Actions: NOT automatically usable
    - Drivers Needed: NONE RECOMMENDED
    - Issues: UNSTABLE (see internet)
    ```
<!--
  - realtek driver website
    - ```
      https://www.realtek.com/Download/Index?cate_id=194&menu_id=297
      ```
  - device
    - ```
      wlp14s0
      ```
  - linux kernel driver
    - ```
      rtl8125
      ```
      - internet claims this is the wifi NIC
	- specific linux github directory
    - ```
      https://github.com/torvalds/linux/blob/master/drivers/net/wireless/realtek/rtw89/rtw8922ae.c
      ```
  - PID (???)
    - ```
      10EC:8922
      ```
  - might need to `re-ENABLE` onboard NIC in BIOS to see in `lshw`
-->
---

## NAS, RAID and OTHERs
- [FreeNAS](https://www.truenas.com/freenas/)
  - absorbed by TrueNAS and renamed TrueNAS Core
  - current as of `Time Of Writing (TOW)`
  	- [direct download - stable (current)](https://download-core.sys.truenas.net/13.0/STABLE/U6.7/x64/TrueNAS-13.0-U6.7.iso)
  	- [upgrading trueNAS Core - documentation](https://www.truenas.com/docs/core/coretutorials/updatingtruenas/updatingcore/)
  	- [download manual update - current `ATOW`](https://download-core.sys.truenas.net/13.0/STABLE/U6.7/TrueNAS-13.0-U6.7-manual-update.tar)
  		- [sha256 download for update](https://download-core.sys.truenas.net/13.0/STABLE/U6.7/TrueNAS-13.0-U6.7-manual-update.tar.sha256)
     		- ```
	          273af10a43e7a382807b281540e6f9f47d40c72da6c4503507904e4e1efcb57d
	          ```
- [OpenMedia Vault](https://www.openmediavault.org/)
  - open network attached storage 
- [Ceph](https://ceph.com/en)
  - Ceph is an open-source, distributed storage system
  - [documentation](https://docs.ceph.com/en/latest/releases/)


---------------- ORGANIZE THE BELOW ------------------------

cd ..


cd into drive to to be copied
sudo mv [target location] ../../[target-drive]
	- use tab to insure correct path
sudo nano etc/fstab
	- remove old directory path down to just /home
reboot
once logged delete old directory




Driver: https://linux-hardware.org/?id=pci:10ec-8125-1019-8125

—————————————	

**generate random chars**

sudo apt install gpw
gpw

disk usage

MAINNNET - 1.06TB

PREPROD - 303GB
￼



BACKUP PATH
- Mainnet - /media/piza/bkup/svc/ada-main-bkup  —> /media/piza/bkup/svc/ada-main-bkup
- Preprod - /media/piza/bkup/svc/ada-pp-bkup —>   /media/piza/bkup/svc/ada-pp-bkup

———————— DURING BACKUP STEPS —————————

￼

————————— AUTOSTART AS A SERVICE ————————

You should set 'KillUserProcesses=no' on '/etc/systemd/logind.conf' and run 'systemctl restart systemd-logind'

—————————————————————————

Docker Shutdown

sudo systemctl stop dandolite-preprod.service —> maybe dandelion-lite-preprod or whatever your container name is

sudo systemctl status dandolite-preprod.service



CSnapshot - Image Creation, minimize install
Duck DNS alternative
Test Failover
Update notes for Dandelion install
Governance around maintenance

——————————————————————————

lspci -vnn | grep Wireless

————————————————————————————————————

correct output for:

docker inspect --format "{{json .State.Health }}" dandolite-preprod-cardano-node-ogmios-1 | jq
docker inspect --format "{{json .State.Health }}" dandolite-preprod-cardano-db-sync-1 | jq

￼

—————— PREPROD BACKUP ———————————————

Start 303GB, end 320GB = 17GB backup
First run, no location or some other path error; corrected per below
Preprod backup start @ 1015hrs, end @ 1018:30

—————— MAINNET BACKUP ————————

303GB backup

—————— SERVICES————————————————

- [Haproxy Stats](https://github.com/unixsurfer/haproxystats)
- [Duck DNS](https://www.duckdns.org/)

-———————————————————————————

TECH PARTS
- Weastlinks Micro SD TF Card to 22pin SATA adapter card 2.5" hdd enclosure TF cards to 7+15 SATA converter
- 7.9"x4.7"x2.9"ABS Waterproof Junction Box Project Enclosure w PC Cover Gray
- https://www.newegg.com/p/0VN-004E-00025?Item=9SIA61HKCF0811
- https://www.newegg.com/ssk-he-c327-enclosure/p/0VN-004N-00005?Item=9SIAZS4ERW7243
- https://www.newegg.com/cooler-master-oracle-air-enclosure/p/N82E16817171237?Item=9SIA4REJXF5596
- https://www.newegg.com/p/3C6-01A5-004X5?Item=9SIBTSNKBB0845
- https://www.newegg.com/sabrent-ec-wpne-enclosure/p/0VN-0036-000D8?Item=9SIBK19K2E7435
- 
