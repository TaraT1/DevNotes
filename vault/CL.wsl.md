---
id: 6l4h865yzb2og94obefpdlb
title: wsl
desc: ''
updated: 1687186017105
created: 1687185783335
---

.Ubuntu Upgrade (18.04 to 20.04)
``` bash
## update system
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
## remove reqd pkgs
sudo apt autoremove
## install update-manager-core pkg
sudo apt install update-manager-core
## run Ubuntu upgrade util
sudo do-release-upgrade
```
### Problem
- terminal label not updated. 
- listed in bash, not powershell