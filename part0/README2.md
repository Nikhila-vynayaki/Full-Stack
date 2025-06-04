# Create a new directory and initialize a Git repo
- mkdir ~/Desktop/test_project
- cd ~/Desktop/test_project
- git init

# First commit
- git add .
- git commit -m "First version with basic functionality"
- git push -u origin main

# List all branches (local and remote)
git branch -a

# Switch to an existing branch
git switch login  # or: git checkout login

# Verify current branch
git branch        # (asterisk * marks the active branch)

# Fetch all remote branches
git fetch origin

# Switch to a remote branch (creates a local copy)
git checkout --track origin/remote_branch

# Create and switch to a new branch
git switch -c new_branch  # or: git checkout -b new_branch

# Delete a remote branch
git push origin --delete login
