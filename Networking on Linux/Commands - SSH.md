##########################
## OpenSSH
##########################
 
# 1. Installing OpenSSH (client and server)
# Ubuntu
sudo apt update && sudo apt install openssh-server openssh-client
 
# CentOS
sudo dnf install openssh-server openssh-clients
 
# connecting to the server
ssh -p 22 username@server_ip        # => Ex: ssh -p 2267 john@192.168.0.100
ssh -p 22 -l username server_ip
ssh -v -p 22 username@server_ip     # => verbose
 
# 2. Controlling the SSHd daemon
# checking its status
sudo systemctl status ssh       # => Ubuntu
sudo systemctl status sshd      # => CentOS
 
# stopping the daemon
sudo systemctl stop ssh       # => Ubuntu
sudo systemctl stop sshd      # => CentOS
 
# restarting the daemon
sudo systemctl restart ssh       # => Ubuntu
sudo systemctl restart sshd      # => CentOS
 
# enabling at boot time 
sudo systemctl enable ssh       # => Ubuntu
sudo systemctl enable sshd      # => CentOS
 
sudo systemctl is-enabled ssh       # => Ubuntu
sudo systemctl is-enabled sshd      # => CentOS
 
# 3. Securing the SSHd daemon
# change the configuration file (/etc/ssh/sshd_config) and then restart the server
man sshd_config
 
a) Change the port
Port 2278
 
b) Disable direct root login
PermitRootLogin no
 
c) Limit Users’ SSH access
AllowUsers stud u1 u2 john
 
d) Filter SSH access at the firewall level (iptables)
 
e) Activate Public Key Authentication and Disable Password Authentication
 
f) Use only SSH Protocol version 2
 
g) Other configurations:
ClientAliveInterval 300
ClientAliveCountMax 0
MaxAuthTries 2
MaxStartUps 3
LoginGraceTime 20
