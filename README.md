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
This will set it will set this information to all repositories from your computer.  
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

###Add files to stage area
`git add "path/to/file.html"` (Individual file)  
`git add .` (All files)"  

###Commit files in stage area
`git commit -m "A nice message about your commit"`

###Pull things to remote repo
`git pull`

###Pull things from remote repository and rebase your changes on top of it
`git pull --rebase`

###Push things to remote repo
`git push`

###See the history of changes
`git log`
`git log --oneline` (Show a small version of your log)  
`git log --graph` (Show a graphical representation of commits/branches)  
`git log --reverse` (Show a reverse log)  
`git log --since=yesterday` (Show only commits from yesterday and before)  
`git log --author "Name of someone"` (Show only commits from that person)  

###See details of a commit
`git show` (Show changes from the last commit)
`git show SHA` (Show changes from a specific commit)

##See differences in a commit
`git diff SHA`

###Revert to a previous commit
`git revert SHA`

