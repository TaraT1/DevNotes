---
id: w8jr0z42lc1uucseit8e4o0
title: Cmd
desc: ''
updated: 1686272787069
created: 1686271123035
---
# Windows Command Line Commands
```
//lists items in dir
dir

// shows tree of current dir or drive
tree

// creates folder
mkdir

//move file or folder to specified folder
move

// delete file
del

//rename file w syntax
ren [filename.ext new-name.ext]

//deletes folder (must be empty)
rmdir

//Run command prompt as admin
powershell start cmd -v runAs

//Change current working dir
chdir  
cd  

//Shows PC details
systeminfo

//shows PCs env vars
set

//copies item to clipboard
clip
dir | clip //copies content of present working dir to clipboard

// wipes free space and encrypts data
cipher

//shows open ports ip addresses and states
netstat -an

//shows website ip address and how long transmit data and get response
ping

//shows info about pc ip addresses and connections
ipconfig

//system file checker
sfc

//Configure power settings
powercfg
powercfg help

// logs on to website from command line
start [website-address]

//shows version of os
ver

//shows open programs
tasklist

//terminate running task
taskkill

// stops execution of a command
Ctrl +C

// provides guide to other commands
-help

//shows custom msgs or msgs from script or file
echo

//clears command line
cls

//closes command line
exit

//shuts down, restarts, hibernates, sleeps computer
shutdown
//restart computer
shutdown /r

```