````md
# Git & GitHub Notes (ChaiCode)

These notes are based on **ChaiCode Git & GitHub series** and my own practice commands.

📌 Reference Documentation:  
https://docs.chaicode.com/youtube/chai-aur-git/introduction/

---

## 📌 Table of Contents

- [Basic Setup](#-basic-setup)
- [File & Folder Commands](#-file--folder-commands)
- [Working Directory, Staging & Commit](#-working-directory-staging--commit)
- [Git Log](#-git-log)
- [Git Editor (Vim / VS Code)](#-git-editor-vim--vs-code)
- [.gitignore](#-gitignore)
- [Keep Empty Folder (.gitkeep)](#-keep-empty-folder-gitkeep)
- [Branches](#-branches)
- [Merging & Merge Conflicts](#-merging--merge-conflicts)
- [Diff Commands](#-diff-commands)
- [Stash](#-stash)
- [Git Tags](#-git-tags)
- [History Management (Merge vs Rebase)](#-history-management-merge-vs-rebase)
- [Reflog & Recovery](#-reflog--recovery)
- [Remote Repository (Origin/Upstream)](#-remote-repository-originupstream)
- [Push / Fetch / Pull](#-push--fetch--pull)

---

## ✅ Basic Setup

### Track a folder using Git

If we want to track folder `one`, we must initialize Git inside that folder:

```bash
cd one
git init
```
````

Before initializing, check if Git is already initialized:

```bash
git status
```

After `git init`, the folder becomes a **Working Directory**.

---

## 📁 File & Folder Commands

### Create a new file

```bash
touch fileName.txt
```

Example:

```bash
touch 1.txt
```

### Create a new folder

```bash
mkdir folderName
```

Example:

```bash
mkdir project
```

---

## ✅ Working Directory, Staging & Commit

### Add file to staging

```bash
git add 1.txt
```

### Add all files to staging

```bash
git add .
```

### Unstage a file

```bash
git rm --cached <file>
```

Example:

```bash
git rm --cached query.sql
```

### Commit changes

Commit moves changes from **staging area** to **repository**:

```bash
git commit -m "your message"
```

---

## 📜 Git Log

### View commit history

```bash
git log
```

### View short log (one-line commits)

```bash
git log --oneline
```

---

## ✍️ Git Editor (Vim / VS Code)

Git’s default editor is **vim**.

### Set VS Code as Git editor

```bash
git config --global core.editor "code --wait"
```

⚠️ If you get error:

```
code: command not found
```

✅ Fix:

1. Open **VS Code**
2. Press `Cmd + Shift + P`
3. Run: **Shell Command: Install 'code' command in PATH**
4. Restart terminal

Now `git commit` opens VS Code.

---

## 🚫 .gitignore

If we don't want to track any file, put it into `.gitignore`.

Example `.gitignore`:

```txt
query.sql
.env
node_modules/
```

---

## 📂 Keep Empty Folder (.gitkeep)

Git does not track empty folders.
To keep an empty folder in repo, create a `.gitkeep` file:

```bash
touch emptyFolder/.gitkeep
```

---

## 🌿 Branches

### List branches

```bash
git branch
```

### Create new branch

```bash
git branch <branch-name>
```

### Switch branch

```bash
git switch <branch-name>
```

### Create and switch branch

```bash
git switch -c <branch-name>
```

### Checkout (old style)

```bash
git checkout <branch-name>
```

### Rename branch

```bash
git branch -m <old-name> <new-name>
```

### Delete branch

```bash
git branch -d <branch-name>
```

---

## 🔀 Merging & Merge Conflicts

### Merge a branch into current branch

```bash
git merge <branch-name>
```

### Merge conflict resolution

If conflict occurs, resolve manually by selecting:

1. Accept Current
2. Accept Incoming
3. Accept Both

Then:

```bash
git add .
git commit -m "resolve merge conflict"
```

---

## 🔍 Diff Commands

### Show staged changes

This compares:
✅ last commit vs staging area

```bash
git diff --staged
```

### Compare two branches

```bash
git diff branch1 branch2
```

OR

```bash
git diff branch1..branch2
```

### Compare two commits

```bash
git diff <hash1> <hash2>
```

---

## 📦 Stash

Stash temporarily saves changes so you can switch branches.

### Save stash (tracked only)

```bash
git stash
```

### Save stash including untracked files

```bash
git stash -u
```

### Save stash with message

```bash
git stash save "work in progress on feature X"
```

### List stashes

```bash
git stash list
```

### Apply latest stash

```bash
git stash apply
```

### Apply specific stash

```bash
git stash apply stash@{0}
```

### Apply and remove stash

```bash
git stash pop
```

### Drop a stash

```bash
git stash drop stash@{0}
```

### Clear all stashes

```bash
git stash clear
```

---

## 🏷️ Git Tags

Tags mark a specific point in repository history.

### Create tag

```bash
git tag <tag-name>
```

Example:

```bash
git tag v1.0
```

---

## 🧠 History Management (Merge vs Rebase)

### Merge Commit

Merge creates a **merge commit**, combining branches history.

### Rebase (clean history)

Some developers prefer rebase to keep history clean.

```bash
git checkout feature-branch
git rebase main
```

If conflicts happen:

```bash
git add <resolved-files>
git rebase --continue
```

---

## 🧾 Reflog & Recovery

### View reflog

Shows all movements of HEAD:

```bash
git reflog
```

### Reset hard to a commit

```bash
git reset --hard <commit-hash>
```

### Reset using reflog position

```bash
git reset --hard HEAD@{1}
```

---

## 🌍 Remote Repository (Origin/Upstream)

### Check remote URL

```bash
git remote -v
```

### Add remote origin

```bash
git remote add origin <remote-url>
```

✅ `origin` is main remote repo.

---

## 🚀 Push / Fetch / Pull

### Push code

```bash
git push origin main
```

### Setup upstream branch (recommended)

After this, you can push/pull without specifying branch each time:

```bash
git push -u origin main
```

### Fetch code

```bash
git fetch <remote-name>
```

Example:

```bash
git fetch origin
```

### Pull latest changes

```bash
git pull origin main
```

```

```
