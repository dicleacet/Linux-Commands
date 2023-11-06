##########################
## Service Management using systemd and systemctl
##########################
# showing info about the boot process
systemd-analyze
systemd-analyze blame
 
# listing all active units systemd knows about
systemctl list-units
systemctl list-units | grep ssh
 
# checking the status of a service
sudo systemctl status nginx.service
 
# stopping a service
sudo systemctl stop nginx
 
# starting a service
sudo systemctl start nginx
 
# restarting a service
sudo systemctl restart nginx
 
# reloading the configuration of a service
sudo systemctl reload nginx
sudo systemctl reload-or-restart nginx
 
# enabling to start at boot time
sudo systemctl enable nginx
 
# disabling at boot time
sudo systemctl disable nginx
 
# checking if it starts automatically at boot time
sudo systemctl is-enabled nginx
 
# masking a service (stopping and disabling it)
sudo systemctl mask nginx
 
# unmasking a service
sudo systemctl unmask nginx
