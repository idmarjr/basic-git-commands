#Basic git commands

##Your information
---
###See what's your name in commits
`git config user.name`

####Config your name to commits
`git config user.name "Your name here"`

###See what's your email in commits
`git config user.email`

####Config your email to commits
`git config user.email "myemail@mydomain.com"`

###Global config
This will set information to all repositories from your computer.  
`git config --global user.name "Your name here"`  
`git config --global user.email "myemail@mydomain.com"`  

##Workflow commands
---
###Start a repo
`git init`

###See repo's status
`git status`

###Revert modified files
`git checkout "path/to/file.html"` (Individual file)  
`git checkout .` (All files)  

###Add changes to stage area
`git add "path/to/file.html"` (Individual file)  
`git add .` (All files)"  

###Remove changes from stage area (And keep it as untracked)
`git reset HEAD "path/to/file.html"` (Individual file)   
`git reset HEAD .` (All files)  

###Remove changes from stage area (And discard it)
`git reset --hard HEAD "path/to/file.html"` (Individual file)   
`git reset --hard HEAD .` (All files)  


###Commit changes in stage area
`git commit -m "A nice message about your commit"`

###Pull things to remote repo
`git pull`

###Push things to remote repo
`git push`

###See the history of changes
`git log`  
`git log --oneline` (Show a small version of your log)  
`git log --graph` (Show a graphical representation of commits/branches)  
`git log --reverse` (Show a reverse log)  
`git log --since=yesterday` (Show only commits from yesterday and before)  
`git log --author "Name of someone"` (Show only commits from that person) 

You can concatenate parameters:  
`git log --oneline --reverse --graph`

###See details of a commit
`git show` (Show changes from the last commit)  
`git show SHA` (Show changes from a specific commit)

###See differences in a commit
`git diff SHA`

###Revert changes of a specific commit
`git revert SHA` (Creating a new commit)  
`git revert -m SHA` (Not creating a new commit. Keep revert files unstaged)  

##Branches

###View list of local branches
`git branch`  

###Change to a different branch
`git checkout name-of-branch` (In this case the branch need to exist before checkout)  
`git checkout -b name-of-new-branch` (Create a new branch from the actual and checkout to it)   

###Publish branch to remote repository
`git push -u origin name-of-branch`

##Merge branches
To merge a branch you need to checkout to the branch that will receive the merge:  
1. `git checkout branch-will-receive-merge`  
2. `git merge branch-to-be-merged`  

##Rebase

###Pull things from remote repository and rebase your changes on top of it
`git pull --rebase`

###Rebase from branch to master
You need to be in the branch:  
1. `git rebase maseter`  
2. `git checkout master`  
3. `git merge name-of-branch`  
