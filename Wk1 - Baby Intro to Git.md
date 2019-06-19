# Baby Intro to Git

> WARNING: Before typing anything make sure you are in the correct folder.

## status 
Status will return what files have changed and what changes have been saved already.

```
git status
```

## commit 
Saves file changes to the local repository.  
- `-m` argument can be used to add a message to the commit

```bash
git commit -m "My what big changes you have made"
``` 

## remote 

Remote helps you manage multiple repositories to track. A remote is a repo that lives somewhere other than on local computer.

```bash
# return list of all remotes
git remote -v
# add a remote repo
git remote add http://github.com/example/repo
```
## push 

Add changes to a remote repository. This will push the changes upstream.

```bash
# set origin master as default tracking for local master
git push -u origin master
# now it will default to origin master
git push
```