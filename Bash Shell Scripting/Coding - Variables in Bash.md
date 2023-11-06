##########################
## Bash Variables
##########################
 
# defining a variable: variable_name=value
# variable names should start with a letter or underscore and can contain letters, digits and underscore
os="Kali Linux"
version=10
 
# referencing the value of a variable (getting the variable value): $variable_name
echo $os
echo $version
 
# defining a read-only variable (constant)
declare -r temperature=100
 
# removing (unsetting) a variable
unset version
 
# listing all environment variables
env
printenv
 
# searching for an environment variable
printenv PATH
env | grep -i path
 
# creating new environment variables for the user: in ~/.bashrc add export MYVAR=”value” 
export IP="80.0.0.1"
 
# changing the PATH
export PATH=$PATH:~/scripts     # in ~/.bashrc
 
# getting user input
read MY_VAR
echo $MY_VAR
 
# displaying a message
read -p "Enter the IP address: " ip
ping -c 1 $ip
 
read -s -p "Enter password:" pswd
echo $pswd
 
 
### SPECIAL VARIABLES AND POSITIONAL ARGUMENTS ###
./script.sh filename1 dir1
 
$0 => the name of the script itself (script.sh)
$1 => the first positional argument (filename1)
$2 => the second positional argument (dir1)
...
${10} => the tenth argument of the script
${11} => the eleventh argument of the script
 
$# => the number of the positional arguments
"$*" => string representation of all positional argument
$? => the most recent foreground command exit status
