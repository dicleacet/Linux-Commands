##########################
## Process Viewing (ps, pstree, pgrep)
##########################
# checking if a command is shell built-in or executable file
type rm        # => rm is /usr/bin/rm
type cd        # => cd is a shell built-in
 
# displaying all processes started in the current terminal
ps
 
# displaying all processes running in the system
ps -ef 
ps aux
ps aux | less       # => piping to less
 
# sorting by memory and piping to less
ps aux --sort=%mem | less
 
# ASCII art process tree
ps -ef --forest
 
# displaying all processes of a specific user
ps -f -u username
 
# checking if a process called sshd is running
pgrep -l sshd
ps -ef | grep sshd
 
#displaying a hierarchical tree structure of all running processes
pstree
 
# prevent merging identical branches
pstree -c
