##########################
## Killing processes (kill, pkill, killall)
##########################
 
# listing all signals
kill -l
 
# sending a signal (default SIGTERM - 15) to a process by pid 
kill pid        # => Ex: kill 12547
 
# sending a signal to more processes
kill -SIGNAL pid1 pid2 pid3 ...
 
# sending a specific signal (SIGHUP - 1) to a process by pid
kill -1 pid
kill -HUP pid
kill -SIGHUP pid
 
# sending a signal (default SIGTERM - 15) to process by process name
pkill process_name          # => Ex: pkill sleep
killall process_name
kill $(pidof process_name)  # => Ex: kill -HUP $(pidof sshd)
 
# running a process in the background
command &   # => Ex: sleep 100 &
 
# Showing running jobs
jobs
 
# Stopping (pausing) the running process
Ctrl + Z
 
# resuming and bringing to the foreground a process by job_d
fg %job_id
 
# resuming in the background a process by job_d
bg %job_id
 
# starting a process immune to SIGHUP
nohup command &     # => Ex: nohup wget http://site.com &
