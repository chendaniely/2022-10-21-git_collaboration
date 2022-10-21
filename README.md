# 2022-10-21: Git Collaboration

## Exercise 1

1. Create a new repository on github
	- with a README.md + LICENCE + .gitigore
2. `clone` the repository to your computer
	- usually somewhere in `~/git`
3. In the `README.md` file define `git clone` and `git init`
4. `git add` and `git commit` your changes
5. `git push` your changes back up to your github repository

## Creating a local repository

- `git clone <URL>`: "downloads" the repository to current directory
	- `git init`: initializes the current directory as a git repository

## Branches

- `git branch <NAME>`: creates a branch <NAME> where HEAD is
- `git branch -a`: list all the branches you have
- `git switch <NAME>`: moves HEAD / switches you to the branch <NAME>
	- `git checkout <NAME>`: "older" command to switch branches

## Exercise 2

- create a branch `branch_defs`
- edit README
	- `git log --oneline --graph --all`
	- `git push`
	- pull request
- add/commit changes
- push branch
- create the PR
- merge the PR
- sync our local `main` with `orign/main`
- `fetch --prune`
- delete local branch

## Merging Branches

- `git log --oneline --graph --all`: show you a decorated history log, your best friend (along with `git status`)
- `git push <WHERE> <WHAT>`: `git push origin main` send branch `main` to remote `origin
	- `git pull <WHERE> <WHAT>`: similar to `push` but goes from remote to local computer

## Cleaning up branches + history

- `git fetch`: update the git log
	- `git fetch --prune`: remove any remote branches that have been deleted from the git log
- `git branch -d <NAME>`: delete the branch <NAME> (local)

- pull requests will auto update when you push changes to the branch

## Rebase

- `git fetch --prune`
- `git switch main`
- `git pull origin main`
- `git switch conflict_2`
- `git rebase main`

- `git rebase`: command to change history, we are useing it to fix conflict
	- `git rebase --abort`: go back to before you typed `git rebase`
