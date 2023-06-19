---
id: h9dogpny8harxizc09cpop1
title: linux-unix
desc: ''
updated: 1687185209970
created: 1686326284010
---
https://www.tutorialspoint.com/unix/index.htm

# Unix
Unix OS is a set of programs that act as link btwn computer and user. 
- operating system or kernel - computer programs that allocate system resources and coordinate all the details of computer's inernals
- shell - how users communicate with the kernel; CL interpreter; translates commands entered by user and converts them into language understood by kernel
- Unix variants Solaris Unix, AIX, HP Unix, BSD aso include Linux
- Unix is multi-user and multi-tasking

## Unix Architecture
- kernel - heart of os; interacts w hdwr and most tasks like memory mgt, task scheduling, and file mgt
- shell processes requests from terminal; interprets command and calls program. Uses std syntax. C Shell, Bourne Shell, Korn Shell
- commands & utils: cp, mv, cat, grep, etc
- files & dirs
    - files
    - dirs
    - filesystem - tree-like structure

## Commands
- Listing Dirs and Files
    - `ls -l` - list long - d: dir
- `whoami`
- who is loged in
    - `users`
    - `who` - detail
    - `w` - lists info associated w users logged in the system
- `logout`
- system shutdown
    - `halt` - brings system down immediately
    - `init 0` - powers off syst using predefined scripts
    - `init 6` - reboots system
    - `poweroff`
    - `reboot`
    - `shutdown`

## File Mgt
### 3 basic files types
- ordinary - text, data, prgm instructions
- dirs - equivalent to folders, store both ordinary and special files
- special files 
    - provide access to hdwr
    - aliases or shortcuts
    
### Column Info of ls -l
1. file type and permissions
    - \- regular file
    - b - block special i/o file
    - c - char special raw i/o device file
    - d - dir file
    - l - symbolic link file
    - p - named pipe - mechanism for interprocess communications
    - s - socket used for interprocess comm
2. number of memory blocks used by file or dir
3. file owner
4. owner's group
5. file size in bytes
6. date and time file created or modified
7. file or dir name

### Metacharacters
- * match 0+ characters
- ? match single char

### Hidden files
- begin with .
- `ls -a` displays hidden 

### Dir
- . - current dir
- .. - parent dir

### Create Files
- use vi, i etc
- ZZ to exit

### Display File Content
- cat <filename>
- `wc <filename>` count words in file
    1. total # of lines
    2. total # of words
    3. bytes
    4. file name
    
### copy, rename, delete files
```
//copy
cp <source> <destination>

//rename
mv <old> <new>

//delete
rm <filename> <file2> <file3>

## Standard Unix Streams (Files) of Unix Programs
- stdin - standard input; file descriptor: 0; STDIN
- stdout - standard output; file descriptor: 1; STDOUT
- stderr - standard error; file descriptor: 2; STDERR
