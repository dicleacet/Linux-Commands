##########################
## Copying files using SCP and RSYNC
##########################
 
### SCP ###
# copying a local file to a remote destination
scp a.txt john@80.0.0.1:~
scp -P 2288 a.txt john@80.0.0.1:~       # using a custom port
 
# copying a local file from a remote destination to the current directory
scp -P 2290 john@80.0.0.1:~/a.txt .
 
# copying a local directory to a remote destination (-r)
scp -P 2290 -r projects/ john@80.0.0.1:~
 
 
### RSYNC ###
# synchronizing a directory
sudo rsync -av /etc/ ~/etc-backup/
 
# mirroring (deleting from destination the files that were deleting from source)
sudo rsync -av --delete /etc/ ~/etc-backup/
 
# excluding files
rsync -av --exclude-from='~/exclude.txt' source_directory/ destination_directory/
# exclude.txt:
# *.avi
# music/
# abc.mkv
 
rsync -av --exclude='*.mkv' --exclude='movie1.avi' source_directory/ destination_directory/
 
# synchronizing a directory over the network using SSH
sudo rsync -av -e ssh /etc/ student@192.168.0.108:~/etc-backup/ 
 
# using a custom port
sudo rsync -av -e 'ssh -p 2267' /etc/ student@192.168.0.108:~/etc-backup/ 
