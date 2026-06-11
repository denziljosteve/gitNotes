# Git Cheat Sheet

A quick reference guide for common Git commands and workflows.

## Repository Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git init` | Initialize a new Git repository locally. | `git init` |
| `git clone [url]` | Clone an existing repository from a remote server. | `git clone https://github.com/user/repo.git` |
| `git status` | Show the status of the working directory and staging area. | `git status` |
| `git add [file]` | Add a file to the staging area. | `git add index.html` |
| `git add .` | Add all modified and new files to the staging area. | `git add .` |
| `git commit -m "[msg]"`| Commit staged changes with a descriptive message. | `git commit -m "feat: add login page"` |
| `git commit -am "[msg]"`| Stage all tracked files and commit in one step. | `git commit -am "fix: resolve typo"` |

## Branch Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git branch` | List all local branches. | `git branch` |
| `git branch [branch]` | Create a new branch. | `git branch feature/auth` |
| `git checkout [branch]`| Switch to a specific branch. | `git checkout feature/auth` |
| `git checkout -b [branch]`| Create a new branch and switch to it immediately. | `git checkout -b bugfix/header` |
| `git switch [branch]` | Modern alternative to `git checkout` for switching branches. | `git switch main` |
| `git branch -d [branch]`| Delete a local branch safely (must be merged). | `git branch -d feature/auth` |
| `git branch -D [branch]`| Force delete a local branch. | `git branch -D feature/auth` |

## Merge & Rebase Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git merge [branch]` | Merge the specified branch into the current branch. | `git merge feature/auth` |
| `git merge --abort` | Abort a merge process in case of conflicts. | `git merge --abort` |
| `git rebase [branch]` | Rebase the current branch onto another branch. | `git rebase main` |
| `git rebase -i [commit]`| Start an interactive rebase for rewriting history. | `git rebase -i HEAD~3` |
| `git rebase --continue`| Continue the rebasing process after resolving conflicts.| `git rebase --continue` |
| `git rebase --abort` | Abort a rebase process. | `git rebase --abort` |

## Stash Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git stash` | Temporarily save uncommitted changes. | `git stash` |
| `git stash save "[msg]"`| Save changes with a descriptive message. | `git stash save "WIP: login form"` |
| `git stash list` | List all stashed changes. | `git stash list` |
| `git stash pop` | Apply the most recent stash and remove it from the list.| `git stash pop` |
| `git stash apply` | Apply the most recent stash but keep it in the list. | `git stash apply` |
| `git stash drop` | Remove the most recent stash from the list. | `git stash drop` |
| `git stash clear` | Remove all stashes. | `git stash clear` |

## Remote Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git remote -v` | List all configured remotes with their URLs. | `git remote -v` |
| `git remote add [name] [url]`| Add a new remote repository. | `git remote add origin https://...` |
| `git fetch [remote]` | Download objects and refs from the remote. | `git fetch origin` |
| `git pull` | Fetch from and integrate with another repository/branch.| `git pull origin main` |
| `git push [remote] [branch]`| Update remote refs along with associated objects. | `git push origin feature/auth` |
| `git push -u [remote] [branch]`| Push and set upstream tracking for the branch. | `git push -u origin feature/auth` |

## Recovery Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git restore [file]` | Discard changes in the working directory. | `git restore config.js` |
| `git restore --staged [file]`| Unstage a file (keep changes in working directory). | `git restore --staged config.js`|
| `git revert [commit]` | Create a new commit that undoes changes from a previous commit. | `git revert a1b2c3d` |
| `git reset --soft [commit]`| Move HEAD back, keeping staging and working directory intact. | `git reset --soft HEAD~1` |
| `git reset --mixed [commit]`| Move HEAD back, reset staging, keep working directory intact (default). | `git reset --mixed HEAD~1` |
| `git reset --hard [commit]`| Move HEAD back, discarding all changes in staging and working dir. | `git reset --hard HEAD~1` |
| `git reflog` | Show a log of all operations that updated HEAD. Useful for finding lost commits. | `git reflog` |

## Tag Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git tag` | List all tags. | `git tag` |
| `git tag [name]` | Create a lightweight tag. | `git tag v1.0.0` |
| `git tag -a [name] -m "[msg]"`| Create an annotated tag. | `git tag -a v1.0.0 -m "Release"` |
| `git push --tags` | Push all local tags to the remote repository. | `git push --tags` |

## Inspection Commands

| Command | Description | Example |
| :--- | :--- | :--- |
| `git log` | Show commit history. | `git log` |
| `git log --oneline` | Show commit history in a compact format. | `git log --oneline` |
| `git log --graph` | Show a text-based graph of the commit history. | `git log --graph` |
| `git diff` | Show changes between working directory and staging area.| `git diff` |
| `git diff --staged` | Show changes between staging area and last commit. | `git diff --staged` |
| `git show [commit]` | Show various types of objects (usually commit details).| `git show HEAD` |