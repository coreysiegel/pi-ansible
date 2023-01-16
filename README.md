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
    * Install Git, Ansible, SSHPass from package manager `sudo apt-get update && sudo apt-get install git ansible sshpass`
    * Clone this git repository `git clone git@github.com:coreysiegel/pi-ansible.git`
    * Reset fingerprint `ssh-keygen -f ~/.ssh/known_hosts -R <IP address>`
    * Manually ssh to Pi to add fingerprint `ssh username@<IP address>`
    * Test connection to servers `ansible all -m ping`
  * Run this Ansible package `ansible-playbook setup.yml`
  * Repeat for each Pi.
    * Shut down Pi.
    * Swap SD card in Pi and boot.
    * Reset fingerprint `ssh-keygen -f ~/.ssh/known_hosts -R <IP address>`
    * Manually ssh to Pi to add fingerprint `ssh username@<IP address>`
    * Test connection via ansible `ansible all -m ping`
    * Run this Ansible package `ansible-playbook setup.yml`


## Capabilities
 * Minicom
 * MTR

## Future Capabilities
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
