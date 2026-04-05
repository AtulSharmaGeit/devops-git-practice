# 🌿 Git Cheat Sheet

---

## Setup & Config

| Command | Description |
|--------|-------------|
| `git config --global user.name "Your Name"` | Set your name for all commits |
| `git config --global user.email "you@example.com"` | Set your email for all commits |
| `git config --global core.editor "code --wait"` | Set VS Code as default editor |
| `git config --global init.defaultBranch main` | Set default branch name to main |
| `git config --list` | Show all current config values |
| `git config --global alias.st status` | Create a shortcut alias (`git st`) |

---

## Starting a Repo

| Command | Description |
|--------|-------------|
| `git init` | Initialize a new repo in current directory |
| `git init my-project` | Create a new directory and init repo inside it |
| `git clone https://github.com/user/repo.git` | Clone a remote repo locally |
| `git clone https://github.com/user/repo.git my-folder` | Clone into a specific folder name |

---

## Staging & Committing

| Command | Description |
|--------|-------------|
| `git status` | Show working tree and staging area status |
| `git add file.txt` | Stage a specific file |
| `git add .` | Stage all changes in current directory |
| `git add -p` | Interactively stage chunks of changes (patch mode) |
| `git commit -m "feat: add login page"` | Commit staged changes with a message |
| `git commit -am "fix: typo"` | Stage tracked files and commit in one step |
| `git commit --amend --no-edit` | Add staged changes to the last commit silently |
| `git commit --amend -m "new message"` | Rewrite the last commit message |

---

## Viewing History & Diffs

| Command | Description |
|--------|-------------|
| `git log` | Full commit history |
| `git log --oneline` | Compact one-line-per-commit history |
| `git log --oneline --graph --all` | Visual branch graph of all branches |
| `git log -n 10` | Show last 10 commits only |
| `git log --author="Jane"` | Filter commits by author |
| `git log -- path/to/file` | Show commits that touched a specific file |
| `git diff` | Show unstaged changes |
| `git diff --staged` | Show staged changes (what's about to be committed) |
| `git diff main..feature` | Compare two branches |
| `git show abc1234` | Show changes introduced by a specific commit |
| `git blame file.txt` | Show who last changed each line of a file |

---

## Branching

| Command | Description |
|--------|-------------|
| `git branch` | List local branches |
| `git branch -a` | List local and remote branches |
| `git branch feature/login` | Create a new branch |
| `git switch feature/login` | Switch to an existing branch |
| `git switch -c feature/login` | Create and switch to a new branch |
| `git branch -d feature/login` | Delete a merged branch |
| `git branch -D feature/login` | Force-delete a branch (merged or not) |
| `git branch -m old-name new-name` | Rename a branch |

---

## Merging & Rebasing

| Command | Description |
|--------|-------------|
| `git merge feature/login` | Merge a branch into the current branch |
| `git merge --no-ff feature/login` | Merge with a merge commit (no fast-forward) |
| `git merge --squash feature/login` | Squash all commits into one before merging |
| `git merge --abort` | Abort a merge in progress |
| `git rebase main` | Rebase current branch onto main |
| `git rebase -i HEAD~3` | Interactively rewrite the last 3 commits |
| `git rebase --abort` | Abort a rebase in progress |
| `git rebase --continue` | Continue after resolving a rebase conflict |
| `git cherry-pick abc1234` | Apply a specific commit onto current branch |

---

## Undoing Things

| Command | Description |
|--------|-------------|
| `git restore file.txt` | Discard unstaged changes to a file |
| `git restore --staged file.txt` | Unstage a file (keep changes in working tree) |
| `git reset HEAD~1` | Undo last commit, keep changes staged |
| `git reset --soft HEAD~1` | Undo last commit, keep changes staged |
| `git reset --mixed HEAD~1` | Undo last commit, keep changes unstaged (default) |
| `git reset --hard HEAD~1` | Undo last commit and discard all changes ⚠️ |
| `git revert abc1234` | Create a new commit that undoes a past commit (safe) |
| `git clean -fd` | Remove untracked files and directories ⚠️ |

---

## Stashing

| Command | Description |
|--------|-------------|
| `git stash` | Stash current uncommitted changes |
| `git stash push -m "wip: half-done login"` | Stash with a descriptive message |
| `git stash list` | Show all stashes |
| `git stash pop` | Apply most recent stash and remove it |
| `git stash apply stash@{2}` | Apply a specific stash without removing it |
| `git stash drop stash@{0}` | Delete a specific stash |
| `git stash clear` | Delete all stashes |
| `git stash branch feature/wip` | Create a branch from a stash |

---

## Remote Repositories

| Command | Description |
|--------|-------------|
| `git remote -v` | List remotes with URLs |
| `git remote add origin https://github.com/user/repo.git` | Add a remote named origin |
| `git remote rename origin upstream` | Rename a remote |
| `git remote remove upstream` | Remove a remote |
| `git fetch origin` | Download remote changes without merging |
| `git fetch --all` | Fetch from all remotes |
| `git pull` | Fetch and merge remote changes into current branch |
| `git pull --rebase` | Fetch and rebase instead of merge (cleaner history) |
| `git push origin main` | Push local branch to remote |
| `git push -u origin feature/login` | Push and set upstream tracking |
| `git push --force-with-lease` | Force push safely (fails if remote has new commits) |
| `git push origin --delete feature/login` | Delete a remote branch |

---

## Tags

| Command | Description |
|--------|-------------|
| `git tag` | List all tags |
| `git tag v1.0.0` | Create a lightweight tag on current commit |
| `git tag -a v1.0.0 -m "Release 1.0"` | Create an annotated tag with a message |
| `git tag -a v1.0.0 abc1234` | Tag a specific past commit |
| `git push origin v1.0.0` | Push a tag to remote |
| `git push origin --tags` | Push all tags to remote |
| `git tag -d v1.0.0` | Delete a local tag |
| `git push origin --delete v1.0.0` | Delete a remote tag |

---

## Searching

| Command | Description |
|--------|-------------|
| `git grep "TODO"` | Search working tree for a string |
| `git log -S "functionName"` | Find commits that added/removed a string (pickaxe) |
| `git log --all --grep="bug fix"` | Search commit messages across all branches |
| `git bisect start` | Start a binary search for a bad commit |
| `git bisect bad` | Mark current commit as bad |
| `git bisect good v1.0.0` | Mark a known-good commit to start the search |
| `git bisect reset` | End bisect and return to original branch |

---

## .gitignore Tricks

| Command | Description |
|--------|-------------|
| `git check-ignore -v file.txt` | Show which rule is ignoring a file |
| `git rm --cached file.txt` | Stop tracking a file without deleting it |
| `git rm --cached -r node_modules/` | Stop tracking a directory |
| `git ls-files --ignored --exclude-standard` | List all ignored files |

---

## Cleanup & Maintenance

| Command | Description |
|--------|-------------|
| `git gc` | Run garbage collection and compress history |
| `git prune` | Remove unreachable objects |
| `git remote prune origin` | Remove stale remote-tracking branches |
| `git fetch --prune` | Fetch and prune stale remote branches in one step |
| `git reflog` | Show history of HEAD movements (recovery lifeline) |
| `git reflog expire --expire=90.days refs/heads/main` | Expire old reflog entries |

---

> **Tip:** `reset --hard` and `clean -fd` are destructive and unrecoverable from working tree.  
> When in doubt, use `revert` (safe, adds a new commit) over `reset` (rewrites history).  
> `reflog` is your safety net — it tracks every HEAD movement for ~90 days.

