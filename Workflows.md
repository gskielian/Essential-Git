## Initializing a repo


comments included after # character
```sh
git init
git remote add origin http://your-github-repo-address.git
git pull origin master #in case there are any files already in the origin's git

git add -A :/ 
git commit -m "first commit"
git push origin master
```

## Feature-Branch Workflow

suppose you wanted to call your feature branch "new-feature" (replace this with any name)

create a branch for your new feature (generally one branch per new feature)
```
git checkout -b new-feature
```

Then loop the following:
```
git add -A :/
git commit
```

finally merge with master:
```
git checkout master
git merge new-feature
git branch -d new-feature #clean-up: the branch's changes have been merged
```

...and repeat from creation of new branch for another feature...


## Master Branch only:


init or clone

```
git clone http://someonesgithubrepo.git
```

then start editing it (cloning automatically makes their repo a remote-git aliased "origin"

```
git add -A :/ # or more specific staging option
git commit
```

and the occasional sync:

```
git push origin master
```
