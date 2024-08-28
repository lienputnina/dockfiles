# git commands

## General:

- `git status` - see the status of the repo (which branch you're on, what's the commit status. staging area etc.)

## Branches:

- `git switch -c <newBranch>` - create feature branch from main (or current) branch
- `git switch -c <newBranch> <old(parent) branch>` - create feature branch from feature branch
- `git switch <branch name>` - switch to a new branch

- `git push --set-upstream <remote> <branch>` - set the upstream branch
- `git switch master && git pull ` - get the latest from master
- `git rebase <master/parent> <myBranch>` - rebase one branch onto another
- `git pull origin master` - pull changes from the origin remote, master branch and merge them to the local checked-out branch
- `git merge master` - creates a merge commit, merges master into feat branch (:wq to leave the vim view, stash changes, git merge master again)
- `git reset --soft HEAD~1`- noņem manus commitus, bet atstāj manas izmaiņas failos (HEAD~1 - last commit)
- `git cherry-pick <commit hash number>` - take any commit from any branch anywhere in the past and put it above your own commits
- `git branch -m test-branch2` - renaming a local branch

## Commits

- `git stash` - stash the current changes to be used later
- `git stash --include-untracked -m "some message"`- stash everything, including the untracked (not-added) files
- `git diff --cached --name-only` -> check, which files will be added to a commit
- `git diff` - check, where the conflicts are
- `git reset` - undo staging commits (git add -A) -` git commit --amend -m` "Fix typo in README.md" => change the commit message for the latest, most recent commit
- `git commit --amend --no-edit`- pievieno staged izmaiņas iepriekšējam commitam, un-staged nebūs
- `git rebase -i HEAD~2` - interactive rebase that (in this case) goes back two commits. Options: swap commits, change commit messages etc.

### To change commit message for an older commit:

1. Find commit that you want, change `pick` to `reword`
2. Save and Exit
3. Change the commit message in the new editor
4. Save and Exit
5. Force push, if necessary

## Rebase

- `git rebase origin/master` - rebase from master - get the lates master state into feature branch
- `git rebase <master/parent> <myBranch>` - rebase one branch onto another
