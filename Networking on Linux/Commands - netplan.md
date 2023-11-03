##########################
## Network Static configuration using Netplan (Ubuntu)
##########################
 
# 1. Stop and disable the Network Manager
 
sudo systemctl stop NetworkManager
sudo systemctl disable NetworkManager
sudo systemctl status NetworkManager
sudo systemctl is-enabled NetworkManager
 
# 2. Create a YAML file in /etc/netplan
 
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
      dhcp4: false
      addresses:
        - 192.168.0.20/24
      gateway4: "192.168.0.1"
      nameservers:
        addresses:
          - "8.8.8.8"
          - "8.8.4.4"
 
# 3. Apply the new config
sudo netplan apply
 
# 4. Check the configuration
ifconfig
route -a
