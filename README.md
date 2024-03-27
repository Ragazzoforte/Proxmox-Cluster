# Proxmox-Cluster


# setup

## Bootstick
download de proxmox .iso image op een usb stick met balena etcher van https://www.proxmox.com/en/downloads

## install proxmox

* Volg de setup wizard van proxmox en zorg er voor dat proxmox goed werkt en goed opstart.
  https://www.youtube.com/watch?v=-OlzEmI0BP8

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

* make a proxmox cluster
  https://www.youtube.com/watch?v=Mz-nXlqovLI&t=69s
  * make drives ready for ceph osd
    ```c
    // go to proxmox shell
    lsblk
    fdsik /dev/sdb
    d
    w
    lsblk
    ```

Resize lxc disk size. first stop the container then type in the shell of the node : pct resize "container number (101)" rootfs "new disksize(20G)"


## install nginx proxy manager
youtube tutorial; https://www.youtube.com/watch?v=1doM_9pijBM&t=97s 

proxmox scripts; https://tteck.github.io/Proxmox/ 

nginx ssl with cloudflare tutorial; https://www.youtube.com/watch?v=GarMdDTAZJo&t=694s

## install guacamole
youtube tutorial; https://www.youtube.com/watch?v=cugExjVmQT4

guacamole url; https://www.youtube.com/watch?v=xHnJKLppchs

## install Nextcloud
youtube tutorial; https://www.youtube.com/watch?v=00FUdmOLh0A&t=210s

onlyoffice youtube tutorial; https://www.youtube.com/watch?v=g8xXfOifyEE

## install Home Assistant
proxmox scripts; https://tteck.github.io/Proxmox/ 

bash -c "$(wget -qLO - https://github.com/tteck/Proxmox/raw/main/vm/haos-vm.sh)"

## install Wordpress
proxmox scripts; https://tteck.github.io/Proxmox/ 

bash -c "$(wget -qLO - https://github.com/tteck/Proxmox/raw/main/turnkey/turnkey.sh)"


# Docker swarm

## setup
make a bootable usb stcik for ubunutu and install it on each node

install docker engine: https://docs.docker.com/engine/install/ubuntu/

## nodes

### server1
ip: 192.168.178.71

sudo docker swarm init --advertise-addr 192.168.178.71
Swarm initialized: current node (oini5aeh4hro0702g7xw0p7lr) is now a manager.

To add a worker to this swarm, run the following command:

    sudo docker swarm join --token SWMTKN-1-06h773rj7dy26lq7pxuk8ysl3dejt4g98iqi7q7b36qd2zvzf0-9evuo5fse6xmzo3berigv4ctt 192.168.178.71:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

### server3
ip: 192.168.178.81

### server4
ip: 192.168.178.70

### server5
ip: 192.168.178.95
