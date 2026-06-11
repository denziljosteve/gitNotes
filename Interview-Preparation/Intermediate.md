# Intermediate Git Interview Questions

## Introduction
This chapter covers intermediate concepts such as branching, merging, and basic repository management, often asked for mid-level roles.

## Questions

### 1. What is a branch in Git?
**Answer:** A branch in Git is essentially a movable pointer to a commit. It allows you to diverge from the main line of development and continue to do work without messing with that main line.

### 2. What is the difference between `git pull` and `git fetch`?
**Answer:**
- `git fetch` only downloads new data from a remote repository, but it doesn't integrate any of this new data into your working files.
- `git pull` downloads the data and also immediately attempts to merge or rebase it into your current working branch.

### 3. How do you resolve a merge conflict?
**Answer:**
1. Identify the files with conflicts (usually marked as "unmerged" in `git status`).
2. Open the files and look for the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
3. Manually edit the file to keep the desired code and remove the conflict markers.
4. Save the file, run `git add` to stage it, and then run `git commit` to finalize the merge.

### 4. What is a detached HEAD state?
**Answer:** A detached HEAD state occurs when you checkout a specific commit instead of a branch. In this state, any new commits you make will be orphaned when you switch back to an existing branch unless you create a new branch to retain them.

### 5. What is the purpose of `git stash`?
**Answer:** `git stash` temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on.

## Summary
Mastering these concepts ensures you can effectively collaborate on a team and manage parallel features.

## Troubleshooting

- Always run `git status` to verify your current state before proceeding.
- Use `git log --oneline --graph` to visualize your commit history and understand where you are.
- If a command fails, read the error message carefully; Git often suggests the solution.
