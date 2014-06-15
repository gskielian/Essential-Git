Essential-Git
=============

A collection of git command line commands which are really useful -- please fork!



## Command

Categories:

* staging
* checking
* committing
* syncing
* logging
* *misc*
 
### Staging

* `git add -A` stages everything and subdirectories (new, modded, and deleted)
* `git add -A :/` like above, but stages *everything*: starts from git's root directory and then goes to subdirectories
* `git add .`  stages new files and modified, not those deleted
* `git add -u` stages removed files and file modifications, without adding new files (useful when you want to specify commit)


### Checking

* `git status`
