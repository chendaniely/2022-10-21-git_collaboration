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

Quick commands to setup conflict

```shell
git checkout -b conflict_branch_1
echo "Changes to b1 commit 1" >> README.md
git status
git add README.md
git commit -m "b1 c1"
echo "Changes to b1 commit 2" >> README.md
git add README.md
git commit -m "b1 c2"

git checkout main

git checkout -b conflict_branch_2
echo "Changes to b2 commit 1" >> README.md
git add README.md
git commit -m "b2 c1"
echo "Changes to b2 commit 2" >> README.md
git add README.md
git commit -m "b2 c2"

git push origin conflict_branch_2
git push origin conflict_branch_1
```

## Git Flow

- https://www.atlassian.com/git/tutorials/syncing
- https://www.atlassian.com/git/tutorials/comparing-workflows

A convention people use for branches to separate "main"/"production" form "development" code

## Extras

- Problem: I just want my files to be somewhere else (commit)
	- solutions: `git reset --hard <HASH>`
	- move HEAD and the branch you are on to whever you specifed <HASH>

- Problem: I want to enforce a branch workflow
	- solution: settings > branches > branch protection rule
	- Note: if you're on your own, un-check review from 1 person

- `git rebase -i HEAD~10`: do an interactive rebase with the last 10 commits
