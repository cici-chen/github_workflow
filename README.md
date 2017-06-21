# Github Workflow
A place for me to keep notes on how to use github

## General Concepts

### What is a commit anyway?
Saved changes are called commits.

### How does a merge conflict occur?
If two people made changes on the same line, for exmaple if one person wrote console.log('apple') and the other wrote console.log('banana') then github wouldn't know which version to use in the merged file. So in the file, it will look like
```
 <<<<<<< HEAD
 console.log('apple')
 ============
 console.log('banana')
 >>>>>>> [other/branch/name]".
```
Now to resolve the conflict, it's not necessarily an either or scenario. Just delete all the syntax things, and leave whatever you want the final version to be in this branch. It could be that you don't want either, and so on.

### No merge conflict != no probmen!!!
Why?

## Git error messages

### 

## Useful Tips

### When you're ready to push things up, to spare yourself from typing password a million times
From your local terminal, make sure you're in the repo:
`git config credential.helper 'cache --timeout=300'`
(300 seconds = 5 mins. 10800 seconds = 3 hours)
`git push`
`Username: <type your username>`
`Password: <type your password>`

[work for 5 more minutes]
$ git push http://example.com/repo.git
[your credentials are used automatically]
You can provide options via the credential.helper configuration variable (this example drops the cache time to 5 minutes):

$ git config credential.helper 'cache --timeout=300'

### To see the difference between branches
For local branches
```
git diff form master
```
Compare local form branch to remote form branch
```
git diff form origin/form
```

### After you fix a merge conflict
You need to add and commit for the merge to finish


## Scenarios

### Before I start pushing things up to a remote repo. 
In local terminal, `git config user.name` to check if user name is yours. If not, `git config user.name cici-chen` and `git config user.email blahbla@balh.com` (must set both!) to set correct username. Then `git config user.name` to double check.  

## Scenario: I have a project on github, and I want to keep working on my project from a computer.
> From your local computer's terminal
1. `git clone` to get repo on to your local computer
2. `cd` into the local folder
3. `git fetch` to see if there is any difference between this local version and the remote version
> Base branch is the branch that you're merging things into
4. If there is difference, and you don't want to just force merge the local and the remote, you can `git checkout -b refactor` to create a new local branch called refactor, and `git push origin refactor` to push that to remote github. Then go to github.com, and click on `new pull request`, select your refactor as the **base** (whoever is behind on commits is the base) and master as **compare**, to see the difference between master and rafactor branch, which is effectively the difference between the remote master branch and your local master branch. If you're happy with updating your local branch to be identical to remote branch, then you can `merge pull request` to make your remote refactor branch identical to master.
5. So now your remote refactor branch is up-to-date with your remote master branch, we're back on local terminal, and we want to pull the things from remote branches into local branches. On local master branch, `git pull origin master`. (To double check, you can perform `git fetch` to see if it is indeed up-to-date with remote master branch. Then checkout to local refactor branch, `git pull origin refactor`. 
6. Now I'm ready to work on my new refactor branch yay.

