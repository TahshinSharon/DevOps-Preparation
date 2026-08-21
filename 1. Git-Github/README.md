<h1 align="center">Git &amp; GitHub Learning Notes</h1>

<p align="center">
  A personal collection of Git commands, GitHub workflows,<br>
  concepts, and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions">
  <img src="https://img.shields.io/badge/GitHub%20CLI-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub CLI">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-8-blue?style=flat-square" alt="Sections">
  <img src="https://img.shields.io/badge/Level-Beginner→Advanced-orange?style=flat-square" alt="Level">
  <img src="https://img.shields.io/badge/Status-Actively%20Updated-brightgreen?style=flat-square" alt="Status">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="../README.md"><b>Back to DevOps Prep</b></a>
  &nbsp;·&nbsp;
  <a href="../Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Networking/README.md"><b>Networking Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Cloud-Engineering/README.md"><b>Cloud Engineering Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Docker/README.md"><b>Docker Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Kubernetes/README.md"><b>Kubernetes Notes</b></a>
</p>

---

> 🎯 **[Common Interview Questions →](#common-interview-questions)** &nbsp;·&nbsp; 50 Git & GitHub interview questions (10 Easy · 20 Medium · 20 Hard) for DevOps junior / mid / senior roles.

---

## Table of Contents

- [Common Interview Questions](#common-interview-questions)
- [Git Basics](#git-basics)
  - [One Shot Revision](#one-shot-revision)
  - [Version Control](#version-control)
  - [git --version](#git---version)
  - [git config](#git-config)
  - [git init](#git-init)
  - [git clone](#git-clone)
  - [git status](#git-status)
  - [git help](#git-help)
- [Working with Changes](#working-with-changes)
  - [One Shot Revision](#one-shot-revision-1)
  - [The Three Areas](#the-three-areas)
  - [git add](#git-add)
  - [git commit](#git-commit)
  - [git diff](#git-diff)
  - [git log](#git-log)
  - [git show](#git-show)
  - [.gitignore](#gitignore)
- [Branching & Merging](#branching--merging)
  - [One Shot Revision](#one-shot-revision-2)
  - [Branches](#branches)
  - [git branch](#git-branch)
  - [git checkout](#git-checkout)
  - [git switch](#git-switch)
  - [git merge](#git-merge)
  - [git rebase](#git-rebase)
  - [git cherry-pick](#git-cherry-pick)
- [Remote Repositories](#remote-repositories)
  - [One Shot Revision](#one-shot-revision-3)
  - [Remotes](#remotes)
  - [git remote](#git-remote)
  - [git fetch](#git-fetch)
  - [git pull](#git-pull)
  - [git push](#git-push)
  - [SSH vs HTTPS](#ssh-vs-https)
- [Undoing Changes](#undoing-changes)
  - [One Shot Revision](#one-shot-revision-4)
  - [git restore](#git-restore)
  - [git reset](#git-reset)
  - [git revert](#git-revert)
  - [git clean](#git-clean)
  - [git reflog](#git-reflog)
- [Stashing & Tagging](#stashing--tagging)
  - [One Shot Revision](#one-shot-revision-5)
  - [git stash](#git-stash)
  - [git tag](#git-tag)
- [Advanced Git](#advanced-git)
  - [One Shot Revision](#one-shot-revision-6)
  - [git bisect](#git-bisect)
  - [git blame](#git-blame)
  - [git submodule](#git-submodule)
  - [git worktree](#git-worktree)
  - [git hooks](#git-hooks)
- [GitHub & Collaboration](#github--collaboration)
  - [One Shot Revision](#one-shot-revision-7)
  - [SSH Keys](#ssh-keys)
  - [Forks & Pull Requests](#forks--pull-requests)
  - [GitHub CLI (gh)](#github-cli-gh)
  - [GitHub Actions](#github-actions)
  - [CI/CD](#cicd)
  - [Issues, README, LICENSE](#issues-readme-license)
- [Useful Tips & Tricks](#useful-tips--tricks)
- [References](#references)

---

## Git Basics

The essentials for starting with Git — installing, configuring identity, creating or cloning a repo, and checking its state.

### One Shot Revision

| Command                                 | Short Description                                              |
| --------------------------------------- | -------------------------------------------------------------- |
| [Version Control](#version-control)     | What VCS is and why distributed VCS like Git matters           |
| [`git --version`](#git---version)       | Print the installed Git version                                |
| [`git config`](#git-config)             | Set your name, email, editor, and other Git preferences        |
| [`git init`](#git-init)                 | Turn the current directory into a brand-new Git repository     |
| [`git clone`](#git-clone)               | Copy a remote repository (and its history) to your machine     |
| [`git status`](#git-status)             | Show what's staged, modified, and untracked in the working dir |
| [`git help`](#git-help)                 | Open the manual for any Git subcommand                         |

---

### Version Control

**What:** Version control tracks every change to your files over time so you can go back to any earlier state, see who changed what, and collaborate without overwriting each other.  
**When:** Always — use it for every project, even solo ones. Git is the industry-standard distributed VCS where every clone holds the full history.  
**Key point:** Git stores **snapshots**, not diffs — each commit is a complete picture of the project identified by a unique SHA hash.

**Hands-on:**

```bash
# Step 1 — Check if Git is installed
git --version

# Step 2 — Initialize a practice repo
mkdir git-practice && cd git-practice
git init -b main

# Step 3 — Create a file and make your first snapshot
echo "Hello Git" > hello.txt
git add hello.txt
git commit -m "first commit"

# Step 4 — View the snapshot (commit) you just created
git log --oneline
```

---

### `git --version`

**What:** Prints the version of Git installed on your machine.  
**When:** Use it as a quick sanity check after installation, or when troubleshooting compatibility issues.  
**Key point:** Some commands (like `git switch`) only exist in Git 2.23+, so always verify your version first.

**Hands-on:**

```bash
# Step 1 — Print the installed Git version
git --version
# Expected output: git version 2.x.x

# Step 2 — If Git is not found, install it
# macOS:   brew install git
# Ubuntu:  sudo apt install git
# Windows: https://git-scm.com/download/win

# Step 3 — Confirm Git is on your PATH
which git        # macOS/Linux → shows the path e.g. /usr/bin/git
where git        # Windows
```

---

### `git config`

**What:** Reads and writes your Git configuration — your name, email, preferred editor, aliases, and hundreds of other settings.  
**When:** Run once globally after installing Git to set your identity; revisit whenever you want to customize behavior for a project or add aliases.  
**Key point:** Settings live in three levels — system, global (`~/.gitconfig`), and local (per-repo `.git/config`) — and local always wins.

**Hands-on:**

```bash
# Step 1 — Set your global identity (Git stamps every commit with this)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Step 2 — Set a sensible default branch name
git config --global init.defaultBranch main

# Step 3 — Add a powerful log alias
git config --global alias.lg "log --oneline --graph --all --decorate"

# Step 4 — View all active settings and their source files
git config --list --show-origin

# Step 5 — Override identity for just one repo (drop --global)
cd my-work-project
git config user.email "work@company.com"
```

---

### `git init`

**What:** Turns any directory into a Git repository by creating a hidden `.git/` folder that stores all history and metadata.  
**When:** Use it whenever you start a brand-new project that isn't cloned from anywhere.  
**Key point:** A repo is just a folder with `.git/` inside — delete `.git/` and you have a plain directory again with no history.

**Hands-on:**

```bash
# Step 1 — Create a new project folder and initialize it
mkdir my-project && cd my-project
git init -b main

# Step 2 — Verify the hidden .git/ folder was created
ls -la        # you should see a .git/ directory

# Step 3 — Add a file and make the first commit
echo "# My Project" > README.md
git add README.md
git commit -m "init: add README"

# Step 4 — Check your repo's current state
git status
git log --oneline
```

---

### `git clone`

**What:** Downloads an existing repository — including its full history — from a URL to your local machine and automatically sets up `origin` as the remote.  
**When:** Use it whenever you want to work on an existing remote repository (from GitHub, GitLab, etc.).  
**Key point:** Every clone is a full copy of the repo — you have the entire history locally and can commit, branch, and log offline.

**Hands-on:**

```bash
# Step 1 — Clone a public repo via HTTPS
git clone https://github.com/torvalds/linux.git

# Step 2 — Clone into a specific folder name
git clone https://github.com/user/repo.git my-folder

# Step 3 — Clone via SSH (faster for daily use after SSH keys are set up)
git clone git@github.com:user/repo.git

# Step 4 — Shallow clone (only last 1 commit — fast, saves space)
git clone --depth 1 https://github.com/some/big-repo.git

# Step 5 — After cloning, check what remote was set up
cd repo
git remote -v
```

---

### `git status`

**What:** Shows the current state of your working directory — which files are staged, modified, or untracked, and which branch you are on.  
**When:** Run it constantly — before staging, before committing, after a merge. It's the cheapest way to know exactly what's going on.  
**Key point:** Three categories matter: **staged** (will go into next commit), **modified** (changed but not staged), and **untracked** (brand new files Git doesn't know about).

**Hands-on:**

```bash
# Step 1 — Check the current state of your repo
git status

# Step 2 — Create and modify files to see each category
echo "new file" > newfile.txt          # untracked
echo "edit" >> README.md              # modified (if tracked)
git add newfile.txt                   # now it's staged

# Step 3 — Run status again and observe the three sections
git status

# Step 4 — Use short format for a compact view
git status -s

# Step 5 — Short format with branch info
git status -sb
```

---

### `git help`

**What:** Opens the full manual page for any Git command directly in your terminal.  
**When:** Use it whenever you're unsure about a command's options or behavior — the built-in docs are comprehensive and always accurate.  
**Key point:** Use `-h` for a quick one-screen summary, and `--help` for the full man page.

**Hands-on:**

```bash
# Step 1 — Open the full manual for git commit
git help commit

# Step 2 — View a short usage summary (fits on one screen)
git commit -h

# Step 3 — Try the same for other commands
git log --help
git merge -h
git stash --help

# Tip: press 'q' to quit the man page
```

---

## Working with Changes

The everyday loop: edit files, stage them, commit them, and inspect the history.

### One Shot Revision

| Command                             | Short Description                                                     |
| ----------------------------------- | --------------------------------------------------------------------- |
| [The Three Areas](#the-three-areas) | Working directory, staging area (index), and repository (history)     |
| [`git add`](#git-add)               | Stage changes to be included in the next commit                       |
| [`git commit`](#git-commit)         | Record the staged changes as a new commit in history                  |
| [`git diff`](#git-diff)             | Show changes between working dir, staging area, and commits           |
| [`git log`](#git-log)               | Browse commit history with formatting and filtering                   |
| [`git show`](#git-show)             | Show the contents and diff of a specific commit                       |
| [`.gitignore`](#gitignore)          | Tell Git which files to never track                                   |

---

### The Three Areas

**What:** Git organizes your work into three areas — the **working directory** (files you edit), the **staging area/index** (changes marked for the next commit), and the **repository** (permanent, committed history in `.git/`).  
**When:** Understand this model before anything else — every Git command moves changes between these three areas.  
**Key point:** The staging area is Git's superpower — it lets you build focused, intentional commits even from a messy working directory.

**Hands-on:**

```bash
# Step 1 — Make two unrelated edits
echo "feature A" >> feature.txt
echo "bugfix B" >> bugfix.txt

# Step 2 — Stage only one file (intentional commit)
git add feature.txt

# Step 3 — Check each area
git status                   # shows what's staged vs unstaged
git diff                     # working dir vs staging area (unstaged)
git diff --staged            # staging area vs last commit (will be committed)

# Step 4 — Commit only the staged change
git commit -m "feat: add feature A"

# Step 5 — The bugfix is still in the working dir, unstaged
git status
```

---

### `git add`

**What:** Stages changes from your working directory into the staging area so they will be included in the next commit.  
**When:** After editing files — you selectively add what belongs in the next logical commit before running `git commit`.  
**Key point:** Use `git add -p` (patch mode) to stage only specific lines/hunks from a file — this is one of Git's most powerful features for clean history.

**Hands-on:**

```bash
# Step 1 — Stage a single file
git add README.md

# Step 2 — Stage an entire folder
git add src/

# Step 3 — Stage everything in the current directory
git add .

# Step 4 — Stage all changes repo-wide (including deletions)
git add -A

# Step 5 — Interactive: review and stage chunk-by-chunk
git add -p
# At each hunk prompt: y=stage, n=skip, s=split, q=quit

# Step 6 — Dry run: see what would be staged without staging it
git add -n .
```

---

### `git commit`

**What:** Records the staged changes as a permanent, immutable snapshot in the repository, identified by a unique SHA hash and tied to your name, email, and message.  
**When:** After staging all the changes that belong together in one logical unit of work.  
**Key point:** Write commit messages in imperative mood (`Add login`, not `Added login`) — a good message explains the **why**, not just the what.

**Hands-on:**

```bash
# Step 1 — Commit with a message inline
git commit -m "feat: add user login page"

# Step 2 — Stage all tracked files and commit in one step
git commit -am "fix: correct typo in README"

# Step 3 — Fix the last commit message (before pushing)
git commit --amend -m "fix: correct typo in welcome message"

# Step 4 — Add a forgotten file to the last commit (before pushing)
git add forgotten-file.txt
git commit --amend --no-edit

# Step 5 — View the commit you just created
git log --oneline -1
git show HEAD
```

---

### `git diff`

**What:** Shows the exact line-by-line differences between files — between your working directory and staging, between staging and last commit, or between any two commits/branches.  
**When:** Use it before staging (`git diff`) to review edits, and before committing (`git diff --staged`) to verify exactly what will be recorded.  
**Key point:** `git diff` (no args) shows **unstaged** changes; `git diff --staged` shows **staged** changes that will go into the next commit.

**Hands-on:**

```bash
# Step 1 — Edit a file and see unstaged changes
echo "new line" >> README.md
git diff                           # working dir vs staging (unstaged)

# Step 2 — Stage it and see staged changes
git add README.md
git diff --staged                  # staging vs last commit (what commit will record)

# Step 3 — Compare all uncommitted changes vs HEAD
git diff HEAD

# Step 4 — Compare two branches
git diff main feature/login

# Step 5 — See just the list of changed files (no line details)
git diff --name-only HEAD~3 HEAD

# Step 6 — See a summary with insertion/deletion counts
git diff --stat HEAD~1 HEAD
```

---

### `git log`

**What:** Displays the commit history of the current branch, showing who committed what and when.  
**When:** Use it to review history, find a commit by message or author, understand what changed in a file, or visualize branch structure.  
**Key point:** `git log --oneline --graph --all --decorate` gives you a visual ASCII tree of all branches — save it as an alias (`git lg`).

**Hands-on:**

```bash
# Step 1 — View full commit history
git log

# Step 2 — Compact one-liner per commit
git log --oneline

# Step 3 — Visual branch graph for all branches
git log --oneline --graph --all --decorate

# Step 4 — Filter by author and time
git log --author="Your Name" --since="1 week ago"

# Step 5 — See what changed in a specific file
git log -p -- README.md

# Step 6 — Save the pretty graph as an alias
git config --global alias.lg "log --oneline --graph --all --decorate"
git lg    # now use this everywhere
```

---

### `git show`

**What:** Displays the full details of a specific commit — its metadata (author, date, message) plus the complete diff of what changed.  
**When:** Use it to inspect a commit by its SHA, or to view the contents of a file at a specific point in history.  
**Key point:** `git show HEAD` shows the most recent commit; `git show HEAD~2` shows two commits back; `git show <sha>` shows any commit by its hash.

**Hands-on:**

```bash
# Step 1 — Inspect the most recent commit
git show

# Step 2 — Inspect a commit 2 steps back from HEAD
git show HEAD~2

# Step 3 — Inspect a commit by its short SHA
git log --oneline    # find a SHA first
git show abc1234     # replace with an actual SHA

# Step 4 — View a file's contents at a specific commit (read-only)
git show HEAD:README.md
git show HEAD~3:src/app.js
```

---

### `.gitignore`

**What:** A text file that lists patterns of files and directories Git should completely ignore — they won't appear as untracked and can never be accidentally committed.  
**When:** Add it at the start of every project to exclude build output, dependencies (`node_modules/`), environment files (`.env`), and OS/editor junk (`.DS_Store`).  
**Key point:** `.gitignore` only affects **untracked** files — if a file is already committed, run `git rm --cached <file>` to untrack it first, then add it to `.gitignore`.

**Hands-on:**

```bash
# Step 1 — Create a .gitignore file
cat > .gitignore << 'EOF'
# Dependencies
node_modules/
vendor/

# Build output
dist/
build/
*.log

# Environment files (NEVER commit these)
.env
.env.*
*.pem

# OS / editor junk
.DS_Store
.vscode/
*.swp
EOF

# Step 2 — Commit it
git add .gitignore
git commit -m "chore: add .gitignore"

# Step 3 — Test: create an ignored file and verify Git ignores it
echo "SECRET=abc123" > .env
git status    # .env should NOT appear as untracked

# Step 4 — Untrack a file that was already committed
git rm --cached accidentally-committed.txt
echo "accidentally-committed.txt" >> .gitignore
git add .gitignore
git commit -m "chore: untrack accidentally-committed.txt"
```

---

## Branching & Merging

Branches are how you isolate work without affecting `main`. Merging (or rebasing) brings that work back together.

### One Shot Revision

| Command                               | Short Description                                                  |
| ------------------------------------- | ------------------------------------------------------------------ |
| [Branches](#branches)                 | What a branch is in Git and why it's so cheap                      |
| [`git branch`](#git-branch)           | List, create, rename, or delete branches                           |
| [`git checkout`](#git-checkout)       | Switch branches or restore files (legacy combined command)         |
| [`git switch`](#git-switch)           | Switch branches — the modern, dedicated command                    |
| [`git merge`](#git-merge)             | Combine another branch's changes into the current branch           |
| [`git rebase`](#git-rebase)           | Reapply commits on top of another base for a linear history        |
| [`git cherry-pick`](#git-cherry-pick) | Apply a specific commit from one branch onto another               |

---

### Branches

**What:** A branch in Git is a lightweight, movable pointer to a commit — creating one costs almost nothing (Git just writes a 40-byte SHA file).  
**When:** Create a branch for every new feature, bugfix, or experiment — keep `main` stable and merge branches in when they're ready.  
**Key point:** `HEAD` is the special pointer that tracks which branch (and commit) you currently have checked out.

**Hands-on:**

```bash
# Step 1 — See the current branch and history
git log --oneline --graph --all --decorate

# Step 2 — Create a feature branch
git branch feature/login

# Step 3 — Switch to it
git switch feature/login

# Step 4 — Make a commit on this branch
echo "login page" > login.html
git add login.html
git commit -m "feat: add login page"

# Step 5 — Go back to main and see the branch structure
git switch main
git log --oneline --graph --all --decorate
```

---

### `git branch`

**What:** Lists, creates, renames, and deletes branches in your repository.  
**When:** Use it to organize your work — list what branches exist, clean up merged ones, or rename a branch before sharing it.  
**Key point:** `git branch <name>` creates a branch but does **not** switch to it — use `git switch -c <name>` to create and switch in one step.

**Hands-on:**

```bash
# Step 1 — List all local branches
git branch

# Step 2 — List all branches (local + remote) with last commit info
git branch -av

# Step 3 — Create a new branch (stays on current branch)
git branch feature/signup

# Step 4 — Rename the current branch
git branch -m feature/signup feature/user-signup

# Step 5 — Delete a merged branch (safe — refuses unmerged)
git branch -d feature/user-signup

# Step 6 — Force-delete an unmerged branch
git branch -D feature/user-signup

# Step 7 — List branches already merged into main (safe to delete)
git branch --merged main
```

---

### `git checkout`

**What:** The original multi-purpose command that switches branches, creates branches, and restores files from any commit.  
**When:** Still valid everywhere, but for clarity prefer `git switch` for changing branches and `git restore` for reverting files in modern workflows.  
**Key point:** Checking out a raw SHA (not a branch) puts you in **detached HEAD** state — commits made there will be lost unless you create a branch to save them.

**Hands-on:**

```bash
# Step 1 — Switch to an existing branch
git checkout main

# Step 2 — Create and switch to a new branch in one step
git checkout -b feature/auth

# Step 3 — Restore a single file from a specific commit
git checkout HEAD~2 -- README.md

# Step 4 — Enter detached HEAD (inspect an old commit)
git log --oneline   # find a SHA
git checkout abc1234

# Step 5 — Save detached HEAD work by creating a branch
git switch -c rescued-work

# Step 6 — Go back to main
git checkout main
```

---

### `git switch`

**What:** The modern, dedicated command for switching branches — introduced in Git 2.23 to replace the branch-switching half of `git checkout`.  
**When:** Use `git switch` instead of `git checkout` for all branch operations — it's clearer and won't accidentally restore files.  
**Key point:** `git switch -c <name>` creates a new branch and switches to it in one step; `git switch -` jumps back to the previous branch (like `cd -`).

**Hands-on:**

```bash
# Step 1 — Switch to an existing branch
git switch main

# Step 2 — Create a new branch and switch to it
git switch -c feature/payments

# Step 3 — Jump back to the previous branch
git switch -

# Step 4 — If you have uncommitted changes, stash them first
git stash
git switch main
git stash pop   # bring changes back when you return

# Step 5 — Force-create (reset if branch already exists)
git switch -C feature/payments
```

---

### `git merge`

**What:** Combines the commits of another branch into your current branch — either by fast-forwarding the pointer or by creating a merge commit.  
**When:** Use it to integrate a completed feature branch into `main`, or to bring `main`'s latest changes into your feature branch.  
**Key point:** A **fast-forward** merge moves the pointer with no merge commit; a **three-way merge** creates a new merge commit when the branches have diverged.

**Hands-on:**

```bash
# Setup: create and commit on a feature branch
git switch -c feature/login
echo "login" > login.html
git add login.html && git commit -m "feat: add login"
git switch main

# Step 1 — Merge feature branch into main
git merge feature/login

# Step 2 — Force a merge commit even if fast-forward is possible
git merge --no-ff feature/login

# Step 3 — If there are conflicts, resolve them
git status                       # see conflicting files
# edit the conflicting file, remove <<<<, ====, >>>> markers
git add resolved-file.html
git commit                       # finishes the merge

# Step 4 — Abort a conflicted merge and restore original state
git merge --abort

# Step 5 — Delete the merged branch when done
git branch -d feature/login
```

---

### `git rebase`

**What:** Replays commits from your branch on top of another branch's latest tip — rewriting history to produce a clean, linear log without merge commits.  
**When:** Use it to clean up your local feature branch before opening a PR, or to update your branch with `main`'s latest changes without a merge commit.  
**Key point:** **Never rebase commits you've already pushed to a shared branch** — it rewrites SHAs and breaks teammates' history.

**Hands-on:**

```bash
# Setup: feature branch is behind main
git switch feature/login

# Step 1 — Get latest changes from remote
git fetch origin

# Step 2 — Rebase your branch on top of origin/main
git rebase origin/main

# Step 3 — If conflicts occur during rebase
# edit the conflicting file, resolve the conflict
git add resolved-file.txt
git rebase --continue            # move to the next commit

# Step 4 — Abort a rebase and restore original state
git rebase --abort

# Step 5 — Interactive rebase: clean up last 3 commits before PR
git rebase -i HEAD~3
# In the editor: change 'pick' to 'squash' to combine commits
# change 'pick' to 'reword' to edit a message
```

---

### `git cherry-pick`

**What:** Applies the exact changes from a specific commit onto your current branch as a brand-new commit with a new SHA.  
**When:** Use it to backport a bug fix to a release branch, or to grab a single useful commit from another branch without merging everything.  
**Key point:** Cherry-picking creates a duplicate commit (new SHA, same diff) — if you later fully merge the source branch, git may show that commit twice.

**Hands-on:**

```bash
# Step 1 — Find the SHA of the commit you want
git log --oneline feature/hotfix

# Step 2 — Apply one commit to current branch
git cherry-pick abc1234

# Step 3 — Apply multiple commits
git cherry-pick abc1234 def5678

# Step 4 — Apply a range of commits (A excluded, B included)
git cherry-pick A..B

# Step 5 — If conflict occurs during cherry-pick
# resolve the conflict, then:
git add resolved-file.txt
git cherry-pick --continue

# Step 6 — Abort if needed
git cherry-pick --abort
```

---

## Remote Repositories

A **remote** is a named URL pointing to another copy of your repo. Push, pull, fetch, and clone all talk to remotes.

### One Shot Revision

| Command                       | Short Description                                                         |
| ----------------------------- | ------------------------------------------------------------------------- |
| [Remotes](#remotes)           | What a remote is and what `origin` and `upstream` mean                    |
| [`git remote`](#git-remote)   | List, add, rename, or remove remotes                                      |
| [`git fetch`](#git-fetch)     | Download commits/refs from a remote — does **not** modify your branches   |
| [`git pull`](#git-pull)       | `fetch` + `merge` (or `rebase`) in one step                               |
| [`git push`](#git-push)       | Send your local commits to a remote                                       |
| [SSH vs HTTPS](#ssh-vs-https) | The two ways to authenticate with a Git host                              |

---

### Remotes

**What:** A remote is a named pointer to another copy of your repository, usually hosted on GitHub, GitLab, or a similar platform.  
**When:** You interact with remotes whenever you push, pull, fetch, or clone — they are how your local work connects to the outside world.  
**Key point:** `origin` is the conventional name for the remote you cloned from; `upstream` is the convention for the original repo when working from a fork.

**Hands-on:**

```bash
# Step 1 — View all configured remotes and their URLs
git remote -v

# Step 2 — Add a remote (e.g. after git init, before first push)
git remote add origin git@github.com:you/my-project.git

# Step 3 — Rename a remote
git remote rename origin old-origin

# Step 4 — Remove a remote
git remote remove old-origin

# Step 5 — In a fork workflow, add the original repo as upstream
git remote add upstream https://github.com/original-owner/repo.git
git remote -v   # verify both remotes exist
```

---

### `git remote`

**What:** Manages the list of remote repositories your local repo knows about — add, remove, rename, or change the URL of any remote.  
**When:** Use it when you first connect a local repo to a remote, when you fork and need to track the original, or when a remote URL changes.  
**Key point:** `git remote -v` shows two entries per remote — one for fetch and one for push — they can point to different URLs.

**Hands-on:**

```bash
# Step 1 — List remotes with their URLs
git remote -v

# Step 2 — Add a new remote
git remote add origin git@github.com:me/repo.git

# Step 3 — Add upstream (for fork workflow)
git remote add upstream https://github.com/original/repo.git

# Step 4 — Change a remote's URL (e.g. switch HTTPS to SSH)
git remote set-url origin git@github.com:me/repo.git

# Step 5 — Download the remote's refs (to verify it works)
git fetch origin
```

---

### `git fetch`

**What:** Downloads new commits, branches, and tags from a remote into your local repo as remote-tracking branches (like `origin/main`) — without touching your working branches.  
**When:** Use it before reviewing what changed upstream, before deciding whether to merge or rebase, or to update your view of the remote state safely.  
**Key point:** `git fetch` is completely safe — it never modifies your local branches or working directory; you review first, then decide to integrate.

**Hands-on:**

```bash
# Step 1 — Fetch all updates from origin
git fetch origin

# Step 2 — Fetch from all remotes
git fetch --all

# Step 3 — Fetch and clean up deleted remote branches
git fetch --prune

# Step 4 — After fetching, compare local vs remote
git log HEAD..origin/main          # commits on remote that you don't have
git log origin/main..HEAD          # commits you have that remote doesn't

# Step 5 — After reviewing, integrate the changes
git merge origin/main              # or: git rebase origin/main
```

---

### `git pull`

**What:** A shortcut for `git fetch` + `git merge` (or `git rebase`) — downloads remote changes and immediately integrates them into your current branch.  
**When:** Use it to quickly update your branch with the latest remote changes when you're not worried about inspecting the diff first.  
**Key point:** Set `pull.rebase = true` globally to keep history linear — `git pull --rebase` replays your local commits on top of the remote instead of creating a merge commit.

**Hands-on:**

```bash
# Step 1 — Update current branch with remote (default: merge)
git pull

# Step 2 — Pull with rebase instead of merge (cleaner history)
git pull --rebase origin main

# Step 3 — Pull only if it can fast-forward (safest — no accidental merges)
git pull --ff-only

# Step 4 — Configure rebase as the default pull strategy (global)
git config --global pull.rebase true

# Step 5 — Pull a specific remote and branch
git pull upstream main
```

---

### `git push`

**What:** Sends your committed local changes to a remote repository, making them available to others.  
**When:** Use it after committing locally to share your work, publish a new branch, or update a remote branch after a rebase.  
**Key point:** Use `-u` on the first push of a new branch to link it to the remote — after that, a plain `git push` is enough.

**Hands-on:**

```bash
# Step 1 — First push of a new branch (sets upstream tracking)
git push -u origin feature/login

# Step 2 — Subsequent pushes on a tracked branch
git push

# Step 3 — Delete a remote branch
git push origin --delete feature/old-stuff

# Step 4 — Push all tags
git push --tags

# Step 5 — Safer force push (after a rebase on your OWN branch)
git push --force-with-lease
# Never use --force on shared branches like main

# Step 6 — Push current branch by name without typing it
git push -u origin HEAD
```

---

### SSH vs HTTPS

**What:** Two protocols for authenticating with GitHub — HTTPS uses a username + Personal Access Token, SSH uses a keypair (private key on your machine, public key on GitHub).  
**When:** Use SSH for daily development work (no password prompts once set up); use HTTPS on restricted networks where port 22 is blocked.  
**Key point:** Switch a repo between protocols at any time with `git remote set-url origin <new-url>` — no re-cloning needed.

**Hands-on:**

```bash
# --- SSH Setup ---

# Step 1 — Generate an Ed25519 SSH key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Step 2 — Add the key to your SSH agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Step 3 — Copy your public key and add it to GitHub
cat ~/.ssh/id_ed25519.pub      # copy this output
# Paste into: GitHub → Settings → SSH and GPG keys → New SSH key

# Step 4 — Test the connection
ssh -T git@github.com
# Expected: "Hi <username>! You've successfully authenticated"

# --- Switch between protocols ---

# Step 5 — Switch a repo from HTTPS to SSH
git remote set-url origin git@github.com:user/repo.git

# Step 6 — Or switch to HTTPS
git remote set-url origin https://github.com/user/repo.git
```

---

## Undoing Changes

Git tracks everything, so almost any action is reversible — if you know which "undo" you need.

### One Shot Revision

| Command                       | Short Description                                                    |
| ----------------------------- | -------------------------------------------------------------------- |
| [`git restore`](#git-restore) | Undo changes in the working dir or unstage files (modern, safe)      |
| [`git reset`](#git-reset)     | Move the branch pointer — soft / mixed / hard rewrites of state      |
| [`git revert`](#git-revert)   | Create a **new** commit that undoes a previous one (history-safe)    |
| [`git clean`](#git-clean)     | Delete **untracked** files from the working directory                |
| [`git reflog`](#git-reflog)   | Log of every move `HEAD` has made — your safety net for lost commits |

---

### `git restore`

**What:** Restores files in your working directory or staging area — discards edits to a file or unstages a file you accidentally added.  
**When:** Use `git restore <file>` to throw away unstaged edits; use `git restore --staged <file>` to unstage a file while keeping your edits.  
**Key point:** Discarding working-directory changes is **permanent** — the edits are gone. Run `git stash` first if you're not sure.

**Hands-on:**

```bash
# Step 1 — Make a change you want to throw away
echo "accidental edit" >> README.md
git status                              # shows README.md as modified

# Step 2 — Discard the unstaged edit (restores from staging area)
git restore README.md
git status                              # README.md is clean again

# Step 3 — Accidentally staged a file? Unstage it (keeps the edit)
git add config.yml
git restore --staged config.yml
git status                              # config.yml is now unstaged

# Step 4 — Restore a file to its state 3 commits ago
git restore --source HEAD~3 -- src/app.js
git diff src/app.js                     # see what changed
```

---

### `git reset`

**What:** Moves the branch pointer (HEAD) to a different commit, optionally changing the staging area and working directory depending on the mode (`--soft`, `--mixed`, `--hard`).  
**When:** Use it to undo recent local commits before pushing — **never** use it on commits already shared with others.  
**Key point:** `--soft` keeps changes staged, `--mixed` (default) unstages them, `--hard` discards everything — `--hard` is the only one that loses work.

**Hands-on:**

```bash
# Step 1 — Make two commits to practice with
echo "first" > a.txt && git add a.txt && git commit -m "first"
echo "second" > b.txt && git add b.txt && git commit -m "second"

# Step 2 — Undo last commit but keep changes STAGED
git reset --soft HEAD~1
git status                    # b.txt is still staged

# Step 3 — Undo last commit and UNSTAGE changes (keep edits)
git reset HEAD~1              # --mixed is the default
git status                    # b.txt is unstaged but still exists

# Step 4 — Undo last commit and DISCARD changes (destructive)
git reset --hard HEAD~1
git status                    # b.txt is completely gone

# Step 5 — Recover with reflog (within ~90 days)
git reflog                    # find the lost commit SHA
git reset --hard <sha>        # restore to that commit
```

---

### `git revert`

**What:** Creates a new commit that applies the **inverse** of a specific past commit — undoing its changes without rewriting history.  
**When:** Use it to undo something that's already been pushed to a shared branch — it's the only safe "undo" for public history.  
**Key point:** Unlike `git reset`, `git revert` **adds** to history — making it safe for shared branches since no one's history is rewritten.

**Hands-on:**

```bash
# Step 1 — View recent commits to find what to undo
git log --oneline

# Step 2 — Revert the most recent commit
git revert HEAD
# Git opens an editor for the revert commit message — save and close

# Step 3 — Revert a specific commit by SHA
git revert abc1234

# Step 4 — Revert without opening the editor
git revert HEAD --no-edit

# Step 5 — If conflicts arise during revert
# resolve the conflict in the file, then:
git add resolved-file.txt
git revert --continue

# Step 6 — Bail out of the revert
git revert --abort
```

---

### `git clean`

**What:** Permanently deletes untracked files (and optionally directories) from your working directory — files that were never added to Git.  
**When:** Use it to wipe build artifacts, generated files, or any clutter that isn't tracked, returning the repo to a pristine state.  
**Key point:** This is **irreversible** — untracked files are not in Git, so there is no recovery. Always run `git clean -n` (dry run) first to preview what will be deleted.

**Hands-on:**

```bash
# Step 1 — Create some untracked files to experiment with
touch temp.log cache.tmp untracked.txt
mkdir build && touch build/output.js

# Step 2 — ALWAYS dry-run first — see what would be deleted
git clean -n

# Step 3 — Remove untracked files (force required as a safety guard)
git clean -f

# Step 4 — Also remove untracked directories
git clean -fd

# Step 5 — Also remove files ignored by .gitignore (deep clean)
git clean -fdx

# Step 6 — Interactive mode (confirm each item before deleting)
git clean -i
```

---

### `git reflog`

**What:** A local-only log of every position HEAD has ever been in — every commit, reset, rebase, checkout, and branch switch recorded chronologically.  
**When:** Use it when you think you've lost commits after a bad reset, rebase, or accidental branch deletion — it's your safety net.  
**Key point:** Reflog entries survive for ~90 days by default — after that, `git gc` prunes them — so act quickly when recovering lost work.

**Hands-on:**

```bash
# Step 1 — View the full reflog
git reflog

# Step 2 — Simulate a "lost" commit
echo "important work" > important.txt
git add important.txt && git commit -m "important work"
git reset --hard HEAD~1     # oops — commit looks gone

# Step 3 — Find the lost commit in the reflog
git reflog                  # look for "important work" commit

# Step 4 — Restore by jumping HEAD back to that position
git reset --hard HEAD@{2}   # or use the SHA directly

# Step 5 — Recover a deleted branch
git reflog                   # find the commit the branch pointed to
git switch -c recovered-branch <sha>
```

---

## Stashing & Tagging

Two everyday tools: **stash** to set aside in-progress changes, **tag** to mark releases.

### One Shot Revision

| Command                   | Short Description                                                |
| ------------------------- | ---------------------------------------------------------------- |
| [`git stash`](#git-stash) | Park uncommitted changes so the working dir is clean             |
| [`git tag`](#git-tag)     | Create lightweight or annotated tags (usually for releases)      |

---

### `git stash`

**What:** Temporarily saves your uncommitted changes onto a stack and reverts your working directory to a clean state, so you can switch tasks without committing half-done work.  
**When:** Use it when you need to urgently switch branches or pull updates but you're not ready to commit your current work.  
**Key point:** `git stash pop` re-applies and removes the top stash; `git stash apply` re-applies but keeps it on the stack — use `apply` when you might need to re-apply to multiple branches.

**Hands-on:**

```bash
# Step 1 — Save current changes to the stash
git stash push -m "WIP: half-done login form"

# Step 2 — Your working dir is clean — switch branches freely
git switch main && git pull

# Step 3 — Come back to your feature branch
git switch feature/login

# Step 4 — View all stashes on the stack
git stash list

# Step 5 — Re-apply and remove the top stash
git stash pop

# Step 6 — Re-apply a specific stash (keep it on stack)
git stash apply stash@{1}

# Step 7 — View the diff of a stash before applying
git stash show -p stash@{0}

# Step 8 — Stash including untracked files
git stash -u
```

---

### `git tag`

**What:** Creates a named, permanent label on a specific commit — used to mark releases (`v1.0.0`, `v2.3.1`) that users and tools can reference by name.  
**When:** Tag every release after merging to `main` — it gives your CI/CD pipeline, package registries, and users a stable, human-readable pointer to that version.  
**Key point:** Use **annotated tags** (`-a`) for releases — they store the tagger's name, date, and message; **lightweight tags** are just sticky notes with no metadata.

**Hands-on:**

```bash
# Step 1 — Create an annotated tag at the current commit
git tag -a v1.0.0 -m "Release 1.0.0 — initial stable release"

# Step 2 — List all tags
git tag

# Step 3 — List tags matching a pattern
git tag -l "v1.*"

# Step 4 — Inspect a tag (shows tagger, date, message, and diff)
git show v1.0.0

# Step 5 — Tag an older commit (backdate a release)
git log --oneline           # find the SHA
git tag -a v0.9.0 abc1234 -m "Backdated release 0.9.0"

# Step 6 — Push a specific tag to remote
git push origin v1.0.0

# Step 7 — Push all tags at once
git push origin --tags

# Step 8 — Delete a tag locally and on remote
git tag -d v0.9.0
git push origin --delete v0.9.0
```

---

## Advanced Git

Power-tools you don't reach for every day, but which are invaluable when you need them.

### One Shot Revision

| Command                            | Short Description                                                |
| ---------------------------------- | ---------------------------------------------------------------- |
| [`git bisect`](#git-bisect)        | Binary-search the history for the commit that introduced a bug   |
| [`git blame`](#git-blame)          | Show who last modified each line of a file                       |
| [`git submodule`](#git-submodule)  | Embed another Git repo inside your repo at a fixed commit        |
| [`git worktree`](#git-worktree)    | Check out multiple branches of one repo into separate dirs       |
| [`git hooks`](#git-hooks)          | Run scripts automatically on Git events (pre-commit, pre-push)   |

---

### `git bisect`

**What:** Performs a binary search through your commit history to find the exact commit that introduced a bug — cutting the search space in half with each step.  
**When:** Use it when you know "it worked at version X, it's broken now" and you have hundreds of commits in between to investigate.  
**Key point:** Binary search means finding the culprit in 1000 commits takes only ~10 steps; automate with `git bisect run <test-script>` for zero manual effort.

**Hands-on:**

```bash
# Step 1 — Start a bisect session
git bisect start

# Step 2 — Mark the current (broken) state as bad
git bisect bad                     # or: git bisect bad HEAD

# Step 3 — Mark a known-good commit (e.g. a tag or SHA)
git bisect good v1.0.0             # or: git bisect good abc1234

# Git checks out a midpoint commit automatically

# Step 4 — Test the code. Then mark it good or bad
git bisect good      # no bug at this commit
# or:
git bisect bad       # bug exists here too

# Step 5 — Repeat until Git identifies the first bad commit
# Git prints: "abc1234 is the first bad commit"

# Step 6 — End the session and return to your branch
git bisect reset

# Bonus — Automate with a test script
git bisect start
git bisect bad HEAD
git bisect good v1.0.0
git bisect run npm test            # exit 0 = good, non-zero = bad
```

---

### `git blame`

**What:** Shows, for every line of a file, the commit SHA, author name, and timestamp of the last change to that line.  
**When:** Use it for code archaeology — "who wrote this line, when, and in what context?" — then follow up with `git show <sha>` for the full commit.  
**Key point:** Most editors (VS Code with GitLens, JetBrains) show blame inline; on GitHub, click the "Blame" button on any file view.

**Hands-on:**

```bash
# Step 1 — Blame an entire file
git blame README.md

# Step 2 — Blame a specific line range (lines 10 to 30)
git blame -L 10,30 src/app.js

# Step 3 — Ignore whitespace-only changes
git blame -w README.md

# Step 4 — Get the full context of any commit shown in blame
git blame README.md               # note the SHA on a line you're curious about
git show abc1234                  # see the full commit with its message and diff

# Step 5 — Find when a specific string was added or removed
git log -S "functionName" --oneline
```

---

### `git submodule`

**What:** Embeds another Git repository inside your repo at a specific pinned commit — the parent repo tracks which exact commit of the child repo to use.  
**When:** Use it when you need to include a shared library or dependency while keeping its full Git history separate from your repo.  
**Key point:** Submodules are a common source of confusion in teams — always clone with `--recurse-submodules` and run `git submodule update --init --recursive` after pulling.

**Hands-on:**

```bash
# Step 1 — Add a submodule to your repo
git submodule add https://github.com/example/library.git vendor/library

# Step 2 — Commit the submodule reference
git commit -m "chore: add library as submodule"

# Step 3 — Clone a repo that has submodules
git clone --recurse-submodules https://github.com/you/repo.git

# Step 4 — Initialize submodules after a regular clone
git submodule update --init --recursive

# Step 5 — Update submodules to their latest upstream commits
git submodule update --remote

# Step 6 — View all submodules
cat .gitmodules
```

---

### `git worktree`

**What:** Lets you check out multiple branches of the same repository into separate directories simultaneously, all sharing the same `.git/` object storage.  
**When:** Use it when you need to work on two branches at the same time — a hotfix while your feature is in progress — without stashing or cloning.  
**Key point:** Much cheaper than cloning twice — no duplicate `.git/` directory, no re-downloading objects; each worktree is just a new working directory.

**Hands-on:**

```bash
# Step 1 — Create a second working directory for an existing branch
git worktree add ../repo-hotfix hotfix/urgent-bug

# Step 2 — Create a second working directory on a NEW branch
git worktree add -b hotfix/payment-crash ../repo-hotfix main

# Step 3 — List all active worktrees
git worktree list

# Step 4 — Work in the new worktree directory
cd ../repo-hotfix
# make changes, commit, push — all linked to the same .git/

# Step 5 — Remove the worktree when done
cd ../your-main-repo
git worktree remove ../repo-hotfix
```

---

### `git hooks`

**What:** Shell scripts that Git runs automatically at specific lifecycle events — before committing, after merging, before pushing — letting you enforce standards without manual discipline.  
**When:** Use them to autorun linters, format checkers, commit message validators, or test suites automatically on each commit or push.  
**Key point:** Hook scripts live in `.git/hooks/` and are not version-controlled by default — use **Husky** (Node) or the **pre-commit** framework to share hooks with your team via the repo.

**Hands-on:**

```bash
# Step 1 — View the sample hooks Git provides
ls .git/hooks/

# Step 2 — Create a pre-commit hook that blocks debug leftovers
cat > .git/hooks/pre-commit << 'EOF'
#!/usr/bin/env bash
if git diff --cached | grep -E "(console\.log|debugger)"; then
  echo "ERROR: Remove console.log/debugger before committing."
  exit 1
fi
EOF

# Step 3 — Make it executable
chmod +x .git/hooks/pre-commit

# Step 4 — Test it — try to commit with a console.log
echo "console.log('test')" >> app.js
git add app.js
git commit -m "test"       # should be BLOCKED by the hook

# Step 5 — Create a commit-msg hook to enforce format
cat > .git/hooks/commit-msg << 'EOF'
#!/usr/bin/env bash
if ! grep -qE "^(feat|fix|docs|chore|refactor|test):" "$1"; then
  echo "ERROR: Commit message must start with a type (feat:, fix:, etc.)"
  exit 1
fi
EOF
chmod +x .git/hooks/commit-msg
```

---

## GitHub & Collaboration

The collaboration layer on top of Git: authentication, pull requests, CI, and the GitHub CLI.

### One Shot Revision

| Topic                                          | Short Description                                                |
| ---------------------------------------------- | ---------------------------------------------------------------- |
| [SSH Keys](#ssh-keys)                          | Generate a keypair and connect to GitHub without passwords       |
| [Forks & Pull Requests](#forks--pull-requests) | The standard open-source contribution workflow                   |
| [GitHub CLI (gh)](#github-cli-gh)              | Manage PRs, issues, releases from your terminal                  |
| [GitHub Actions](#github-actions)              | Native CI/CD — run workflows on push, PR, or schedule            |
| [CI/CD](#cicd)                                 | Build → test → deploy pipeline concepts and strategies           |
| [Issues, README, LICENSE](#issues-readme-license) | The "social" files every public repo needs                  |

---

### SSH Keys

**What:** An SSH keypair (private key on your machine + public key on GitHub) lets you authenticate with GitHub for every push and pull — no password required.  
**When:** Set it up once after creating your GitHub account — every git operation over SSH will then work silently without prompting for credentials.  
**Key point:** Keep your **private key** (`~/.ssh/id_ed25519`) secret — only the **public key** (`.pub`) is safe to share or upload to GitHub.

**Hands-on:**

```bash
# Step 1 — Generate an Ed25519 key (modern, fast, secure)
ssh-keygen -t ed25519 -C "your_email@example.com"
# Press Enter for the default path; optionally set a passphrase

# Step 2 — Start the SSH agent and add your key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Step 3 — Copy your public key
cat ~/.ssh/id_ed25519.pub          # copy the entire output

# Step 4 — Add it to GitHub
# Go to: GitHub → Settings → SSH and GPG keys → New SSH key
# Paste the public key and save

# Step 5 — Test the connection
ssh -T git@github.com
# Expected: "Hi <username>! You've successfully authenticated."

# Step 6 — Switch your repo remote to SSH
git remote set-url origin git@github.com:you/repo.git
```

---

### Forks & Pull Requests

**What:** A **fork** is a server-side copy of a repo under your GitHub account; a **Pull Request** is a request to merge your changes from a branch/fork back into the original repo — the standard open-source contribution workflow.  
**When:** Fork when you want to contribute to a repo you don't have write access to; open a PR when your branch is ready for review and merging.  
**Key point:** Keep your fork's `main` synced with `upstream/main` before starting any new work to avoid painful merge conflicts later.

**Hands-on:**

```bash
# Step 1 — Fork on GitHub UI (click "Fork" on the repo page)

# Step 2 — Clone YOUR fork locally
git clone git@github.com:you/repo.git && cd repo

# Step 3 — Add the original repo as upstream
git remote add upstream https://github.com/original-owner/repo.git
git remote -v   # should show both origin and upstream

# Step 4 — Sync your fork's main with upstream before new work
git fetch upstream
git switch main
git merge upstream/main
git push origin main

# Step 5 — Create a feature branch and make changes
git switch -c feature/my-improvement
# ...edit files, add, commit...
git push -u origin feature/my-improvement

# Step 6 — Open a PR from the GitHub UI or with gh CLI
gh pr create --base main --head feature/my-improvement \
  --title "Add my improvement" --body "Fixes #42"
```

---

### GitHub CLI (`gh`)

**What:** The official GitHub command-line tool — lets you create repos, manage PRs and issues, trigger Actions, and handle releases without leaving the terminal.  
**When:** Use it instead of the GitHub web UI for PR creation, review, and merge — it integrates naturally with your git workflow in the terminal.  
**Key point:** Authenticate once with `gh auth login` and `gh` automatically knows which repo you're in based on `origin`.

**Hands-on:**

```bash
# Step 1 — Install and authenticate (one-time setup)
# macOS: brew install gh
gh auth login                    # follow the browser-based prompts

# Step 2 — Create a new GitHub repo from your current directory
gh repo create my-project --public --source . --push

# Step 3 — Create a pull request
gh pr create --title "feat: add login" --body "Implements OAuth flow" --base main

# Step 4 — List open pull requests
gh pr list

# Step 5 — Check out a PR locally to test it
gh pr checkout 42

# Step 6 — Approve and merge a PR
gh pr review --approve
gh pr merge --squash --delete-branch

# Step 7 — Create an issue
gh issue create -t "Bug: login fails on Safari" -b "Steps to reproduce..."

# Step 8 — Watch a GitHub Actions run in real time
gh run list
gh run watch
```

---

### GitHub Actions

**What:** GitHub's built-in CI/CD platform — YAML workflow files in `.github/workflows/` that automatically run jobs on triggers like pushes, PRs, or schedules.  
**When:** Use it to automatically lint, test, build, and deploy your app on every commit or PR — replacing manual human steps with reliable automation.  
**Key point:** Jobs run **in parallel** by default on separate runners; steps within a job run **sequentially** — use `needs:` to create dependencies between jobs.

**Hands-on:**

```bash
# Step 1 — Create the workflows directory
mkdir -p .github/workflows

# Step 2 — Create a basic CI workflow
cat > .github/workflows/ci.yml << 'EOF'
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Node
        uses: actions/setup-node@v4
        with:
          node-version: 20

      - name: Install dependencies
        run: npm ci

      - name: Run tests
        run: npm test
EOF

# Step 3 — Commit and push to trigger the workflow
git add .github/workflows/ci.yml
git commit -m "ci: add GitHub Actions CI workflow"
git push

# Step 4 — Watch the workflow run
gh run list
gh run watch
```

---

### CI/CD

**What:** Continuous Integration (CI) automatically builds and tests every code change; Continuous Delivery/Deployment (CD) automatically packages and deploys passing builds — eliminating manual, error-prone release steps.  
**When:** Set it up from day one — even a simple "run tests on every PR" pipeline catches bugs early and builds team confidence in the codebase.  
**Key point:** Keep CI fast (under 10 minutes) — slow pipelines kill adoption; put cheap checks (lint, unit tests) first and expensive checks (e2e, security scans) last.

**Hands-on:**

```bash
# A practical multi-stage pipeline with GitHub Actions:

cat > .github/workflows/pipeline.yml << 'EOF'
name: CI/CD Pipeline

on:
  pull_request:
  push:
    branches: [main]

jobs:
  # Stage 1 — Lint (fast, cheap)
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: npm ci && npm run lint

  # Stage 2 — Test (runs after lint passes)
  test:
    needs: lint
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node: [18, 20]             # test on multiple Node versions
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: "${{ matrix.node }}" }
      - run: npm ci && npm test

  # Stage 3 — Deploy (only on main branch, after tests pass)
  deploy:
    needs: test
    if: github.ref == 'refs/heads/main'
    runs-on: ubuntu-latest
    environment: production        # requires manual approval gate
    steps:
      - uses: actions/checkout@v4
      - run: ./deploy.sh
        env:
          DEPLOY_TOKEN: ${{ secrets.DEPLOY_TOKEN }}
EOF
```

---

### Issues, README, LICENSE

**What:** The non-code files that make a repository professional, discoverable, and collaborative — they tell visitors what the project is, how to use it, and how to contribute.  
**When:** Add `README.md` and a `LICENSE` to every public repo before sharing the link — without a license, code is legally "all rights reserved" and unusable by others.  
**Key point:** Writing `Closes #42` in a PR description automatically closes issue #42 when the PR is merged — a powerful way to link work to tracking items.

**Hands-on:**

```bash
# Step 1 — Create a minimal README
cat > README.md << 'EOF'
# Project Name

One sentence describing what this project does.

## Installation
\`\`\`bash
npm install
\`\`\`

## Usage
\`\`\`bash
npm start
\`\`\`

## Contributing
See CONTRIBUTING.md
EOF

# Step 2 — Add a LICENSE (choose from choosealicense.com)
# Example: MIT License
# Go to: GitHub → your repo → Add file → Create new file → type "LICENSE"
# GitHub will offer a license picker

# Step 3 — Create a GitHub Issue from the CLI
gh issue create -t "Feature: add dark mode" -b "Users have requested a dark mode toggle."

# Step 4 — Create a PR that auto-closes an issue
git switch -c feature/dark-mode
# ...make your changes...
git commit -m "feat: add dark mode toggle"
git push -u origin feature/dark-mode
gh pr create --title "feat: add dark mode" \
  --body "Implements dark mode toggle. Closes #1"
```

---

## Common Interview Questions

**50 commonly asked Git & GitHub interview questions** for DevOps roles — **10 Easy** (junior), **20 Medium** (mid-level), **20 Hard** (senior). Curated to cover the topics that come up most in real interviews: workflow basics, branching, merging vs rebasing, undoing changes, remotes, Git internals, GitHub collaboration, and CI/CD with Actions.

### Easy (Junior Level)

**1. What is Git, and how is it different from GitHub?**

**Git** is a distributed version control system (DVCS) that tracks changes to files locally — every clone is a full repository with complete history. **GitHub** is a web platform built **around** Git that adds hosting, pull requests, issues, code review, Actions (CI/CD), and access control. Git works offline; GitHub is the centralized collaboration layer. Alternatives to GitHub include GitLab, Bitbucket, and Gitea.

**2. What is version control, and why use it?**

**Version control** records changes to files over time so you can recall any earlier state, see who changed what, and collaborate without overwriting each other. Benefits:

- **History** — every change is attributable and revertible.
- **Branching** — work on features in parallel without breaking `main`.
- **Collaboration** — multiple developers merge work safely.
- **Backup** — every clone is a full copy of the repo.

**3. How do you initialize a new Git repository?**

```bash
git init                  # turns the current dir into a Git repo (creates .git/)
git init my-project       # creates my-project/ and inits it
git init --bare repo.git  # bare repo (no working tree) — used on servers
```

Then configure your identity once globally:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**4. What's the difference between `git pull` and `git fetch`?**

- **`git fetch`** — downloads new commits/refs from the remote into your local **remote-tracking branches** (e.g. `origin/main`). Your working branch is untouched.
- **`git pull`** — `fetch` + immediately **merges** (or rebases, with `pull.rebase=true`) the remote branch into your current branch.

`fetch` is **safe** and lets you inspect changes before integrating. `pull` is a shortcut that does the merge for you.

**5. How do you check the status of your working directory?**

```bash
git status                # full output: branch, staged, unstaged, untracked
git status -sb            # short + branch info (great for aliasing)
```

Output sections: **Changes to be committed** (staged), **Changes not staged for commit** (modified), **Untracked files** (new files Git doesn't know about yet).

**6. What is `.gitignore` and how does it work?**

`.gitignore` is a text file listing **path patterns Git should ignore** — they won't show up as untracked and can't be accidentally committed. Common patterns:

```gitignore
node_modules/
dist/
*.log
.DS_Store
.env
*.pem
```

Already-tracked files are **not** ignored retroactively — run `git rm --cached <file>` to untrack them.

**7. How do you stage and commit changes?**

```bash
git add file.txt          # stage one file
git add .                 # stage everything in the current dir
git add -p                # stage by hunk (interactive — recommended)
git commit -m "Fix typo in README"
git commit -am "..."      # stage all tracked + commit in one step
```

Staging (the "index") lets you assemble a commit out of partial changes — small, focused commits are easier to review and revert.

**8. What is a branch in Git?**

A **branch** is just a **movable pointer to a commit**. Creating one is O(1) — Git writes a 40-byte SHA to `.git/refs/heads/<name>`. Branches let you isolate work (a feature, a bugfix, an experiment) without touching `main`.

```bash
git branch                       # list local branches
git branch feature-x             # create
git switch feature-x             # move HEAD to it (modern)
git switch -c feature-x          # create + switch in one step
```

**9. How do you clone a repository?**

```bash
git clone https://github.com/user/repo.git           # via HTTPS
git clone git@github.com:user/repo.git               # via SSH
git clone --depth 1 <url>                             # shallow clone (fast, no history)
git clone --branch develop <url>                      # clone a specific branch
```

Clone copies the entire `.git` directory, checks out `HEAD`, and sets `origin` to the remote URL.

**10. How do you view commit history?**

```bash
git log                                # full log
git log --oneline                      # one line per commit
git log --oneline --graph --all        # ASCII branch graph
git log -p                             # show patch (diff) for each commit
git log --author="alice"               # filter by author
git log --since="2 weeks ago"          # time filter
git log -- path/to/file                # history of a specific file
```

Useful alias: `git config --global alias.lg "log --oneline --graph --all --decorate"`.

---

### Medium (Mid-Level)

**11. What's the difference between `git merge` and `git rebase`?**

Both integrate changes from one branch into another, but with very different histories:

| Aspect       | `merge`                                      | `rebase`                                    |
| ------------ | -------------------------------------------- | ------------------------------------------- |
| History      | Preserves branching — creates a merge commit | Linear — replays your commits on top of target |
| Commit SHAs  | Unchanged                                    | **New SHAs** (commits are recreated)        |
| Safety       | Always safe                                  | **Never rebase shared/pushed branches**     |
| Best for     | Long-lived branches, public history          | Cleaning up local feature branches          |

Rule of thumb: **rebase before you push, merge after**.

**12. Explain the three areas: working directory, staging area, and repository.**

```
Working Directory  ── git add ──▶  Staging Area (index)  ── git commit ──▶  Repository (.git)
       ▲                                    ▲                                       │
       └──────── git restore ◀──────────────┴───────── git restore --staged ◀──────┘
```

- **Working directory** — actual files on disk you edit.
- **Staging area** ("index") — a snapshot of what will go into the next commit.
- **Repository** — the immutable history of commits in `.git/`.

**13. What is a detached HEAD state?**

`HEAD` is the pointer to your current commit. Normally `HEAD` points to a **branch ref** (`refs/heads/main`), which points to a commit. A **detached HEAD** means `HEAD` points directly at a commit SHA, not through a branch. It happens when you `git checkout <sha>` or `git checkout v1.0` (a tag).

You can look around and even commit in detached HEAD — but those commits aren't on any branch and will be **garbage-collected** if you switch away. To save them: `git switch -c new-branch` while still detached.

**14. How do you undo the last commit (keeping vs discarding changes)?**

```bash
git reset --soft HEAD~1     # undo commit, KEEP changes staged
git reset --mixed HEAD~1    # undo commit, KEEP changes unstaged (default)
git reset --hard HEAD~1     # undo commit, DISCARD changes (destructive)
git commit --amend          # fix the LAST commit (message or staged changes)
```

If the commit was already pushed and shared, prefer **`git revert HEAD`** instead.

**15. Explain `git reset --soft`, `--mixed`, and `--hard`.**

| Mode      | HEAD moves | Staging area | Working dir | Use when                                |
| --------- | ---------- | ------------ | ----------- | --------------------------------------- |
| `--soft`  | ✅          | unchanged    | unchanged   | You want to re-do the commit message    |
| `--mixed` | ✅          | reset        | unchanged   | You want to re-stage differently (default) |
| `--hard`  | ✅          | reset        | **wiped**   | You want to throw the work away — **destructive** |

`--hard` is the only one that can lose work. Even then, `git reflog` can usually recover it within ~90 days.

**16. How do you resolve a merge conflict?**

When Git can't auto-merge, it marks conflicts in the file:

```
<<<<<<< HEAD
your version
=======
their version
>>>>>>> feature-branch
```

Steps:

```bash
git status                  # see which files conflict
# Edit each file — choose your code, theirs, or a blend; remove the markers.
git add resolved-file.js
git commit                  # for merge
git rebase --continue       # for rebase
git merge --abort           # bail out entirely
```

**17. What is a fast-forward merge?**

A **fast-forward** happens when the target branch (e.g. `main`) has not advanced since you branched off — Git just moves `main`'s pointer forward to your branch's tip. **No merge commit is created.**

```bash
git merge --no-ff feature   # force a merge commit even if FF is possible
git merge --ff-only feature # only merge if FF is possible (reject if diverged)
```

**18. What is `git stash` and when do you use it?**

`git stash` saves uncommitted changes (tracked files by default) onto a **stack** and reverts your working directory to a clean state — useful when you need to switch branches but aren't ready to commit.

```bash
git stash                   # stash tracked changes
git stash -u                # include untracked
git stash list              # show stack
git stash pop               # re-apply newest + drop from stack
git stash apply stash@{1}   # apply a specific stash, keep it on stack
git stash clear             # wipe all
```

**19. What's the difference between annotated and lightweight tags?**

```bash
git tag v1.0                                    # lightweight — just a name → commit SHA
git tag -a v1.0 -m "Release 1.0"                # annotated — full Git object with metadata
```

- **Lightweight** — like a branch that doesn't move. No metadata.
- **Annotated** — stored as a full object with tagger, date, message. **Always use annotated tags for releases.**

Push tags: `git push origin v1.0` or `git push --tags` (all).

**20. What is `git cherry-pick`?**

`git cherry-pick <commit>` applies the **changes** from a specific commit onto your current branch as a **new commit**. Use it to pull a bug fix from `main` into a release branch without merging unrelated work.

```bash
git cherry-pick abc1234              # one commit
git cherry-pick abc1234..def5678     # a range (exclusive of first)
git cherry-pick -x abc1234           # adds "(cherry picked from ...)" to message
git cherry-pick --abort              # bail on conflict
```

**21. What's the difference between HTTPS and SSH for Git remotes?**

| Aspect          | HTTPS                              | SSH                                  |
| --------------- | ---------------------------------- | ------------------------------------ |
| URL             | `https://github.com/user/repo.git` | `git@github.com:user/repo.git`       |
| Auth            | Username + **Personal Access Token** | **SSH key pair**                   |
| Firewall        | Almost always allowed (port 443)   | May be blocked (port 22)             |

SSH is the day-to-day favorite for developers; HTTPS is friendlier for restricted networks and CI.

**22. How do you delete a local and remote branch?**

```bash
# Local
git branch -d feature-x         # safe — refuses if unmerged
git branch -D feature-x         # force delete

# Remote
git push origin --delete feature-x

# Prune stale remote-tracking branches
git fetch --prune
```

**23. What's the difference between a fork and a clone?**

- **Clone** — a **local** copy of any repo, made with `git clone`. Pushes go back to the same remote.
- **Fork** — a **server-side** copy of a repo under **your** GitHub account. Fork → clone your fork → open a PR back to the original.

**24. What is a Pull Request, and why use one?**

A **Pull Request** is a request to merge changes from one branch (or fork) into another. It's a GitHub feature — not a Git concept. PRs add code review, automated CI checks, discussion, and a controlled merge strategy (squash, rebase, merge commit).

**25. What does `git revert` do, and how is it different from `git reset`?**

- **`git revert <sha>`** — creates a **new commit** that applies the inverse of the target commit. History is **preserved**. Safe on shared branches.
- **`git reset <sha>`** — moves the branch pointer backward. History is **rewritten**. **Only safe locally.**

Rule: **revert public history, reset private history.**

**26. What is `git reflog`, and when do you use it?**

`git reflog` is a **local log of every position HEAD has been in** — saves you when something seems lost:

```bash
git reflog                            # list recent HEAD movements
git reset --hard HEAD@{3}             # jump back to where HEAD was 3 moves ago
git checkout -b rescue HEAD@{1}       # rescue a "lost" branch
```

Entries live ~90 days by default. Reflog is **per-clone** and **never pushed**.

**27. What is Conventional Commits, and how does it integrate with CI/CD?**

Conventional Commits is a commit-message specification: `<type>[scope]: <description>`. Common types: `feat`, `fix`, `chore`, `docs`, `refactor`, `test`.

Tools like `semantic-release` parse commit types to auto-bump semver (`feat` → minor, `fix` → patch) and generate CHANGELOGs. Enforce it in CI with `commitlint`.

**28. What's the difference between `origin` and `upstream`?**

Both are just remote names — Git gives them no special meaning. **Convention:**
- **`origin`** — your own fork (or the only remote if you have direct access).
- **`upstream`** — the **original** repo you forked from.

**29. What is `git blame` used for?**

`git blame <file>` shows, for **every line**, the commit and author that last changed it. Use it for archaeology — "who wrote this line?" — then `git show <sha>` for full context.

**30. How do you squash multiple commits into one?**

```bash
git rebase -i HEAD~5             # edit the last 5 commits
# Change 'pick' to 'squash' for commits to fold into the one above
```

Alternatives: `git commit --amend` (last commit only), GitHub's "Squash and merge" button on PRs.

---

### Hard (Senior Level)

**31. Explain Git internals: blobs, trees, commits, and refs.**

Git is a **content-addressable filesystem** with four object types in `.git/objects/`, all keyed by SHA:

- **Blob** — file content (no name, no metadata). Two identical files share one blob.
- **Tree** — a directory listing: maps names → blob/tree SHAs + modes.
- **Commit** — points to one tree, lists parent commit(s), plus author, committer, message.
- **Tag** (annotated) — points to a commit, with tagger, message, optional signature.

**Refs** (`.git/refs/heads/main`, `HEAD`) are text files containing a SHA — mutable names that point into the immutable object graph.

**32. What is GitOps, and how do tools like ArgoCD or Flux use Git as the source of truth?**

**GitOps** is an operational model where the desired state of infrastructure is declared in Git (YAML, Helm, Terraform), and a reconciliation agent continuously compares actual vs. desired state and corrects drift. All changes go through PRs — rollback = `git revert`.

Tools: **ArgoCD** and **Flux** (Kubernetes), **Atlantis** (Terraform PR automation).

**33. How does Git store data — what makes it "content-addressable"?**

Every object's name **is** the SHA-1 of its content. Identical content → identical SHA → stored once. This gives Git deduplication, built-in integrity checking (`git fsck`), and cheap branching (a branch is just 40 bytes).

**34. What is `git bisect` and how do you use it?**

`git bisect` binary-searches history to find the commit that introduced a bug. Mark a good commit and a bad commit; Git checks out the midpoint; you mark it good or bad; repeat until the culprit is found in O(log N) steps.

Automate: `git bisect run ./test.sh` (exit 0 = good, non-zero = bad).

**35. Explain Git hooks. Client-side vs server-side.**

**Client-side** hooks (`.git/hooks/`): `pre-commit` (lint/format), `commit-msg` (message format), `pre-push` (run tests).
**Server-side** hooks: `pre-receive` (enforce push policy), `post-receive` (trigger deploys).

Share hooks with teams using **Husky** (Node) or the **pre-commit** framework.

**36. What is `git submodule`? What are its pitfalls?**

A submodule is a reference to another Git repo pinned to a specific commit embedded inside your repo. Pitfalls: forgetting `--recurse-submodules` on clone, detached HEAD inside the submodule, extra `git submodule update` step needed after every pull. Modern alternatives: monorepo tools, `git subtree`, or package managers.

**37. Compare branching strategies: Git Flow, GitHub Flow, Trunk-Based.**

| Strategy        | Key Branches                                | Best for                             |
| --------------- | ------------------------------------------- | ------------------------------------ |
| **Git Flow**    | main, develop, feature/*, release/*, hotfix/* | Versioned software with scheduled releases |
| **GitHub Flow** | main + short-lived feature/*                | SaaS, web apps, continuous deployment |
| **Trunk-Based** | Everyone commits to main; feature flags hide WIP | High-velocity teams with strong CI/CD |

**38. What's the difference between `git push --force` and `--force-with-lease`?**

- **`--force`** — overwrites the remote branch even if a teammate pushed since your last fetch. You can erase their work.
- **`--force-with-lease`** — checks that the remote tip matches your last fetch; fails safely if someone else pushed.

Rule: **never `--force`**. Use `--force-with-lease` on your own feature branches only.

**39. What's inside the `.git` directory?**

```
.git/
├── HEAD                ← current branch ref
├── config              ← repo-local config
├── index               ← the staging area (binary file)
├── hooks/              ← client-side hook scripts
├── objects/            ← all blobs, trees, commits, tags
│   └── pack/           ← packfiles (compressed bundles)
├── refs/
│   ├── heads/          ← local branches → SHAs
│   ├── tags/           ← tags → SHAs
│   └── remotes/        ← remote-tracking branches
└── logs/               ← reflog data
```

**40. What are packfiles, and what does `git gc` do?**

A **packfile** bundles many objects delta-compressed together for space and speed. `git gc` rolls loose objects into packfiles and prunes unreachable objects (from old rebases, deleted branches) older than ~2 weeks. `git reflog` and `git fsck --lost-found` can recover objects before pruning.

**41. How do you sign commits, and why?**

Signed commits prove the commit was made by the holder of a key — not just someone who set `user.email`. Use GPG or SSH signing:

```bash
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global commit.gpgsign true
```

Upload the signing key to GitHub. PRs show a green **"Verified"** badge. Enforce it with branch protection: "Require signed commits".

**42. What is `git worktree`, and when is it useful?**

`git worktree` lets you check out **multiple branches** from one `.git/` into separate directories simultaneously — no duplicate `.git/`, shared object database. Use cases: fix a hotfix while your feature is in progress, compare branches side-by-side, run tests on another branch.

**43. How do you recover a deleted branch or lost commits?**

```bash
git reflog                              # find the dangling SHA
git fsck --lost-found                   # scan for unreachable commits
git switch -c rescued <sha>             # restore the branch
```

Works if loss is recent (≤ 90 days) and `git gc --prune=now` hasn't run.

**44. Explain GitHub Actions architecture: workflows, jobs, steps, runners.**

- **Workflow** — top-level YAML in `.github/workflows/`, triggered by events.
- **Job** — a unit of work; jobs run **in parallel** by default on separate runners.
- **Step** — a command or Action inside a job; steps run **sequentially**.
- **Runner** — the machine executing the job (GitHub-hosted or self-hosted).
- **Action** — reusable building block (`actions/checkout`, `actions/setup-node`).

**45. How do you handle large files in Git?**

Git LFS (Large File Storage) replaces large binaries with small pointer files in the repo and stores actual content on an LFS server:

```bash
git lfs install
git lfs track "*.psd" "*.mp4"
git add .gitattributes && git commit -m "Track large files via LFS"
```

Already in history: rewrite with `git filter-repo` or BFG Repo-Cleaner (forces everyone to re-clone).

**46. How do you prevent secrets from leaking into Git history?**

Prevention: `.gitignore`, pre-commit hooks (`detect-secrets`, `gitleaks`), GitHub Secret Scanning + Push Protection, encrypted secrets (SOPS, git-crypt).

Incident response: **rotate the secret first** (assume compromised), then remove from history with `git filter-repo`, force-push, ask all contributors to re-clone.

**47. How do CODEOWNERS files and branch protection rules work?**

`CODEOWNERS` maps path patterns to reviewers — when a PR touches a path, matching owners are auto-requested. Combined with branch protection: require PR reviews, require CI to pass, require signed commits, restrict direct pushes — these enforce policy in code, not just in chat.

**48. What's the difference between three-way merge and recursive merge strategies?**

**Three-way merge**: uses the common ancestor + both tips to produce a merged result. **Recursive** (now replaced by `ort` as default in Git 2.34): when multiple merge bases exist (criss-cross merges), merges the bases first to create a virtual ancestor, then three-way merges. Other strategies: `octopus` (>2 branches), `ours` (keep our side entirely), `subtree` (grafted subtrees).

**49. What is `git filter-repo` / BFG, and when would you use them?**

Both rewrite Git history — to remove secrets, strip large files, or reorganize a repo. `git filter-repo` is the modern recommended tool; BFG is simpler but more limited.

Caveats: rewrites all SHAs (everyone must re-clone); doesn't unleak secrets (rotate first); coordinate with team and force-push during a quiet window.

**50. How do you structure CI/CD with GitHub Actions for a typical app?**

```yaml
jobs:
  lint:       # fast, cheap — runs first
  test:
    needs: lint
    strategy:
      matrix: { node: [18, 20] }    # test multiple versions in parallel
  deploy:
    needs: test
    if: github.ref == 'refs/heads/main'
    environment: production          # manual approval gate
    permissions:
      id-token: write                # OIDC for cloud auth — no static keys
```

Best practices: OIDC over static keys, cache dependencies, `concurrency:` to cancel stale PR runs, pin Action versions to SHA for security-sensitive repos.

---

## Useful Tips & Tricks

- Use `git help <command>` or `git <command> --help` for the full manual; `git <command> -h` for a quick summary.
- Run `git status` constantly — it's the cheapest, safest way to know what's going on.
- Pretty log alias: `git config --global alias.lg "log --oneline --graph --all --decorate"`.
- **Stage by hunk** with `git add -p` for small, focused commits.
- **Recover lost commits** with `git reflog` — Git rarely throws anything away within ~90 days.
- Use `git switch -c` and `git restore` over `git checkout` — they're clearer and harder to misuse.
- Prefer `--force-with-lease` over `--force` when you must rewrite a pushed branch.
- Set `pull.rebase = true` to keep history linear without thinking about it.
- A global `.gitignore_global` keeps editor / OS junk out of every repo: `git config --global core.excludesfile ~/.gitignore_global`.
- For big binary files (assets, datasets), use **Git LFS** (`git lfs track "*.psd"`).
- When stuck in `vim` after `git commit` with no `-m`: type the message, press `Esc`, then `:wq`.

---

## References

- [Free Git & GitHub Crash Course for Beginners](https://www.youtube.com/watch?v=mAFoROnOfHs&t=480s) — YouTube video, great starting point for hands-on learners
- [Git official documentation](https://git-scm.com/doc)
- [Pro Git book (free)](https://git-scm.com/book/en/v2)
- [GitHub Docs](https://docs.github.com/)
- [GitHub CLI docs](https://cli.github.com/manual/)
- [GitHub Actions docs](https://docs.github.com/en/actions)
- [Oh My Git! (interactive game)](https://ohmygit.org/)
- [Choose a License](https://choosealicense.com/)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [BongoDev](https://www.bongodev.com/)
- [BongoDev on GitHub](https://github.com/bongodev)

---

<p align="center">
  <sub>Part of the <a href="../README.md"><b>DevOps Preparation</b></a> repository — maintained by <b>Tahshin Sharon</b></sub>
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/TahshinSharon"><b>GitHub</b></a>
</p>
