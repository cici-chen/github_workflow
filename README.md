# Github Workflow
A place for me to keep notes on how to use github

## Styling this ReadMe file 
https://help.github.com/articles/basic-writing-and-formatting-syntax/

## Before I start pushing things up to a remote repo. 
In local terminal, `git config user.name` to check if user name is yours. If not, `git config user.name cici-chen` and `git config user.email blahbla@balh.com` (must set both!) to set correct username. Then `git config user.name` to double check.  

## When you're ready to push things up, to spare yourself from typing password a million times
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

## Scenario 1: I have a project on github, and I want to keep working on my project from a computer.
> From your local computer's terminal
1. `git clone` to get repo on to your local computer
2. `cd` into the local folder
3. `git fetch` to see if there is any difference between this local version and the remote version
> Base branch is the branch that you're merging things into
4. If there is difference, and you don't want to just force merge the local and the remote, you can `git checkout -b refactor` to create a new local branch called refactor, and `git push origin refactor` to push that to remote github. Then go to github.com, and click on `new pull request`, select your refactor as the **base** (whoever is behind on commits is the base) and master as **compare**, to see the difference between master and rafactor branch, which is effectively the difference between the remote master branch and your local master branch. If you're happy with updating your local branch to be identical to remote branch, then you can `merge pull request` to make your remote refactor branch identical to master.
5. So now your remote refactor branch is up-to-date with your remote master branch, we're back on local terminal, and we want to pull the things from remote branches into local branches. On local master branch, `git pull origin master`. (To double check, you can perform `git fetch` to see if it is indeed up-to-date with remote master branch. Then checkout to local refactor branch, `git pull origin refactor`. 
6. Now I'm ready to work on my new refactor branch yay.

### To see the difference between branches
For local branches
```
git diff form master
```
Compare local form branch to remote form branch
```
git diff form origin/form
```
