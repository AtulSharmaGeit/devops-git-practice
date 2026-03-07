# Git Commands Reference.

1. Setup & Config
- `git --version` - Check Git installation  
- `git config --global user.name "Atul"` - Set username  
- `git config --global user.email "atul@example.com"` - Set email  
- `git config --list` - View all config  


2. Basic Workflow
- `git init` - Initialize repo  
- `git add <file>` - Stage file  
- `git commit -m "message"` - Commit staged changes  

3. Viewing Changes
- `git status` - Show repo status  
- `git log` - Show commit history  
- `git log --oneline` - Compact history  

4. Git Branching
- `git branch` - List all branches
- `git branch feature-1` - Create a new branch
- `git checkout feature-1` - Switch to a branch
- `git checkout -b feature-2` - Create and switch in one command
- `git switch feature-1` - Modern alternative to checkout
- `git switch -c feature-2 ` - create + switch
- `git switch main` - Switch back to main
- `git branch -d feature-2` - Delete a branch

