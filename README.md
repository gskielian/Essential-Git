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

this just starts the git, only got to do this once.

* `git init` after typing this, you can begin *gitting* in your current directory
* `git init yourfolderhere` you can begin *gitting* in *yourfolderhere*.

Congrats! Now you can git, add the files you want to keep track of (goto staging -> committing)

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

Only need to do this once for each git url (I call these remote-gits -- because they are usually somewhere far away):
* `git remote add origin place_your_git_url_here` -- you can now sync with the `git` associated with this url (push, pull, fetch, merge, and stuff) replace `origin` with another name to call it something different: example `git remote add otherserver http://somegit.git` allows you to sync with http://somegit.git through the alias `otherserver` -- see next line for additional example.

Update a remote-git:
* `git push origin master` -- tries to update the "origin"'s git master with your changes.  Another example `git push otherserver master` attempts to update the "otherserver"'s git with your modifications.

Update your local-git from a remote-git:
* `git pull origin master` -- if the git at the remote called "origin" has changes you don't have, use this to get yours up to date.

Merge Conflicts -- if you have updates and the remote-git has updates to the same file, you must figure stuff out manually.
Do a pull, and comb through the files to choose who's update (local or remote) you want to keep.


### Branching/Merging

Branching makes a copy of your code that you can mess around with it while leaving your stable code alone. (this is the way I use branches)

List all branches
* `git branch` shows the branch you are currently on is starred with a *, also shows other branches any.

How to make a branch:
* `git branch some_feature` this command creates a branch called "some_feature"

How to move to another branch:
* `git checkout some_feature` allows you to "check out" and see that branch (in this case you are checking out some_feature).

Hybrid Command:
* `git checkout -b a_new_branch` very useful: creates the new branch and switches to it.


Merging -- suppose your changes are debugged and ready to become live, merge your changes back into the master (aka stabble) branch:

The following commands do the job
```sh
git checkout master
git merge some_feature
```
Tada! you may want to delete the remnants of your feature-branch now that you're done with it:
* `git branch -d some_feature`

### Summary

These are the basic commands which I use on the daily.

For workflows see the `Workflow.md` which is coming soon...

(starring this repo will make that file happen create itself faster).
