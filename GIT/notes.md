# Introduction
Git is a popular version control system. It is used for:
- Tracking code changes
- Tracking who made the changes
- Code collaborations

(Git is like a memory card for a code)
--- 

# Getting started with GIT
As we begin, the first step is to initialize git on a folder. That is done by: git init
This creates a new repository- A Git repository is a folder that Git tracks for changes. It stores all your project's history and versions.

When we run 'git init, it creates a hidden folder called .git inside the project. This is where git stores all the information.

--- 

# Checking the status
To check whether Git is tracking your file or not, we use: git status
If the output you recieve is under Untracked files, that means, that Git hasn't started tracking that file yet, or it hasn't been pushed to to repository yet. On the other hand, a tracked file is a file that Git is watching for changes.

---

# Staging Environment
The staging environment is like a waiting area for the changes. You use it to tell Git exactly which files you want to include in your next commit.

git add <file> : Stage a file
git add . : Stage all changes

To unstage a file, we use: git restore --staged <file>

---

# Commit
A commit is like a save point in your project. It records a snapshot of your files at a certain time, with a message describing what changed. It is done using:

git commit -m "message" - Commit staged changes with a message
git commit -a -m "message" - Commit all tracked changes (skip staging)

To view the commit hisory, we use: git log

---


# Tag
It is like a tag or bookmark for a specific commit. Suppose your commit history looks like this:

A -- B -- C -- D -- E -- F
Today you're at commit F. But commit C is where your app was first completed. Instead of remembering that weird commit ID(8d7ac91), you can simply say: v1.0
Now Git remembers that v1.0 → C

A tag is created by: git tag < tagname >
You can list out all tags by the command git tag

There are two types of tag: Lightweight and Annotated
- A lightweight tag just has a name and nothing else
- Annotated tag contains extra information too like: git tag -a v1.0 -m "First stable release"

Tags also don't automatically gets pushed to github. To do so, we command: git push origin v1.0 OR git push origin --tags

---

# Stash
When we don't want to commit the work but want to save it temporarily, we use the stash command (git stash). If the stashing is done along a message, we use: git stash push -m "message"
All the stashes are displayed using: git stash list

To apply a latest stash we use: git stash apply, while to apply a particular stash, we use: git stash apply stash@{n}

---

# Git Branch
In git, a branch is a separate workspace where you can work and make changes without affecting the main project. It is like a parallel universe to the code.

git branch < branch name > is used to create a new branch
To see all the branches, we simply use git branch

To switch between branches, we use the checkout command: git checkout < branch_name > or we prefer: git switch branch_name
Finally to delete a branch: git branch -d < branch_name >

---

# Merge
Merging in git means combining the changes from one branch with another. It is simply done using: git merge < branch_name >

---