##########################
## Software Management (dpkg and apt)
##########################
 
### DPKG ###
# getting info about a deb file
dpkg --info google-chrome-stable_current_amd64.deb
 
# installing an application from a deb file
sudo dpkg -i google-chrome-stable_current_amd64.deb
 
# list all installed programs
dpkg --get-selections
dpkg-query -l
 
# filtering the output
dpkg-query -l | grep ssh
 
# listing all files of an installed package
dpkg-query -l | grep ssh
dpkg -L openssh-server
 
# finding to which package a file belongs 
which ls
dpkg -S /bin/ls
    coreutils: /bin/cp
 
# removing a package
sudo dpkg -r google-chrome-stable
 
# purging a package
sudo dpkg -P google-chrome-stable
 
### APT ###
# updating the package index (doesn't install/uninstall/update any package)
sudo apt update
# installing or updating a package named apache2
sudo apt install apache2
 
# listing all upgradable packages
sudo apt list --upgradable
 
# upgrading all applications
sudo apt full-upgrade
sudo apt full-upgrade -y        # => assume yes to any prompt (useful in scripts)
 
# removing a package
sudo apt remove apache2
 
# removing a package and its configurations
sudo apt purge apache2
 
# removing dependencies that are not needed anymore
sudo apt autoremove
 
# removing the saved deb files from the cache directory (var/cache/apt/archives)
sudo apt clean
 
# listing all available packages
sudo apt list
sudo apt list | wc -l
 
# searching for a package
sudo apt list | grep nginx
 
# showing information about a package
sudo apt show nginx
 
# listing all installed packages
sudo apt list --installed
