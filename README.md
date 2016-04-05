# Disabling network manager

cf http://xmodulo.com/disable-network-manager-linux.html

## check network manager status

Check Which Network Interfaces are Managed by Network Manager:
```bash
    nmcli dev status
```
## debian (sysV init)

```bash
    sudo /etc/init.d/network-manager stop
    sudo update-rc.d network-manager remove 
```

## ubuntu (sysV init)

```bash
    sudo stop network-manager
    echo "manual" | sudo tee /etc/init/network-manager.override 
```

## fedora / debian jessie (systemd)

```bash
    sudo systemctl stop NetworkManager
    sudo systemctl disable NetworkManager
```

# Set network interface

## debian/ubuntu

edit /etc/network/interface

```
    # add nic interface dynamically
    iface eth0 inet dhcp
```

sudo service networking restart (not required)

## fedora

edit /etc/sysconfig/network-scripts/ifcfg-enps03

```
    # add nic interface dynamically
DEVICE=enps03
TYPE=Ethernet
BOOTPROTO=dhcp
ONBOOT=yes
USERCTL=yes
```

then enable network service

```bash
  systemctl enable netwok.service
  systemctl start network.service
```




