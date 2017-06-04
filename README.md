# github_workflow
A place for me to keep notes on how to use github

## Styling this ReadMe file https://help.github.com/articles/basic-writing-and-formatting-syntax/

## Scenario 1: I have a project on github, and I want to keep working on my project from a computer.
> From your local computer's terminal
1. `git clone` to get repo on to your local computer
2. `cd` into the local folder
3. `git fetch` to see if there is any difference between this local version and the remote version
4. If there is difference, and you don't want to just force merge the local and the remote, you can `git checkout -b refactor` to create a new local branch called refactor, and `git push origin refactor` to push that to remote github. Then go to github.com, and click on `new pull request`, select your refactor as the **base** (whoever is behind on commits is the base) and master as **compare**, to see the difference between master and rafactor branch, which is effectively the difference between the remote master branch and your local master branch. If you're happy with updating your local branch to be identical to remote branch, then you can `merge pull request` to make your remote refactor branch identical to master.
5. So now your remote refactor branch is up-to-date with your remote master branch, we're back on local terminal, and we want to pull the things from remote branches into local branches. On local master branch, `git pull origin master`. (To double check, you can perform `git fetch` to see if it is indeed up-to-date with remote master branch. Then checkout to local refactor branch, `git pull origin refactor`. 
6. Now I'm ready to work on my new refactor branch yay.
