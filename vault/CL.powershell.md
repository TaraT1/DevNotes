---
id: 8qszpd34fgrgf0suh9uy487
title: powershell
desc: ''
updated: 1687201049755
created: 1686322911552
---
https://www.javatpoint.com/powershell-get-childitem  

# PowerShell 
`Get-ChildItem` gets items and child items in one or more locations. Location can be registry hive, file system registry, or certificate store  
- does not display empty dirs
- gci, dir, ls are aliases

## Syntax
```
//gets child items in current location; displays all file and subdir names. If no child items, returns no output
get-childitem

//get child item for given path. Lists mode, LastWriteTime, size, name
get-childitem -Path 'C:\dir'

//get name of child items in given loc
get-childitem -Path 'C:\dir' -Name

//get child items in current dir and subdirs
get-childitem -Recurse

```

### Operators
! (NOT)  
+ (AND)  
, (OR)  

### Abbreviations for common attributes
D (Directory)
H (Hidden)
R (Read-only)
S (System)

### WSL 
``` powershell
wsl --install
wsl --shutdown
```