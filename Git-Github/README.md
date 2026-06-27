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
</p>

---

> 🎯 **[Common Interview Questions →](#common-interview-questions)** &nbsp;·&nbsp; 50 Git & GitHub interview questions (10 Easy · 20 Medium · 20 Hard) for DevOps junior / mid / senior roles.

---

## Table of Contents

- [Common Interview Questions](#common-interview-questions)
- [Introduction](#introduction)
- [Command Note Template](#command-note-template)
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
  - [Issues, README, LICENSE](#issues-readme-license)
- [Useful Tips & Tricks](#useful-tips--tricks)
- [References](#references)

---

## Introduction

Brief notes about Git, GitHub, and the goal of these notes.

- **Git version:** _e.g., 2.43.0_
- **Platform:** _e.g., GitHub / GitLab / Bitbucket_
- **Goal:** Build strong Git & GitHub fundamentals for DevOps interview prep.

**Git** is a **distributed version control system** — every developer's machine holds a full copy of the project history, and changes are synced through "pushes" and "pulls" rather than locking files on a central server. **GitHub** (and friends like GitLab, Bitbucket) is a **hosting platform** built on top of Git that adds pull requests, issues, code review, CI/CD, and collaboration features.

---

## Command Note Template

Use this format whenever a new command is added.

### `command-name`

**Description:** What the command does in one or two lines.

**Syntax:**

```bash
command-name [options] [arguments]
```

**Common Options:**

| Option | Description                |
| ------ | -------------------------- |
| `-a`   | Example option description |
| `-l`   | Example option description |

**Examples:**

```bash
# Example 1 — short description
command-name -a

# Example 2 — short description
command-name -l /path/to/file
```

**Notes:**

- Any edge cases, gotchas, or related commands.

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

### Version Control

**Version Control** is the practice of tracking changes to files over time so you can revisit earlier versions, see what changed, and work in parallel without overwriting each other.

- **Centralized VCS (CVCS)** — e.g. SVN, Perforce. One server holds the history; clients check files out and commit back.
- **Distributed VCS (DVCS)** — e.g. **Git**, Mercurial. **Every clone is a full repository**, so you can commit, branch, and inspect history offline.

Git tracks **snapshots** of your project, not diffs. Each commit is a complete picture of the project at that moment, identified by a unique SHA-1 hash.

### `git --version`

**Description:** Prints the installed Git version. Quick sanity check that Git is on your `PATH`.

```bash
git --version
```

Outputs something like `git version 2.43.0`.

### `git config`

**Description:** Reads and writes Git configuration — your identity (name, email), editor, default branch name, aliases, etc. Settings live in three scopes:

| Scope    | File                                | Flag         |
| -------- | ----------------------------------- | ------------ |
| System   | `/etc/gitconfig`                    | `--system`   |
| Global   | `~/.gitconfig` or `~/.config/git/config` | `--global`   |
| Local    | `.git/config` (per repo)            | `--local`    |

**Syntax:**

```bash
git config [--global|--local|--system] <key> <value>
git config --list
```

**Common Keys:**

| Key                        | Purpose                                                       |
| -------------------------- | ------------------------------------------------------------- |
| `user.name`                | Your name on commits.                                         |
| `user.email`               | Your email on commits (use the same one as GitHub).           |
| `init.defaultBranch`       | Name of the initial branch on `git init` (e.g. `main`).       |
| `core.editor`              | Editor used for commit messages (e.g. `vim`, `nano`, `code`). |
| `pull.rebase`              | `true` to rebase on pull instead of merging.                  |
| `alias.<name>`             | Define a Git alias (e.g. `alias.co=checkout`).                |

**Examples:**

```bash
# Set your identity once, globally
git config --global user.name "Tarek Mahmud"
git config --global user.email "tarek@example.com"

# Use main as the default branch on new repos
git config --global init.defaultBranch main

# Create a useful alias
git config --global alias.lg "log --oneline --graph --all --decorate"

# List every config value Git is currently using, with its source
git config --list --show-origin
```

**Notes:**

- **Local** config overrides **global**, which overrides **system**.
- Use a per-repo `user.email` (drop `--global`) when contributing under a different identity (e.g. work vs personal).

### `git init`

**Description:** Turns the current directory into a Git repository by creating a hidden `.git/` folder that stores all history and metadata.

**Syntax:**

```bash
git init [directory]
git init -b main          # initial branch named "main"
```

**Examples:**

```bash
mkdir my-project && cd my-project
git init -b main
```

Creates an empty repo on the `main` branch. Add files, then `git add` and `git commit` to record the first snapshot.

**Notes:**

- A repo is just a directory with a `.git/` folder inside — delete `.git/` and it's a plain directory again.
- Use `git init --bare` for **server-side** repos that don't have a working tree (the format used by remotes).

### `git clone`

**Description:** Downloads an existing repository — including its **full history** — to your machine and sets up `origin` as the remote.

**Syntax:**

```bash
git clone <url> [directory]
```

**Common Options:**

| Option              | Description                                                              |
| ------------------- | ------------------------------------------------------------------------ |
| `--depth N`         | **Shallow clone** — only the last N commits (saves space/time).          |
| `--branch <name>`   | Clone and check out a specific branch instead of the default.            |
| `--recurse-submodules` | Also clone any submodules the repo references.                        |

**Examples:**

```bash
git clone https://github.com/torvalds/linux.git
git clone --depth 1 https://github.com/some/big-repo.git
git clone git@github.com:user/repo.git my-folder
```

**Notes:**

- The URL can be **HTTPS** (`https://...`) or **SSH** (`git@host:user/repo.git`). See [SSH vs HTTPS](#ssh-vs-https).
- After cloning, `git remote -v` shows the configured `origin` URL.

### `git status`

**Description:** Shows the current state of the working tree — which files are **staged**, **modified**, or **untracked**, and which branch you are on. The single most useful command for situational awareness.

**Syntax:**

```bash
git status [-s|--short]
```

**Examples:**

```bash
git status
git status -s     # short, machine-friendly format
```

Sample short output:

```
 M  README.md     # modified, staged
 ?? notes.txt     # untracked
 A  newfile.js    # added (staged)
```

**Notes:**

- Run it constantly — before staging, before committing, after merging.
- `git status -sb` adds a branch header to the short output.

### `git help`

**Description:** Opens the manual for any Git subcommand.

**Syntax:**

```bash
git help <command>
git <command> --help
git <command> -h    # short usage
```

**Examples:**

```bash
git help commit
git commit -h
```

Opens the full man page for `git commit` (`git help`) or shows a short usage summary (`-h`).

---

## Working with Changes

The everyday loop: edit files, stage them, commit them, and inspect the history.

### One Shot Revision

| Command                           | Short Description                                                     |
| --------------------------------- | --------------------------------------------------------------------- |
| [The Three Areas](#the-three-areas) | Working directory, staging area (index), and repository (history)   |
| [`git add`](#git-add)             | Stage changes to be included in the next commit                       |
| [`git commit`](#git-commit)       | Record the staged changes as a new commit in history                  |
| [`git diff`](#git-diff)           | Show changes between working dir, staging area, and commits           |
| [`git log`](#git-log)             | Browse commit history with formatting and filtering                   |
| [`git show`](#git-show)           | Show the contents and diff of a specific commit                       |
| [`.gitignore`](#gitignore)        | Tell Git which files to never track                                   |

### The Three Areas

Every file Git knows about lives in one of three places:

| Area                   | What it is                                                                |
| ---------------------- | ------------------------------------------------------------------------- |
| **Working directory**  | The files you see and edit on disk.                                       |
| **Staging area (index)** | A snapshot of changes you've marked for the next commit (`git add`).    |
| **Repository (`.git/`)** | The committed history — immutable snapshots identified by SHA hashes.   |

```
  edit          git add           git commit
   ↓               ↓                  ↓
working dir  →  staging area  →  repository
```

`git restore` / `git reset` are the commands that move changes **backwards** through these areas.

### `git add`

**Description:** **Stages** changes from the working directory into the staging area so they'll be part of the next commit. You can stage entire files, individual chunks (hunks), or everything at once.

**Syntax:**

```bash
git add [options] <pathspec>...
```

**Common Options:**

| Option   | Description                                                                |
| -------- | -------------------------------------------------------------------------- |
| `.`      | Stage **all** changes in the current directory and below.                  |
| `-A`     | Stage **all** changes in the whole repo (including deletions).             |
| `-u`     | Stage **updates/deletions** to tracked files only (skip new untracked).    |
| `-p`     | **Patch mode** — interactively pick which hunks to stage.                  |
| `-n`     | **Dry run** — show what would be added without actually staging.           |

**Examples:**

```bash
git add README.md             # stage a single file
git add src/                  # stage everything under src/
git add .                     # stage all changes from the current dir down
git add -A                    # stage everything, including deletions, repo-wide
git add -p                    # review and stage hunks interactively
```

**Notes:**

- Files must be **staged** before they can be committed.
- `git add -p` is one of Git's superpowers — split a messy working tree into small, focused commits.

### `git commit`

**Description:** Records the **staged** changes as a new commit in the repository. Each commit is a snapshot identified by a unique SHA hash and tied to your name/email and a message.

**Syntax:**

```bash
git commit [options]
```

**Common Options:**

| Option            | Description                                                                |
| ----------------- | -------------------------------------------------------------------------- |
| `-m "msg"`        | Provide the commit message inline (no editor).                             |
| `-a`              | Auto-stage **modified/deleted tracked** files, then commit.                |
| `-am "msg"`       | Combine `-a` and `-m` (most common shortcut for quick commits).            |
| `--amend`         | **Replace** the last commit (edit message or add forgotten changes).       |
| `--no-edit`       | Use with `--amend` to keep the previous message unchanged.                 |
| `-s` / `--signoff` | Append a `Signed-off-by:` line — required by some projects (e.g. kernel). |
| `-S`              | **GPG-sign** the commit.                                                   |

**Examples:**

```bash
git commit -m "Add user authentication"
git commit -am "Fix typo in README"          # stage + commit tracked files
git commit --amend -m "Better message"        # rewrite last commit message
git commit --amend --no-edit                  # add extra staged changes to the last commit
```

**Writing good commit messages:**

```
<type>: <short subject line, ≤50 chars, imperative mood>

<optional body — wrap at ~72 chars. Explain the WHY, not the HOW.>
```

Common types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`. Example: `feat: add OAuth login flow`.

**Notes:**

- **Never amend a commit you've already pushed** to a shared branch — it rewrites history and forces collaborators to reset.
- Empty commits are allowed with `--allow-empty` (sometimes useful for triggering CI).

### `git diff`

**Description:** Shows differences — between the working dir and staging, between staging and the last commit, between two commits, between two branches, etc.

**Syntax:**

```bash
git diff [options] [<commit>] [<commit>] [-- <path>...]
```

**Common Forms:**

| Form                            | What it shows                                                              |
| ------------------------------- | -------------------------------------------------------------------------- |
| `git diff`                      | Working dir vs **staging** (unstaged changes).                             |
| `git diff --staged` (or `--cached`) | Staging vs **last commit** (what `git commit` would record).           |
| `git diff HEAD`                 | Working dir vs **last commit** (all uncommitted changes).                  |
| `git diff <a> <b>`              | Differences between two commits / branches / tags.                         |
| `git diff main..feature`        | Changes on `feature` since it diverged from `main`.                        |
| `git diff --stat`               | Summary of changed files with insertion/deletion counts.                   |
| `git diff --name-only`          | Just the list of changed files.                                            |

**Examples:**

```bash
git diff                          # what have I changed since I last staged?
git diff --staged                 # what will be in my next commit?
git diff HEAD~3 HEAD              # what changed in the last 3 commits?
git diff main feature -- src/     # diff src/ between two branches
```

**Notes:**

- Use `git difftool` to open changes in a graphical diff viewer (`meld`, `vimdiff`, VS Code).
- `git diff --word-diff` is great for prose / docs changes.

### `git log`

**Description:** Browses the commit history of the current branch. Highly customizable via formatting flags.

**Syntax:**

```bash
git log [options] [<revision range>] [-- <path>...]
```

**Common Options:**

| Option                    | Description                                                            |
| ------------------------- | ---------------------------------------------------------------------- |
| `--oneline`               | One line per commit (short hash + subject).                            |
| `--graph`                 | Draw an ASCII graph of branch/merge history.                           |
| `--all`                   | Include commits from **all branches**, not just the current one.       |
| `--decorate`              | Show branch/tag names next to commits.                                 |
| `-n N` / `-N`             | Limit to the last N commits.                                           |
| `--author="name"`         | Filter by author.                                                      |
| `--since="2 weeks ago"`   | Filter by date.                                                        |
| `--grep="fix"`            | Filter by commit message content.                                      |
| `-p`                      | Show the **patch** (diff) of each commit.                              |
| `--stat`                  | Show changed-files summary for each commit.                            |
| `-- <path>`               | Only commits that touched a specific file/directory.                   |

**Examples:**

```bash
git log --oneline --graph --all --decorate    # pretty visual history
git log -p -- README.md                        # full history of README.md with diffs
git log --author="Tarek" --since="1 month ago"
git log v1.0..v2.0                             # commits between two tags
```

**Notes:**

- Save the pretty form as an alias: `git config --global alias.lg "log --oneline --graph --all --decorate"` → now `git lg` works.
- For "what changed on this branch only", use `git log main..HEAD`.

### `git show`

**Description:** Shows the details (metadata + diff) of a specific commit, tag, or other Git object.

**Syntax:**

```bash
git show [<commit>]
```

**Examples:**

```bash
git show                       # last commit
git show HEAD~2                # commit 2 before HEAD
git show abc1234               # commit by short SHA
git show HEAD:path/to/file     # contents of file at HEAD (read-only)
```

**Notes:**

- Useful for code review — `git show <sha>` is exactly what reviewers look at when discussing a commit.

### `.gitignore`

**Description:** A plain text file at the repo root (or any subdirectory) that tells Git **which files to never track**. Patterns are matched relative to the location of the `.gitignore`.

**Format:**

```gitignore
# Comments start with #

# Ignore a specific file
secrets.env

# Ignore everything in a directory
node_modules/
dist/

# Ignore by extension
*.log
*.tmp

# Negate a rule — DO track this file even if a broader rule excludes it
!important.log

# Match in any directory
**/*.cache

# Only at repo root (leading slash)
/build
```

**Examples:**

```bash
# Common starting .gitignore for a Node.js project
node_modules/
.env
.env.*
dist/
coverage/
*.log
.DS_Store
```

**Notes:**

- `.gitignore` only affects **untracked** files. To stop tracking a file that was previously committed, run `git rm --cached <file>` first, then add it to `.gitignore`.
- Get sensible templates from [github.com/github/gitignore](https://github.com/github/gitignore) (one per language/tool).
- A **global** ignore file is useful for editor / OS junk: `git config --global core.excludesfile ~/.gitignore_global`.

---

## Branching & Merging

Branches are how you isolate work without affecting `main`. Merging (or rebasing) is how you bring that work back together.

### One Shot Revision

| Command                             | Short Description                                                  |
| ----------------------------------- | ------------------------------------------------------------------ |
| [Branches](#branches)               | What a branch is in Git and why it's so cheap                      |
| [`git branch`](#git-branch)         | List, create, rename, or delete branches                           |
| [`git checkout`](#git-checkout)     | Switch branches or restore files (legacy combined command)         |
| [`git switch`](#git-switch)         | Switch branches — the modern, dedicated command                    |
| [`git merge`](#git-merge)           | Combine another branch's changes into the current branch           |
| [`git rebase`](#git-rebase)         | Reapply commits on top of another base for a linear history        |
| [`git cherry-pick`](#git-cherry-pick) | Apply a specific commit from one branch onto another             |

### Branches

A **branch** in Git is nothing more than a **movable pointer to a commit**. The default branch is usually `main` (older repos used `master`). `HEAD` is a special pointer to the branch (and through it, the commit) you currently have checked out.

```
main:     A → B → C
                  ↑
                 HEAD
```

Create a branch and commit on it:

```
main:     A → B → C
                  ↘
feature:           D → E
                       ↑
                      HEAD
```

Because a branch is just a pointer (a few bytes in `.git/refs/heads/`), creating, switching, and deleting branches is **instantaneous** — there is no copying of files involved.

### `git branch`

**Description:** Manages branches — lists, creates, renames, and deletes them.

**Syntax:**

```bash
git branch [options] [<branch>]
```

**Common Options:**

| Option        | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| (no arg)      | List local branches (current marked with `*`).                           |
| `-a`          | List **all** branches, including remote-tracking (`origin/...`).         |
| `-r`          | List **only** remote-tracking branches.                                  |
| `-v`          | Verbose — show last commit SHA + message for each branch.                |
| `<name>`      | Create a new branch from `HEAD` (does **not** switch to it).             |
| `-d <name>`   | Delete a branch (safe — refuses if it has unmerged commits).             |
| `-D <name>`   | **Force** delete (use with caution).                                     |
| `-m <new>`    | Rename the current branch.                                               |
| `--merged`    | List branches already merged into the current one (safe to delete).      |

**Examples:**

```bash
git branch                            # list local branches
git branch -av                        # all branches with last commit info
git branch feature/login              # create a new branch from HEAD
git branch -d old-feature             # delete a merged branch
git branch -m main                    # rename current branch to main
```

**Notes:**

- Creating a branch and switching to it in one go: `git switch -c new-branch` (or `git checkout -b new-branch`).
- A common convention: short, lowercase, kebab-case names with optional namespace — `feature/login`, `fix/null-pointer`, `chore/upgrade-deps`.

### `git checkout`

**Description:** The original Swiss-army-knife command — switches branches **and** restores files from a commit. In Git 2.23+ its responsibilities were split into the dedicated `git switch` and `git restore`, but `checkout` still works everywhere.

**Syntax:**

```bash
git checkout <branch>
git checkout -b <new-branch>
git checkout <commit> -- <path>
```

**Examples:**

```bash
git checkout main                    # switch to main
git checkout -b feature/auth         # create and switch to feature/auth
git checkout HEAD~1 -- README.md     # restore README.md to its state 1 commit ago
git checkout abc1234                 # detached HEAD — inspect an old commit
```

**Notes:**

- Switching to a commit SHA puts you in **detached HEAD** state — any commits you make won't belong to a branch and may be lost. Run `git switch -c new-branch` to save them.
- Prefer `git switch` (branches) and `git restore` (files) in new workflows — they're harder to misuse.

### `git switch`

**Description:** Modern, dedicated command for **switching branches**. Introduced in Git 2.23 to split off the "switch branch" part of `git checkout`.

**Syntax:**

```bash
git switch [options] <branch>
```

**Common Options:**

| Option         | Description                                                       |
| -------------- | ----------------------------------------------------------------- |
| `-c <name>`    | **Create** a new branch and switch to it.                         |
| `-C <name>`    | Force-create (reset if branch already exists).                    |
| `-`            | Switch to the **previous** branch (like `cd -`).                  |
| `--detach <ref>` | Explicitly enter detached HEAD on a commit.                     |

**Examples:**

```bash
git switch main
git switch -c feature/payments
git switch -                       # back to the branch you were just on
```

**Notes:**

- `git switch` will refuse to leave a branch with uncommitted changes that would conflict — use `git stash` or commit first.

### `git merge`

**Description:** Combines another branch's commits into the current branch by creating a **merge commit** (or fast-forwarding if no divergence).

**Syntax:**

```bash
git merge [options] <branch>
```

**Common Options:**

| Option            | Description                                                                |
| ----------------- | -------------------------------------------------------------------------- |
| `--no-ff`         | Always create a merge commit, even if a fast-forward is possible.          |
| `--ff-only`       | Refuse to merge unless it can be done as a fast-forward (no merge commit). |
| `--squash`        | Combine all commits from the other branch into **one** new commit.         |
| `--abort`         | Abort an in-progress merge with conflicts and restore the pre-merge state. |
| `--continue`      | Continue after resolving conflicts.                                        |

**Merge types:**

| Type                | When it happens                                                              |
| ------------------- | ---------------------------------------------------------------------------- |
| **Fast-forward**    | The current branch is a direct ancestor of the target — Git just moves the pointer forward. No merge commit. |
| **Three-way merge** | Branches diverged — Git uses the common ancestor + both tips to compute a merge, creating a new merge commit. |
| **Conflict**        | Both sides edited the same lines — Git stops and asks you to resolve manually. |

**Examples:**

```bash
git checkout main
git merge feature/login              # merge feature/login into main

git merge --no-ff feature/login      # always create a merge commit (preserves branch history)
git merge --squash feature/login     # collapse to one commit, then commit it yourself
git merge --abort                    # bail out of a conflicted merge
```

**Resolving conflicts:**

When Git can't auto-merge, it marks conflicted regions in the file:

```
<<<<<<< HEAD
your version
=======
their version
>>>>>>> feature/login
```

Edit the file to keep what you want, remove the conflict markers, then:

```bash
git add <file>
git commit            # finishes the merge
```

**Notes:**

- Use `git log --merges` to see only merge commits.
- `git mergetool` opens conflicts in a graphical resolver (`meld`, `vimdiff`, VS Code, etc.).

### `git rebase`

**Description:** **Replays** the commits of the current branch on top of another branch's tip — producing a **linear** history without merge commits. Cleaner log, but **rewrites history** (commit SHAs change).

**Syntax:**

```bash
git rebase [options] <base>
git rebase -i <base>          # interactive — edit, squash, drop, reorder commits
```

**Common Options:**

| Option        | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| `-i`          | **Interactive** rebase — pick / reword / squash / fixup / drop commits.  |
| `--continue`  | Continue after resolving a conflict during rebase.                       |
| `--abort`     | Abort and restore the pre-rebase state.                                  |
| `--skip`      | Skip the current patch (use carefully — it discards that commit's changes). |
| `--onto`      | Rebase a range of commits onto a different base (advanced).              |

**Examples:**

```bash
# Update feature branch on top of latest main
git checkout feature/login
git fetch origin
git rebase origin/main

# Interactively clean up the last 5 commits before opening a PR
git rebase -i HEAD~5
```

Inside `-i`, you'll see a list like:

```
pick a1b2c3 first commit
pick d4e5f6 second commit
pick 7g8h9i typo fix
```

Change `pick` to `squash` / `s` (combine with previous), `reword` / `r` (edit message), `drop` / `d` (delete commit), or reorder lines.

**Notes:**

- **Golden rule of rebase: never rebase commits you've already pushed to a shared branch.** Rebasing rewrites history; collaborators will see conflicts and broken refs.
- Rebase is great for **your own** feature branches before merging — it produces a clean, linear PR.
- Conflicts during rebase are resolved one commit at a time: fix → `git add` → `git rebase --continue`.

### `git cherry-pick`

**Description:** Applies the **changes from a specific commit** onto the current branch as a new commit. Useful for backporting fixes between branches.

**Syntax:**

```bash
git cherry-pick <commit>...
```

**Examples:**

```bash
git cherry-pick abc1234                # apply one commit
git cherry-pick abc1234 def5678        # apply two commits, in order
git cherry-pick A..B                   # apply a range (A excluded, B included)
git cherry-pick --continue             # after resolving conflicts
git cherry-pick --abort                # bail out
```

**Notes:**

- The cherry-picked commit gets a **new SHA** — it's a new commit with the same diff.
- If the original commit doesn't apply cleanly, you'll get conflicts to resolve like a merge/rebase.

---

## Remote Repositories

A **remote** is a named pointer to a copy of your repo hosted elsewhere (usually on GitHub/GitLab). Push, pull, fetch, and clone all talk to remotes.

### One Shot Revision

| Command                          | Short Description                                                  |
| -------------------------------- | ------------------------------------------------------------------ |
| [Remotes](#remotes)              | What a remote is and what `origin` and `upstream` mean             |
| [`git remote`](#git-remote)      | List, add, rename, or remove remotes                               |
| [`git fetch`](#git-fetch)        | Download commits/refs from a remote — does **not** modify your branches |
| [`git pull`](#git-pull)          | `fetch` + `merge` (or `rebase`) in one step                        |
| [`git push`](#git-push)          | Send your local commits to a remote                                |
| [SSH vs HTTPS](#ssh-vs-https)    | The two ways to authenticate with a Git host                       |

### Remotes

A **remote** is a named URL pointing to another copy of the repo. Each remote has tracking branches like `origin/main` that mirror what the remote looked like the last time you `fetched`.

| Name        | Convention                                                                   |
| ----------- | ---------------------------------------------------------------------------- |
| `origin`    | The default name for the remote you cloned from.                             |
| `upstream`  | Common convention for the **original** repo when working from a **fork**.    |

A repo can have **many** remotes (`origin`, `upstream`, `staging`, `backup`, ...).

### `git remote`

**Description:** Manages the list of remote repositories your local repo knows about.

**Syntax:**

```bash
git remote [-v]
git remote add <name> <url>
git remote rename <old> <new>
git remote remove <name>
git remote set-url <name> <new-url>
```

**Examples:**

```bash
git remote -v                                       # show remotes with their URLs
git remote add origin git@github.com:me/repo.git
git remote add upstream https://github.com/orig/repo.git
git remote set-url origin git@github.com:me/repo.git
git remote remove old-server
```

**Notes:**

- `git remote -v` shows two entries per remote — one for `fetch` and one for `push` (they can differ).
- After `git remote add`, run `git fetch <name>` to download its refs.

### `git fetch`

**Description:** Downloads new commits, branches, and tags **from a remote** into your local repo as remote-tracking branches (`origin/main`, `origin/feature`, ...). It does **not** touch your working branches — completely safe.

**Syntax:**

```bash
git fetch [<remote>] [<branch>]
git fetch --all
git fetch --prune        # remove tracking branches whose remote was deleted
```

**Examples:**

```bash
git fetch origin                # update all origin/* tracking branches
git fetch --all --prune         # update everything, drop dead branches
git fetch origin main:main      # also fast-forward local main if possible
```

**Notes:**

- After `fetch`, compare your local branch to its upstream with `git log HEAD..origin/main`.
- Fetch first, then decide whether to merge or rebase — `pull` does both in one step but hides the decision.

### `git pull`

**Description:** Shortcut for `git fetch` + `git merge` (or `git rebase`, if configured). Brings your **current branch** up to date with its upstream.

**Syntax:**

```bash
git pull [<remote>] [<branch>]
git pull --rebase
git pull --ff-only
```

**Common Options:**

| Option        | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| `--rebase`    | After fetching, rebase your local commits on top of the remote.          |
| `--ff-only`   | Refuse to pull unless it can fast-forward (avoids accidental merges).    |
| `--no-rebase` | Force a merge even if `pull.rebase=true` is configured.                  |

**Examples:**

```bash
git pull                                 # default behaviour (merge or rebase per config)
git pull --rebase origin main            # cleaner: rebase local commits on top of remote
git pull --ff-only                       # safest: only update if no divergence
```

**Notes:**

- Many teams set `git config --global pull.rebase true` to keep history linear.
- If `pull` causes conflicts, resolve them like a normal merge/rebase, then `git pull` is finished.

### `git push`

**Description:** Sends commits from a local branch to a remote.

**Syntax:**

```bash
git push [<remote>] [<branch>]
git push -u <remote> <branch>         # set upstream tracking on first push
git push --tags                       # also push tags
git push --force-with-lease           # safer "force push"
```

**Common Options:**

| Option                | Description                                                         |
| --------------------- | ------------------------------------------------------------------- |
| `-u` / `--set-upstream` | Link the local branch to a remote branch so future `git push` / `pull` need no args. |
| `--force` / `-f`      | **Overwrite** the remote branch with your local one — destructive.  |
| `--force-with-lease`  | Force-push **only if** the remote hasn't moved since your last fetch — much safer than plain `--force`. |
| `--delete <branch>`   | Delete a branch on the remote (`git push origin --delete old-feature`). |
| `--tags`              | Push tags as well as commits.                                       |

**Examples:**

```bash
git push                              # push current branch to its tracked remote
git push -u origin feature/login      # first push of a new branch
git push origin --delete old-feature  # delete a remote branch
git push --force-with-lease           # safely rewrite remote after a rebase
```

**Notes:**

- **Never `--force` push to a shared branch (e.g. `main`)** — you'll wipe collaborators' work. Use `--force-with-lease` after a rebase on your **own** feature branches only.
- `git push -u origin HEAD` pushes the current branch by name without typing it.

### SSH vs HTTPS

Both protocols clone, fetch, and push the same way — they differ in **how you authenticate**.

| Protocol  | URL form                                | Auth method                            |
| --------- | --------------------------------------- | -------------------------------------- |
| **HTTPS** | `https://github.com/user/repo.git`      | Username + Personal Access Token (PAT) — cached by the OS keychain / Git Credential Manager. |
| **SSH**   | `git@github.com:user/repo.git`          | An SSH keypair on your machine, public half uploaded to your Git host account. |

**When to use which:**

- **HTTPS** — easier on networks with restrictive firewalls (port 443), common on Windows.
- **SSH** — no password prompts once set up, ideal for daily work and servers.

Switch a repo between them at any time with `git remote set-url`:

```bash
git remote set-url origin git@github.com:me/repo.git
```

See [SSH Keys](#ssh-keys) for how to generate one.

---

## Undoing Changes

Git tracks everything, so almost any action is reversible — **if** you know which "undo" you need.

### One Shot Revision

| Command                       | Short Description                                                    |
| ----------------------------- | -------------------------------------------------------------------- |
| [`git restore`](#git-restore) | Undo changes in the working dir or unstage files (modern, safe)      |
| [`git reset`](#git-reset)     | Move the branch pointer — soft / mixed / hard rewrites of state      |
| [`git revert`](#git-revert)   | Create a **new** commit that undoes a previous one (history-safe)    |
| [`git clean`](#git-clean)     | Delete **untracked** files from the working directory                |
| [`git reflog`](#git-reflog)   | Log of every move `HEAD` has made — your safety net for "I lost it!" |

### `git restore`

**Description:** Restores files in the **working directory** or **staging area**. The modern, dedicated command for the "undo a change to a file" part of the old `git checkout`.

**Syntax:**

```bash
git restore [options] <pathspec>...
```

**Common Options:**

| Option           | Description                                                              |
| ---------------- | ------------------------------------------------------------------------ |
| (default)        | Restore the working-tree file from the **staging area** (discard unstaged changes). |
| `--staged`       | **Unstage** a file — keep the working-dir content, remove it from the index. |
| `--source <ref>` | Restore from a specific commit / branch instead of the index.            |
| `--worktree`     | Restore the working tree (implicit default).                             |

**Examples:**

```bash
git restore README.md                    # throw away unstaged edits to README.md
git restore --staged config.yml          # unstage config.yml (keep edits)
git restore --source HEAD~3 -- src/app.js # bring back src/app.js as it was 3 commits ago
```

**Notes:**

- Discarding working-dir changes is **destructive** — there is no undo. Stash first if unsure: `git stash`.
- Use `git restore --staged <file>` instead of the old `git reset HEAD <file>`.

### `git reset`

**Description:** Moves the **branch pointer** (and optionally the index and working tree) to a different commit. The most powerful undo — and the easiest to misuse.

**Syntax:**

```bash
git reset [--soft|--mixed|--hard] <commit>
git reset HEAD <file>          # unstage a file (old style — prefer `git restore --staged`)
```

**Modes:**

| Mode      | Branch ptr | Staging area | Working dir | When to use                                                  |
| --------- | ---------- | ------------ | ----------- | ------------------------------------------------------------ |
| `--soft`  | moved      | kept         | kept        | Undo last commit but keep changes staged for re-committing.  |
| `--mixed` (default) | moved | reset    | kept        | Undo commit AND unstage, but keep file edits.                |
| `--hard`  | moved      | reset        | reset       | **Discard** everything — commits, staged changes, file edits. |

**Examples:**

```bash
git reset --soft HEAD~1               # undo last commit, keep changes staged
git reset HEAD~1                      # (--mixed) undo last commit, keep edits unstaged
git reset --hard HEAD~1               # 💀 throw away last commit AND changes
git reset --hard origin/main          # 💀 force local branch to match remote exactly
```

**Notes:**

- **`--hard` is destructive** — but if you regret it within ~90 days, the commits are usually still recoverable via `git reflog`.
- **Never `git reset` commits you've already pushed** to a shared branch; use `git revert` instead.
- "Unstage a file" is now better expressed as `git restore --staged <file>`.

### `git revert`

**Description:** Creates a **new commit** whose changes are the **inverse** of an existing commit. The history-safe way to undo something that's already been pushed.

**Syntax:**

```bash
git revert <commit>
```

**Examples:**

```bash
git revert HEAD                  # undo the last commit by adding an inverse commit
git revert abc1234               # undo a specific commit by SHA
git revert HEAD~3..HEAD          # revert a range of commits (creates one new commit per)
git revert -m 1 <merge-sha>      # revert a merge commit (pick the "mainline" parent)
```

**Notes:**

- `revert` **adds** history rather than rewriting it — safe for shared branches.
- If the revert conflicts, resolve like a merge, then `git revert --continue`.

### `git clean`

**Description:** Deletes **untracked** files from the working directory. Permanent — these files aren't in Git, so they cannot be recovered.

**Syntax:**

```bash
git clean [options]
```

**Common Options:**

| Option | Description                                                              |
| ------ | ------------------------------------------------------------------------ |
| `-n`   | **Dry run** — list what would be deleted without deleting.               |
| `-f`   | **Force** — actually delete (required, as a safety guard).               |
| `-d`   | Also remove untracked **directories**.                                   |
| `-x`   | Also delete files ignored by `.gitignore` (e.g. `node_modules/`).        |
| `-i`   | **Interactive** mode — confirm each item before deletion.                |

**Examples:**

```bash
git clean -n                # preview what would be removed
git clean -fd               # remove untracked files AND directories
git clean -fdx              # also wipe .gitignore'd stuff (deep cleanup)
git clean -i                # interactive — safest
```

**Notes:**

- Always run `git clean -n` first to see what you're about to delete.
- Great for resetting a build mess: `git reset --hard && git clean -fdx` → pristine working tree.

### `git reflog`

**Description:** A local-only log of **every move `HEAD` has made** — every commit, reset, rebase, checkout, etc. Git keeps reflog entries for ~90 days by default. It's your safety net for "I just `reset --hard`-ed away my work!"

**Syntax:**

```bash
git reflog [show]
```

**Examples:**

```bash
git reflog                     # see every HEAD move
git reset --hard HEAD@{2}      # restore HEAD to where it was "2 moves ago"

# Real-world rescue: I lost a branch after a bad rebase
git reflog                          # find the SHA of the commit I want back
git checkout -b recovered abc1234   # resurrect it as a new branch
```

**Notes:**

- Reflog is **local** — it doesn't sync with remotes. It exists on the machine where the commits were made.
- Reflog entries expire (default: 90 days for reachable, 30 for unreachable) — recover quickly.
- Old commits become eligible for garbage collection (`git gc`) once they fall out of the reflog.

---

## Stashing & Tagging

Two everyday tools: **stash** to set aside in-progress changes, **tag** to mark releases.

### One Shot Revision

| Command                     | Short Description                                                |
| --------------------------- | ---------------------------------------------------------------- |
| [`git stash`](#git-stash)   | Park uncommitted changes so the working dir is clean             |
| [`git tag`](#git-tag)       | Create lightweight or annotated tags (usually for releases)      |

### `git stash`

**Description:** Temporarily saves your uncommitted changes (tracked files) to a stack, leaving a clean working directory. Useful when you need to switch branches mid-task without committing half-done work.

**Syntax:**

```bash
git stash [push] [-m "message"]
git stash list
git stash show [<stash>]
git stash pop [<stash>]
git stash apply [<stash>]
git stash drop [<stash>]
git stash clear
```

**Common Subcommands:**

| Command                  | What it does                                                              |
| ------------------------ | ------------------------------------------------------------------------- |
| `git stash`              | Push your current changes onto the stash stack (with default message).    |
| `git stash push -m "msg"` | Stash with a descriptive message.                                        |
| `git stash list`         | List all stashes (`stash@{0}` is the most recent).                        |
| `git stash show -p`      | Show the diff of the top stash.                                           |
| `git stash pop`          | Re-apply the top stash and **remove** it from the stack.                  |
| `git stash apply`        | Re-apply the top stash but **keep** it on the stack.                      |
| `git stash drop stash@{1}` | Delete a specific stash.                                                |
| `git stash clear`        | Delete **all** stashes (irreversible).                                    |
| `git stash -u`           | Also stash **untracked** files.                                           |
| `git stash --keep-index` | Stash unstaged changes only; keep staged ones in place.                   |

**Examples:**

```bash
git stash push -m "WIP: refactor login form"
git checkout main && git pull
git switch feature/login
git stash pop                          # bring back the WIP

git stash list
# stash@{0}: On feature/login: WIP: refactor login form

git stash show -p stash@{0}            # view changes
```

**Notes:**

- `pop` can conflict with current changes — resolve and `git stash drop` if needed.
- Stashes are local; they aren't pushed to remotes.

### `git tag`

**Description:** Marks a specific commit with a **name** — usually used to label releases (`v1.0.0`, `v2.3.1`). Tags don't move once created.

**Syntax:**

```bash
git tag                              # list tags
git tag <name>                       # lightweight tag at HEAD
git tag -a <name> -m "msg"           # annotated tag (recommended for releases)
git tag -a <name> <commit>           # tag a specific commit
git tag -d <name>                    # delete local tag
git push origin <name>               # push a single tag
git push origin --tags               # push all tags
git push origin --delete <name>      # delete tag on remote
```

**Tag types:**

| Type            | Stored as                          | Has metadata?                            |
| --------------- | ---------------------------------- | ---------------------------------------- |
| **Lightweight** | Just a ref pointing to a commit    | No — like a sticky note on the commit.   |
| **Annotated**   | Full Git object with author/date/message | Yes — used for **signed/published releases**. |

**Examples:**

```bash
git tag v1.0.0                                     # lightweight tag at HEAD
git tag -a v1.0.0 -m "Release 1.0.0"               # annotated tag
git tag -a v0.9.0 abc1234 -m "Backdated tag"       # tag an older commit
git push origin v1.0.0                             # share it with the world
git push origin --tags                             # push every tag

# Inspect
git show v1.0.0
git tag -l "v1.*"                                  # list matching tags
```

**Notes:**

- Use **annotated tags for releases** — they carry the tagger's name, date, and a message that release tools (GitHub Releases, npm publish) display.
- Tags are **not pushed automatically** with `git push` — you must push them explicitly.
- **Semantic Versioning** (`MAJOR.MINOR.PATCH`) is the most common tag convention: `v1.4.2`.

---

## Advanced Git

Power-tools you don't reach for every day, but which are invaluable when you need them.

### One Shot Revision

| Command                          | Short Description                                                |
| -------------------------------- | ---------------------------------------------------------------- |
| [`git bisect`](#git-bisect)      | Binary-search the history for the commit that introduced a bug   |
| [`git blame`](#git-blame)        | Show who last modified each line of a file                       |
| [`git submodule`](#git-submodule) | Embed another Git repo inside your repo at a fixed commit       |
| [`git worktree`](#git-worktree)  | Check out multiple branches of one repo into separate dirs       |
| [`git hooks`](#git-hooks)        | Run scripts automatically on Git events (pre-commit, pre-push, ...) |

### `git bisect`

**Description:** Performs a **binary search** through commits to find the one that introduced a bug. You tell Git a known-good commit and a known-bad commit; it checks out a midpoint, you test, and mark it good/bad — Git narrows down until it identifies the culprit.

**Syntax:**

```bash
git bisect start
git bisect bad <bad-commit>          # often just HEAD
git bisect good <good-commit>        # last commit known to work
# Git checks out a midpoint commit. Test. Then:
git bisect good   # or
git bisect bad
# Repeat until Git prints the first bad commit.
git bisect reset                     # return to your original branch
```

**Example session:**

```bash
git bisect start
git bisect bad                       # current HEAD is broken
git bisect good v1.0                 # v1.0 worked fine
# Git checks out a commit halfway between. Test the build.
# Bug still there → git bisect bad
# Bug gone     → git bisect good
# ... a few rounds later:
# "abc1234 is the first bad commit"
git bisect reset
```

**Notes:**

- Automate with `git bisect run <script>` — Git runs the script on each step and uses its exit code (0 = good, non-zero = bad).
- Works on `O(log N)` commits — narrowing 1,000 commits takes ~10 steps.

### `git blame`

**Description:** For each line of a file, shows the **commit, author, and timestamp** of the last change. Great for archaeology — "who wrote this line and when?"

**Syntax:**

```bash
git blame [options] <file>
```

**Common Options:**

| Option           | Description                                                                |
| ---------------- | -------------------------------------------------------------------------- |
| `-L <start>,<end>` | Limit to a line range.                                                   |
| `-w`             | Ignore whitespace changes.                                                 |
| `-C` / `-M`      | Detect lines moved/copied from other files/commits.                        |
| `--since=<date>` | Only show commits newer than `<date>`.                                     |

**Examples:**

```bash
git blame README.md
git blame -L 10,30 src/auth.go        # blame lines 10-30
git blame -w -C config.yml            # ignore whitespace and detect moves
```

**Notes:**

- Most editors (VS Code, JetBrains, Neovim) integrate blame inline with plugins like **GitLens**.
- On GitHub, click the "Blame" button on any file to see the same info graphically.

### `git submodule`

**Description:** Embeds another Git repository inside your repo at a **specific commit**. Useful for vendoring shared libraries while keeping their history separate.

**Syntax:**

```bash
git submodule add <url> [<path>]
git submodule init
git submodule update [--recursive]
git clone --recurse-submodules <url>     # clone with submodules in one step
git submodule update --remote            # pull latest from each submodule's tracked branch
git submodule deinit <path>              # remove a submodule
```

**Examples:**

```bash
git submodule add https://github.com/example/lib.git vendor/lib
git commit -m "Add lib as submodule"

# Someone else clones your repo
git clone --recurse-submodules <your-repo>

# Update submodules to the commits recorded in the parent repo
git submodule update --init --recursive
```

**Notes:**

- Submodules pin to a **specific commit**, not a branch — that commit SHA is stored in the parent repo.
- They can be confusing in teams — many projects prefer **monorepos**, **subtree merges**, or package managers (npm/Cargo/Go modules) instead.
- `.gitmodules` at the repo root records the submodule's URL and path.

### `git worktree`

**Description:** Lets you check out **multiple branches** of one repo into **separate directories** simultaneously, sharing the same `.git/` storage. No more `git stash` just to peek at another branch.

**Syntax:**

```bash
git worktree add <path> <branch>
git worktree list
git worktree remove <path>
git worktree prune
```

**Examples:**

```bash
git worktree add ../repo-feature feature/login    # check out feature/login next door
git worktree add -b hotfix ../hotfix main         # new branch hotfix from main
git worktree list
git worktree remove ../repo-feature
```

**Notes:**

- Each worktree has its own working dir and `HEAD`, but shares objects with the main repo — much cheaper than cloning twice.
- Great for: running tests on a different branch while editing another, code review without stashing, hotfixes during long-running features.

### `git hooks`

**Description:** Shell scripts that Git runs **automatically** at specific points in the workflow. They live in `.git/hooks/` and are not version-controlled by default.

**Common hooks:**

| Hook              | Fires                                                            |
| ----------------- | ---------------------------------------------------------------- |
| `pre-commit`      | Before a commit is finalized — run linters, formatters, tests.  |
| `commit-msg`      | After the commit message is written — enforce message format.   |
| `pre-push`        | Before `git push` — run the full test suite, block bad pushes.  |
| `post-merge`      | After `git merge` — auto-install dependencies, rebuild.         |
| `pre-receive` / `post-receive` | Server-side — enforce policies on pushes.          |

**Example — block commits with debugging leftovers:**

```bash
#!/usr/bin/env bash
# .git/hooks/pre-commit
if git diff --cached | grep -E "(console\.log|debugger|TODO_BLOCK)"; then
  echo "✋ Found debug artifacts. Remove them before committing."
  exit 1
fi
```

Make it executable: `chmod +x .git/hooks/pre-commit`.

**Notes:**

- `.git/hooks/` is **not committed** — share hooks with your team using tools like **Husky** (Node), **pre-commit** (Python, multi-language), or **lefthook** (Go).
- Skip hooks for a one-off with `git commit --no-verify` (use sparingly — it bypasses the safety net).

---

## GitHub & Collaboration

The collaboration layer on top of Git: authentication, pull requests, CI, and the GitHub CLI.

### One Shot Revision

| Topic                                       | Short Description                                                |
| ------------------------------------------- | ---------------------------------------------------------------- |
| [SSH Keys](#ssh-keys)                       | Generate a keypair and connect to GitHub without passwords       |
| [Forks & Pull Requests](#forks--pull-requests) | The standard open-source workflow                             |
| [GitHub CLI (gh)](#github-cli-gh)           | Manage PRs, issues, releases from your terminal                  |
| [GitHub Actions](#github-actions)           | Native CI/CD — run workflows on push, PR, schedules              |
| [Issues, README, LICENSE](#issues-readme-license) | The "social" files every public repo needs                |

### SSH Keys

**Description:** Public-key cryptography lets GitHub identify you **without a password** on every push. You generate a **keypair** locally, keep the **private** key secret, and upload the **public** key to GitHub.

**Generate a key (Ed25519 — modern, fast, secure):**

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press `Enter` to accept the default path (`~/.ssh/id_ed25519`). Optionally set a passphrase.

**Add the key to your SSH agent (so you don't re-type the passphrase):**

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519           # macOS: ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

**Copy the public key and add it on GitHub:**

```bash
# macOS
pbcopy < ~/.ssh/id_ed25519.pub
# Linux
xclip -selection clipboard < ~/.ssh/id_ed25519.pub
```

Paste into **GitHub → Settings → SSH and GPG keys → New SSH key**.

**Test the connection:**

```bash
ssh -T git@github.com
# → "Hi <username>! You've successfully authenticated, but GitHub does not provide shell access."
```

**Notes:**

- Switch a repo from HTTPS to SSH: `git remote set-url origin git@github.com:user/repo.git`.
- Use multiple GitHub accounts on one machine with `~/.ssh/config` `Host` aliases.

### Forks & Pull Requests

**Description:** The standard open-source contribution workflow.

1. **Fork** the repo on GitHub — creates a copy in your own account.
2. **Clone** your fork locally and add the original as a second remote (`upstream`).
3. **Branch** off `main`, make changes, **commit**, **push** to your fork.
4. **Open a Pull Request** on GitHub: from `your-fork:your-branch` → `original-repo:main`.
5. **Review** — maintainers comment; you push more commits to the same branch (the PR updates automatically).
6. **Merge** — maintainer merges (or squashes / rebases) into `main`.

**Typical commands:**

```bash
# 1-2: fork on GitHub UI, then clone your fork
git clone git@github.com:me/repo.git
cd repo
git remote add upstream https://github.com/original-owner/repo.git

# Keep your fork's main in sync with upstream
git fetch upstream
git checkout main
git merge upstream/main          # or: git rebase upstream/main
git push origin main

# 3: feature branch
git checkout -b feature/cool-thing
# ...edit, commit...
git push -u origin feature/cool-thing

# 4: open PR on GitHub (or with gh CLI)
gh pr create --base main --head feature/cool-thing
```

**Merge strategies on PRs:**

| Strategy            | Result                                                                 |
| ------------------- | ---------------------------------------------------------------------- |
| **Create a merge commit** | Preserves all commits + a merge commit. Most history-preserving.  |
| **Squash and merge** | Combines all PR commits into a single commit on `main`. Clean log.    |
| **Rebase and merge** | Replays PR commits onto `main` linearly without a merge commit.       |

**Notes:**

- Most teams configure **branch protection** on `main`: require PR review, passing CI, no direct pushes.
- Conventional Commits / squash-merge is a popular combination — every `main` commit becomes a clean changelog entry.

### GitHub CLI (`gh`)

**Description:** The official GitHub command-line tool. Manage PRs, issues, releases, repos, gists, secrets, and Actions runs without leaving the terminal.

**Install:** [cli.github.com](https://cli.github.com/). Authenticate once with `gh auth login`.

**Common Commands:**

| Command                            | Purpose                                                          |
| ---------------------------------- | ---------------------------------------------------------------- |
| `gh auth login`                    | One-time interactive login (browser or token).                   |
| `gh repo clone <owner>/<repo>`     | Clone a repo by owner/name shorthand.                            |
| `gh repo create my-app --public`   | Create a new repo on GitHub from the current dir.                |
| `gh repo view --web`               | Open the current repo in your browser.                           |
| `gh pr create`                     | Create a pull request from the current branch.                   |
| `gh pr list`                       | List open PRs in the current repo.                               |
| `gh pr checkout <num>`             | Check out the branch for PR #<num>.                              |
| `gh pr review --approve`           | Approve the current PR.                                          |
| `gh pr merge --squash`             | Merge the current PR with squash strategy.                       |
| `gh issue create -t "Bug" -b "..."` | Open an issue from the terminal.                                |
| `gh run list`                      | Show recent GitHub Actions workflow runs.                        |
| `gh run watch`                     | Stream a workflow run live.                                      |
| `gh release create v1.0.0 ./dist/*` | Create a release with assets.                                   |

**Examples:**

```bash
gh repo create devops-notes --public --source . --push
gh pr create --title "Add login" --body "Implements OAuth flow" --base main
gh pr checkout 42                            # try out PR #42 locally
gh pr merge --squash --delete-branch
```

**Notes:**

- `gh` understands the current repo from `origin` — no need to specify it most of the time.
- Scriptable: combine with `jq` for advanced automation — e.g. `gh pr list --json number,title | jq '.[] | .number'`.

### GitHub Actions

**Description:** GitHub's built-in **CI/CD** platform. Workflows are YAML files in `.github/workflows/` that run on triggers (push, PR, schedule, manual dispatch) on GitHub-hosted or self-hosted runners.

**Workflow file layout:**

```yaml
# .github/workflows/ci.yml
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
      - name: Checkout
        uses: actions/checkout@v4

      - name: Set up Node
        uses: actions/setup-node@v4
        with:
          node-version: 20

      - name: Install dependencies
        run: npm ci

      - name: Run tests
        run: npm test
```

**Core concepts:**

| Concept       | Meaning                                                                       |
| ------------- | ----------------------------------------------------------------------------- |
| **Workflow**  | A YAML file. Triggered by events.                                             |
| **Job**       | A set of steps that runs on a single runner (parallel by default).            |
| **Step**      | A single shell command or **action** (`uses:`).                               |
| **Action**    | A reusable unit — official (`actions/checkout`) or third-party.               |
| **Runner**    | The machine that executes the job (Ubuntu, Windows, macOS, or self-hosted).   |
| **Secret**    | Encrypted credential exposed to workflows as `${{ secrets.NAME }}`.           |
| **Matrix**    | Run the same job against multiple parameter sets (e.g. Node 18/20/22).        |

**Common triggers:**

```yaml
on:
  push:                       # every push
  pull_request:               # every PR
  workflow_dispatch:          # manual run via UI / API
  schedule:
    - cron: '0 5 * * *'       # daily at 05:00 UTC
```

**Notes:**

- Browse / inspect runs: `gh run list` or the **Actions** tab on GitHub.
- The official actions marketplace lives at [github.com/marketplace?type=actions](https://github.com/marketplace?type=actions).
- Pin actions to a SHA (not just `@v4`) for supply-chain safety on sensitive repos.

### Issues, README, LICENSE

**Description:** The non-code files that make a repo welcoming and collaborative.

| File / Feature        | Purpose                                                                |
| --------------------- | ---------------------------------------------------------------------- |
| `README.md`           | Front page — what is this project, how to install, how to use.         |
| `LICENSE`             | Legal terms (MIT, Apache-2.0, GPL-3.0, ...). Without one, code is "all rights reserved." |
| `CONTRIBUTING.md`     | How to set up a dev env, run tests, open a PR.                         |
| `CODE_OF_CONDUCT.md`  | Community behavior expectations.                                       |
| `.github/ISSUE_TEMPLATE/` | Markdown templates for bug reports / feature requests.             |
| `.github/PULL_REQUEST_TEMPLATE.md` | Checklist that pre-fills new PRs.                        |
| `CHANGELOG.md`        | Human-readable list of notable changes per release.                    |
| **Issues**            | Built-in tracker — bugs, features, discussion, linked to PRs.          |
| **Discussions**       | Forum-style thread (Q&A, ideas) — separate from issues.                |
| **Projects**          | Kanban-style boards backed by issues / PRs.                            |

**Notes:**

- Pick a license from [choosealicense.com](https://choosealicense.com/) when starting a public project.
- Add a snappy **About** description and topics in the repo settings — it makes the repo discoverable.
- `Closes #42` / `Fixes #42` in a PR description **auto-closes** issue #42 when the PR is merged.

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
# Dependencies / build output
node_modules/
dist/
*.log

# OS / editor junk
.DS_Store
.vscode/
*.swp

# Secrets
.env
*.pem
```

Already-tracked files are **not** ignored retroactively — run `git rm --cached <file>` to untrack them. A global `.gitignore` for OS/editor noise: `git config --global core.excludesfile ~/.gitignore_global`.

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

| Aspect       | `merge`                                  | `rebase`                                |
| ------------ | ---------------------------------------- | --------------------------------------- |
| History      | Preserves branching — creates a merge commit | Linear — replays your commits on top of target |
| Commit SHAs  | Unchanged                                | **New SHAs** (commits are recreated)    |
| Safety       | Always safe                              | **Never rebase shared/pushed branches** |
| Best for     | Long-lived branches, public history      | Cleaning up local feature branches      |

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

The staging area is what makes Git different from systems like SVN — you build up a commit deliberately rather than committing everything at once.

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

If the commit was already pushed and shared, prefer **`git revert HEAD`** instead — it creates a new commit that undoes the change without rewriting history.

**15. Explain `git reset --soft`, `--mixed`, and `--hard`.**

All three move `HEAD` (and usually the branch pointer); they differ in what they touch:

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
# 1. See which files conflict
git status

# 2. Edit each file — choose your code, theirs, or a blend; remove the markers.

# 3. Stage the resolved files
git add resolved-file.js

# 4. Continue the operation
git commit                  # for merge
git rebase --continue       # for rebase
git merge --abort           # bail out entirely
```

Tools: `git mergetool`, VS Code's 3-way merge view, or `git config merge.conflictstyle diff3` to also see the **common ancestor** in the conflict block.

**17. What is a fast-forward merge?**

A **fast-forward** happens when the target branch (e.g. `main`) has not advanced since you branched off — Git just moves `main`'s pointer forward to your branch's tip. **No merge commit is created.**

```bash
git merge --no-ff feature   # force a merge commit even if FF is possible
git merge --ff-only feature # only merge if FF is possible (reject if diverged)
```

Teams often use `--no-ff` on `main` to preserve the "this was a feature" boundary in history.

**18. What is `git stash` and when do you use it?**

`git stash` saves uncommitted changes (tracked files by default) onto a **stack** and reverts your working directory to a clean state — useful when you need to switch branches but aren't ready to commit.

```bash
git stash                   # stash tracked changes
git stash -u                # include untracked
git stash list              # show stack
git stash show -p stash@{0} # see contents
git stash pop               # re-apply newest + drop from stack
git stash apply stash@{1}   # apply a specific stash, keep it on stack
git stash drop stash@{0}    # delete one
git stash clear             # wipe all
```

For longer-lived parking, prefer a WIP commit on a branch — stashes are easy to forget.

**19. What's the difference between annotated and lightweight tags?**

```bash
git tag v1.0                                    # lightweight — just a name → commit SHA
git tag -a v1.0 -m "Release 1.0"                # annotated — full Git object with metadata
git tag -s v1.0 -m "Signed release"             # annotated + GPG-signed
```

- **Lightweight** — like a branch that doesn't move. No metadata.
- **Annotated** — stored as a full object with tagger, date, message, optional signature. **Always use annotated tags for releases.**

Push tags: `git push origin v1.0` or `git push --tags` (all). Tags are not automatically pushed by `git push`.

**20. What is `git cherry-pick`?**

`git cherry-pick <commit>` applies the **changes** from a specific commit onto your current branch as a **new commit** (with a new SHA). Use it to pull a bug fix from `main` into a release branch without merging unrelated work.

```bash
git cherry-pick abc1234              # one commit
git cherry-pick abc1234..def5678     # a range (exclusive of first)
git cherry-pick -x abc1234           # adds "(cherry picked from ...)" to message
git cherry-pick --abort              # bail on conflict
```

Cherry-picking duplicates a commit (different SHA), so the same change can show up twice if you later merge — usually fine, but be aware.

**21. What's the difference between HTTPS and SSH for Git remotes?**

| Aspect          | HTTPS                              | SSH                                  |
| --------------- | ---------------------------------- | ------------------------------------ |
| URL             | `https://github.com/user/repo.git` | `git@github.com:user/repo.git`       |
| Auth            | Username + **Personal Access Token** | **SSH key pair**                     |
| Firewall        | Almost always allowed (port 443)   | May be blocked (port 22)             |
| Caching         | OS keychain / credential helper    | `ssh-agent`                          |
| 2FA             | Forces PAT use                     | Independent of 2FA                   |

SSH is the day-to-day favorite for developers; HTTPS is friendlier for restricted networks and CI. Switch with `git remote set-url origin <new-url>`.

**22. How do you delete a local and remote branch?**

```bash
# Local
git branch -d feature-x         # safe — refuses if unmerged
git branch -D feature-x         # force delete (use with care)

# Remote
git push origin --delete feature-x
# or the older syntax:
git push origin :feature-x

# Prune stale remote-tracking branches (after teammates delete them)
git fetch --prune
```

`git branch -d` will refuse if the branch has commits not in any other branch — that's a feature, not a bug.

**23. What's the difference between a fork and a clone?**

- **Clone** — a **local** copy of any repo, made with `git clone`. Pushes go back to the same remote (if you have write access).
- **Fork** — a **server-side** copy of a repo under **your** GitHub account. You then clone the fork locally. Forks are how you contribute to repos you can't push to directly — push to your fork, open a PR back to the original ("upstream").

A typical fork workflow:

```bash
# Clone your fork as origin
git clone git@github.com:you/repo.git
cd repo
# Add the original repo as upstream
git remote add upstream git@github.com:original/repo.git
git fetch upstream
git switch -c my-feature upstream/main
```

**24. What is a Pull Request, and why use one?**

A **Pull Request** (or **Merge Request** on GitLab) is a request to merge changes from one branch (or fork) into another. It's a GitHub feature — not a Git concept. PRs add:

- **Code review** — line-by-line comments, suggested edits.
- **Automated checks** — CI status, required reviewers, branch protections.
- **Discussion** — context lives with the change, not in chat history.
- **Atomic merge** — squash, rebase, or merge commit options.

A good PR is small (< ~400 lines), focused (one logical change), and self-explanatory in its description.

**25. What does `git revert` do, and how is it different from `git reset`?**

- **`git revert <sha>`** — creates a **new commit** that applies the inverse of the target commit. History is **preserved**. Safe on shared branches.
- **`git reset <sha>`** — moves the branch pointer backward. History is **rewritten**. **Only safe locally.**

```bash
git revert HEAD              # undo last commit by adding an inverse commit
git revert -m 1 <merge-sha>  # revert a merge commit (pick parent to keep)
```

Rule: **revert public history, reset private history.**

**26. What is `git reflog`, and when do you use it?**

`git reflog` is a **local log of every position HEAD has been in** — every commit, reset, rebase, checkout, merge. It saves you when something seems "lost":

```bash
git reflog                            # list recent HEAD movements
git reset --hard HEAD@{3}             # jump back to where HEAD was 3 moves ago
git checkout -b rescue HEAD@{1}       # rescue a "lost" branch
```

Entries live ~90 days by default (configurable via `gc.reflogExpire`). Reflog is **per-clone** and **never pushed** — it can't save you if you lose the whole repo.

**27. How do you rename a branch (local and remote)?**

```bash
# Local — rename the current branch
git branch -m new-name
# Or rename a non-checked-out branch
git branch -m old-name new-name

# Push the new name and set upstream
git push -u origin new-name

# Delete the old remote name
git push origin --delete old-name
```

If you renamed `master` → `main`, also update the default branch in GitHub's repo settings.

**28. What's the difference between `origin` and `upstream`?**

These are just **remote names** — they have no special meaning to Git. **Convention:**

- **`origin`** — your own fork (or the only remote, if you have direct access).
- **`upstream`** — the **original** repo you forked from.

```bash
git remote -v
# origin    git@github.com:you/repo.git (fetch/push)   ← your fork
# upstream  git@github.com:org/repo.git (fetch/push)   ← the source

# Keep your fork in sync
git fetch upstream
git switch main
git merge upstream/main          # or: git rebase upstream/main
git push origin main
```

**29. What is `git blame` used for?**

`git blame <file>` shows, for **every line**, the commit and author that last changed it.

```bash
git blame README.md
git blame -L 50,80 src/auth.py            # only lines 50–80
git blame -w README.md                     # ignore whitespace-only changes
git blame --ignore-revs-file .git-blame-ignore-revs  # skip formatting commits
```

Use it to find the commit that introduced a line — then `git show <sha>` for the full context (message, diff, related files). Pair with `git log -S "string"` to find when a literal string was added or removed ("pickaxe" search).

**30. How do you squash multiple commits into one?**

Interactive rebase:

```bash
git rebase -i HEAD~5             # edit the last 5 commits
```

In the editor, change `pick` to `squash` (or `s`) for commits to fold into the one above:

```
pick   abc1234  Add login endpoint
squash def5678  Fix lint
squash 9876543  Typo
pick   1111111  Add logout endpoint
```

Git will then open another editor to combine the commit messages. Alternatives:

- **`git commit --amend`** — squash into the previous commit (only the last one).
- **GitHub's "Squash and merge"** button — squashes a whole PR into one commit on merge.

---

### Hard (Senior Level)

**31. Explain Git internals: blobs, trees, commits, and refs.**

Git is a **content-addressable filesystem** with four object types, all stored in `.git/objects/` keyed by SHA-1 (or SHA-256):

- **Blob** — file content (no name, no metadata). Two identical files share one blob.
- **Tree** — a directory listing: maps names → blob/tree SHAs + modes.
- **Commit** — points to **one tree**, lists **parent commit(s)**, plus author, committer, message.
- **Tag** (annotated) — points to a commit, with tagger + message + optional signature.

```
commit
  └─ tree (root dir)
       ├─ blob (README.md)
       ├─ blob (LICENSE)
       └─ tree (src/)
            └─ blob (main.py)
```

**Refs** (`.git/refs/heads/main`, `refs/tags/v1.0`, `HEAD`) are just text files containing a SHA — they're the mutable names that point into the immutable object graph.

**32. What's the difference between `git pull` and `git pull --rebase`?**

- **`git pull`** (default) = `git fetch` + **`git merge`** → creates a merge commit if histories diverged.
- **`git pull --rebase`** = `git fetch` + **`git rebase`** → replays your local commits **on top of** the remote tip → linear history, no merge commits.

```bash
git config --global pull.rebase true       # make rebase the default
git config --global rebase.autoStash true  # auto-stash dirty files during rebase
```

Rebase keeps history clean but rewrites SHAs of your unpushed commits. For feature branches that are still local, rebase is usually preferable.

**33. How does Git store data — what makes it "content-addressable"?**

Every object's name **is** the SHA-1 of its content (`header + content`):

```bash
echo -n "hello" | git hash-object --stdin    # b6fc4c620b67d95f953a5c1c1230aaab5db5a1b0
echo "hello" > a.txt && echo "hello" > b.txt
# a.txt and b.txt share ONE blob — same content, same SHA
```

This gives Git:

- **Deduplication** — identical content stored once across the entire repo's history.
- **Integrity** — any corruption changes the SHA; `git fsck` detects it.
- **Cheap branching** — a branch is one SHA on a 40-byte ref.

Loose objects are compressed individually; older objects are bundled into **packfiles** for efficiency.

**34. What is `git bisect` and how do you use it?**

`git bisect` is a **binary search through history** to find the commit that introduced a bug.

```bash
git bisect start
git bisect bad                # current commit is broken
git bisect good v1.2.0        # this older tag worked
# Git checks out the midpoint. Test it, then:
git bisect good   # or:  git bisect bad
# Git keeps halving until one commit remains
git bisect reset              # return to original HEAD
```

Automate with a script:

```bash
git bisect run ./test.sh       # exit 0 = good, non-zero = bad, 125 = skip
```

In `log₂(N)` steps you find the culprit in repos with thousands of commits.

**35. Explain Git hooks. Client-side vs server-side.**

**Hooks** are scripts in `.git/hooks/` that Git runs at lifecycle points. Make them executable to enable.

**Client-side** (run on the developer's machine):
- **`pre-commit`** — lint, format, run fast tests before allowing the commit.
- **`commit-msg`** — enforce commit-message format (Conventional Commits, JIRA ID).
- **`pre-push`** — last-chance check before sending to remote.

**Server-side** (run on the receiving repo):
- **`pre-receive`** — accept or reject a whole push (enforce policy).
- **`update`** — per-branch check.
- **`post-receive`** — trigger deploys, send notifications.

Hooks aren't versioned by default. Share them with tools like **`pre-commit`** (Python framework, `pre-commit-config.yaml`) or **Husky** (Node ecosystem) — they wire up a single repo-tracked hook that delegates.

**36. What is `git submodule`? What are its pitfalls?**

A **submodule** is a reference to another Git repository, pinned to a specific commit, embedded inside your repo at a path.

```bash
git submodule add https://github.com/foo/bar libs/bar
git submodule update --init --recursive            # after a clone
git submodule update --remote                       # update to latest upstream
```

`.gitmodules` records the URL and path. The parent repo stores **the submodule's commit SHA** as a special "gitlink" tree entry.

**Pitfalls:**
- Easy to forget `--recursive` on clone and end up with empty submodule dirs.
- Detached HEAD inside the submodule by default — commits made there are easy to lose.
- A new contributor needs to know to run `git submodule update` after every pull.
- Refactoring across submodule boundaries is painful.

Modern alternatives: **monorepo tools** (Nx, Turborepo, Bazel), **`git subtree`**, or **package managers**.

**37. Compare branching strategies: Git Flow, GitHub Flow, Trunk-Based.**

| Strategy        | Branches                                      | Releases         | Best for                             |
| --------------- | --------------------------------------------- | ---------------- | ------------------------------------ |
| **Git Flow**    | `main`, `develop`, `feature/*`, `release/*`, `hotfix/*` | Scheduled, versioned | Shrink-wrapped software with versions |
| **GitHub Flow** | `main` + short-lived `feature/*`              | Continuous, on merge | Web apps, SaaS, fast-moving teams    |
| **Trunk-Based** | Everyone commits to `main`; feature flags hide WIP | Continuous, many/day | High-velocity teams, strong CI/CD    |

Trunk-based is the modern default for SaaS — it requires **strong CI**, **feature flags**, and **short-lived branches** (< 1 day). Git Flow's `develop` branch is now considered overhead for most teams.

**38. What's the difference between `git push --force` and `--force-with-lease`?**

- **`--force`** ("force push") — **overwrites the remote branch** with your local one, **even if someone else pushed in between**. You can erase a teammate's work without warning.
- **`--force-with-lease`** — checks that the remote tip is still what you last saw locally. If a teammate pushed since your last fetch, the push **fails safely**.

```bash
git push --force-with-lease origin feature-branch
```

**Rule:** never `--force`. Use `--force-with-lease`. And **never force-push to `main`** — protect it with a branch rule.

**39. What's inside the `.git` directory?**

```
.git/
├── HEAD                ← current branch ref (e.g. "ref: refs/heads/main")
├── config              ← repo-local config (remotes, user, hooks path)
├── description         ← shown in cgit/gitweb only
├── index               ← the staging area (binary file)
├── hooks/              ← client-side hook scripts
├── info/exclude        ← repo-local .gitignore (not shared)
├── objects/            ← all blobs, trees, commits, tags
│   ├── ab/cd1234...    ← loose objects (first 2 chars = dir)
│   └── pack/           ← packfiles (compressed bundles)
├── refs/
│   ├── heads/          ← local branches → SHAs
│   ├── tags/           ← tags → SHAs
│   └── remotes/        ← remote-tracking branches
├── logs/               ← reflog data
└── packed-refs         ← refs packed into one file
```

Delete `.git` and you have just files — no history. **Never** edit object files by hand; use `git update-ref` and `git update-index` for low-level surgery.

**40. What are packfiles, and what does `git gc` do?**

A **packfile** is a single file containing many objects, **delta-compressed** against each other. New commits create loose objects (`.git/objects/ab/cdef...`); periodically Git rolls them into packfiles for space and speed.

```bash
git gc                  # garbage collect: pack loose objects, prune unreachable
git gc --aggressive     # slower, better compression
git count-objects -v    # see object/pack stats
```

`git gc` also **prunes unreachable objects** older than `gc.pruneExpire` (default 2 weeks) — orphaned commits from rebases, deleted branches, etc. Until pruned, `git reflog` and `git fsck --lost-found` can recover them.

**41. How do you sign commits, and why?**

Signed commits prove a commit was **made by the holder of a key**, not just someone who set `user.email`. (Anyone can forge an author field — `git config user.email "linus@kernel.org"` will let you commit as Linus.)

```bash
# GPG (classic)
gpg --full-generate-key
git config --global user.signingkey <KEY-ID>
git config --global commit.gpgsign true
git commit -S -m "Signed commit"

# SSH-based signing (Git ≥ 2.34, simpler)
git config --global gpg.format ssh
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global commit.gpgsign true
```

Upload your signing public key to GitHub (Settings → SSH and GPG keys → Signing keys). PRs show a green **"Verified"** badge. Enforce it via branch protection: "Require signed commits".

**42. What is `git worktree`, and when is it useful?**

`git worktree` lets you have **multiple working directories** backed by **one `.git` directory** — each on a different branch.

```bash
git worktree add ../hotfix main      # check out main into ../hotfix
git worktree list
git worktree remove ../hotfix
```

Use cases:

- Fix a `main` hotfix without stashing your feature branch.
- Run long tests on one branch while coding on another.
- Compare two branches side-by-side in your editor.

Much lighter than a second clone — no duplicate `.git`, shared object database.

**43. How do you recover a deleted branch or lost commits?**

If the loss is recent (≤ 90 days, no `git gc --prune=now`):

```bash
# 1. Find the dangling SHA in reflog
git reflog                              # for HEAD
git reflog show feature-x               # for a deleted branch (may still exist briefly)

# 2. Or scan for unreachable commits
git fsck --lost-found
# writes orphaned commits to .git/lost-found/commit/

# 3. Restore
git switch -c rescued <sha>
```

For destroyed remote branches: if anyone else still has a local copy or it's in the GitHub Activity API, you can re-push it. Once `git gc --prune=now` has run with no references, the objects are gone.

**44. Explain GitHub Actions architecture: workflows, jobs, steps, runners.**

```
Repository
└── .github/workflows/ci.yml          ← Workflow (one YAML file)
    ├── on: push, pull_request        ← Triggers
    └── jobs:
        ├── test:                     ← Job (runs on its own runner)
        │   runs-on: ubuntu-latest    ← Runner OS
        │   steps:                    ← Steps (run sequentially in the job)
        │     - uses: actions/checkout@v4    ← Reusable Action
        │     - run: npm test                ← Shell command
        └── deploy:
            needs: test               ← Run only after `test` succeeds
            ...
```

Key concepts:

- **Workflow** — top-level YAML, triggered by events.
- **Job** — a unit of work; jobs run **in parallel** by default on separate runners.
- **Step** — a command or Action inside a job; steps run **sequentially**.
- **Runner** — the machine executing the job. **GitHub-hosted** (free minutes) or **self-hosted** (your own infra).
- **Action** — reusable building block (`actions/checkout`, `actions/setup-node`).

Secrets via `secrets.MY_TOKEN`; matrix builds via `strategy.matrix`; reusable workflows via `workflow_call`.

**45. How do you handle large files in Git?**

Git struggles with large binaries — they bloat history, slow clones, and can't be deduped well. Solutions:

**Git LFS (Large File Storage)**:

```bash
git lfs install
git lfs track "*.psd" "*.mp4"        # writes .gitattributes
git add .gitattributes *.psd
git commit -m "Track large files via LFS"
git push                              # LFS uploads blobs to a separate store
```

The repo only stores small **pointer files**; the actual binaries live on the LFS server (GitHub provides 1 GiB free).

**Other approaches:**
- **`git annex`** — distributed large-file management, decoupled from any host.
- **External storage** — keep binaries in S3/artifact registry, version their URLs.
- **If they're already in history**: rewrite with **`git filter-repo`** or **BFG Repo-Cleaner** to remove them (forces a re-clone for everyone).

**46. What's the difference between a Personal Access Token and an SSH key?**

| Aspect             | Personal Access Token (PAT)        | SSH Key                                |
| ------------------ | ---------------------------------- | -------------------------------------- |
| Used over          | HTTPS                              | SSH                                    |
| Auth model         | Bearer token (acts like a password) | Public-key cryptography (challenge-response) |
| Scopes             | Fine-grained — repo, workflow, packages, etc. | All-or-nothing per user (broader) |
| Expiry             | Configurable (recommended: 90 days) | None unless you rotate                 |
| Where used         | CLI, CI, API calls, Git over HTTPS  | Git over SSH, server access            |
| Stored             | Credential helper / OS keychain    | `~/.ssh/`, optional passphrase + agent |
| Revoke             | One click on GitHub                | Remove the public key                  |

For CI, prefer **fine-grained PATs** or, better, **GitHub Apps** / `GITHUB_TOKEN` (auto-issued, scoped to the workflow run).

**47. How do CODEOWNERS files and branch protection rules work?**

**`CODEOWNERS`** (in `.github/`, repo root, or `docs/`) maps **path patterns** to **reviewers**:

```
# .github/CODEOWNERS
*                       @org/platform-team
/frontend/              @alice @bob
*.tf                    @org/infra-team
/docs/**                @org/docs-team
```

When a PR touches a path, the matching owners are **auto-requested as reviewers**. Combined with **branch protection rules** on `main`:

- **Require pull request reviews before merging** — N approvals, possibly from a code owner.
- **Require status checks to pass** — CI must be green.
- **Require signed commits**.
- **Require linear history** — disallow merge commits.
- **Restrict who can push** — even maintainers go through PRs.
- **Do not allow force pushes / branch deletion**.

These are how teams enforce policy in code, not just in chat.

**48. What's the difference between three-way merge and recursive merge strategies?**

Git's default merge is a **three-way merge**: it compares the **common ancestor** of the two branches with each of the two tips, producing a merged result based on what changed on each side.

```
        A───B───C    ← branch1 (tip)
       /
   ───O               ← O = merge base (common ancestor)
       \
        D───E         ← branch2 (tip)
```

When **multiple merge bases** exist (criss-cross merges), Git uses the **recursive** strategy: it merges the merge bases first to produce a virtual ancestor, then does the three-way merge. This is the default for two-head merges since 2008.

Other strategies (`-s`):
- **`ort`** (default since Git 2.34) — modern recursive replacement, faster and handles renames better.
- **`octopus`** — merge >2 branches at once (no conflicts allowed).
- **`ours`** — keep our side entirely (discard theirs).
- **`subtree`** — for grafted subtrees with offset paths.

**49. What is `git filter-repo` / BFG, and when would you use them?**

Both tools rewrite Git history — to **remove secrets**, **strip large files**, or **reorganize a repo**.

```bash
# Remove a file from ALL history
git filter-repo --path secrets.env --invert-paths

# Strip files > 100 MB
bfg --strip-blobs-bigger-than 100M repo.git

# Replace text (e.g. expose+rotate a leaked token)
echo "OLD_KEY==>***REMOVED***" > replacements.txt
bfg --replace-text replacements.txt repo.git
```

`git filter-repo` is the modern, recommended tool (replaces the deprecated `git filter-branch`). **BFG** is simpler but more limited.

**Caveats:**
- **Rewrites all SHAs** — everyone must re-clone.
- **Doesn't unleak secrets** — if a token was ever pushed, treat it as compromised and **rotate it**, even after rewriting.
- Coordinate with the team and force-push during a quiet window.

**50. How do you structure CI/CD with GitHub Actions for a typical app?**

A practical layout:

```yaml
# .github/workflows/ci.yml
name: CI
on:
  pull_request:
  push:
    branches: [main]

concurrency:                       # cancel superseded runs on the same PR
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: 20, cache: npm }
      - run: npm ci
      - run: npm run lint

  test:
    runs-on: ubuntu-latest
    strategy:
      matrix: { node: [18, 20] }
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: ${{ matrix.node }}, cache: npm }
      - run: npm ci && npm test

  build-and-deploy:
    needs: [lint, test]
    if: github.ref == 'refs/heads/main'
    runs-on: ubuntu-latest
    environment: production         # required reviewers + secrets gate
    permissions:
      id-token: write               # OIDC for cloud auth — no long-lived keys
      contents: read
    steps:
      - uses: actions/checkout@v4
      - uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: arn:aws:iam::123:role/deploy
          aws-region: us-east-1
      - run: ./deploy.sh
```

Best practices:
- **OIDC over static cloud keys** — short-lived, repo-scoped tokens.
- **Cache dependencies** (`actions/cache` or `setup-*` built-in cache).
- **`concurrency`** to cancel stale PR runs.
- **`environment`** for production gates (reviewers, secrets, deployment history).
- **Pin Action versions to a SHA** in security-sensitive repos (`uses: actions/checkout@<sha>`).
- **Use reusable workflows** (`workflow_call`) to share pipelines across repos.

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
