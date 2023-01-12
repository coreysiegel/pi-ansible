# pi-ansible
This project is intended to create standard Raspberry Pi systems for SF ACS field operations.

## Installation/Usage
	* On server/workstation with an SD card reader:
		* Install latest base Raspbian base image from https://www.raspberrypi.com/software/ onto SD card.
		* Under "Install Raspberry Pi OS using Raspberry Pi Imager," select "Download for" the OS that you are using.
		* From download, install Raspberry Pi Imager.
		* Run Raspberry Pi Imager.
			* OS: Select Raspberry Pi OS Desktop (32-bit).
			* Storage: Select SD card.
			* Write.
	* Connect Pi to same network as server/workstation.
	* Boot Pi from the new SD card.
		* Set country, language, timezone.
		* Set username and password per ACS General Info Sheet (first page).
		* Skip wifi setup.
		* Check for updates.
	* On server/workstation:
		* Install Git and Ansible from package manager.
		* Clone this git repository via `git clone git@github.com:coreysiegel/pi-ansible.git`
	* Run this Ansible package.

## Capabilities
 * None

## Future Capabilities
 * Vim
 * Minicom
 * MTR
 * Pat
 * Direwolf
 * Packet via external hardware TNC (minicom)
 * Packet via software TNC (direwolf)
 * Winlink via telnet (pat)
 * Winlink via packet (pat, hardware/software above)
 * Winlink via mesh (pat)
 * WSJT-X
 * Logging software
 * Various ICS forms (PDF, Word, Excel, HTML)
