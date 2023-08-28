# steps
1. update & configure your motherboard's bios
	- attach any size flash drive to your computer
	- format your flash drive as fat32 ([tutorial](<https://www.asus.com/support/FAQ/1044735/>))
	- download the latest bios file from your motherboard's support page
	- copy the bios file to the flash drive
	- undergo the bios update process ([tutorial](<https://www.youtube.com/watch?v=n6ZAMrjRudg>))
	- enable x.m.p ([tutorial](<https://www.youtube.com/watch?v=qCnGQPlY6pE>) | should be similar for most motherboards)
	- set fan curves in bios if desired ([tutorial](<https://www.youtube.com/watch?v=ZoWlNIzOO0E>) | different per motherboard)
2. create a bootable flash drive & install windows
	- attach an 8gb+ flash drive to your computer
	- download & install [rufus](<https://rufus.ie/en/>)
	- use rufus to download & mount the windows 11 iso to your flash drive ([tutorial](<https://pureinfotech.com/rufus-create-bootable-windows-11-usb/>))
	- undergo the windows setup process ([tutorial](<https://youtu.be/mTDbHgs9dHk?si=hBSuKpeqPmHCfUP6&t=117>) | start video at 1:57)
3. update windows
	- open windows settings & navigate to updates
	- check for updates & wait for them to install
	- restart your computer
4. update windows terminal
	- open the microsoft store & search for windows terminal
	- click the windows terminal & wait a few seconds
	- click the update button & wait for the update to complete
5. install powershell 7
	- open windows terminal
	- run the following command
		- `winget install microsoft.powershell`
6. configure windows terminal & winget
	- restart windows terminal
	- go to settings & set your default profile as powershell 7 (darker blue powershell)
	- select the powershell 7 profile in the left hand menu & enable "run this profile as administrator"
	- close windows terminal & open it again
	- run the following command
		- `winget settings --enable InstallerHashOverride`
7. install git
	- open windows terminal
	- run the following command
		- `winget install git.git`
8. download `bulk-edit-settings`  powershell script
	- restart windows terminal
	- run the following commands
		- `New-Item -Path "repo" -ItemType Directory`
		- `cd /repo`
		- `git clone https://github.com/ninbura/bulk-edit-windows-settings`
9. run `bulk-edit-settings` powershell script
	- open `c:/repo/bulk-edit-settings` folder 
	- open `bulk-edit-settings.ps1` in desired text editor
	- configure setting parameters at top of file as desired
	- save and close file
	- right click `run-me.bat` & run as administrator
	- wait for script to finish then restart your computer
10. manually configure other windows settings
	- theme settings
		- navigate to `personalization > colors`
		- change "choose your mode" to dark
		- set desired accent color
	- display settings
		- navigate to `system > display`
		- order displays as desired
		- select main display
		- open "multiple displays" dropdown
			- check "make this my main display"
		- scroll to bottom of list & select "advanced display"
			- set refresh rate for each monitor
	- network settings
		- navigate to `network & internet > advanced network settings > advanced sharing settings`
		- expand "all networks" drop down
		- enable "public folder sharing"
		- enable "password protected sharing"
11. download, install, & run winget-autoupdate (bulk software installer/updater)
	- download wigui & run (wigui = gui for winget-autoupdate)
		- `winget install wigui --location documents`
		- should be in your user's documents folder after download
	- click on the "configure WAU tab"
	  - reference image below for configuration on this tab
    ![Pasted_image_20230826144011-1](https://github.com/ninbura/install-and-configure-microsoft-windows/assets/58058942/cb2b2bad-d395-498f-852e-16483525fe5f)
	- restart your computer
	- wait for winget-autoupdate to update existing packages
	- open `install-list.txt` in your text editor of choice and remove/add entries per your desires
    - `c:/repo/install-and-configure-microsoft-windows/.install-list.txt`
	- Restart wigui, load your install list, click install, & wait for the process to finish.
    - `c:/repo/install-and-configure-microsoft-windows/.blacklist.txt` 
	- to modify update blacklist going forward edit the following txt file
		- `C:\ProgramData\Winget-AutoUpdate\excluded_apps.txt`
		- blacklist apps the consistently fail to update via winget-autoupdate
12. configure msi afterburner (gpu fan curve)
	- *this is not applicable if your gpu is water cooled*
	- This program should have been installed via wigui, just search for it in start and open it.
	- enable startup at launch
		- open settings (should be a button on the left hand side)
		- click on the "general" tab
		- check "start with windows"
		- check "start minimized"
		- hit "apply"
	- enable msi afterburners fan curve
		- click on the "fan" tab
		- check "enable user defined software automatic fan control"
			- Leaving it at default should be fine, but feel free to create your own curve if you want.
		- hit "apply"
	- hit "ok" to close settings dialog
	- minimize msi afterburner
13. download/install drivers from the **drivers** list below
14. download/install remaining software as desired from **software** list below
# drivers
- Some drivers will need be downloaded from your motherboard's support page, others are typically universal. If your motherboard uses intel drivers for bluetooth, lan, & wan (wifi) you can use the links below to get the latest versions. To verify that your motherboard uses universal intel drivers, you'll need to go to your motherboards support page.
- drivers you typically need to grab from your motherboards support page
	- audio driver 
		- usually labeled as realtek
	- intel chipset driver
		- only required if you're using an intel cpu
	- sata driver
		- only required if you're using sata based storage
		- typically labeled as "intel rapid storage technology"
- latest intel device drivers 
	- check motherboard page to make sure your motherboard uses intel for these devices
	- [intel bluetooth](<https://www.intel.com/content/www/us/en/support/articles/000005489/wireless.html>)
	- [intel lan](<https://www.intel.com/content/www/us/en/download/18293/intel-network-adapter-driver-for-windows-10.html>) (ethernet)
	- [intel wan](<https://www.intel.com/content/www/us/en/download/19351/windows-10-and-windows-11-wi-fi-drivers-for-intel-wireless-adapters.html>) (wifi)
- drivers you will need from your motherboard's support page if said devices aren't intel
	- bluetooth driver
	- lan driver (ethernet)
	- wan driver (wifi)
- [amd cpu/chipset & gpu drivers](<https://www.amd.com/en/support>)
- [nvidia drivers](<https://www.nvidia.com/download/index.aspx>)
	- *click buttons on nvidia driver page slowly, if you move too fast you will get ip banned!*
	- always select **custom install** then **clean install**
	- open nvidia control panel ([shift+right click] desktop)
		- select "manage 3d settings" in left hand side menu
			- set "power management mode" to "prefer maximum performance"
		- select "change resolution" in left hand side menu & verify that all monitors are
			- set to the correct resolution & refresh rate
			- set to full rgb color mode
				- If color mode is partial and greyed out; override settings with "use nvidia color settings".
- other drivers
	- [silabs 3.9.2](<https://hdfury.com/product/integral-2/>) (hdfury integral 2)
		- must be installed via **admin elevated** terminal
		- `start-process -path [releativepath]/Silabs_Driver_v3/Silabs_Driver_v3/USBXpressInstaller.exe`
	- [magewell pro capture](<https://www.magewell.com/downloads/pro-capture>) (magewell capture pro cards)
	- [rme drivers](<https://www.rme-usa.com/downloads.html>) (rme audio interfaces)
	- [tx401](<https://www.tp-link.com/us/support/download/tx401/>) (10g ethernet pcie card)
# software
- [adobe creative cloud](<https://www.adobe.com/creativecloud.html>) (photoshop, premiere, etc.)
- [advanced scene switcher](<https://github.com/WarmUpTill/SceneSwitcher/releases>) (obs plugin)
- appstudio (reporting client for afs)
- [battlenet launcher](<https://us.shop.battle.net/en-us>)
- cisco anyconnect (vpn client for afs)
	- microsoft store
- [crystaldiskinfo](<https://crystalmark.info/en/software/crystaldiskinfo/>) (check disk hard drive health)
- [crystaldiskmark](<https://crystalmark.info/en/software/crystaldiskmark/>) (test hard drive speed)
- [davinci resolve](<https://www.blackmagicdesign.com/products/davinciresolve>) (download link near the bottom of the page)
- [easybcd](<https://neosmart.net/EasyBCD/>) (tool for dual booting)
- ffmpeg (cli media editor)
	- run in **elevated** console
	- `winget install gyan.ffmpeg`
- [ffxiv launcher](<https://na.finalfantasyxiv.com/lodestone/playguide/#returner>) 
- icloud
	- microsoft store
- [ireboot](<https://neosmart.net/iReboot/>) (tool for dual booting)
- [obs asio](<https://github.com/Andersama/obs-asio/releases>) (obs plugin)
- [synergy](<https://symless.com/synergy/account-login?redirect=https%3A%2F%2Fsymless.com%2Fsynergy%2Fdownload>) (tool for sharing single mouse & keyboard with multiple computers)
- [rode central](<https://rode.com/en-us/software/rode-central>) (Rodecaster Pro II & Rodecaster Duo)
- [via](<https://www.caniusevia.com/>) (tool for configuring many keyboard models)
- [vlc 4.0](<https://artifacts.videolan.org/vlc/nightly-win64/>) (video player, plays all codecs including the new av1 codec)
- [window-switcher](<https://github.com/sigoden/window-switcher/releases>) (macOS style window switching for windows 11)
- [wootliltiy](<https://wooting.io/wootility>) (software to configure wooting keyboards)
- wsa (windows subsystem for android)
	- download amazon store via windows store
	- restart your computer
- wsl (windows subsystem for linux)
	- run in **elevated** console
	- `wsl --install`
		- restart your computer
	- `winget search ubuntu`
	- `winget install Canonical.Ubuntu.2204`
- xbox accessories (tool for configuring xbox controllers)
	- microsoft store
