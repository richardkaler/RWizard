#!/bin/bash


# "When you set up a virtual environment, the directory it lives in isn’t meant to hold anything but the virtual environment itself. 
# Your project belongs in its own separate directory tree. 
# There are many good reasons for this."  SOURCE: https://www.infoworld.com/article/3306656/python-virtualenv-and-venv-dos-and-donts.html

echo -e "---------------------------------------------------------------------------------------------------" >> ~/tmp/venvlog.txt
date >> ~/tmp/venvlog.txt
echo -e "---------------------------------------------------------------------------------------------------" >> ~/tmp/venvlog.txt

shopt -s expand_aliases 
shopt -s cdable_vars  
shopt -s autocd 
shopt -s checkjobs  

echo "You are using $0. Or else - something is terribly wrong!"

if [ ! -f "$1"  ]; then 
    set -e 
    mkdir "$1" 
    echo -e "project named $1 created"     
    pushd "$1"
    #APPLICATION_PATH=$1
    #cd "${APPLICATION_PATH}"
    echo -e "descending into directory "
    echo -e "...Making changes in $1"  
    python3 -m venv env
    echo -e "Your venv has been created" 
    env/bin/python -m pip install --upgrade pip setuptools wheel | tee -a ~/tmp/venvlog.txt
    echo -e "pip has been both installed and upgraded"
    echo -e "...Finished creating venv in $1"
    #echo -e "Type 'source $1/env/bin/activate' to activate your venv and type deactivate when you are finished"  
    #echo -e "When you are finished and need to leave your virtual environment, simply type 'deactivate'"
    echo "You need to source the following location: $1/env/bin/activate"
elif   [ -f "$1" ]; then 
    echo -e "There is already a file named '$1' at the location you specified.\nPlease enter a new name for your virtual environment or choose a different location where the file does not already exist"
#    echo -e "Enter a valid directory path or..."
#    echo -e "Type 'venv <directoryPath>' to create a Python Virtual Environment in the directory of your choice." 		
#    echo -e "virtual environment can be activated using source $1/env/bin/activate. If you want to activate it now, type yes"
fi
    read -r -p "Do you want to source your virtual environment. Please type yes or no: " ans
if [ "$ans" = "yes" ]; then 
    echo -e "---------------------------------------------------------------------------------------------------"
    #echo -e "check /home/tmp/venvlog.txt for results"
    echo -e "STEP: 1) Copy and paste the following: source $1/env/bin/activate " 
    echo -e "STEP: 2) When you are finished and need to leave your virtual environment, simply type 'deactivate'"
    echo -e "A log for this program can be found in $HOME/tmp/venvlog.txt"
    echo -e "---------------------------------------------------------------------------------------------------"
    echo -e "---------------------------------------------------------------------------------------------------" >> ~/tmp/venvlog.txt
    now=$(date); printf "%s\n" "$now"  >> ~/tmp/venvlog.txt
    echo -e "---------------------------------------------------------------------------------------------------" >> ~/tmp/venvlog.txt
    #now=$(date)
exit 0
else   
#    read -r -p -r -p "Copy and paste the following: source $1/env/bin/activate " choice 
#if [ "$choice" = "$1/env/bin/activate" ]; then      
#    echo -e "Your virtual environment should now be active"
#    pip -V
#    echo -e "You can check for the status by reading the output above. Note any changes to the left in your CLI environment"

    echo -e "Uh oh - Looks like there's a problem."
fi     
$$
