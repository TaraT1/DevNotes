---
id: ezqnt41qecw5fj03xwrx37p
title: Git
desc: ''
updated: 1674788617922
created: 1653163066368
---
## Version control system (VCS) for tracking changes in computer files
- distributed version control
- coordinates work between devs
- records who made changes and when
- can revert 
- local & remote repos

## Concepts
- keeps track of code story
- snapshots of files making commits
- can visit snapshots
- can stage files before committing (add)

## Basic commits
```
$ git init //initialize local git repo creates spcl folder to hold snapshots (commits)
$ git add <file> //(also * and .) add file(s) to staging area
$ git status //check status of working tree, shows everything in staging area
$ git rm --cached <filename> //removes <file> from staging area
$ git commit //commit changes in index, adds everything in staging as snapshot to special folder
```

## Remote repo commands
```
git push //push to remote repo
git pull // pull latest from remote repo
git clone //clone repo into new dir
git fork //if no write privs, git fork to repo and then git clone to local machine
```

## Install
- debian sudo apt-get install git
- http://git-scm.com/download/win - use git and optional Linux tools from win cmd

## Config
- right click to get git bash
- git config --global user.name ' '
- git config --global user.email ' '

## gitignore
- ref: https://www.freecodecamp.org/news/gitignore-file-how-to-ignore-files-and-folders-in-git/
- files that should not be committed e.g. .env, OS files, config files, etc.
- best practice: create .gitignore w files to ignore when creating new repo before committing. Git can only ignore untracked files that haven't been committed to repo
- How to ignore previously committed file
    - update .gitignore to include file(s) & dir(s) to ignore
    - remove file from index with
    ``` git rm --cached <file>
        git rm -r --cached <dir> ``` for directories/folders.
    - cached option deletes file from repo but not the actual file. Omit cached if want to delete from repo & local system
    ``` git add .gitignore && git commit -m "update ignored files"
        git push
    ```

    


## Add Files to Git
```
git add <filename> . or *
git status - what's in staging area
```
## Remove files from git
```
// remove files from git repo and the filesystem
git rm file1.txt && git commit -m 'Remove file'
// remove file only from git repo and not from filesystem
git rm --cached file1.txt && git commit -m 'Remove file from repo and not filesystem'
//push changes to remote repo
git push origin branch_name
```
[Ref to delete file](https://stackoverflow.com/questions/2047465/how-do-i-delete-a-file-from-a-git-repository)

## Commit
```
git commit //goes to vim
git commit -m " " //incl msg w commit
```
- .gitignore - put filenames in .gitignore to remove them from git process

## Amend Commit
For those files that should have been in the last commit... After adding files, use 
```
git commit --amend --no-edit
```


## Branches
- Alternative to main codebase
```
git branch -M main //changes name of staging area to main
git branch <branchname> //create new branch
git checkout <branchname>
git merge <branchname> //from branch merge branch that is to be imported
```

## Remote Repo
- create new or sign in to github
- create repository
- From command line, 
```
$ git remote add origin https//github... 
$ git push -u origin main //for initial push, then git push after
$ git push //from cl
```
- will need to validate creds
- Others can clone repo with download or clone
``` 
git clone <url to repo > // copies entire repo into local repo

```
## 5 Essential Git Commands
```
git clone
git status - difference btwn local and remote 
git add / git add -A (git add all)
git commit -m " "
git push - pushes to remote
git pull - pulls down from remote
```
## Workflow
- git pull - integrate changes from others to local repo

## References
https://graphite.dev/guides/topic/git
https://graphite.dev/guides/how-to-remove-a-file-from-a-git-commit
