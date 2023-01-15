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
    * Reboot when prompted.
    * Enable SSH from Menu, Preferences, Raspberry Pi Configuration, Interfaces, enable SSH
  * On server/workstation:
    * Install Git, Ansible, SSHPass from package manager via `sudo apt-get update && sudo apt-get install git ansible sshpass`
    * Clone this git repository via `git clone git@github.com:coreysiegel/pi-ansible.git`
		* Test connection to servers via `ansible all -i inventory -m ping`
  * Run this Ansible package.
	* Repeat for each Pi.
	  * Shut down Pi.
		* Swap SD card in Pi and boot.
		* Reset fingerprint with `ssh-keygen -f ~/.ssh/known_hosts -R <IP address>`.
		* Manually ssh to Pi to add fingerprint.
		* Test connection via ansible with `ansible all -m ping`
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
