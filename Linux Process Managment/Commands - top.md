##########################
## Dynamic Real-Time View of Processes(top)
##########################
 
# starting top
top
 
## top shortcuts while it's running
h       # => getting help
space   # => manual refresh
d       # => setting the refresh delay in seconds
q       # => quitting top
u       # => display processes of a user
m       # => changing the display for the memory
1       # => individual statistics for each CPU
x/y     # => highlighting the running process and the sorting column
b       # => toggle between bold and text highlighting
<       # => move the sorting column to the left
>       # => move the sorting column to the right
F       # => entering the Field Management screen 
W       # => saving top settings
 
# running top in batch mode (3 refreshes, 1 second delay)
top -d 1 -n 3 -b > top_processes.txt
 
# Interactive process viewer (top alternative)
sudo apt update && sudo apt install htop    # => Installing htop
htop
