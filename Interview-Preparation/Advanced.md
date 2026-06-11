# Advanced Git Interview Questions

## Introduction
This chapter covers complex scenarios, history rewriting, and deep internal workings of Git, suitable for senior engineering or DevOps interviews.

## Questions

### 1. Explain the difference between `git merge` and `git rebase`.
**Answer:**
- `git merge` integrates the histories of two branches by creating a new "merge commit". It preserves the exact history of both branches.
- `git rebase` moves the base of your current branch to the tip of another branch, rewriting the project history by creating brand new commits for each commit in the original branch. This results in a cleaner, linear history but alters commit IDs.

### 2. How can you combine multiple commits into one before pushing?
**Answer:** By using an interactive rebase: `git rebase -i HEAD~N` (where N is the number of commits). In the interactive prompt, you can change the commands from `pick` to `squash` (or `s`) for the commits you want to combine into the previous one.

### 3. What is `git cherry-pick` and when would you use it?
**Answer:** `git cherry-pick` enables you to apply the changes introduced by one or more existing commits to your current working branch. It is highly useful for backporting a bug fix from the main branch to an older release branch without pulling in all other changes.

### 4. How do you recover a commit that was "lost" due to a hard reset?
**Answer:** You can use `git reflog` to see the history of HEAD movements. Once you identify the hash of the lost commit, you can run `git checkout <hash>` or `git branch <new-branch> <hash>` to recover it.

### 5. Describe how Git stores data internally.
**Answer:** Git is essentially a content-addressable filesystem. It stores data as key-value pairs using SHA-1 hashes. The three main object types are:
- **Blobs:** Store file data.
- **Trees:** Store directory structures and file names, pointing to blobs or other trees.
- **Commits:** Point to a single tree (the snapshot) and contain metadata (author, message, parent commit).

## Summary
These advanced operations provide the necessary power to manipulate repository history, perform complex integrations, and recover from seemingly catastrophic errors.

## Troubleshooting

- Always run `git status` to verify your current state before proceeding.
- Use `git log --oneline --graph` to visualize your commit history and understand where you are.
- If a command fails, read the error message carefully; Git often suggests the solution.
