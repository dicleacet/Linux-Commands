##########################
## WGET
##########################
# installing wget
apt install wget        # => Ubuntu
dnf install wget        # => CentOS
 
# download a file in the current directory
wget https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
 
# resuming the download 
wget -c https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
 
# saving the file into a specific directory
mkdir kali
wget -P kali/ https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
 
# limiting the rate (bandwidth)
wget --limit-rate=100k -P kali/ https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
 
# downloading more files 
wget -i urls.txt      # urls.txt contains urls
 
# starting the download in the background
wget -b -P kali/ https://cdimage.kali.org/kali-2020.2/kali-linux-2020.2-installer-amd64.iso
tail -f wget-log        # => checking its status
 
# getting an offline copy of a website
wget --mirror --convert-links --adjust-extension --page-requisites --no-parent http://example.org
wget -mkEpnp http://example.org
 
 
##########################
## NETSTAT and SS
##########################
# displaying all open ports and connections
sudo netstat -tupan
sudo ss -tupan
netstat -tupan | grep :80   # => checking if port 80 is open
 
##########################
## LSOF
##########################
# listing all files that are open
lsof
 
# listing all files opened by the processes of a specific user
lsof -u username
 
# listing all files opened by a specific process
lsof -c sshd
 
# listing all files that have opened TCP ports
lsof -iTCP -sTCP:LISTEN
lsof -iTCP -sTCP:LISTEN -nP
 
 
##########################
## Scanning hosts and networks using nmap
##########################
##** SCAN ONLY YOUR OWN HOSTS AND SERVERS !!! **##
## Scanning Networks is your own responsibility ##
 
# Syn Scan - Half Open Scanning (root only)
nmap -sS 192.168.0.1
 
# Connect Scan
nmap -sT 192.168.0.1
 
# Scanning all ports (0-65535)
nmap -p- 192.168.0.1
 
# Specifying the ports to scan
nmap -p 20,22-100,443,1000-2000 192.168.0.1
 
# Scan Version
nmap -p 22,80 -sV 192.168.0.1
 
# Ping scanning (entire Network)
nmap -sP 192.168.0.0/24
 
# Treat all hosts as online -- skip host discovery
nmap -Pn 192.168.0.0/24
 
# Excluding an IP
nmap -sS 192.168.0.0/24 --exclude 192.168.0.10
 
# Saving the scanning report to a file
nmap -oN output.txt 192.168.0.1
 
# OS Detection
nmap -O 192.168.0.1
 
# Enable OS detection, version detection, script scanning, and traceroute
nmap -A 192.168.0.1
 
# reading the targets from a file (ip/name/network separated by a new line or a whitespace)
nmap -p 80 -iL hosts.txt 
 
# exporting to out output file and disabling reverse DNS
nmap -n -iL hosts.txt -p 80 -oN output.txt
