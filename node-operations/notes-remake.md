# ALL DANDO BUILD NOTES
##### Starting 04 April 2025
###### Includes hardware specific notes
- The below are a compilation of notes that were taken while installing the preprod <br> and mainnet dandeklion nodes. Some are basic, some not so much. If there was <br> and issue it was noted. In the future I will play around with the formatting so that <br> it is more user friendly. Tables will be inserted where it makes sense.
- These notes are as much for me as they are for YOU.
- All links were current at time of writing


<!--
---

1. [Install Linux]()
  
	  - [Download Linux ISO]()
	
	  - [Create a bootable drive]()
	
	  - [Utilities]()
	  
	  - [Terminal Commands]()
		- [Updates & Package Management]()
		- [General]()
		- [Command Flags]()
	  
	  - [Other Linux websites]()

2. [M2Tec Mods]()

3. [Dandelion Lite]()
  
	  - General specs, measurements, errors
	      - [Server/Node build]()
	      - [Usage after n days up-time]()
	      - [Common errors and resource hogs]()
	  
	  - Requirements
	      - [Swap file resize]()

-->

---

# INSTALL LINUX
```
This section will contain all things Linux. From requirements, to utilities, to general and useful commands
```
<!--
1. [Download Linux ISO]()
2. [Create a bootable drive]()
3. [Utilities]()
4. [Terminal commands]()
	- [Updates & package management]()
	- [General]()
	- [Command flags]()
5. [Other Linux websites]()
-->

## DOWNLOAD LINUX ISO
```
It is recommended to only use LTS versions of Linux.
LTS means Long Term Support
```
| **LINUX TYPE**   |  **VERSION**  |  **LINK** | **DATE**  |
| ----             |    ------     |  -------- | -------   |
| Server [LTS]     | 24.04         | [click here](https://ubuntu.com/download/server/thank-you?version=24.04.2&architecture=amd64&lts=true)  | 12 April 2025 |
| Desktop [LTS]    | 24.04         | [click here](https://ubuntu.com/download/desktop/thank-you?version=24.04.2&architecture=amd64&lts=true) | 12 April 2025 |

## CREATE A BOOTABLE DRIVE
- you can use a thumb-drive, usb-drive, external harddrive, SD-card or even a disc if your server and support system both have disc drives.
  ```
  ***NOTE*** Any data on the media being used for this process will be wiped of data
  ```
  - `MacOS:` install [balenaEtcher](https://etcher.balena.io/) and follow instructions
  - `Windows:` install [UNetbootin](https://unetbootin.github.io/) and follow instructions
  - `Linux:` install [UNetbootin](https://unetbootin.github.io/) and follow instructions

## UTILITIES
| **NAME**                    		| **REQUIRED**   | **USE**  				 | **INSTALL** 				| **COMMANDS**  | **WEB/DOC** |
| --------                              | :---------:    | :-------:  				 |  ---------------    			| ------------- | ----- |
| `git`                                 | YES            | git <br> functionality  		 | ``` sudo apt install git ``` 	| [see here]()  | [documentation](https://git-scm.com/doc) |
| `gufw`				| YES		 | firewall				 | ```sudo apt install gufw```		| [see here]()	| [linux pkg](https://help.ubuntu.com/community/Gufw)
| `nano`                                | SUGGESTED      | inline <br> terminal <br> editor 	 | ```sudo apt install nano```		| [see here]()  | cli - `man nano` |
| `vim`                                 | ALT            | inline <br> terminal <br> editor	 | ```sudo apt install vim```		| [see here]()  | [website](https://www.vim.org/) |
| `nmap`				| YES		 | network mapping utility	    	 | ```sudo apt install nmap``` 		| [see here]	| [website](https://nmap.org/download) |
| `glances`                             | SUGGESTED      | complete <br> system <br> monitor  	 | ```sudo apt install glances``` 	| [see here]()  | [github](https://github.com/nicolargo/glances) |
| `sensors` <br> `fka: lm-sensors`      | ALT            | system <br> sensor <br> monitoring	 | ```sudo apt install sensors``` 	| [see here]()  | [github](https://github.com/lm-sensors/lm-sensors) |
| `gpw`                                 | SUGGESTED      | random <br> character <br> generator  | ```sudo apt install gpw``` 		| [see here]()  | [linux pkg](https://packages.ubuntu.com/oracular/gpw) |
| `inxi`                                | SUGGESTED      | pretty <br> system <br> information   | ```sudo apt install inxi``` 		| [see here]()  | [documentation](https://smxi.org/docs/inxi.htm) |

## TERMINAL COMMANDS (CLI)
```
Useful commands to help navigate the Linux operating system and Dandelion node directories
```

<!--
1. [Updates and Package Management]()
2. [General]()
3. [Command Flags]()
-->
### UPDATES & PACKAGE MANAGEMENT
```
Requires root privilege - `sudo` - for full usage

EXAMPLE: sudo apt search sensors
```

| **COMMAND**			| **ACTION**						| **OUTPUT**	|
| ---------			| --------						| -------	|
| ```apt update```		| see which systems & apps need updating 		| provides list of updateable items |
| ```apt upgrade``` 		| upgrades upgradeable systems & apps			| **note:** may need to press 'Y' <br> shows upgrade progress |
| ```apt search [pkg name]```   | search apt packages for specific app by text		| provides list of matches if found	|
| ```apt info [pkg name]``` 	| get information on a package				| limited output, 10-20 lines of info	|
| ```apt remove [pkg name]```	| remove packages					| may request input <br> returns to prompt	|

### GENERAL
| **COMMAND**	| **ACTION**				 | **EXAMPLES**		| **OUTPUT**	|
| ---------	| --------				 | --------  		| -------	|
| ```pwd```	| see present working directory (folder) | 			||
| ```ls```	| show files within current directory 	 |			||
| ```cd [namme-of-directory```	| change directory 	 | ```cd home/dev``` 	||
| ```cd ..```	| go back one directory level		 |	  	        ||
| ```cd```	| go back to home directory	         |		        ||
| ```lshw```	| list hardware			      	 | ```lshw --short``` 	||
| ```which```	| which [package name]			 | ```which nano```	| shows path	|

### COMMAND FLAGS
```
Flags can be different between the operating system (Linux) and applications. The flags below are general Linux flags

NOTE: For python use `--version`
```
| **FLAG**			| **ACTION**				 | **EXAMPLES**		| **OUTPUT**	|
| ---------			| --------				 | --------  		| -------	|
| `-help` <br> `-h`		| help					 | `python3 -h`		| provides usage and options	|
| `-version` <br> `-v`		| version				 | `python3 --version`  | `Python 3.12.3`	|


## OTHER LINUX WEBSITES

| **Usage**		       | **Website** 			 |
| ---------		       | -------			 |
| Linux Ubuntu Package Search  | https://packages.ubuntu.com/    |
| Linux Hardware Drivers       | https://linux-hardware.org/     |
|			       | 				 |

---

# M2TEC MODS
```
List of ongoing modifications that may be rolled into Dandelion Lite Node package

Completed modifications/updates are rolled into the Dandelion Lite Package
```
| **Mod & Updates**			| **Related Links**								| **Discussions**	|
| --------------			| :---------------:								| :-------------:		|
| Cardano GraphQL without metadata 	| [Github](https://github.com/M2tec/cardano-graphql/tree/feat/no_Meta)		| [Discord](https://discord.com/channels/912354788795109396/1359910909459566814)  |

---

# DANDELION LITE
<!--
1. General specs, measurements, errors
  - [`Server/Node build`]()
  - [`Usage after n days up-time`]()
  - [`Common errors and resource hogs`]()
2. System Requirements
  - [`Firewall`]()
  - [`Swap file resize`]()
  - 
4. 
5. 
-->
## GENERAL SPECS, MEASURMENTS, ERRORS
<!--
1. [Server/node build]()
2. [Resource Usage]()
3. [Common errors & resource hogs]()
-->
### SERVER/NODE BUILD
```
- actual system build
- purchased from NewEgg + Amazon
- total cost: USD $2371.72 + tax + shipping ~ $2600.00
```

| **PART**																		| **MAKE**  		| **MODEL** 		 		| **P/N** 			| **CAPACITY**				 		| **COST (USD)** 	|
| ----------																		| -------   		| ----------		 		| ----   			| ------------				 		| ----------		|
| [case](https://www.newegg.com/black-phanteks-enthoo-pro-atx-full-tower/p/N82E16811854004?Item=N82E16811854004)					| PHANTEKS  		| ETHOO     	  	 		| PH-ES614PC_BK  		| Full ATX Tower					| 120.99		|		
| [power supply](https://www.amazon.com/dp/B0BWKT2JRV?ref_=ppx_hzod_title_dt_b_fed_asin_title_0_0)							| Thermaltake		| Toughpower				| PS-TPD-1200FNFAPU-L		| PF3, ATX-3.0, 1200W 80+ <br> Platinum Full Modular	| 226.59		|
| [memory](https://www.newegg.com/nemix-ram-128gb/p/1X5-003Z-01FR6?Item=9SIA7S6K3T3025)								        | Nemix     		| DDR5 ECC Unbuffered UDIMM Memory	| ME38400-328K4			| DDR5, 4800MHz, 4x32GB			 		| 519.29		|	
| [cpu](https://www.newegg.com/amd-ryzen-9-9950x-4-3-ghz-16-core-am5-170w-processor-100-100001277wof/p/N82E16819113841?Item=N82E16819113841)		| AMD	    		| Ryzen 9 - 9950X	  	  	| 100-100001277WOF    		| 16-Core; 4.3 GHz			 		| 538.99		|
| [cpu cooler](https://www.newegg.com/be-quiet-liquid-cooling-system-black/p/N82E16835269032?Item=N82E16835269032)					| Be quiet! 		| Silent Loop 3     	  		| ---				| 420mm AIO				 		| 174.90		|
| [motherboard](https://www.newegg.com/p/N82E16813145517?Item=N82E16813145517)										| Gigabyte  		| Aorus	         	  		| X870E AORUS ELITE WIFI7	| AM5, DDR5, 4xM.2, PCI-5		 		| 309.99		|
| [nvme](https://www.newegg.com/pny-2tb-cs2150-nvme-2-0/p/N82E16820177170?Item=N82E16820177170) 							| PNY	   		| CS2150	  	     		| M280CS2150-2TB-TB		| 2TB, PCI-Express 5.0 x4		 		| 179.99		|
| [nvme](https://www.newegg.com/pny-2tb-cs2150-nvme-2-0/p/N82E16820177170?Item=N82E16820177170) 							| PNY	    		| CS2150	  	     		| M280CS2150-2TB-TB		| 2TB, PCI-Express 5.0 x4		 		| 179.99		|
| [nvme](https://www.newegg.com/western-digital-1tb-black-sn850x-nvme/p/N82E16820250243?Item=N82E16820250243)						| Western Digital	| BLACK SN850X NVMe			| WDS100T2X0E			| 1TB, PCI-Express 4.0 x4		 		| 0.00			|
| [nic](https://www.newegg.com/intel-x550-t2/p/N82E16833106292?Item=9SIA4A0K9D5713)									| Lenovo/Intel		| X550-T2 	  	      		| ---				| 2 x RJ-45, 10GbE/5GbE/2.5GbE/1GbE/100Mb		| 120.99		|
|																			| 			|					|				|			       **`TOTAL`** 		| `2371.72`		|

### RESOURCE USAGE
```
*** NOTE ***
This section is for REFERENCE ONLY and is system-specific
Your dashboards may look different
```  

| **UPTIME or DATE**			| **RESOURCE**		| **USAGE**  	| **MAX**				| **NOTES**				|
| ---------				| -------		| --------	| -------				| --------------------			|
| `2 days, 0:41:5`			| swap space		| 27.4%		| 40GB					| [`resized from 8GB to 40GB`]()	|
| 					| memory		| 45.3% 	| 128GB					| --					|
| 					| cpu			| 25.3% 	| 16-Core				| --					|
| 					| disk usage		| 682G 		| 1.0 TB				| [`changed root drive to 2tb`]()	|
| `11 April 2025`			| backup - mainnet 	| 		| 2.0 TB				|					|
|					| backup - preprod 	|		| 2.0 TB				|					|
| `12 April`				| disk usage		| 1.06TB	| 2.0 TB				| `includes both preprod and mainnet`	|



### COMMON ERRORS & RESOURCE HOGS
- CPU_IOWAIT
  ```
  Examples:
  2025-04-08 09:01:10 (0:00:12) - CRITICAL on CPU_IOWAIT (Min:3.3 Mean:4.9 Max:7.4): cardano-node, java, conmon
  2025-04-08 09:01:10 (0:00:12) - CRITICAL on CPU_IOWAIT (Min:3.3 Mean:4.9 Max:7.4): postgres, postgres, postgres
  ```
- "Applying patch..."
  ```
  Examples:
  Name                    Status    Uptime  CPU%    MEM/MAX      IOR/s IOW/s     Rx/s Tx/ Command
  dandolite-mainnet-ca   running  yesterday 132.6    _/_           _ _            _ _     /bin/sh -c  echo "Applying patch to provide env vars due to hardcoded values:" ; echo "   OGMIOS_HOST='cardano-node-ogmios'" ; echo " >
  dandolite-mainnet-ca   running yesterday   0.1     _/_           _ _            _ _     /bin/sh -c  echo "Applying patch to provide env vars due to hardcoded values:" ; echo "   OGMIOS_HOST='cardano-node-ogmios'" ; ech>
  dandolite-preprod-ca   running  just now   0.0     _/_           _ _            _ _     /bin/sh -c  echo "Applying patch to provide env vars due to hardcoded values:" ; echo "   OGMIOS_HOST='cardano-node-ogmios'" ; ech>
  dandolite-preprod-ca   running     a min   0.9     _/_           _ _            _ _     /bin/sh -c  echo "Applying patch to provide env vars due to hardcoded values:" ; echo "   OGMIOS_HOST='cardano-node-ogmios'" ; ech>
  ```

## NETWORK & FIREWALL
### COMMUNICATION PORT REQUIREMENTS
  
| **SERVICE**		|  **PORT**	| **STANDARD** 	| **DIRECTION**	|
| ------------	| ----------	| ----------	| ----------	|
| Cardano Node	| 3001		| TCP		| Inbound	|
| Haproxy		| 8053		| TCP		| Inbound	|

### SETUP FIREWALL
```
This install uses UFW, uncomplicated firewall
You may use any firewall you are comfortable with. 

*** NOTE ***
You system could possibly become a target for hackers. It is important that you take all seurity precautions.
The guides within these pages are just that, guides, with no warranty implied or written.
Use at your own risk.
```
#### install GUFW
  ```
  sudo apt install gufw
  ```
- there should be a shield icon in programs or on desktop menu (Ubuntu Desktop only)
	1. Double-click UFW icon (shield with diagnol stripe)
	2. Turn firewall on, click slider
	3. Click on Rules
	4. Click on Simople
	5. Name: create a name for this rule, i.e. c-node
	6. Policy: Allow
	7. Direction: In
	8. Protocol: TCP
	9. Port or Service: 3001
	10. Click on Add
- REPEAT ABOVE for Haproxy on port 8053
  
#### SWAP FILE RESIZE
- from default (8GB) to 40G
    ```
    cd into [docker directory]
    docker compose down
    swapon --show
    sudo swapoff -v /swap.img 
    sudo rm -rf /swap.img
    sudo fallocate -l 40G /swap.img 
    sudo chmod 0600 /swap.img 
    sudo mkswap /swap.img 
    sudo swapon 
    sudo reboot now
    ```

#### REQUIRED LINUX INSTALLS
- see [table above]()


## TIPS, TRICKS, USEFUL CMDs

### autocomplete using TAB
- start typing path or directory and hit `TAB` to autcomplete
  - if not autocomplete, hit `TAB` twice for list of 'paths'
  - example
    ```
    ./scripts/dand   -> TAB key  —> ENTER
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


lsblk


-------- DOCKER NOTES -------------

remove volumes docker
docker volume ls

For Mainnet Only
docker down -v   ---> purges volumes not containers
docker down -->
- will reinstantiate

---------- POSSIBLE CONTAINER ISSUES -------------

Container deployment issue
- option to select a volumes (option 1 = , option 2 = )
- change in Docker configuration file
- FIXED

----
--------------------- ENV FILE ---------------------

#Dandelion Network Information
NODE_NAME="sunkiller-13"
NODE_TICKER="sunk13"

POST_GRES_PASSWORD= "create new password"
epleci-teckerski-nsssini-zeionneste

UNIMATRIX_VERSION=1.0.3

----------------------

----
haproxy default port 8053
cardano node port comms --> 3ls
001

sudo ufw allow <port>/tcp


docker compose up -- in appropriate directory

docker compose logs -f

<!--

-———————————————————————————

TECH PARTS
- Weastlinks Micro SD TF Card to 22pin SATA adapter card 2.5" hdd enclosure TF cards to 7+15 SATA converter
- 7.9"x4.7"x2.9"ABS Waterproof Junction Box Project Enclosure w PC Cover Gray
- https://www.newegg.com/p/0VN-004E-00025?Item=9SIA61HKCF0811
- https://www.newegg.com/ssk-he-c327-enclosure/p/0VN-004N-00005?Item=9SIAZS4ERW7243
- https://www.newegg.com/cooler-master-oracle-air-enclosure/p/N82E16817171237?Item=9SIA4REJXF5596
- https://www.newegg.com/p/3C6-01A5-004X5?Item=9SIBTSNKBB0845
- https://www.newegg.com/sabrent-ec-wpne-enclosure/p/0VN-0036-000D8?Item=9SIBK19K2E7435

-->
