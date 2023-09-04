---
id: 6l4h865yzb2og94obefpdlb
title: wsl
desc: ''
updated: 1687549139248
created: 1687185783335
---
## Windows Subsystem for Linux Commands
https://www.windowscentral.com/how-install-wsl2-windows-10
``` powershell
wsl --install
wsl --shutdown
```
## Maintain
``` bash
sudo apt update && sudo apt upgrade 
```
### apt vs apt-get
- dpkg (Debian Package Manager) is low level app that performs installation of archive files (apps executables, man pages, libraries, &c)
- APT - Advanced Package Tool suite
- apt-get front end to dpkg suite of commands
- apt provides more accesssible and user-friendly CL tool; provides large subset of apt-get and provides commonly used features; suppresses obscure info apt-get displays
- apt and apt-get will retrieve files and try to assist w missing deps and conflicts

``` bash
install [pkgname]
remove [pkgname]
purge [pkgname]
update [pkgname]
upgrade ## updates all pkgs
autoremove ## removes libs and pkgs no longer required
```

## Ubuntu Upgrade 
References: https://blog.eldernode.com/upgrade-ubuntu-18-04-to-22-04/  

https://www.nextofwindows.com/how-to-upgrade-existing-wsl-wsl2-ubuntu-18-04-to-20-04

``` bash
## check existing lts v
lsb_release -a
## update system
sudo apt update
sudo apt list --upgradable
sudo apt upgrade
##
## remove reqd pkgs
sudo apt --purge autoremove
## install update-manager-core pkg
sudo apt install update-manager-core
## run Ubuntu upgrade util
sudo do-release-upgrade
```
### Journal
- Upgrade 18.04 to 20.04
- failed (exit 1):
``` bash
sudo apt remove --purge snapd  
[sudo apt-get remove screen snapd]  
## From <https://github.com/microsoft/WSL/discussions/3489#discussioncomment-961901
## run sudo do-release-upgrade
```

- Upgrade 20.04 to 22.04
refs: https://askubuntu.com/questions/1428423/upgrade-ubuntu-in-wsl2-from-20-04-to-22-04
```bash
sudo apt update && sudo apt full-upgrade
```

```powershell
wsl -l -v  #conform dist name
wsl --terminate Ubuntu
```

``` bash
sudo do-release-upgrade
```
### Problem 18-20 Upgrade
- terminal label not updated. 
- listed in bash, not powershell
- culprit is snapd ref: https://www.mzonline.com/blog/2022-04/place-upgrade-wsl-ubuntu-1804-2004
