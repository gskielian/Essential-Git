Essential-Git
=============

A collection of git command line commands which are really useful -- please fork!



## Command

for the bare minimum workflow (master branch only) refer first to staging, committing, and syncing in that order

Categories:

* initialize
* staging
* checking
* committing
* syncing
* branching/merging
* *misc*
 

### Initialize

* `git init`
* `git init mydirectory` replace mydirectory with the directory you want to start tracking changes.

### Staging

* `git add -A` stages everything and subdirectories (new, modded, and deleted)
* `git add -A :/` like above, but stages *everything*: starts from git's root directory and then goes to subdirectories
* `git add .`  stages new files and modified, not those deleted
* `git add -u` stages removed files and file modifications, without adding new files (useful when you want to specify commit)

Hybrid Commands:
* `git commit -a` stages and adds all tracked files (onlt files which have been added at least once)

### Checking

* `git status` -- shows untracked files, files to be committed, and current branch
* `git diff --cached` shows changes between previous commit and current stage.
* `git diff HEAD~ HEAD` -- shows differences between last commit and this commit
* `git diff HEAD~2 HEAD` -- shows differences between two commits ago and this commit
* `git diff HEAD~10 HEAD` -- shows differences between 10 commits ago and this commit, etc.

For checking log of changes:

*in order from less info to more detailed info*

* `git log --oneline` simply commit abbreviation, and commit message
* `git log --graph --oneline` -- shows commit abbreviation and branching info
* `git log -2`  last two commits (change -2 to -4 for last 4 commits): commit id, author of commit, date of commit, and commit message
* `git log -p -3` same as git log, plus actual commit changes, navigation via `j` and `k` (like unix `less` interface)

*UltiLog: may want to alias this one:*

* `git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''          %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all` -- shout out to Slipp D. Thompson for this gem [link to source](http://stackoverflow.com/questions/1057564/pretty-git-branch-graphs)

### Committing

* `git commit` -- simply commits, bringing you to either nano, vim, or some text editor to create your commit message.
* `git commit -m "added stuff" ` commits without bringing to an editor, replace "added stuff" with your commit message.
* `git commit -a` stages all modifications (mods only, no new files) and commits

### Syncing

* `git remote add origin place_your_git_url_here` -- you can now sync with the `git` associated with this url (push, pull, fetch, merge, and stuff) replace `origin` with another name to call it something different: example `git remote add otherserver http://somegit.git` allows you to sync with http://somegit.git through the alias `otherserver` -- see next line for additional example.
* `git push origin master` -- tries to update the "origin"'s git master with your changes.  Another example `git push otherserver master` attempts to update the "otherserver"'s git with your modifications.
* `git pull origin master` -- if the git at the remote called "origin" is 











### Committing
