# ALL DANDO BUILD NOTES
### LINKS
- [Dandelion Node Operators meeting link - `JitSi`](https://meet.jit.si/moderated/d2b4d761960b5ead162c5f3e522166be2eef812bffd500a35b28f79885b18ffc)
- 
##### Starting 04 April 2025
###### Includes hardware specific notes
- The below are a compilation of notes that were taken while installing the preprod <br> and mainnet dandeklion nodes. Some are basic, some not so much. If there was <br> and issue it was noted. In the future I will play around with the formatting so that <br> it is more user friendly. Tables will be inserted where it makes sense.
- These notes are as much for me as they are for YOU.
- All links were current at time of writing

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

## INSTALLING LINUX
```
THIS SECTION can be expanded upon
```
- boot to bootable disk from [above]()
- click disc image in upper left-hand corner
  - follow instructions
  - when rebooting remove installation media
- initial boot may take some time depending on your system and specs

## FIRST THINGS FIRST

### CHANGE SWAP FILE RESIZE
- from default (8GB) to 40G
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
### NETWORK & FIREWALL
- This section is mostly for Desktop variants of Linux
- For Server variant commands and setup [SEE HERE](https://github.com/st8tikratio/Uselessness/blob/main/node-operations/pdfs/Ubuntu-Server-CLI_cheat-sheet-2024-v6.pdf)

#### setup firewall
```
This install uses UFW, uncomplicated firewall
You may use any firewall you are comfortable with. 

*** NOTE ***
Your system could possibly become a target for hackers. It is important that you take all seurity precautions.
The guides within these pages are just that, guides, with no warranty implied or written.
Use at your own risk.
```

##### install GUFW
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

#### communication ports
  
| **SERVICE**		|  **PORT**	| **STANDARD** 	| **DIRECTION**	|
| ------------	| ----------	| ----------	| ----------	|
| Cardano Node	| 3001		| TCP		| Inbound	|
| Haproxy	| 8053		| TCP		| Inbound	|
| Mainnet	| 3080		| TCP		| Inbound	|
| Preprod	| 3081		| TCP		| Inbound	|


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
| **FLAG**			| **ACTION**				 | **EXAMPLES**				| **OUTPUT** <br> **EXPLANATION**	|
| ---------			| --------				 | --------  				| -------				|
| `-help` <br> `-h`		| help					 | `python3 -h`				| provides usage and options		|
| `-version` <br> `-v`		| version				 | `python3 --version`  		| `Python 3.12.3`			|
| `-p`				| permissions				 | cp -p [filename] [destination]	| copy file & permissions to destination|	


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
```
This section will provide:
Dandelion build specs, setup and operation notes
Docker commands and related instructions
```

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

### OBSERVED POWER USAGE
```
Measurements taken with both MAINNET and PREPROD running

Measured from a Cyberpower 1500W Battery Backup
```
| **TYPE**   | **UNIT**    | **MEASUREMENT 1** | **MEASUREMENT 2** |
| ---------         | ---------   | ---------------    |  -------------    |
| **FIXED OBSERVATION**  | | | |
| `input voltage`   | volts (V)   | 122                |     --            |
| `output voltage`   | volts (V)   | 122                |     --           |
| `output frequency` | hertz (Hz)  | 60                 |   --             |
| **RANGED OBSERVATIONS** | | | |
| power usage        | watts (W)    | 210  | 283  |
| power draw         | volts (V)    | 204  | 218  |

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

## REQUIRED LINUX INSTALLS
- see [table above]()


--------------

## TIPS, TRICKS, USEFUL CMDs
```
Some of these may require SUDO for full effectiveness

If output reads:
    - Command 'ipconfig' not found, did you mean:
You will need to install using:
    - sudo apt install [pkg name]

```

| **FUNCTION**  				| **CMD or ACTION** 				| 	**NOTES**										|
| --------------				 	| ----------				| -----------------										|
|   when typing in the CLI use `TAB` to autocomplete	| autocomplete <br> list options	| `./scripts/dand`   -> `TAB` key  —> `ENTER`							|
| `CTRL + S`						|pause large outputs			| may/may-not work on your particular output							|
| `CTRL + Q`						| resume large outputs			| if `CTRL + S` worked, this will resume the output						|
| `ip -br a`						| check network connectivity		| will show network device, ip address, and state						|
| `nmap` [your ip address from **ip -br a**]/24		| map a devices IP Address		| the `/24` may be different, see `ip -br a` output						|
|  `sudo lshw -short` <br> `sudo lshw -h`		| show hardware devices			| shows list of all hardware <br> use CTRL+F to search within output				|
| `sudo lshw -json`					| shows hardware list in json format	| may want to save to file instead of screen output	|
|  `df -h`						| show harddrives and usage		| shows every mounted drive and their respective values						|
| `sudo watch -n 1 -d sensors`				| show sensors, [x] seconds internval	| change `1` to whatever seconds for output refresh 						|
| `inxi -Fxz`						| shows system info in pretty output	| requires installation			|
| `sudo glances`					| shows realtime system ovrerview	| requires install <br> use `sudo` to see more details	|



### sensors
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

### adding another drive to node build
- open fstab
  - ```
    sudo nano /etc/fstab
    ```
- copy primary drive information on newline and replace info with new drive info
	- last two digits on line should be 0 and 2
	- find UUID in `Drive Manager` (Linux Desktop 24.04 LTS)

### change root (main) drive to another drive of equal or greater size
- ***USE AT OWN RISK***
  ```
  THIS PROCESS NEEDS VERIFICATION
  
  	cd into drive to to be copied
	sudo mv [target location] ../../[target-drive]
		- use tab to insure correct path
	sudo nano etc/fstab
		- remove old directory path down to just /home
	reboot
	once logged delete old directory
  ```
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

## DOCKER INFOS
```
*** NOTE ***
You must navigate to the docker directory before executing the commands below
	- cd [path to docker container]
```
- docker uses project name as folder name
- possible to run multiple pre-prod instances with different variables being entered into `.env` in global variable
  - must not conflict; cannot have two that are both 0, 0; must be 0, 1 **OR** 0, 2

### commands

| **COMMAND**			| **USE**					| **NOTES**												|
| ---------			| ------------					| ----------												|
| `docker compose down`		| spin down docker container			| may take some time											|
| `docker compose up -d`	| bring docker container back up 		| **MUST USE** `-d` of on-screen processes will run as long as container is up <br> `-d` means detached	|
| `docker compose logs -f`	| shows process logs for **that** container	| continuously shows log entries <br> `CTRL + C` to stop						|
| `docker volume ls`		| lists all docker volumes			| docker does not us `-` for ls										| 
| `docker ps`			| lists all ports used by docker		| none													|
| `docker down -v`		| purges volumes but `NOT containers`		| use carefully												|
| `docker down`			| reinstantiates the containers ??		| not sure if the use-case is correct <br> use carefully						|
| `docker compose logs haproxy`	| show logs related to `haproxy`		| can replace `haproxy` with another service running within the container				|
| 

### container & koios tip checks
```
must navigate to the appropriate container:
	- cd [container path]
```
#### cardano-node-ogmios check
Use:
```
docker inspect --format "{{json .State.Health }}" dandolite-preprod-cardano-node-ogmios-1 | jq
```
Output (or similar):
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-04-25T06:20:51.765056388-04:00",
      "End": "2025-04-25T06:20:55.973940869-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-04-25T06:21:26.048605012-04:00",
      "End": "2025-04-25T06:21:28.420051814-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-04-25T06:22:00.277662882-04:00",
      "End": "2025-04-25T06:22:05.784163753-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-04-25T06:22:36.23304327-04:00",
      "End": "2025-04-25T06:22:36.325506032-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    },
    {
      "Start": "2025-04-25T06:23:06.59659955-04:00",
      "End": "2025-04-25T06:23:09.09397988-04:00",
      "ExitCode": 0,
      "Output": "NETWORK=preprod\nOK - Node sync progress: 100.00 %"
    }
  ]
}
```
#### cardano-db-sync check
Use:
```
docker inspect --format "{{json .State.Health }}" dandolite-preprod-cardano-db-sync-1 | jq
```
Ouput (or similar):
```
{
  "Status": "healthy",
  "FailingStreak": 0,
  "Log": [
    {
      "Start": "2025-04-25T06:18:36.872086509-04:00",
      "End": "2025-04-25T06:18:42.41664094-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 43 < 3600"
    },
    {
      "Start": "2025-04-25T06:19:42.729241288-04:00",
      "End": "2025-04-25T06:19:45.114280353-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 109 < 3600"
    },
    {
      "Start": "2025-04-25T06:20:45.236456103-04:00",
      "End": "2025-04-25T06:20:45.727457649-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 171 < 3600"
    },
    {
      "Start": "2025-04-25T06:21:46.324527501-04:00",
      "End": "2025-04-25T06:21:47.71038067-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 22 < 3600"
    },
    {
      "Start": "2025-04-25T06:22:48.235770233-04:00",
      "End": "2025-04-25T06:22:48.405765326-04:00",
      "ExitCode": 0,
      "Output": "Block table available\nOK 47 < 3600"
    }
  ]
}
```

#### koios tip check
Use:
```
curl http://127.0.0.1:8050/koios/v1/tip
```
Ouput:
```
{ }
```


---

## DRIVERS
- Linux Kernel Driver Database
  ```
  - https://cateee.net/lkddb/
  - https://github.com/torvalds/linux/blob/master/drivers/
  ```

- NIC(s) drivers for `Aorus 870E Elite Wifi 7`
  ```
  DO NOT INSTALL DRIVERS FOR THE NIC BELOW
  ```
  - Device-2: `Realtek RTL8125 2.5GbE`
    ```
    - Type: hardware; 2.5 GbE
    - Actions: NOT automatically usable
    - Drivers Needed: NONE RECOMMENDED
    - Issues: UNSTABLE (see internet)
    ```


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

<!--

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
docker down -v   > purges volumes not containers

docker down > - will reinstantiate

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

UNIMATRIX_VERSION=1.0.3

----------------------

----
haproxy default port 8053
cardano node port comms -> 3ls

3001

sudo ufw allow <port>/tcp


docker compose up -- in appropriate directory

docker compose logs -f

-———————————————————————————

TECH PARTS
- Weastlinks Micro SD TF Card to 22pin SATA adapter card 2.5" hdd enclosure TF cards to 7+15 SATA converter
- 7.9"x4.7"x2.9"ABS Waterproof Junction Box Project Enclosure w PC Cover Gray
- https://www.newegg.com/p/0VN-004E-00025?Item=9SIA61HKCF0811
- https://www.newegg.com/ssk-he-c327-enclosure/p/0VN-004N-00005?Item=9SIAZS4ERW7243
- https://www.newegg.com/cooler-master-oracle-air-enclosure/p/N82E16817171237?Item=9SIA4REJXF5596
- https://www.newegg.com/p/3C6-01A5-004X5?Item=9SIBTSNKBB0845
- https://www.newegg.com/sabrent-ec-wpne-enclosure/p/0VN-0036-000D8?Item=9SIBK19K2E7435

------VVVV----- ADDED ALREADY ------VVVV-----------


**generate random chars**

sudo apt install gpw
gpw

disk usage

MAINNNET - 1.06TB

PREPROD - 303GB
￼

--VVV----- MY SYS RELATED DETAILS ----VVV--

BACKUP PATH
- Mainnet - /media/piza/bkup/svc/ada-main-bkup  —> /media/piza/bkup/svc/ada-main-bkup
-->
