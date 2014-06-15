Essential-Git
=============

A collection of git command line commands which are really useful -- please fork!



## Command

for the bare minimum workflow (master branch only) refer first to staging, committing, and syncing in that order

Categories:

* staging
* checking
* committing
* syncing
* branching/merging
* logging
* *misc*
 
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

### Committing
