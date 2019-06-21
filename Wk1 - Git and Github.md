# Git and Github

## 1. Clone the project

```
git clone <Github Clone url>
```

> WARNING: NEVER make any changes directly on the master branch. (Like peeing in the pool) Don't do it, make a new feature branch.

If you need to see what branch you are on you can get a list of branches, one with the star is the current one
```
git branch
```
use the `q` key 


## 2. Take an issue on github... create a branch for that issue.  

Make sure you have an issue assigned on github for what you are working on. Grab the issue number from github.

```
git checkout -b feature-3964-aaron-make-the-navbar
```
naming convention = type-number-name-description-of-problem


## 3. Make file changes

## 4. Save changes and push to github(origin) your branch name

```bash
git status

git add .

git commit -m "Updated Navbar"

# only on first time is -u needed
git push -u origin feature-3964-aaron-make-the-navbar
```

## 5. Open pull request on github

When opening the pull request don't forget in the description to write  
`closes #3964`  
The number should be the issue that was assigned.


## 6. Go back to master

before going back to master you have to clear any files you are working on.

> Have to wipe your feet clean before going back into the house

```bash
# -u means even the untracked files
git stash -u
```
You want to make sure working tree is clean first.

```
git checkout master
```

This will not have any changes. to get the latest changes.

```
git fetch
```

get the latest changes to your machine

```
git pull
```



> Be sure that at the end of the day you try to be on master so when you come in you will be on the master branch.
