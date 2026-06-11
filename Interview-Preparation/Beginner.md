# Beginner Git Interview Questions

## Introduction
This chapter covers foundational Git questions typically asked during junior developer or internship interviews.

## Questions

### 1. What is Git and why is it used?
**Answer:** Git is a distributed version control system used to track changes in source code during software development. It is used to coordinate work among programmers, maintain a history of changes, and allow reverting to previous states.

### 2. What is the difference between Git and GitHub?
**Answer:** Git is the version control software that runs locally on your machine. GitHub is a cloud-based hosting service that lets you manage Git repositories online and collaborate with others.

### 3. What is a repository in Git?
**Answer:** A repository (or repo) is a directory where Git has been initialized to start version controlling your files. It contains a `.git` folder which houses the metadata and object database.

### 4. How do you initialize a new Git repository?
**Answer:** By running the command `git init` in the desired directory.

### 5. What are the three main states that a file can reside in within Git?
**Answer:**
1. **Committed:** The data is safely stored in your local database.
2. **Modified:** You have changed the file but have not committed it to your database yet.
3. **Staged:** You have marked a modified file in its current version to go into your next commit snapshot.

## Summary
Understanding these fundamental concepts is critical before moving on to more complex Git workflows.

## Troubleshooting

- Always run `git status` to verify your current state before proceeding.
- Use `git log --oneline --graph` to visualize your commit history and understand where you are.
- If a command fails, read the error message carefully; Git often suggests the solution.
