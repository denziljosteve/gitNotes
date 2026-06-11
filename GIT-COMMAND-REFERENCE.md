# Git Command Reference

This is an exhaustive Git command reference designed to help you quickly understand the purpose, syntax, and examples for commands across all skill levels.

---

## Beginner Commands

### `git init`
- **Purpose:** Initialize a new, empty Git repository.
- **Syntax:** `git init [directory]`
- **Common Examples:**
  - `git init`: Initializes in the current directory.
  - `git init my-project`: Creates a new directory and initializes it.
- **Notes:** Running `git init` creates a hidden `.git` folder where Git stores all internal tracking data.

### `git clone`
- **Purpose:** Create a local copy of a remote repository.
- **Syntax:** `git clone <repo-url> [directory]`
- **Common Examples:**
  - `git clone https://github.com/user/repo.git`
  - `git clone git@github.com:user/repo.git my-folder`
- **Notes:** Automatically sets up a remote named `origin` pointing back to the cloned repository.

### `git status`
- **Purpose:** Display the state of the working directory and the staging area.
- **Syntax:** `git status`
- **Common Examples:** `git status`
- **Notes:** Does not show any commit history. Use this command frequently to understand what Git sees.

### `git add`
- **Purpose:** Add file contents to the staging area.
- **Syntax:** `git add <file|directory|pattern>`
- **Common Examples:**
  - `git add index.html`
  - `git add src/`
  - `git add .` (Stages all changes)
- **Notes:** This command tells Git to track updates to files before committing.

### `git commit`
- **Purpose:** Record changes to the repository.
- **Syntax:** `git commit [-m <message>] [-a]`
- **Common Examples:**
  - `git commit -m "feat: add user login"`
  - `git commit -am "fix: resolve typo"` (Stages tracked files and commits)
- **Notes:** Always write clear, semantic commit messages.

### `git push`
- **Purpose:** Update remote refs along with associated objects.
- **Syntax:** `git push [<remote>] [<branch>]`
- **Common Examples:**
  - `git push origin main`
  - `git push -u origin feature-branch`
- **Notes:** Use `-u` (or `--set-upstream`) to track the branch so future pushes can just be `git push`.

### `git pull`
- **Purpose:** Fetch from and integrate with another repository or a local branch.
- **Syntax:** `git pull [<remote>] [<branch>]`
- **Common Examples:** `git pull origin main`
- **Notes:** `git pull` is effectively a combination of `git fetch` and `git merge`.

---

## Intermediate Commands

### `git branch`
- **Purpose:** List, create, or delete branches.
- **Syntax:** `git branch [--list] | <branch-name> | [-d <branch-name>]`
- **Common Examples:**
  - `git branch` (Lists local branches)
  - `git branch new-feature` (Creates branch but does not switch)
  - `git branch -d old-feature` (Deletes merged branch)
- **Notes:** Use `-D` to force-delete an unmerged branch.

### `git checkout` / `git switch`
- **Purpose:** Switch branches or restore working tree files.
- **Syntax:** `git checkout <branch>` or `git switch <branch>`
- **Common Examples:**
  - `git checkout main`
  - `git switch -c new-feature` (Creates and switches)
- **Notes:** `git switch` was introduced to separate the branch-switching functionality from file restoration (`git restore`).

### `git merge`
- **Purpose:** Join two or more development histories together.
- **Syntax:** `git merge <commit|branch>`
- **Common Examples:** `git merge feature-branch`
- **Notes:** Be prepared to resolve conflicts if the same lines were modified differently in the two branches.

### `git log`
- **Purpose:** Show commit logs.
- **Syntax:** `git log [<options>]`
- **Common Examples:**
  - `git log --oneline --graph`
  - `git log -n 5` (Show last 5 commits)
- **Notes:** Press `q` to exit the log viewer.

### `git stash`
- **Purpose:** Stash the changes in a dirty working directory away.
- **Syntax:** `git stash [push|pop|apply|list|drop]`
- **Common Examples:**
  - `git stash`
  - `git stash pop`
- **Notes:** Useful for quickly switching branches without committing half-done work.

---

## Advanced Commands

### `git rebase`
- **Purpose:** Reapply commits on top of another base tip.
- **Syntax:** `git rebase [-i] <branch>`
- **Common Examples:**
  - `git rebase main`
  - `git rebase -i HEAD~3` (Interactive rebase of last 3 commits)
- **Notes:** **Never rebase commits that have been pushed to a public repository.**

### `git cherry-pick`
- **Purpose:** Apply the changes introduced by some existing commits.
- **Syntax:** `git cherry-pick <commit-hash>`
- **Common Examples:** `git cherry-pick a1b2c3d`
- **Notes:** Useful for backporting bug fixes to older release branches without pulling everything else.

### `git reset`
- **Purpose:** Reset current HEAD to the specified state.
- **Syntax:** `git reset [--soft | --mixed | --hard] <commit>`
- **Common Examples:**
  - `git reset --soft HEAD~1` (Undoes last commit, keeps changes staged)
  - `git reset --hard HEAD~1` (Undoes last commit, discards changes entirely)
- **Notes:** Extremely destructive when using `--hard`. Use with caution.

### `git reflog`
- **Purpose:** Manage reflog information (track where HEAD has been).
- **Syntax:** `git reflog`
- **Common Examples:** `git reflog`
- **Notes:** Your safety net. Allows you to find commits that seem lost (e.g., after a bad reset or rebase).

### `git bisect`
- **Purpose:** Use binary search to find the commit that introduced a bug.
- **Syntax:** `git bisect [start|bad|good|reset]`
- **Common Examples:**
  - `git bisect start`
  - `git bisect bad` (Current state is broken)
  - `git bisect good v1.0` (Last known working version)
- **Notes:** Automates the process of finding regressions.

### `git worktree`
- **Purpose:** Manage multiple working trees attached to the same repository.
- **Syntax:** `git worktree [add|list|remove]`
- **Common Examples:** `git worktree add ../repo-hotfix hotfix-branch`
- **Notes:** Prevents the need to stash changes or do fresh clones when needing to work on a different branch immediately.