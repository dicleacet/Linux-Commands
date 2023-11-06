##########################
## Getting System Hardware Information
##########################
 
# displaying full hardware information
lshw
lshw -short     # => short format
lshw -json      # => json format
lshw -html      # => html format
 
inxi -Fx
# displaying info about the CPU
lscpu
lshw -C cpu
lscpu -J    => json format
 
# displaying info about the installed RAM memory
dmidecode -t memory 
dmidecode -t memory | grep -i size
dmidecode -t memory | grep -i max
 
# displaying info about free/used memory
free -m
 
# getting info about pci buses and about the devices connected to them
lspci
lspci | grep -i wireless
lspci | grep -i vga
 
# getting info about USB controllers and about devices connected
lsusb
lsusb -v
 
# getting info about hard disks
lshw -short -C disk
fdisk -l
fdisk -l /dev/sda
lsblk
hdparm -i /dev/sda
hdparm -I /dev/sda
 
# benchmarking disk read performance
hdparm -tT --direct /dev/sda
 
# getting info about WiFi cards and networks
lshw -C network
iw list
iwconfig
iwlist wlo1 scan
 
# Getting hardware information from the /proc virtual fs
cat /proc/cpuinfo
/proc/partitions
cat /proc/meminfo
cat /proc/version
uname -r    # => kernel version
uname -a
 
acpi -bi    # battery information
acpi -V
 
## Working directly with device files (dd)
 
# backing up the MBR (the first sector of /dev/sda)
dd if=/dev/sda of=~/mbr.dat bs=512 count=1
 
# restoring the MBR
dd if=~/mbr.dat of=/dev/sda bs=512 count=1
 
# cloning a partition (sda1 to sdb2)
dd if=/dev/sda1 of=/dev/sdb2 bs=4M status=progress
