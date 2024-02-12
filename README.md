# Proxmox-Cluster


# setup

## Bootstick
download de proxmox .iso image op een usb stick met balena etcher van https://www.proxmox.com/en/downloads

## install proxmox
https://www.youtube.com/watch?v=-OlzEmI0BP8

Volg de setup wizard van proxmox en zorg er voor dat proxmox goed werkt en goed opstart.

updata community repo
* go to the rpoxmox shell
* cd /etc/apt/sources.list.d/
* nano ceph.list
* comment out the exisitng lane
* ctrl + 0 & ctrl + x  //to write and exit
* nano pve-enterprise.list
* comment out the exisitng lane
* add; deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription
* ctrl + o & ctrl + x  //to write and exit
* apt update
* apt upgrade
* reboot

