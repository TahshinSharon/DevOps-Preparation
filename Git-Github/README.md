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
</p>

---

## Table of Contents

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
