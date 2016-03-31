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