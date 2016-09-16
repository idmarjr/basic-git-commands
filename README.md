#Basic git commands

##Disclaimer
---
This document serve as a reference of git commands. Its organization follow a (kind of) logical order to help you to understand how git works from scratch, but notice that its just a *reference*. If you want to start from zero with git, I strongly recomend you to take a look in those links (In this order):

1. [Try Git Tutorial](http://try.github.io/);
2. [Git-it](https://github.com/jlord/git-it-electron#git-it-desktop-app);
3. The document that you're reading right now;
4. [Roger Dudler - Git Guide](http://rogerdudler.github.io/git-guide/);
5. [Bruno Passos - Git commands](https://github.com/bpassos/git-commands);

Now that you know it, feel free to go through this document. I hope it help! :sunglasses:  
  
  
##Your information
---
###View your info
`git config user.name` (See how your name is displayed in commits)  
`git config user.email` (See what is your email showed in commits)    

###Setup your info in a single repository
`git config user.name "Your name here"`  
`git config user.email "myemail@mydomain.com"`  

###Global setup
This will set information to all repositories from your computer.  
`git config --global user.name "Your name here"`  
`git config --global user.email "myemail@mydomain.com"`  

[[+] More info about `git config`](https://git-scm.com/docs/git-config)  

##Workflow commands
---
###Start a repo
`git init`  
[[+] More info about `git init`](https://git-scm.com/docs/git-init)  

###See repo's status
`git status`  
[[+] More info about `git status`](https://git-scm.com/docs/git-status)  

###Revert modified files
`git checkout "path/to/file.html"` (Individual file)  
`git checkout .` (All files)  
[[+] More info about `git checkout`](https://git-scm.com/docs/git-checkout)  

###Add changes to stage area
`git add "path/to/file.html"` (Individual file)  
`git add .` (All files)"  
[[+] More info about `git add`](https://git-scm.com/docs/git-add)  

###Remove changes from stage area (And keep it as untracked)
`git reset HEAD "path/to/file.html"` (Individual file)  
`git reset HEAD .` (All files)  

###Remove changes from stage area (And discard it)
`git reset --hard HEAD "path/to/file.html"` (Individual file)   
`git reset --hard HEAD .` (All files)  

###Revert master/branch to specific commit
`git reset --hard SHA`  
[[+] More info about `git reset`](https://git-scm.com/docs/git-reset)  

###Remove local untracked files (Files that are not under version control)
`git clean -f path/to/file` (individual files)  
`git clean -df` (All files)  
[[+] More info about clean](https://git-scm.com/docs/git-clean)

###Commit changes in stage area
`git commit -m "A nice message about your commit"`

###Modify local commit
`git commit --amend` (Modify just the message from last local commit)  

Add a new file to stage area and include it to last local commit:  
1. `git add path/to-file.html`  
2. `git commit --amend "A nice new message about your commit"`  

[[+] More info about `git add`](https://git-scm.com/docs/git-add)  
[[+] More info about `git commit`](https://git-scm.com/docs/git-commit)  


###Pull things to remote repo
`git pull`  
[[+] More info about `git pull`](https://git-scm.com/docs/git-pull)  

###Push things to remote repo
`git push`  
[[+] More info about `git push`](https://git-scm.com/docs/git-push)  

###See the history of changes
`git log`  
`git log --oneline` (Show a small version of your log)  
`git log --graph` (Show a graphical representation of commits/branches)  
`git log --reverse` (Show a reverse log)  
`git log --since=yesterday` (Show only commits from yesterday and before)  
`git log --author "Name of someone"` (Show only commits from that person) 

You can concatenate parameters:  
`git log --oneline --reverse --graph`  
[[+] More info about `git log`](https://git-scm.com/docs/git-log)  

###See details of a commit
`git show` (Show changes from the last commit)  
`git show SHA` (Show changes from a specific commit)  
[[+] More info about `git show`](https://git-scm.com/docs/git-show)  

###See modified files in your local working copy (If there are any)
`git diff`  
`git diff --stats` (Resumed status version)  

###See differences in a commit
`git diff SHA`  
[[+] More info about `git diff`](https://git-scm.com/docs/git-diff)  

###Revert changes of a specific commit
`git revert SHA` (Creating a new commit)  
`git revert -m SHA` (Not creating a new commit. Keep revert files unstaged)  
[[+] More info about `git revert`](https://git-scm.com/docs/git-revert)  

##Branches
---

###View list of local branches
`git branch`  
[[+] More info about `git branch`](https://git-scm.com/docs/git-branch)  

###Change to a different branch
`git checkout name-of-branch` (In this case the branch need to exist before checkout)  
`git checkout -b name-of-new-branch` (Create a new branch from the actual and checkout to it)   

###Publish branch to remote repository
`git push -u origin name-of-branch`

###Delete a branch
`git branch -d name-of-branch` (Delete local branch)  
`git push --delete origin name-of-branch` (Delete remote branch) 

##Merge branches
To merge a branch you need to checkout to the branch that will receive the merge:  
1. `git checkout name-of-branch-will-receive-merge`  
2. `git merge name-of-branch-to-be-merged`  

##Rebase
---

###Pull things from remote repository and rebase your changes on top of it
`git pull --rebase`

###Rebase master in to branch
You need to be in the branch:  
`git rebase master`  
[[+] More info about `git rebase`](https://git-scm.com/docs/git-rebase)  

###Rebase one branch in to another
You need to be in the branch that will receive the rebase  
`git rebase name-of-branch-to-be-rebased`  

###Rebase master in to branch and merge it to master
You need to be in the branch:  
1. `git rebase master`  
2. `git checkout master`  
3. `git merge name-of-branch`  
