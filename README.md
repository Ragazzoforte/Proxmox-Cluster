# Proxmox-Cluster


# setup

## Bootstick
download de proxmox .iso image op een usb stick met balena etcher van https://www.proxmox.com/en/downloads

## install proxmox
https://www.youtube.com/watch?v=-OlzEmI0BP8

* Volg de setup wizard van proxmox en zorg er voor dat proxmox goed werkt en goed opstart.

* update community repo
```c
// go to proxmox shell
cd /etc/apt/sources.list.d/
nano ceph.list
//comment out the exisitng lane
nano pve-enterprise.list
// comment out the exisitng lane and add; deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription
apt update
apt upgrade
reboot
```
