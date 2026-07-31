<h1 align="center">Linux Learning Notes</h1>

<p align="center">
  A personal collection of Linux commands, concepts,<br>
  and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Bash">
  <img src="https://img.shields.io/badge/Zsh-89E051?style=for-the-badge&logo=zsh&logoColor=black" alt="Zsh">
  <img src="https://img.shields.io/badge/Vim-019733?style=for-the-badge&logo=vim&logoColor=white" alt="Vim">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-6-blue?style=flat-square" alt="Sections">
  <img src="https://img.shields.io/badge/Level-Beginner→Intermediate-orange?style=flat-square" alt="Level">
  <img src="https://img.shields.io/badge/Status-Actively%20Updated-brightgreen?style=flat-square" alt="Status">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="../README.md"><b>Back to DevOps Prep</b></a>
  &nbsp;·&nbsp;
  <a href="../Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
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

> 🎯 **[Common Interview Questions →](#common-interview-questions)** &nbsp;·&nbsp; 50 Linux interview questions (10 Easy · 20 Medium · 20 Hard) for DevOps junior / mid / senior roles.

---

## Table of Contents

- [Common Interview Questions](#common-interview-questions)
- [Introduction](#introduction)
- [Command Note Template](#command-note-template)
- [Basic Commands](#basic-commands)
  - [One Shot Revision](#one-shot-revision)
  - [The Shell](#the-shell)
  - [pwd](#pwd)
  - [cd](#cd)
  - [ls](#ls)
  - [touch](#touch)
  - [file](#file)
  - [cat](#cat)
  - [less](#less)
  - [history](#history)
  - [cp](#cp)
  - [mv](#mv)
  - [mkdir](#mkdir)
  - [rm](#rm)
  - [find](#find)
  - [help](#help)
  - [man](#man)
  - [whatis](#whatis)
  - [alias](#alias)
  - [exit](#exit)
- [Text-Formating](#text-formating)
  - [One Shot Revision](#one-shot-revision-1)
  - [Pipe & Tee](#pipe--tee)
  - [Environment](#env-environment)
  - [cut](#cut)
  - [paste](#paste)
  - [head](#head)
  - [tail](#tail)
  - [expand](#expand)
  - [unexpand](#unexpand)
  - [join](#join)
  - [split](#split)
  - [sort](#sort)
  - [tr](#tr-translate)
  - [uniq](#uniq)
  - [wc](#wc)
  - [nl](#nl)
  - [grep](#grep)
- [Advanced Text-Formating](#advanced-text-formating)
  - [One Shot Revision](#one-shot-revision-2)
  - [regex (Regular Expressions)](#regex-regular-expressions)
  - [vim editor](#vim-editor)
- [User Management](#user-management)
  - [One Shot Revision](#one-shot-revision-3)
  - [Users and Groups](#users-and-groups)
  - [/etc/passwd](#etcpasswd)
  - [/etc/shadow](#etcshadow)
  - [/etc/group](#etcgroup)
  - [User Management Tools](#user-management-tools)
  - [root](#root)
- [Permissions](#permissions)
  - [One Shot Revision](#one-shot-revision-4)
  - [File Permissions](#file-permissions)
  - [Modifying Permissions](#modifying-permissions)
  - [Ownership Permissions](#ownership-permissions)
  - [Umask](#umask)
  - [Setuid](#setuid)
  - [Setgid](#setgid)
  - [Process Permissions](#process-permissions)
  - [The Sticky Bit](#the-sticky-bit)
- [Processes](#processes)
  - [One Shot Revision](#one-shot-revision-5)
  - [Process Concepts](#process-concepts)
  - [ps](#ps)
  - [Controlling Terminal](#controlling-terminal)
  - [Process Details](#process-details)
  - [Process Creation](#process-creation)
  - [Process Termination](#process-termination)
  - [Process States](#process-states)
  - [top](#top)
  - [htop](#htop)
  - [pstree](#pstree)
  - [pgrep & pkill](#pgrep--pkill)
  - [kill](#kill)
  - [Signals](#signals)
  - [Job Control](#job-control)
  - [nohup & disown](#nohup--disown)
  - [nice & renice](#nice--renice)
  - [/proc Filesystem](#proc-filesystem)
- [Packages](#packages)
  - [One Shot Revision](#one-shot-revision-6)
  - [Software Distribution](#software-distribution)
  - [Package Repositories](#package-repositories)
  - [tar and gzip](#tar-and-gzip)
  - [Package Dependencies](#package-dependencies)
  - [rpm and dpkg](#rpm-and-dpkg)
  - [yum and apt](#yum-and-apt)
  - [Compile Source Code](#compile-source-code)
  - [How to Build NGINX from Source](#how-to-build-nginx-from-source)
- [Devices](#devices)
  - [One Shot Revision](#one-shot-revision-7)
  - [/dev directory](#dev-directory)
  - [Device Types](#device-types)
  - [Device Names](#device-names)
  - [sysfs](#sysfs)
  - [udev](#udev)
  - [lsusb / lspci / lsscsi](#lsusb--lspci--lsscsi)
  - [dd](#dd)
- [The Filesystem](#the-filesystem)
  - [One Shot Revision](#one-shot-revision-8)
  - [Filesystem Hierarchy](#filesystem-hierarchy)
  - [Filesystem Types](#filesystem-types)
  - [Anatomy of a Disk](#anatomy-of-a-disk)
  - [Disk Partitioning](#disk-partitioning)
  - [Creating Filesystems](#creating-filesystems)
  - [mount and umount](#mount-and-umount)
  - [/etc/fstab](#etcfstab)
  - [swap](#swap)
  - [Disk Usage](#disk-usage)
  - [Filesystem Repair](#filesystem-repair)
  - [Inodes](#inodes)
  - [symlinks](#symlinks)
- [Boot the System](#boot-the-system)
  - [One Shot Revision](#one-shot-revision-9)
  - [Boot Process Overview](#boot-process-overview)
  - [Boot Process: BIOS](#boot-process-bios)
  - [Boot Process: Bootloader](#boot-process-bootloader)
  - [Boot Process: Kernel](#boot-process-kernel)
  - [Boot Process: Init](#boot-process-init)
- [Kernel](#kernel)
  - [One Shot Revision](#one-shot-revision-10)
  - [Overview of the Kernel](#overview-of-the-kernel)
  - [Privilege Levels](#privilege-levels)
  - [System Calls](#system-calls)
  - [Kernel Installation](#kernel-installation)
  - [Kernel Location](#kernel-location)
  - [Kernel Modules](#kernel-modules)
- [Init](#init)
  - [One Shot Revision](#one-shot-revision-11)
  - [System V Overview](#system-v-overview)
  - [System V Service](#system-v-service)
  - [Upstart Overview](#upstart-overview)
  - [Upstart Jobs](#upstart-jobs)
  - [Systemd Overview](#systemd-overview)
  - [Systemd Goals](#systemd-goals)
  - [Power States](#power-states)
- [Process Utilization](#process-utilization)
  - [One Shot Revision](#one-shot-revision-12)
  - [Tracking processes: top](#tracking-processes-top)
  - [lsof and fuser](#lsof-and-fuser)
  - [Process Threads](#process-threads)
  - [CPU Monitoring](#cpu-monitoring)
  - [I/O Monitoring](#io-monitoring)
  - [Memory Monitoring](#memory-monitoring)
  - [Continuous Monitoring](#continuous-monitoring)
  - [Cron Jobs](#cron-jobs)
- [Logging](#logging)
  - [One Shot Revision](#one-shot-revision-13)
  - [System Logging](#system-logging)
  - [syslog](#syslog)
  - [General Logging](#general-logging)
  - [Kernel Logging](#kernel-logging)
  - [Authentication Logging](#authentication-logging)
  - [Managing Log Files](#managing-log-files)
- [Useful Tips & Tricks](#useful-tips--tricks)
- [References](#references)

---

## Introduction

Brief notes about Linux, distributions used, and the goal of these notes.

- **Distro:** _e.g., Ubuntu 22.04 / CentOS / Arch_
- **Shell:** _e.g., bash / zsh_
- **Goal:** Build strong Linux fundamentals for DevOps interview prep.

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

## Basic Commands

Everyday Linux commands for navigating the filesystem, working with files, and using the shell itself.

### One Shot Revision

| Command                 | Short Description                                        |
| ----------------------- | -------------------------------------------------------- |
| [The Shell](#the-shell) | The program that reads your commands (Bash, Zsh, ...)    |
| [`pwd`](#pwd)           | Print the current working directory                      |
| [`cd`](#cd)             | Change to another directory                              |
| [`ls`](#ls)             | List the contents of a directory                         |
| [`touch`](#touch)       | Create an empty file or update its timestamp             |
| [`file`](#file)         | Identify the type of a file by its contents              |
| [`cat`](#cat)           | Print the contents of a file to stdout                   |
| [`less`](#less)         | View a file one screen at a time (with search)           |
| [`history`](#history)   | Show previously run commands                             |
| [`cp`](#cp)             | Copy files or directories                                |
| [`mv`](#mv)             | Move or rename files and directories                     |
| [`mkdir`](#mkdir)       | Create a new directory (with `-p` for parents)           |
| [`rm`](#rm)             | Remove files (and directories with `-r`) — **permanent** |
| [`find`](#find)         | Recursively search a directory tree for files            |
| [`help`](#help)         | Show help for shell built-in commands                    |
| [`man`](#man)           | Open the manual page for a command                       |
| [`whatis`](#whatis)     | One-line description of a command (from its man page)    |
| [`alias`](#alias)       | Create a shortcut for a longer command                   |
| [`exit`](#exit)         | Exit the current shell session                           |

### The Shell

The **shell** is the program that reads what you type, runs the command, and shows you the result. The default on most Linux systems is **Bash** (`/bin/bash`); macOS defaults to **Zsh**. Check yours with:

```bash
echo $SHELL
```

Prints the path of your current login shell, e.g. `/bin/bash`.

### `pwd`

**Description:** **Print Working Directory** — shows the full path of the directory you are currently in.

```bash
pwd
```

Outputs something like `/home/tarek/projects`.

### `cd`

**Description:** **Change Directory** — moves you into another directory.

```bash
cd /etc
```

Switches your working directory to `/etc`. Shortcuts: `cd` alone goes **home**, `cd -` jumps to the **previous** directory, `cd ..` goes **up one** level.

### `ls`

**Description:** **List** the contents of a directory.

```bash
ls -la
```

Lists **all** files (`-a`, including hidden ones starting with `.`) in **long** format (`-l`, showing permissions, owner, size, and modification time).

### `touch`

**Description:** Creates an **empty file** if it doesn't exist, or updates the **timestamp** of an existing file.

```bash
touch notes.txt
```

Creates an empty `notes.txt` in the current directory (or refreshes its modification time if it already exists).

### `file`

**Description:** Identifies the **type** of a file by looking at its contents, not its extension.

```bash
file /bin/ls
```

Prints something like `/bin/ls: ELF 64-bit LSB executable, x86-64, ...` — telling you it's a compiled binary.

### `cat`

**Description:** **Concatenate** — prints the contents of one or more files to stdout.

```bash
cat /etc/hostname
```

Displays the system's hostname (the contents of `/etc/hostname`).

### `less`

**Description:** Views a file **one screen at a time** with scroll and search support — much friendlier than `cat` for big files. Quit with `q`.

```bash
less /var/log/syslog
```

Opens `/var/log/syslog` in a pager. Use arrow keys / `Space` to scroll, `/pattern` to search, `q` to quit.

### `history`

**Description:** Shows the list of commands you've run in this shell.

```bash
history
```

Prints a numbered list of past commands. Re-run one with `!N` (e.g. `!42`), or search interactively with `Ctrl + R`.

### `cp`

**Description:** **Copy** files or directories.

```bash
cp notes.txt notes.bak
```

Makes a copy of `notes.txt` called `notes.bak` in the same directory. Use `cp -r src/ dst/` to copy directories **recursively**.

### `mv`

**Description:** **Move** or **rename** files and directories.

```bash
mv notes.txt archive/notes.txt
```

Moves `notes.txt` into the `archive/` directory. If the destination is in the same directory with a different name, it acts as a **rename**: `mv old.txt new.txt`.

### `mkdir`

**Description:** **Make a directory.**

```bash
mkdir -p projects/linux/notes
```

Creates the whole path `projects/linux/notes`, making any missing parent directories along the way (`-p`).

### `rm`

**Description:** **Remove** files (and, with `-r`, directories). **Deletions are permanent** — there is no trash bin.

```bash
rm -i old.txt
```

Removes `old.txt` after **prompting** you to confirm (`-i`). Use `rm -r dir/` to delete a directory and its contents.

### `find`

**Description:** Recursively searches a directory tree for files matching given criteria (name, size, type, time, etc.).

```bash
find /etc -name "*.conf"
```

Searches `/etc` and all its subdirectories for files whose names end in `.conf`.

### `help`

**Description:** Shows brief docs for **shell built-in** commands (like `cd`, `alias`, `export`) in Bash. For external commands, use `man` or `--help`.

```bash
help cd
```

Prints the built-in help text for the `cd` command.

### `man`

**Description:** Opens the **manual page** for a command — the full, authoritative reference. Navigation is the same as `less`; quit with `q`.

```bash
man ls
```

Opens the manual page for `ls`. Search inside with `/pattern`, quit with `q`.

### `whatis`

**Description:** Prints a **one-line description** of a command, pulled from its man page.

```bash
whatis grep
```

Outputs something like `grep (1) - print lines matching a pattern`.

### `alias`

**Description:** Creates a **shortcut** for a longer command. Defined for the current shell — add to `~/.bashrc` / `~/.zshrc` to make it permanent.

```bash
alias ll='ls -la'
```

Now typing `ll` runs `ls -la`. Run `alias` with no arguments to list all defined aliases; remove one with `unalias ll`.

### `exit`

**Description:** **Exits** the current shell session (or logs you out of an SSH session). `Ctrl + D` does the same thing.

```bash
exit
```

Closes the current shell. If it was your login shell or terminal tab, that window closes too.

---

## Text-Formating

Notes on text processing commands in Linux — viewing, searching, filtering, and transforming text.

### One Shot Revision

| Command                                         | Short Description                                                |
| ----------------------------------------------- | ---------------------------------------------------------------- |
| [`echo`](#echo)                                 | Print text to stdout or redirect it into a file                  |
| [`cat` with redirection](#cat-with-redirection) | Read a file as stdin and write stdout to another file            |
| [Redirecting `stderr`](#redirecting-stderr)     | Send error output (fd 2) to a file or merge it with stdout       |
| [Pipe & Tee](#pipe--tee)                        | Chain commands and split output to a file mid-pipeline           |
| [`env` (Environment)](#env-environment)         | List, set, and persist environment variables                     |
| [`cut`](#cut)                                   | Extract fields, characters, or bytes from each line              |
| [`paste`](#paste)                               | Merge lines of files side by side                                |
| [`head`](#head)                                 | Print the first N lines of a file                                |
| [`tail`](#tail)                                 | Print the last N lines (or follow with `-f`)                     |
| [`expand`](#expand)                             | Convert TAB characters to spaces                                 |
| [`unexpand`](#unexpand)                         | Convert runs of spaces back into TABs                            |
| [`join`](#join)                                 | Merge two files on a common field (SQL-style join)               |
| [`split`](#split)                               | Split a file into smaller pieces                                 |
| [`sort`](#sort)                                 | Sort the lines of a file (alphabetical, numeric, reverse, ...)   |
| [`tr` (translate)](#tr-translate)               | Translate, squeeze, or delete characters from stdin              |
| [`uniq`](#uniq)                                 | Filter out adjacent duplicate lines (usually paired with `sort`) |
| [`wc`](#wc)                                     | Count lines, words, and bytes in a file                          |
| [`nl`](#nl)                                     | Number the lines of a file                                       |
| [`grep`](#grep)                                 | Search input for lines matching a pattern                        |

### `echo`

```bash
echo Hello World
```

Prints `Hello World` to the terminal (stdout).

```bash
echo Hello World > peanuts.txt
```

Writes `Hello World` into `peanuts.txt` — **overwrites** the file if it exists.

```bash
echo Hello World >> peanuts.txt
```

**Appends** `Hello World` to the end of `peanuts.txt` (creates it if missing).

### `cat` with redirection

```bash
cat < peanuts.txt > banana.txt
```

Reads `peanuts.txt` as **stdin** (`<`) and writes the output to `banana.txt` as **stdout** (`>`) — effectively copies the contents.

### Redirecting `stderr`

```bash
ls /fake/directory /etc/passwd > peanuts.txt 2>&1
```

Runs `ls` on a missing path and a real path. `>` sends **stdout** to `peanuts.txt`, and `2>&1` redirects **stderr** (fd `2`) into the same place as stdout (fd `1`) — so both normal output and error messages end up in `peanuts.txt`.

### Pipe & Tee

Notes on chaining commands together and splitting output to multiple destinations.

- **Pipe (`|`)** — sends the stdout of one command as the stdin of the next.
- **Tee (`tee`)** — reads stdin, writes it to a file **and** passes it through to stdout (so it can keep flowing down the pipeline).

```bash
ls -la /etc | tee etc_listing.txt | grep "conf"
```

`ls -la /etc` lists `/etc`. `|` **pipes** that output into `tee`, which **saves** a full copy to `etc_listing.txt` _and_ passes it on. The next `|` sends it to `grep "conf"`, which prints only lines containing `conf`.

### `env` (Environment)

**Description:** **Environment variables** are named values stored by the shell that programs can read — they hold things like your username (`USER`), home directory (`HOME`), search path (`PATH`), language (`LANG`), etc. The `env` command prints them; `export` sets new ones.

**Syntax:**

```bash
env
echo $VAR
export VAR=value
```

**Common Options / Forms:**

| Form             | Description                                                |
| ---------------- | ---------------------------------------------------------- |
| `env`            | Lists all environment variables in the current shell.      |
| `echo $VAR`      | Prints the value of a single variable.                     |
| `export VAR=val` | Sets a variable and makes it available to child processes. |
| `unset VAR`      | Removes a variable from the environment.                   |

**Persisting env values across all sessions — Shell Configuration Files:**

`export` in a terminal only lasts for that shell session. To make a variable available **every time** you open a new shell, add the `export` line to your shell's startup config file:

| Shell | Config file                                                                                        |
| ----- | -------------------------------------------------------------------------------------------------- |
| Bash  | `~/.bashrc` (non-login interactive shells; also `~/.bash_profile` / `~/.profile` for login shells) |
| Zsh   | `~/.zshrc`                                                                                         |
| Fish  | `~/.config/fish/config.fish`                                                                       |

Example — add a permanent variable for Bash:

```bash
echo 'export NAME="Tarek"' >> ~/.bashrc
source ~/.bashrc   # reload so the change applies now
```

### `cut`

**Description:** Extracts (cuts) selected sections — characters, bytes, or **fields** — from each line of a file or input.

**Syntax:**

```bash
cut [options] [file]
```

**Common Options:**

| Option | Description                                                        |
| ------ | ------------------------------------------------------------------ |
| `-d`   | Set the **delimiter** (e.g. `","`, `";"`, `":"`). Default is TAB.  |
| `-f`   | Pick which **field(s)** to keep (e.g. `-f 1`, `-f 1,3`, `-f 2-4`). |
| `-c`   | Pick characters by position (e.g. `-c 1-5`).                       |

**Examples:**

```bash
cut -f 1 -d ";" sample.txt
```

Splits each line of `sample.txt` on `;` and prints **field 1** (the first column).

For example, if `sample.txt` contains:

```
apple;red;sweet
banana;yellow;soft
```

the output is:

```
apple
banana
```

**Notes:**

- `-d` only accepts a **single character** as the delimiter.
- Combine with pipes, e.g. `cat /etc/passwd | cut -d ":" -f 1` to list all usernames.

### `paste`

**Description:** Merges lines of files **side by side** (the opposite of `cut`). With `-s`, it joins all lines of a **single** file into one line, separated by a delimiter.

**Syntax:**

```bash
paste [options] [file...]
```

**Common Options:**

| Option | Description                                                                                                        |
| ------ | ------------------------------------------------------------------------------------------------------------------ |
| `-d`   | Set the **delimiter** between joined fields (default is TAB).                                                      |
| `-s`   | **Serial** mode — paste each file's lines into one single line instead of merging multiple files column-by-column. |

**Examples:**

```bash
paste -d ' ' -s sample2.txt
```

Takes every line of `sample2.txt` and joins them into **one line**, separated by a space.

For example, if `sample2.txt` contains:

```
apple
banana
cherry
```

the output is:

```
apple banana cherry
```

**Notes:**

- Without `-s`, `paste` is used to combine multiple files side by side, e.g. `paste file1.txt file2.txt`.
- `paste` is a natural counterpart to `cut` — `cut` splits columns, `paste` joins them.

### `head`

**Description:** Prints the **first lines** of a file (default: 10 lines). Useful for peeking at the top of logs or large files.

**Syntax:**

```bash
head [options] [file]
```

**Common Options:**

| Option | Description                                              |
| ------ | -------------------------------------------------------- |
| `-n N` | Print the first **N** lines (instead of the default 10). |
| `-c N` | Print the first **N** bytes.                             |

**Examples:**

```bash
head -n 15 /var/log/syslog
```

Prints the **first 15 lines** of `/var/log/syslog` — handy for quickly checking recent log entries from the top of the file.

**Notes:**

- Counterpart to `tail`, which prints the **last** lines.
- Works well in pipes, e.g. `ls -la | head -n 5` to see the top 5 entries.

### `tail`

**Description:** Prints the **last lines** of a file (default: 10 lines). With `-f`, it keeps the file open and streams new lines as they are appended — perfect for watching logs live.

**Syntax:**

```bash
tail [options] [file]
```

**Common Options:**

| Option | Description                                                         |
| ------ | ------------------------------------------------------------------- |
| `-n N` | Print the last **N** lines (instead of the default 10).             |
| `-f`   | **Follow** the file — keep printing new lines as they get appended. |
| `-c N` | Print the last **N** bytes.                                         |

**Examples:**

```bash
tail -f /var/log/syslog
```

Prints the last few lines of `/var/log/syslog` and **keeps watching** — any new log entry written to the file shows up in your terminal immediately. Stop with `Ctrl + C`.

**Notes:**

- Counterpart to `head`, which prints the **first** lines.
- `tail -F` (capital F) also follows the file, but reopens it if it's rotated/renamed — useful for log files managed by `logrotate`.

### `expand`

**Description:** Converts **TAB characters** in a file to **spaces** (default: 8 spaces per tab). Prints the result to stdout — the original file is not changed.

**Syntax:**

```bash
expand [options] [file]
```

**Common Options:**

| Option | Description                                                  |
| ------ | ------------------------------------------------------------ |
| `-t N` | Use **N** spaces per tab instead of 8.                       |
| `-i`   | Only convert tabs at the **start** of a line (leading tabs). |

**Examples:**

```bash
expand sample.txt
```

Reads `sample.txt`, replaces every TAB with spaces, and prints the cleaned-up version to the terminal.

To save the result, redirect it:

```bash
expand sample.txt > result.txt
```

**Notes:**

- Useful for normalizing files before diffing or feeding into tools that don't handle tabs well.

### `unexpand`

**Description:** The **opposite** of `expand` — converts runs of **spaces** back into **TAB characters**. By default, only leading whitespace is converted; use `-a` to convert spaces anywhere on the line.

**Syntax:**

```bash
unexpand [options] [file]
```

**Common Options:**

| Option | Description                                                           |
| ------ | --------------------------------------------------------------------- |
| `-a`   | Convert **all** runs of spaces to tabs (not just leading whitespace). |
| `-t N` | Treat **N** spaces as one tab.                                        |

**Examples:**

```bash
unexpand -a result.txt
```

Reads `result.txt` and converts every group of spaces (anywhere on each line) back into tabs, printing the result to stdout.

**Notes:**

- `expand` ↔ `unexpand` are inverses — together they make it easy to switch a file's indentation style between spaces and tabs.

### `join`

**Description:** Merges two files line-by-line on a **common field** (like a SQL join). Both files should be sorted on the join field.

**Syntax:**

```bash
join [options] file1 file2
```

**Common Options:**

| Option | Description                                                         |
| ------ | ------------------------------------------------------------------- |
| `-1 N` | Use field **N** of **file1** as the join key.                       |
| `-2 N` | Use field **N** of **file2** as the join key.                       |
| `-t C` | Set the field separator to character **C** (default is whitespace). |

**Examples:**

```bash
join -1 2 -2 1 file1.txt file2.txt
```

Joins on **field 2 of `file1.txt`** and **field 1 of `file2.txt`**. Sample output:

```
1 John Doe
2 Jane Doe
3 Mary Sue
```

**Notes:**

- Both files **must be sorted** on the join field, otherwise `join` will miss matches. Pre-sort with `sort` if needed.

### `split`

**Description:** Splits a file into **smaller pieces**. By default, it creates chunks of 1000 lines each, named `xaa`, `xab`, `xac`, ...

**Syntax:**

```bash
split [options] [file] [prefix]
```

**Common Options:**

| Option    | Description                                                      |
| --------- | ---------------------------------------------------------------- |
| `-l N`    | Split every **N lines** per file.                                |
| `-b SIZE` | Split by **byte size** (e.g. `-b 1M`, `-b 500K`).                |
| `-d`      | Use **numeric** suffixes (`x00`, `x01`, ...) instead of letters. |

**Examples:**

```bash
split somefile
```

Splits `somefile` into chunks of 1000 lines each, producing `xaa`, `xab`, `xac`, ... in the current directory.

**Notes:**

- You can give a custom prefix: `split -l 100 somefile chunk_` → `chunk_aa`, `chunk_ab`, ...
- Reassemble the pieces with `cat`, e.g. `cat xaa xab xac > somefile`.

### `sort`

**Description:** Sorts the lines of a file (or stdin) and prints the result. By default it sorts **alphabetically**; flags switch to numeric, reverse, unique, etc.

**Syntax:**

```bash
sort [options] [file]
```

**Common Options:**

| Option | Description                                                  |
| ------ | ------------------------------------------------------------ |
| `-n`   | **Numeric** sort — compare lines as numbers instead of text. |
| `-r`   | **Reverse** order.                                           |
| `-u`   | Output only **unique** lines (drop duplicates).              |
| `-k N` | Sort by **field N** (e.g. `-k 2` sorts on the 2nd column).   |

**Examples:**

```bash
sort -n file1.txt
```

Sorts `file1.txt` numerically and prints the result. Sample output:

```
bird
cat
cow
elephant
dog
```

**Notes:**

- `-n` treats non-numeric lines as `0`, so a file of plain words stays in **input order** under `-n` (a stable sort with all-equal keys). Use plain `sort file1.txt` (no `-n`) for true alphabetical order.
- Combine with pipes, e.g. `cat names.txt | sort -u` to get a sorted, deduplicated list.

### `tr` (translate)

**Description:** Translates, squeezes, or deletes characters from **stdin** and writes the result to **stdout**. It does **not** take a filename as an argument — feed input via a pipe or redirection.

**Syntax:**

```bash
tr [options] SET1 [SET2]
```

**Common Options:**

| Option | Description                                                |
| ------ | ---------------------------------------------------------- |
| `-d`   | **Delete** characters in SET1.                             |
| `-s`   | **Squeeze** repeated characters in SET1 into a single one. |
| `-c`   | **Complement** — operate on characters **not** in SET1.    |

**Examples:**

```bash
echo "hello world" | tr 'a-z' 'A-Z'
```

Translates lowercase letters to uppercase → `HELLO WORLD`.

```bash
echo "hello   world" | tr -s ' '
```

Squeezes repeated spaces into a single space → `hello world`.

```bash
echo "hello123world" | tr -d '0-9'
```

Deletes all digits → `helloworld`.

```bash
tr 'a-z' 'A-Z' < file.txt
```

Uppercases every letter of `file.txt` (input via redirection).

**Notes:**

- `tr` works **character-by-character**, not on whole words or patterns — for that, use `sed` or `awk`.
- SET1 and SET2 should be the same length; if SET2 is shorter, its last character is repeated.

### `uniq`

**Description:** Filters out **adjacent duplicate lines** from input. Because it only compares neighbouring lines, the input usually needs to be **sorted first** to remove all duplicates from a file.

**Syntax:**

```bash
uniq [options] [file]
```

**Common Options:**

| Option | Description                                                 |
| ------ | ----------------------------------------------------------- |
| `-c`   | Prefix each line with its **count** of occurrences.         |
| `-d`   | Print **only duplicated** lines.                            |
| `-u`   | Print **only unique** lines (those appearing exactly once). |
| `-i`   | Case-insensitive comparison.                                |

**Examples:**

```bash
sort reading.txt | uniq
```

Sorts `reading.txt` (so duplicates become adjacent), then collapses repeats. Sample output:

```
article
book
magazine
paper
```

```bash
sort reading.txt | uniq -c
```

Same as above but also shows how many times each line appeared, e.g. `3 book`.

**Notes:**

- `uniq` **only** removes consecutive duplicates — always `sort` first if you want a fully deduplicated list.
- Shortcut: `sort -u file` does the sort+uniq in one step.

### `wc`

**Description:** Prints the **word count** of a file — by default it shows lines, words, and bytes. Useful for measuring the size of files or the output of a pipeline.

**Syntax:**

```bash
wc [options] [file]
```

**Common Options:**

| Option | Description                                                         |
| ------ | ------------------------------------------------------------------- |
| `-l`   | Count **lines** only.                                               |
| `-w`   | Count **words** only.                                               |
| `-c`   | Count **bytes**.                                                    |
| `-m`   | Count **characters** (matters for multi-byte encodings like UTF-8). |

**Examples:**

```bash
wc file.txt
```

Prints `lines  words  bytes  file.txt`, e.g. `  12   45  280 file.txt`.

```bash
wc -l /var/log/syslog
```

Counts only the lines in `/var/log/syslog`.

```bash
ls /etc | wc -l
```

Counts how many entries are in `/etc` by piping `ls` into `wc -l`.

**Notes:**

- Great in pipes for quick "how many?" answers, e.g. `grep ERROR app.log | wc -l` to count error lines.

### `nl`

**Description:** Prints a file with **line numbers** added to each line. By default, only non-empty lines are numbered.

**Syntax:**

```bash
nl [options] [file]
```

**Common Options:**

| Option  | Description                                                                          |
| ------- | ------------------------------------------------------------------------------------ |
| `-b a`  | Number **all** lines (including blank ones).                                         |
| `-b t`  | Number only **non-empty** lines (default).                                           |
| `-n ln` | Number format: left-justified (`ln`), right-justified (`rn`), or zero-padded (`rz`). |
| `-w N`  | Width of the line number column.                                                     |

**Examples:**

```bash
nl file.txt
```

Prints `file.txt` with each non-empty line prefixed by a line number, e.g.:

```
     1  apple
     2  banana
     3  cherry
```

```bash
nl -b a file.txt
```

Numbers **every** line, including blank ones.

**Notes:**

- Similar to `cat -n`, but `nl` gives you more formatting control (column width, justification, skip-blanks behavior).

### `grep`

**Description:** Searches input for lines that **match a pattern** and prints them. The name comes from `g/re/p` — _globally search for a regular expression and print_. One of the most-used tools in Linux.

**Syntax:**

```bash
grep [options] PATTERN [file...]
```

**Common Options:**

| Option | Description                                                                |
| ------ | -------------------------------------------------------------------------- |
| `-i`   | **Case-insensitive** match.                                                |
| `-v`   | **Invert** — show lines that do **not** match.                             |
| `-n`   | Show **line numbers** with each match.                                     |
| `-r`   | **Recursively** search through directories.                                |
| `-w`   | Match **whole words** only.                                                |
| `-c`   | Print only the **count** of matching lines.                                |
| `-E`   | Use **extended** regex (so `+`, `?`, `\|`, `()` work without escaping).    |

**Examples:**

```bash
grep "error" /var/log/syslog
```

Prints every line in `/var/log/syslog` containing the word `error`.

```bash
grep -i "warning" app.log
```

Case-insensitive search — matches `warning`, `WARNING`, `Warning`, etc.

```bash
grep -rn "TODO" .
```

Recursively searches the current directory for `TODO`, showing file paths and line numbers.

```bash
ps aux | grep nginx
```

Filters the running processes to lines mentioning `nginx`.

```bash
grep -v "^#" config.conf
```

Shows every line **except** comments (lines starting with `#`).

**Notes:**

- `grep` reads stdin if no file is given — handy in pipes like `cat file | grep ...`.
- For Perl-style regex (lookarounds, `\d`, etc.) use `grep -P`.
- Variants: `egrep` ≈ `grep -E`, `fgrep` ≈ `grep -F` (fixed strings, no regex).

---

## Advanced Text-Formating

Notes on more advanced text-processing tools — pattern matching, scripting, and stream editing.

### One Shot Revision

| Command                                                     | Short Description                                                         |
| ----------------------------------------------------------- | ------------------------------------------------------------------------- |
| [`regex` (Regular Expressions)](#regex-regular-expressions) | Pattern-matching mini-language used by `grep`, `sed`, `awk`, and others   |
| [`vim` editor](#vim-editor)                                 | Modal, keyboard-driven text editor available on virtually every Linux box |

### `regex` (Regular Expressions)

**Description:** A **regular expression** (regex) is a mini-language for describing **patterns** in text. Tools like `grep`, `sed`, `awk`, and many programming languages use regex to search, match, and transform strings. There are two common flavors on Linux: **BRE** (Basic Regular Expressions — used by `grep` by default) and **ERE** (Extended — used by `grep -E` / `egrep`).

**Syntax:**

```bash
grep "PATTERN" file
grep -E "PATTERN" file     # extended regex
sed -E 's/PATTERN/REPL/g' file
```

**Common Metacharacters:**

| Pattern        | Meaning                                                     |
| -------------- | ----------------------------------------------------------- |
| `.`            | Match **any single character** (except newline).            |
| `^`            | **Anchor** — start of a line.                               |
| `$`            | **Anchor** — end of a line.                                 |
| `*`            | Match the previous element **0 or more** times.             |
| `+`            | Match the previous element **1 or more** times (ERE).       |
| `?`            | Match the previous element **0 or 1** times (ERE).          |
| `[abc]`        | **Character class** — match any one of `a`, `b`, `c`.       |
| `[^abc]`       | **Negated** class — match any character **not** in the set. |
| `[a-z]`        | **Range** — match any lowercase letter.                     |
| `\|`           | **Alternation** — match left OR right (ERE).                |
| `(...)`        | **Group** patterns together (ERE).                          |
| `{n,m}`        | Match the previous element between **n** and **m** times.   |
| `\d` `\w` `\s` | Digit / word-char / whitespace (Perl regex, `grep -P`).     |

**Examples:**

```bash
grep "^Error" app.log
```

Matches lines that **start with** `Error`.

```bash
grep "failed$" app.log
```

Matches lines that **end with** `failed`.

```bash
grep -E "cat|dog" pets.txt
```

Matches lines containing either `cat` **or** `dog`.

```bash
grep -E "^[A-Z][a-z]+$" names.txt
```

Matches lines that are a single capitalized word (one uppercase letter followed by one or more lowercase letters).

```bash
grep -E "[0-9]{3}-[0-9]{4}" contacts.txt
```

Matches phone-number-style patterns like `555-1234`.

```bash
grep -Ev "^#|^$" config.conf
```

Shows the config file with **comments and blank lines removed** (`-v` inverts the match).

**Notes:**

- Quote your patterns with single or double quotes so the shell doesn't expand `*`, `?`, `$`, etc.
- **BRE vs ERE:** in basic regex, `+`, `?`, `|`, `()`, `{}` must be **escaped** (`\+`, `\?`, `\|`, `\(\)`, `\{\}`). Use `grep -E` to drop the backslashes.
- Use `grep -P` for Perl-compatible regex (lookaheads, `\d`, `\w`, non-greedy `*?`).
- Test patterns interactively on sites like [regex101.com](https://regex101.com/) — pick the right flavor (BRE / ERE / PCRE) for the tool you're using.

### `vim` editor

**Description:** **Vim** is a powerful, keyboard-driven text editor that ships with almost every Linux system. It is **modal** — instead of typing directly, you switch between modes that decide what your keystrokes do. Knowing a handful of commands is enough to start editing files confidently over SSH or on servers without a GUI.

**Syntax:**

```bash
vim [file]
```

Opens `file` in Vim. If the file doesn't exist, Vim creates it on save.

**Vim Modes:**

| Mode        | How to enter          | Purpose                                                                |
| ----------- | --------------------- | ---------------------------------------------------------------------- |
| **Normal**  | Default / press `Esc` | Navigate, delete, copy, paste — keystrokes are **commands**, not text. |
| **Insert**  | `i`, `a`, `o`, etc.   | Type text like a normal editor.                                        |
| **Visual**  | `v`, `V`, `Ctrl+v`    | Select text by character / line / block.                               |
| **Command** | `:` from Normal mode  | Run `:w`, `:q`, search/replace, settings, etc.                         |

**Common Commands:**

| Keys / Command  | Action                                                                 |
| --------------- | ---------------------------------------------------------------------- |
| `i`             | Enter **Insert** mode at the cursor.                                   |
| `a`             | Enter Insert mode **after** the cursor.                                |
| `o`             | Open a **new line below** and enter Insert mode.                       |
| `O`             | Open a new line **above** and enter Insert mode.                       |
| `Esc`           | Return to **Normal** mode.                                             |
| `h` `j` `k` `l` | Move **left / down / up / right**.                                     |
| `w` / `b`       | Jump to next / previous **word**.                                      |
| `0` / `^` / `$` | Go to **start of line** / first non-blank / **end of line**.           |
| `gg` / `G`      | Go to **top** / **bottom** of file.                                    |
| `:N`            | Jump to **line N** (e.g. `:42`).                                       |
| `x`             | **Delete** the character under the cursor.                             |
| `dd`            | **Delete (cut) the current line**.                                     |
| `yy`            | **Yank (copy) the current line**.                                      |
| `p` / `P`       | **Paste** after / before the cursor.                                   |
| `u`             | **Undo** last change.                                                  |
| `Ctrl + r`      | **Redo**.                                                              |
| `/pattern`      | **Search** forward for `pattern` (then `n` / `N` for next / previous). |
| `:%s/old/new/g` | **Replace** every `old` with `new` in the whole file.                  |
| `:w`            | **Write** (save) the file.                                             |
| `:q`            | **Quit** Vim.                                                          |
| `:wq` or `ZZ`   | Save **and** quit.                                                     |
| `:q!`           | Quit **without** saving (discard changes).                             |

**Examples:**

```bash
vim notes.txt
```

Open `notes.txt` in Vim. You start in **Normal** mode — press `i` to type, `Esc` to stop typing, then `:wq` to save and quit.

A typical first edit session:

```
i            # enter insert mode
Hello Vim!   # type some text
Esc          # back to normal mode
:wq          # save and quit
```

Quick line edit:

```
5G           # jump to line 5
dd           # delete that line
u            # changed your mind — undo
:w           # save
```

**Notes:**

- If you're stuck inside Vim, press `Esc` a couple of times, then `:q!` to bail out without saving.
- Run `vimtutor` in your terminal — it's a free, built-in 30-minute interactive tutorial that ships with Vim.
- Vim has its own config file: `~/.vimrc` (e.g. `set number`, `syntax on`, `set tabstop=4`).
- On many systems `vi` is just a symlink to `vim` (or a smaller `vi` variant). Commands above work on both.

---

## User Management

Notes on managing **users**, **groups**, and identities on a Linux system.

### One Shot Revision

| Command                                           | Short Description                                                 |
| ------------------------------------------------- | ----------------------------------------------------------------- |
| [Users and Groups](#users-and-groups)             | Create, modify, delete, and switch users and groups (UIDs / GIDs) |
| [/etc/passwd](#etcpasswd)                         | User account records — one line per user, 7 colon-separated fields |
| [/etc/shadow](#etcshadow)                         | Encrypted passwords and aging info (root-readable only)           |
| [/etc/group](#etcgroup)                           | Group definitions and secondary memberships                       |
| [User Management Tools](#user-management-tools)   | Command-line tools that manage users, groups, and passwords       |
| [root](#root)                                     | The superuser account (UID `0`) and how to act as it safely       |

### Users and Groups

**Description:** Linux is **multi-user** — every process runs as a user and belongs to one or more groups. **Users** are identified by a **UID** and **groups** by a **GID**. User and group info lives in a few key files under `/etc`, and a set of standard commands lets you create, modify, inspect, and switch identities.

**Key files:**

| File           | Purpose                                                      |
| -------------- | ------------------------------------------------------------ |
| `/etc/passwd`  | One line per user: `username:x:UID:GID:comment:home:shell`.  |
| `/etc/shadow`  | Encrypted **passwords** and aging info (root-readable only). |
| `/etc/group`   | One line per group: `groupname:x:GID:members`.               |
| `/etc/gshadow` | Encrypted group passwords / admins (rarely used).            |
| `/etc/skel/`   | Template files copied into a new user's home on creation.    |

**Notes:**

- Most user/group changes require **root** — prefix with `sudo`.
- UIDs/GIDs below `1000` are typically **system** accounts; regular users start at `1000`.
- A user has **one primary group** (the GID in `/etc/passwd`) and may belong to many **secondary groups** (listed in `/etc/group`).
- Always use `usermod -aG` (append) when adding secondary groups — plain `-G` **replaces** the list and can lock a user out of `sudo`.
- View a user's password aging with `sudo chage -l <user>`.

### /etc/passwd

**Description:** The **`/etc/passwd`** file holds an entry for every user account on the system — both human users and system accounts. It is **world-readable** so programs can map UIDs to usernames. Each line is a **colon-separated** record of 7 fields.

**Format:**

```
username:x:UID:GID:GECOS:home:shell
```

| Field      | Meaning                                                                     |
| ---------- | --------------------------------------------------------------------------- |
| `username` | Login name (e.g. `tarek`).                                                  |
| `x`        | Placeholder — the actual password hash lives in `/etc/shadow`.              |
| `UID`      | **User ID** (e.g. `1000`). `0` is root; `<1000` is usually system accounts. |
| `GID`      | **Primary group ID** (links to `/etc/group`).                               |
| `GECOS`    | Full name / description (often the user's display name, may be empty).      |
| `home`     | Path to the user's home directory (e.g. `/home/tarek`).                     |
| `shell`    | Default login shell (e.g. `/bin/bash`, or `/usr/sbin/nologin` for daemons). |

**Example:**

```bash
grep ^tarek /etc/passwd
```

Prints the line for user `tarek`, e.g. `tarek:x:1000:1000:Tarek Mahmud:/home/tarek:/bin/bash`.

**Notes:**

- Quick list of all usernames on the system: `cut -d ":" -f 1 /etc/passwd`.
- Never edit this file by hand — use `useradd` / `usermod` / `userdel`, or `sudo vipw` (which locks the file safely while you edit).
- A shell of `/usr/sbin/nologin` or `/bin/false` blocks interactive logins — common for service accounts.

### /etc/shadow

**Description:** The **`/etc/shadow`** file stores the **hashed passwords** and password-aging info for every account. It is **only readable by root** (mode `0640`, owner `root:shadow`) so the hashes are not exposed to attackers.

**Format:**

```
username:hash:lastchange:min:max:warn:inactive:expire:reserved
```

| Field        | Meaning                                                                       |
| ------------ | ----------------------------------------------------------------------------- |
| `username`   | Login name — matches `/etc/passwd`.                                           |
| `hash`       | The hashed password (e.g. `$6$...` for SHA-512). `!` or `*` means **locked**. |
| `lastchange` | Days since 1970-01-01 when the password was last changed.                     |
| `min`        | Minimum days between password changes.                                        |
| `max`        | Maximum days the password is valid before it must be changed.                 |
| `warn`       | Days of warning before the password expires.                                  |
| `inactive`   | Days after expiry before the account is disabled.                             |
| `expire`     | Account expiry date (days since 1970-01-01).                                  |

**Example:**

```bash
sudo grep ^tarek /etc/shadow
```

Shows the shadow line for `tarek`, e.g. `tarek:$6$abc...:19500:0:99999:7:::`.

**Notes:**

- A `!` or `*` in the hash field means the account is **locked** (can't log in with a password). Lock with `sudo passwd -l <user>`, unlock with `sudo passwd -u <user>`.
- Modify safely via `passwd`, `chage`, or `sudo vipw -s` (the shadow variant of `vipw`).
- The `$6$` prefix in the hash indicates SHA-512; `$5$` is SHA-256; older systems used `$1$` (MD5, deprecated).

### /etc/group

**Description:** The **`/etc/group`** file lists every group on the system, along with its GID and the **secondary members** of that group. It is **world-readable**, like `/etc/passwd`.

**Format:**

```
groupname:x:GID:member1,member2,...
```

| Field       | Meaning                                                                    |
| ----------- | -------------------------------------------------------------------------- |
| `groupname` | Group name (e.g. `sudo`, `developers`).                                    |
| `x`         | Placeholder for the group password (rarely used, lives in `/etc/gshadow`). |
| `GID`       | **Group ID** number.                                                       |
| `members`   | Comma-separated list of users for whom this is a **secondary** group.      |

**Example:**

```bash
grep ^sudo /etc/group
```

Prints the `sudo` group line, e.g. `sudo:x:27:tarek,alice` — meaning `tarek` and `alice` are members of `sudo` and can therefore run privileged commands.

**Notes:**

- A user's **primary group** is set by the `GID` field in `/etc/passwd`, not by being listed here — `/etc/group` only records **secondary** memberships.
- `groups <user>` is the quickest way to see every group a user belongs to.
- Manage with `groupadd`, `groupmod`, `groupdel`, and `gpasswd -a <user> <group>` / `gpasswd -d <user> <group>` to add or remove members.

### User Management Tools

**Description:** A bundle of **command-line tools** for creating, modifying, and inspecting users and groups. These all wrap reads / writes to `/etc/passwd`, `/etc/shadow`, and `/etc/group` — prefer them over editing the files by hand.

**Common Tools:**

| Tool                       | Purpose                                                                     |
| -------------------------- | --------------------------------------------------------------------------- |
| `useradd <user>`           | Create a new user account.                                                  |
| `usermod <options> <user>` | Modify an existing user (shell, home, groups, name, ...).                   |
| `userdel <user>`           | Delete a user (`-r` also removes the home directory).                       |
| `passwd <user>`            | Set or change a user's password (run as root for other users).              |
| `chage <user>`             | View or change password **aging** info (`chage -l <user>` to view).         |
| `groupadd <group>`         | Create a new group.                                                         |
| `groupmod <opts> <group>`  | Rename or change the GID of a group.                                        |
| `groupdel <group>`         | Delete a group.                                                             |
| `gpasswd <group>`          | Manage group members and admins (`-a` to add, `-d` to delete).              |
| `id <user>`                | Show UID, GID, and group memberships.                                       |
| `getent passwd <user>`     | Look up a user via NSS (works for LDAP / SSSD users, not just local files). |
| `who` / `w` / `last`       | Show currently / recently logged-in users.                                  |

**Example:**

```bash
sudo useradd -m -s /bin/bash -G sudo alice && sudo passwd alice
```

Creates user `alice` with a **home directory** (`-m`), `bash` as the **login shell** (`-s`), adds her to the `sudo` group (`-G`), then prompts you to set her password.

**Notes:**

- On Debian / Ubuntu, **`adduser`** is a friendlier, interactive wrapper around `useradd` that prompts for each option and sets sane defaults.
- Always use `usermod -aG <group> <user>` (note the `-a`!) when adding to **secondary** groups — without `-a`, `-G` overwrites the entire group list.
- For service accounts, pair `useradd` with `--system --shell /usr/sbin/nologin --no-create-home` so the account can own files / processes without being usable for login.

### root

**Description:** **`root`** is the **superuser** on Linux — the special account with **UID `0`** that bypasses all permission checks. Anything root does, the system trusts: create / delete users, modify any file, install packages, change network settings, reboot, etc. Because mistakes as root can destroy the system, the modern convention is to **stay as a normal user** and elevate to root only when needed, via `sudo` (one command) or `su -` (a full root shell).

**Common ways to act as root:**

| Command          | What it does                                                                |
| ---------------- | --------------------------------------------------------------------------- |
| `sudo <command>` | Run **one** command as root (after entering your own password).             |
| `sudo -i`        | Start a **root login shell** (loads root's environment).                    |
| `su -`           | Switch to root — prompts for **root's** password.                           |
| `sudo su -`      | Become root via your own password (works when root's password is disabled). |
| `whoami`         | Confirm which user you are currently acting as.                             |

**Example:**

```bash
sudo whoami
```

Runs the `whoami` command **as root** and prints `root`, confirming the privilege escalation worked. Use this pattern to verify `sudo` is configured for your user before running anything risky.

**Notes:**

- Root's home directory is **`/root`**, not `/home/root`.
- On Ubuntu/Debian-based systems, the **root password is disabled by default** — use `sudo` instead of `su`. Set one with `sudo passwd root` only if you really need it.
- A user can run `sudo` only if they're listed in `/etc/sudoers` (usually by being in the `sudo` or `wheel` group).
- Prefer `sudo <cmd>` over a long-lived root shell — fewer accidental destructive commands, and every action is logged in `/var/log/auth.log`.
- The shell prompt usually changes from `$` (regular user) to `#` (root) — a quick visual cue that you're operating with full privileges.

---

## Permissions

Notes on the Linux **permission system** — how the kernel decides who can read, write, or execute a file or directory.

### One Shot Revision

| Command                                       | Short Description                                                            |
| --------------------------------------------- | ---------------------------------------------------------------------------- |
| [File Permissions](#file-permissions)             | Read / write / execute bits for **user**, **group**, and **other** classes   |
| [Modifying Permissions](#modifying-permissions)   | Change permissions with `chmod` — symbolic (`u+x`) and numeric (`755`) forms |
| [Ownership Permissions](#ownership-permissions)   | Change a file's **owner** with `chown` and its **group** with `chgrp`        |
| [Umask](#umask)                                   | The default permission **mask** subtracted from new files / directories      |
| [Setuid](#setuid)                                 | Special bit — run an executable with the **owner's** privileges, not yours   |
| [Setgid](#setgid)                                 | Special bit — run as the file's **group**, or make new files **inherit** the dir's group |
| [Process Permissions](#process-permissions)       | How a running process's **UID / GID** decides what it's allowed to do        |
| [The Sticky Bit](#the-sticky-bit)                 | Special bit on a directory — only the file's **owner** can delete its files  |

### File Permissions

**Description:** Every file and directory on a Linux system has a set of **permissions** that decide who can do what with it. Permissions are split across three **classes** — **user** (the owner), **group** (the file's group), and **other** (everyone else) — and within each class there are three **bits**: **read (r)**, **write (w)**, and **execute (x)**. The kernel checks these bits on every file access; `root` bypasses the checks entirely.

**Viewing permissions:**

```bash
ls -l file.txt
```

Produces a line like:

```
-rw-r--r-- 1 tarek devs 1240 May 22 10:14 file.txt
```

Breaking down the first column `-rw-r--r--`:

| Position | Value | Meaning                                                       |
| -------- | ----- | ------------------------------------------------------------- |
| 1        | `-`   | **File type** — `-` regular file, `d` directory, `l` symlink. |
| 2–4      | `rw-` | **User** (owner) permissions — read + write, no execute.      |
| 5–7      | `r--` | **Group** permissions — read only.                            |
| 8–10     | `r--` | **Other** permissions — read only.                            |

**The three permission bits:**

| Bit | On a **file**                              | On a **directory**                                                               |
| --- | ------------------------------------------ | -------------------------------------------------------------------------------- |
| `r` | Read the file's contents.                  | **List** the directory's contents (`ls`).                                        |
| `w` | Modify the file's contents.                | **Create / delete / rename** entries inside the directory.                       |
| `x` | **Execute** the file (script or binary).   | **Enter** the directory (`cd`) and access files inside by name.                  |

**Symbolic vs Numeric (Octal) notation:**

Permissions can be written two ways:

| Symbolic    | Octal | Meaning                                |
| ----------- | ----- | -------------------------------------- |
| `---`       | `0`   | No permissions                         |
| `--x`       | `1`   | Execute only                           |
| `-w-`       | `2`   | Write only                             |
| `-wx`       | `3`   | Write + execute                        |
| `r--`       | `4`   | Read only                              |
| `r-x`       | `5`   | Read + execute                         |
| `rw-`       | `6`   | Read + write                           |
| `rwx`       | `7`   | Read + write + execute                 |

So `-rw-r--r--` is **`644`** (user `6`, group `4`, other `4`), and `-rwxr-xr-x` is **`755`**.

**Common modes you'll see:**

| Mode  | Symbolic       | Typical use                                                                |
| ----- | -------------- | -------------------------------------------------------------------------- |
| `644` | `rw-r--r--`    | Regular files — owner edits, everyone else reads.                          |
| `600` | `rw-------`    | Private files (SSH keys, secrets) — only the owner can read or write.      |
| `755` | `rwxr-xr-x`    | Executables and directories — owner full, others can run / enter + read.   |
| `700` | `rwx------`    | Private directories (e.g. `~/.ssh`) — only the owner can access.           |
| `777` | `rwxrwxrwx`    | Everyone can do anything — **avoid**, almost always a security mistake.    |

**Examples:**

```bash
ls -l /etc/passwd
```

Shows the permissions, owner, and group of `/etc/passwd`, e.g. `-rw-r--r-- 1 root root 2890 May 10 09:42 /etc/passwd` — root can write, everyone can read.

```bash
ls -ld /home/tarek
```

The `-d` flag shows info about the **directory itself** instead of listing its contents — useful for checking a directory's permissions (e.g. `drwxr-xr-x 5 tarek tarek 4096 May 22 10:00 /home/tarek`).

```bash
stat file.txt
```

Prints detailed metadata for `file.txt`, including the permissions in **both** symbolic and octal form (e.g. `Access: (0644/-rw-r--r--)`).

**Notes:**

- `root` (UID `0`) **bypasses** all permission checks — it can read, write, or execute anything regardless of the bits.
- Permission checks short-circuit by class: if you're the **owner**, only the **user** bits apply (even if `group` / `other` are more permissive). The kernel doesn't fall through to group/other.
- For a directory, **`x` without `r`** means you can `cd` in and access files **by name** but can't `ls` the contents. **`r` without `x`** means you can list filenames but can't read or `stat` them.
- To **change** permissions, use `chmod` (covered next); to change the **owner / group**, use `chown` and `chgrp`.
- Beyond these 9 bits there are 3 special bits (**setuid**, **setgid**, **sticky**) shown as `s`, `S`, `t`, `T` in the `ls -l` output — covered in later subsections.

### Modifying Permissions

**Description:** Use **`chmod`** ("**ch**ange **mod**e") to change the permission bits of a file or directory. It accepts two flavors of input — **symbolic mode** (human-friendly, e.g. `u+x`) or **numeric / octal mode** (compact, e.g. `755`). Only the **owner** of a file (and `root`) can change its permissions.

**Syntax:**

```bash
chmod [options] MODE file...
```

**Common Options:**

| Option | Description                                                                                  |
| ------ | -------------------------------------------------------------------------------------------- |
| `-R`   | **Recursive** — apply the change to a directory and everything inside it.                    |
| `-v`   | **Verbose** — print one line per file describing the change.                                 |
| `-c`   | Like `-v`, but only print files whose permissions **actually changed**.                      |
| `--reference=FILE` | Copy the permission bits from `FILE` onto the target(s).                          |

**Symbolic mode:**

Symbolic mode reads as **`[who][op][perms]`**:

| Part      | Values    | Meaning                                                          |
| --------- | --------- | ---------------------------------------------------------------- |
| **who**   | `u` `g` `o` `a` | **u**ser (owner), **g**roup, **o**ther, **a**ll (`u+g+o`). |
| **op**    | `+` `-` `=`     | **add** bits, **remove** bits, **set exactly** to these.   |
| **perms** | `r` `w` `x`     | The permission bits to apply.                              |

So `chmod u+x file` reads as _"to the **user** class, **add** the **execute** bit."_

**Numeric (octal) mode:**

Pass a 3-digit number where each digit is the sum of the bits for **user**, **group**, **other**:

```
4 = r    2 = w    1 = x
```

So `chmod 755 file` means **user `7` (rwx)**, **group `5` (r-x)**, **other `5` (r-x)**.

**Examples:**

```bash
chmod u+x script.sh
```

Adds the **execute** bit for the **owner** of `script.sh` — turning a plain text file into something you can run with `./script.sh`.

```bash
chmod go-w notes.txt
```

Removes **write** permission from **group** and **other**, leaving the owner's bits untouched.

```bash
chmod a=r README.md
```

Sets every class (user, group, other) to **read-only** — overwrites whatever was there before (because of `=`).

```bash
chmod 644 file.txt
```

Sets permissions to `rw-r--r--` — owner can read/write, everyone else read-only. The classic "regular file" mode.

```bash
chmod 700 ~/.ssh
```

Locks down the SSH directory so **only the owner** can enter or read it — required for SSH to trust your keys.

```bash
chmod -R 755 /var/www/html
```

Recursively sets every file and directory under `/var/www/html` to `rwxr-xr-x`.

```bash
chmod --reference=template.conf new.conf
```

Copies the exact permissions from `template.conf` onto `new.conf` — handy when you don't remember the right mode.

**Symbolic ↔ Numeric quick map:**

| Symbolic command      | Equivalent octal | Result        |
| --------------------- | ---------------- | ------------- |
| `chmod u=rw,go=r f`   | `chmod 644 f`    | `rw-r--r--`   |
| `chmod u=rwx,go=rx f` | `chmod 755 f`    | `rwxr-xr-x`   |
| `chmod u=rwx,go= f`   | `chmod 700 f`    | `rwx------`   |
| `chmod a=rwx f`       | `chmod 777 f`    | `rwxrwxrwx`   |

**Notes:**

- **`chmod -R` on a directory tree is blunt** — it applies the same bits to **files and directories alike**, which is usually wrong (you rarely want `x` on regular files). For a mixed tree, use `find` to target each type:

  ```bash
  find /path -type d -exec chmod 755 {} \;   # directories: rwxr-xr-x
  find /path -type f -exec chmod 644 {} \;   # files:       rw-r--r--
  ```

- **Capital `X`** is a smart execute bit: `chmod -R u+X dir/` adds `x` to **directories** and to **files that already have at least one `x` bit**, but leaves plain text files alone. Much safer than blanket `+x` recursion.
- `chmod` cannot change the **owner** or **group** of a file — use `chown` / `chgrp` for that (next subsection).
- Permissions on a **symlink** are ignored — `chmod` follows the link and changes the target's bits instead. Use `chmod -h` (where supported) to touch the link itself.
- The owner can always change a file's permissions — even if the current mode is `000`. The mode controls who can use the file, not who can re-permission it; only ownership does that.

### Ownership Permissions

**Description:** Every file has an **owner** (a user) and a **group**. The permission bits (`rwx` for user / group / other) decide _what_ can be done, but the **owner** and **group** decide _who_ falls into each class. Use **`chown`** to change the owner (and optionally the group) and **`chgrp`** to change just the group. Both normally require **root** — a regular user cannot give away their files.

**Syntax:**

```bash
chown [options] USER[:GROUP] file...
chgrp [options] GROUP file...
```

**Forms of the `chown` argument:**

| Form              | What it changes                                           |
| ----------------- | --------------------------------------------------------- |
| `user`            | Owner only — group is left unchanged.                     |
| `user:group`      | **Owner and group** at the same time.                     |
| `user:`           | Owner, and set group to the **user's primary group**.     |
| `:group`          | **Group only** — owner is left unchanged.                 |

**Common Options:**

| Option | Description                                                                                  |
| ------ | -------------------------------------------------------------------------------------------- |
| `-R`   | **Recursive** — apply to a directory and everything inside it.                               |
| `-v`   | **Verbose** — print one line per file describing the change.                                 |
| `-c`   | Like `-v`, but only print files whose ownership **actually changed**.                        |
| `--reference=FILE` | Copy the owner / group from `FILE` onto the target(s).                             |
| `-h`   | Operate on the **symlink itself**, not the file it points to.                                |

**Examples:**

```bash
sudo chown alice notes.txt
```

Changes the **owner** of `notes.txt` to `alice`; the group stays the same.

```bash
sudo chown alice:devs project/
```

Sets `project/`'s owner to `alice` **and** its group to `devs` in one shot.

```bash
sudo chown :devs report.pdf
```

Leaves the owner alone and just changes the **group** to `devs` (equivalent to `chgrp devs report.pdf`).

```bash
sudo chown -R www-data:www-data /var/www/html
```

Recursively transfers ownership of the whole web root to the `www-data` user and group — the standard fix when nginx / apache can't read site files.

```bash
sudo chgrp developers shared.log
```

Changes only the group of `shared.log` to `developers`.

```bash
sudo chown --reference=template.conf new.conf
```

Copies the owner and group from `template.conf` onto `new.conf` — useful when you want files in a directory to all match.

**Quick sanity check:**

```bash
ls -l report.pdf
```

The 3rd and 4th columns of `ls -l` show the **owner** and **group** — verify your `chown` / `chgrp` actually landed.

**Notes:**

- A regular user **cannot give a file away** — only `root` can change ownership to another user. (A user _can_ change the group, but only to a group they're a member of.)
- `chown` does **not** change the permission **bits** — `rw-r--r--` stays `rw-r--r--`. It only changes who falls into the user / group classes when those bits are checked.
- `chown` on a **symlink** by default updates the **target's** owner, not the link's. Use `-h` to change the link itself.
- Same `-R` caveat as `chmod`: recursing into mounted filesystems or symlinked dirs can re-chown far more than you expected. Combine with `find -xdev` if you need to stay on one filesystem.
- `chgrp` is essentially `chown :group` — both exist for historical reasons; pick whichever reads more clearly.
- To **see** ownership programmatically, use `stat -c '%U %G' file` (prints just `owner group`).

### Umask

**Description:** **`umask`** ("**u**ser **mask**") is the **default permission mask** the shell hands to every new file or directory it creates. When a process creates a file, the kernel starts from a base mode and **removes** the bits set in the umask — so the umask is what you _don't_ want new files to have. It is a per-shell setting, inherited by every program you launch from that shell.

**Base modes (before the mask is applied):**

| Type        | Base mode |
| ----------- | --------- |
| Regular file | `666` (`rw-rw-rw-`) — no `x` by default. |
| Directory   | `777` (`rwxrwxrwx`) — `x` is needed to enter it. |

**Formula:**

```
new permissions = base mode  AND NOT  umask
```

Practically: subtract the umask digits from the base mode.

| Umask | New file (`666 - umask`) | New directory (`777 - umask`) |
| ----- | ------------------------ | ----------------------------- |
| `022` | `644` (`rw-r--r--`)      | `755` (`rwxr-xr-x`)           |
| `002` | `664` (`rw-rw-r--`)      | `775` (`rwxrwxr-x`)           |
| `077` | `600` (`rw-------`)      | `700` (`rwx------`)           |
| `000` | `666` (`rw-rw-rw-`)      | `777` (`rwxrwxrwx`)           |

**Syntax:**

```bash
umask              # show current mask (octal)
umask -S           # show it symbolically
umask NEW_MASK     # set a new mask for this shell
```

**Common Options:**

| Form        | Description                                                            |
| ----------- | ---------------------------------------------------------------------- |
| `umask`     | Print the current mask, e.g. `0022`.                                   |
| `umask -S`  | Print symbolically, e.g. `u=rwx,g=rx,o=rx` (the **allowed** bits).     |
| `umask 077` | Set the mask so new files / dirs are only accessible to **you**.       |
| `umask 002` | Group-friendly mask — new files are also writable by the **group**.   |

**Examples:**

```bash
umask
```

Shows the current umask, e.g. `0022` (the leading `0` marks it as octal — only the last three digits matter for normal use).

```bash
umask -S
```

Same value in symbolic form, e.g. `u=rwx,g=rx,o=rx` — note this shows the bits that **remain**, not the bits that are removed.

```bash
umask 077
touch private.txt
ls -l private.txt
```

Sets a strict mask, then creates a file. Output is `-rw------- 1 tarek tarek 0 May 22 12:34 private.txt` — only the owner can read or write it.

```bash
umask 002
mkdir teamwork
ls -ld teamwork
```

With a group-friendly mask, the new directory is `drwxrwxr-x` — owner and group both have full access; others can enter and read.

**Persisting umask across sessions:**

`umask` set in a terminal only lasts for that shell. To make it permanent, add the line to your shell's startup file:

| Shell | Config file               |
| ----- | ------------------------- |
| Bash  | `~/.bashrc` or `~/.profile` |
| Zsh   | `~/.zshrc`                |

Example:

```bash
echo 'umask 022' >> ~/.bashrc
source ~/.bashrc
```

System-wide defaults usually live in `/etc/profile` or `/etc/login.defs` (the `UMASK` setting).

**Notes:**

- Umask **only removes** bits — it cannot add execute (`x`) to a regular file. That's why scripts you `touch` come out non-executable even with `umask 000`; you still need `chmod +x` afterwards.
- Typical default umask is **`022`** on single-user / server systems (group + other read-only) and **`002`** on systems where users collaborate within a shared primary group.
- A umask of **`077`** is the standard choice for **secrets directories** (e.g. `~/.ssh`, `~/.gnupg`) — make sure new files there are private by default.
- The umask is **inherited** by child processes — so setting it in your shell affects every program you launch from that shell, including editors that create new files.
- Tools like `cp -p`, `tar`, and `rsync -a` **preserve the source file's mode** and ignore the umask, which is usually what you want.

### Setuid

**Description:** **Setuid** ("**Set U**ser **ID** on execution") is a special permission bit that, when set on an **executable file**, makes the program run with the **file owner's** privileges instead of the user who launched it. The classic example is `/usr/bin/passwd` — it's owned by `root` and setuid, which is why any regular user can run it to update their entry in `/etc/shadow` (a file only `root` can write).

**How it shows in `ls -l`:**

The setuid bit appears in the **user's `x` position**:

| Display     | Meaning                                                                    |
| ----------- | -------------------------------------------------------------------------- |
| `-rwsr-xr-x` | Setuid **AND** owner has execute → **active** (lowercase `s`).            |
| `-rwSr--r--` | Setuid **without** owner-execute → **set but useless** (uppercase `S`).   |

So the case of the letter tells you whether the bit will actually do anything.

**Setting and unsetting it:**

```bash
chmod u+s file       # symbolic — add setuid
chmod u-s file       # symbolic — remove setuid
chmod 4755 file      # octal — prefix '4' adds setuid to mode 755
chmod 0755 file      # octal — leading '0' clears all special bits
```

The **4-digit octal mode** uses the leading digit for special bits: `4` = setuid, `2` = setgid, `1` = sticky. So `4755` = setuid + `rwxr-xr-x`.

**Examples:**

```bash
ls -l /usr/bin/passwd
```

Typical output:

```
-rwsr-xr-x 1 root root 68208 May  1 09:00 /usr/bin/passwd
```

The `s` in `-rws...` means the program runs **as root** regardless of who invokes it — that's how `passwd` can edit `/etc/shadow` for an unprivileged user.

```bash
sudo chown root:root mytool
sudo chmod 4755 mytool
ls -l mytool
```

Sets `mytool` to **setuid root**. Anyone who runs `./mytool` now executes it with **root** privileges. The output line becomes `-rwsr-xr-x 1 root root ... mytool`.

```bash
find / -perm -4000 -type f 2>/dev/null
```

Lists **every setuid file** on the system — useful for security audits. Anything unexpected on this list is a red flag.

```bash
chmod u-s mytool
```

Removes the setuid bit, returning the file to normal execution rules.

**Notes:**

- **Setuid is a privilege-escalation mechanism** — a buggy setuid-root binary is a textbook way to get a local root shell. Only set it on programs you understand and trust, and prefer narrower tools (e.g. `sudo`, capabilities, polkit) when possible.
- **The Linux kernel ignores setuid on shell scripts** for security reasons — the bit may be set, but the script still runs as you. To run a script with elevated privileges, wrap it in `sudo` or write a compiled wrapper.
- **Setuid on directories is meaningless** on Linux — it has no effect (unlike setgid, which _does_ affect directories — covered next).
- After a setuid program starts, its **real UID** is still you (the invoker) while its **effective UID** is the file's owner. Well-written setuid programs drop privileges back to the real UID as soon as they're done with the privileged work.
- The setuid bit is **cleared automatically** when the file is written to (e.g. by an editor or `cp`) — a safety measure so privileges don't survive a content change.
- To find all setuid (`4000`) **and** setgid (`2000`) files in one sweep: `find / -perm /6000 -type f 2>/dev/null`.

### Setgid

**Description:** **Setgid** ("**Set G**roup **ID** on execution") is the **group-class** counterpart to setuid — but with one extra ability that makes it far more useful in everyday admin work: when set on a **directory**, every new file or subdirectory created inside it **inherits the directory's group** instead of the creator's primary group. This is the standard way to set up a **shared collaboration directory** where multiple users need to read and write each other's files.

**How it shows in `ls -l`:**

The setgid bit appears in the **group's `x` position**:

| Display       | Meaning                                                                  |
| ------------- | ------------------------------------------------------------------------ |
| `-rwxr-sr-x`  | Setgid **AND** group has execute → **active** (lowercase `s`).           |
| `-rwxr-Sr--`  | Setgid **without** group-execute → **set but useless** (uppercase `S`).  |
| `drwxrwsr-x`  | Setgid **on a directory** → new entries inherit the directory's group.  |

**Setting and unsetting it:**

```bash
chmod g+s file_or_dir     # symbolic — add setgid
chmod g-s file_or_dir     # symbolic — remove setgid
chmod 2775 shared/        # octal — prefix '2' adds setgid to mode 775
chmod 0755 file           # octal — leading '0' clears all special bits
```

The leading octal digit for setgid is **`2`** (vs `4` for setuid and `1` for sticky). To combine: `6755` = setuid + setgid + `rwxr-xr-x`.

**Two distinct effects:**

| Target          | What setgid does                                                                |
| --------------- | ------------------------------------------------------------------------------- |
| **Executable**  | The program runs with the **file's group** as its effective group.              |
| **Directory**   | New files / subdirs created inside take the **directory's group**, not the creator's primary group. Subdirectories also **inherit the setgid bit**, so the rule cascades. |

**Examples — directory inheritance (the common case):**

```bash
sudo groupadd devs
sudo mkdir /srv/project
sudo chown root:devs /srv/project
sudo chmod 2775 /srv/project
ls -ld /srv/project
```

Creates a shared directory for the `devs` group. Output:

```
drwxrwsr-x 2 root devs 4096 May 22 14:10 /srv/project
```

The `s` in the group column means: any file `alice` or `bob` creates in `/srv/project` will be group-owned by `devs` automatically — so all team members can read and (with `g+w`) edit each other's files without manual `chgrp`.

**Without setgid** (for contrast):

```bash
mkdir /srv/plain
chgrp devs /srv/plain
chmod 775 /srv/plain
# alice creates a file inside — it ends up owned by alice:alice, not alice:devs
```

That's the bug setgid fixes.

**Examples — setgid on an executable:**

```bash
ls -l /usr/bin/wall
```

Typical output:

```
-rwxr-sr-x 1 root tty 35344 May  1 09:00 /usr/bin/wall
```

`wall` is setgid `tty` so it can write to every user's terminal device — its effective group is `tty` regardless of who runs it.

**Examples — find all setgid files / dirs:**

```bash
find / -perm -2000 2>/dev/null
```

Lists every entry with the setgid bit set (both files and directories).

**Notes:**

- **Directory setgid is the everyday use case** — it's how you build shared `/srv/team`, `/var/www`, or NFS group folders without users constantly forgetting `chgrp`.
- Pair directory setgid with a **group-friendly umask** (`002` instead of `022`) so new files are also **group-writable**, not just group-owned. Without that, the inheritance is half-useful.
- Like setuid, **the kernel ignores setgid on shell scripts** — only compiled binaries get the elevated group.
- Setgid on existing files inside a directory is **not** retroactively applied when you turn on the bit — only **new** files inherit. To fix existing contents: `chgrp -R devs /srv/project` and `find /srv/project -type d -exec chmod g+s {} \;`.
- The bit is **cleared automatically** when an executable is written to (same safety rule as setuid).
- Combined setuid + setgid + sticky in one octal: `chmod 7775 dir` (= `4+2+1`). The sticky bit is covered next.

### Process Permissions

**Description:** File permissions decide _who can touch a file_, but the kernel actually checks them against the **running process's identity** — its **user ID (UID)** and **group ID (GID)**. Every process carries this identity from the moment it's spawned: a new process **inherits** its parent's UID/GID, and that identity is what gets compared to the owner / group of every file it tries to open, every signal it sends, and every port it tries to bind. Understanding the process side of permissions is what lets you reason about questions like _"why can my script read this file but the service running the same code can't?"_

**The three UIDs every process has:**

| ID                | Purpose                                                                                       |
| ----------------- | --------------------------------------------------------------------------------------------- |
| **Real UID (RUID)**     | The user who **launched** the process. Used for accounting and signals.                 |
| **Effective UID (EUID)** | The UID used for **permission checks**. This is what the kernel actually compares.     |
| **Saved UID (SUID)**     | A copy the process can switch **back** to after temporarily dropping privileges.       |

For normal processes, all three are the same. They diverge when the executable has the **setuid** bit set: RUID stays as the invoker, but EUID becomes the file's owner — so a regular user running `/usr/bin/passwd` has `RUID=1000, EUID=0`. The same trio exists for groups (**RGID / EGID / SGID**), plus a list of **supplementary GIDs** for the user's secondary groups.

**Where the process identity comes from:**

| Trigger                               | Effect                                                                          |
| ------------------------------------- | ------------------------------------------------------------------------------- |
| `fork()` / launching a command        | Child **inherits** all UIDs / GIDs from the parent shell.                       |
| `exec()` a **setuid** binary          | EUID becomes the **file's owner**; RUID stays as the invoker.                   |
| `exec()` a **setgid** binary          | EGID becomes the **file's group**; RGID stays as the invoker's group.           |
| `sudo cmd`                            | `sudo` (itself a setuid-root binary) launches `cmd` with **EUID = 0**.          |
| `su - user` / login                   | A new shell is started with **all IDs set to `user`'s** values.                 |

**Inspecting a running process's identity:**

```bash
ps -eo pid,user,ruser,group,rgroup,cmd
```

Shows every process with its **effective** user (`user`) and **real** user (`ruser`), plus the group equivalents. When they differ, you're looking at a setuid/setgid program in action.

```bash
cat /proc/$$/status | grep -E '^(Uid|Gid|Groups):'
```

For any process, `/proc/<pid>/status` exposes the full ID set. `$$` is your current shell's PID. Sample output:

```
Uid:    1000    1000    1000    1000
Gid:    1000    1000    1000    1000
Groups: 4 24 27 1000
```

The four numbers on each `Uid`/`Gid` line are **real, effective, saved, filesystem** IDs. `Groups:` is the supplementary list.

```bash
id
id -u   # current effective UID
id -un  # current effective username
id alice
```

`id` is the friendly way to ask "who am I (to the kernel)?" — same data as `/proc/.../status`, formatted for humans. With a username it shows that user's IDs.

**Examples — why a service can't read your file:**

```bash
# As your user:
echo "secret" > /tmp/notes.txt
ls -l /tmp/notes.txt
# -rw-r--r-- 1 tarek tarek 7 May 22 14:30 /tmp/notes.txt

# Service running as 'www-data' tries to read it — works (other has r).
# But your home dir:
ls -ld /home/tarek
# drwx------ 20 tarek tarek 4096 May 22 14:30 /home/tarek
# www-data has EUID=33, not 1000, and 'other' has no x → can't even cd in.
```

The file's permissions never changed — what changed is **whose identity is doing the check**.

**Examples — watching `sudo` flip the EUID:**

```bash
id -u                   # 1000  (you)
sudo id -u              # 0     (root, via sudo's setuid bit)
sudo -u www-data id -u  # 33    (became www-data)
```

Each row is the same `id -u` command — the answer changes because the **process's effective UID** changes.

**Notes:**

- **Permission checks always use the EUID/EGID**, not the real IDs. That's why `sudo cmd` can write to root-owned files while you (RUID 1000) still get billed for the process in `ps`.
- A process can **drop privileges permanently** by setting RUID = EUID = SUID to an unprivileged user — well-behaved daemons (nginx master → worker, postgres postmaster → backend) do this right after binding privileged ports.
- **Killing a process** with `kill` checks the **real UID** — you can only signal your own processes. `root` (EUID 0) can signal anything.
- **Supplementary group changes don't apply to existing sessions** — after `usermod -aG docker tarek` you must log out and back in (or `newgrp docker`) for the new GID to show up in your shell's `Groups:` list.
- **`ps`** shows the EUID by default; pass `-o ruser` or `-eo pid,user,ruser,cmd` to also see who originally launched the process.
- A process's working **umask**, environment variables (`PATH`, `HOME`, ...), and open file descriptors are also inherited from the parent — identity is just the most visible piece of the permission context.

### The Sticky Bit

**Description:** The **sticky bit** is the third special permission bit. On modern Linux, it only does one useful thing — and it only does it on **directories**: when the sticky bit is set on a directory, a file inside can be **deleted or renamed only by the file's owner**, the **directory's owner**, or **root** — even if other users have full write access to the directory. The textbook example is **`/tmp`**: every user can create files there (it's `world-writable`), but the sticky bit stops you from deleting someone else's files.

**How it shows in `ls -l`:**

The sticky bit appears in the **other's `x` position**:

| Display       | Meaning                                                                       |
| ------------- | ----------------------------------------------------------------------------- |
| `drwxrwxrwt`  | Sticky **AND** other has execute → **active** (lowercase `t`).                |
| `drwxrwxrwT`  | Sticky **without** other-execute → **set but ineffective** (uppercase `T`).   |

**Setting and unsetting it:**

```bash
chmod +t dir          # symbolic — add sticky
chmod -t dir          # symbolic — remove sticky
chmod 1777 dir        # octal — prefix '1' adds sticky to mode 777
chmod 0777 dir        # octal — leading '0' clears all special bits
```

The leading octal digit for the sticky bit is **`1`** (vs `4` for setuid and `2` for setgid). All three combined: `chmod 7777 dir` = `4+2+1` = setuid + setgid + sticky.

**Examples:**

```bash
ls -ld /tmp
```

Typical output:

```
drwxrwxrwt 18 root root 4096 May 22 15:02 /tmp
```

The `t` at the end means anyone can write to `/tmp`, but **users can only delete their own files** — even though the directory itself is world-writable.

```bash
sudo mkdir /srv/dropbox
sudo chmod 1777 /srv/dropbox
ls -ld /srv/dropbox
# drwxrwxrwt 2 root root 4096 May 22 15:05 /srv/dropbox
```

Creates a shared "drop folder" where any user can leave files, but no one can wipe out anyone else's contributions.

**What it actually prevents:**

```bash
# As alice — create a file in a sticky dir:
echo "mine" > /tmp/alice.txt
ls -l /tmp/alice.txt
# -rw-r--r-- 1 alice alice 5 May 22 15:08 /tmp/alice.txt

# As bob — try to delete it:
rm /tmp/alice.txt
# rm: cannot remove '/tmp/alice.txt': Operation not permitted
```

Bob has write access to `/tmp` (it's `rwxrwxrwt`), which is normally enough to delete any file inside. The sticky bit overrides that and protects the file because bob is **neither the file's owner nor the directory's owner**.

**Important: sticky controls deletion, not contents.**

If `/tmp/alice.txt` is itself `rw-r--r--`, bob still can't modify it (no write bit for other). But if the file were `rw-rw-rw-`, bob **could edit its contents** — the sticky bit on `/tmp` would not stop that. Sticky only governs **deletion and renaming** of entries in the directory.

**Find every sticky directory on the system:**

```bash
find / -perm -1000 -type d 2>/dev/null
```

Common results: `/tmp`, `/var/tmp`, `/dev/shm`.

**Notes:**

- **On regular files**, the sticky bit is **ignored** by modern Linux kernels. It originally told the kernel to keep an executable's text segment in swap (the "stuck" memory that gave the bit its name) — that optimization is decades obsolete, but the name stuck.
- The sticky bit is **the only special bit you'd ever sensibly apply to a world-writable directory** — `chmod 1777` is the standard recipe for any shared drop folder, and `chmod 0777` (without sticky) is almost always a mistake.
- **Root bypasses the sticky check** — root can rename or delete anything regardless of who owns the file.
- The **file's permissions are not checked** for the sticky restriction; only the **ownership** of the file and the directory matter. You can't grant deletion rights to others by tweaking the file's mode — they have to be the file's owner.
- Sticky pairs naturally with `chmod o+rwx` for shared dirs; for **group-only** drop folders, use **setgid + write-for-group** instead (see [Setgid](#setgid)) — sticky is overkill when access is already restricted by group membership.

---

## Processes

Notes on Linux **processes** — every running program is a process, identified by a **PID**, owned by a user, and reachable through **signals**. This section covers how to list them, watch them, signal them, and control them from the shell.

### One Shot Revision

| Command                                       | Short Description                                                            |
| --------------------------------------------- | ---------------------------------------------------------------------------- |
| [Process Concepts](#process-concepts)         | PID, PPID, the **fork / exec** model, and the process **state** codes        |
| [ps](#ps)                                     | One-shot **snapshot** of running processes                                   |
| [Controlling Terminal](#controlling-terminal) | The **TTY** a process is tied to — TTY column, `?` for daemons, `setsid`     |
| [Process Details](#process-details)           | Drill into one PID — `pidof`, `lsof`, `pwdx`, fd / cwd / env via `/proc`     |
| [Process Creation](#process-creation)         | How new processes are born — `fork()` + `exec()`, copy-on-write, PID 1       |
| [Process Termination](#process-termination)   | `exit()`, signals, exit codes, **zombies** vs **orphans**, reparenting       |
| [Process States](#process-states)             | The `STAT` codes — `R`, `S`, `D`, `T`, `Z`, `I` — and what they really mean  |
| [top](#top)                                   | Real-time, interactive view of CPU / memory usage                            |
| [htop](#htop)                                 | Friendlier, colorized alternative to `top` with mouse and tree view          |
| [pstree](#pstree)                             | Show the **parent / child** process hierarchy as a tree                      |
| [pgrep & pkill](#pgrep--pkill)                | Find or signal processes **by name / pattern** instead of PID                |
| [kill](#kill)                                 | Send a signal to a process by **PID** — defaults to `SIGTERM`                |
| [Signals](#signals)                           | The signal table — `TERM`, `KILL`, `HUP`, `INT`, `STOP`, `CONT`, ...         |
| [Job Control](#job-control)                   | `&`, `Ctrl+Z`, `jobs`, `fg`, `bg` — shell foreground / background management |
| [nohup & disown](#nohup--disown)              | Keep a job running **after the shell exits**                                 |
| [nice & renice](#nice--renice)                | Adjust a process's **scheduling priority** (CPU politeness)                  |
| [/proc Filesystem](#proc-filesystem)          | Virtual filesystem exposing **live kernel and process state** as files       |

### Process Concepts

**Description:** A **process** is a running instance of a program. The kernel gives every process a unique **PID** (process ID), records its **PPID** (parent's PID), tracks which **user** it runs as (RUID/EUID), and accounts for its CPU time, memory, and open files. New processes are created by **`fork()`** (which clones the parent) and then usually call **`exec()`** to replace themselves with a new program — that's how every command you type from the shell actually starts.

**Key identifiers:**

| Field   | Meaning                                                                            |
| ------- | ---------------------------------------------------------------------------------- |
| `PID`   | Process ID — unique integer assigned by the kernel.                                |
| `PPID`  | Parent PID — the process that `fork()`ed this one.                                 |
| `UID`   | Real user ID — the user who originally started the process.                        |
| `EUID`  | Effective UID — the identity used for **permission checks** (changed by setuid).   |
| `PGID`  | Process group ID — used for **signal delivery** to a whole pipeline.               |
| `SID`   | Session ID — usually the shell that started the job; `setsid` detaches from it.    |
| `TTY`   | Controlling terminal — `?` means **no terminal** (typical for daemons).            |
| `NI`    | Nice value — scheduling politeness (`-20` highest priority → `+19` lowest).        |

**Process states (`STAT` column in `ps`):**

| Code | Meaning                                                                              |
| ---- | ------------------------------------------------------------------------------------ |
| `R`  | **Running** or runnable — on the CPU, or in the run queue waiting for it.            |
| `S`  | **Interruptible sleep** — waiting for an event (most processes are here most of the time). |
| `D`  | **Uninterruptible sleep** — usually blocked on I/O; cannot be killed until it returns. |
| `T`  | **Stopped** — paused by a signal (`SIGSTOP` / `SIGTSTP`, e.g. after `Ctrl+Z`).        |
| `Z`  | **Zombie** — exited but not yet reaped by its parent; only a `task_struct` remains.  |
| `I`  | **Idle** kernel thread — like `S` but excluded from load average.                    |

Additional flags often appended: `s` (session leader), `+` (foreground group), `l` (multi-threaded), `<` (high priority), `N` (low priority).

**The lifecycle in one diagram:**

```
fork()      → child created (copy of parent)
exec()      → child replaces itself with a new program
wait()      → parent collects the child's exit status
              (without wait(), the child becomes a zombie)
```

A process whose parent dies before it does is **reparented to PID 1** (init / systemd), which keeps calling `wait()` so orphans don't accumulate as zombies.

**Notes:**

- **PID 1** is special — it's the first process the kernel starts (today: `systemd` on most distros) and the ancestor of every other process. Killing PID 1 kernel-panics the system.
- **Zombies** are not dangerous in small numbers but indicate a buggy parent that isn't reaping its children. A flood of zombies can exhaust the PID table.
- A process inherits the parent's **environment variables, open file descriptors, working directory, umask, and UID/GID** at `fork()` time. `exec()` keeps the file descriptors and identity but replaces the code and memory map.
- The kernel addresses processes by **PID**, but PIDs are **reused** after a process exits — long-lived scripts that store a PID should re-check it (or use cgroups / `systemd` units) before signaling.

### ps

**Description:** `ps` prints a **one-shot snapshot** of the processes running at the moment you run it — unlike `top`, it doesn't refresh. It accepts two competing flag families: **BSD style** (no dashes, e.g. `aux`) and **UNIX style** (with dashes, e.g. `-ef`). Both are universally accepted; pick one and stick with it.

**Syntax:**

```bash
ps [options]
```

**Common Options:**

| Option       | Style  | Description                                                              |
| ------------ | ------ | ------------------------------------------------------------------------ |
| `aux`        | BSD    | **All** processes, **u**ser-oriented format, including those **x** without a TTY |
| `-ef`        | UNIX   | **Every** process, **f**ull format (PID, PPID, command, time, ...)         |
| `-eLf`       | UNIX   | Like `-ef` but show **threads** (LWPs) too                               |
| `-u <user>`  | UNIX   | Only processes owned by `<user>`                                         |
| `-p <pid>`   | UNIX   | Only the given PID(s) — comma-separated                                  |
| `-o <cols>`  | UNIX   | Pick output columns — e.g. `-o pid,user,stat,cmd`                        |
| `--sort`     | GNU    | Sort by a column — `--sort=-%cpu` for highest CPU first                  |
| `-H`         | UNIX   | Indent children under parents (forest view)                              |
| `--forest`   | GNU    | ASCII tree view (similar to `pstree`)                                    |

**Examples:**

```bash
ps aux
# Snapshot of every process on the system, with USER, %CPU, %MEM, STAT, START, COMMAND

ps -ef
# Same idea in UNIX format — shows PPID (useful for finding parents)

ps -ef | grep nginx
# Quick search by command name — pipe into grep
# (prefer `pgrep nginx` for cleaner output; see below)

ps -u tarek
# Only processes owned by user 'tarek'

ps -o pid,ppid,user,stat,%cpu,%mem,cmd --sort=-%cpu | head
# Top 10 processes by CPU, custom columns
```

**Notes:**

- **`ps aux`** is the most common everyday invocation — memorize it. `aux` and `-ef` show roughly the same data in different column orders.
- The `STAT` column merges the **process state** (see [Process Concepts](#process-concepts)) with flags like `+` (foreground), `s` (session leader), `<` (high priority).
- Use **`--sort=-%cpu`** or **`--sort=-rss`** to surface the heaviest processes without piping into `sort`.
- `ps` reads from **`/proc`** — the data is as live as the kernel, but it's still a snapshot. For continuous monitoring, use [top](#top) or [htop](#htop).
- On macOS / BSD, only the **BSD-style** flags work and column names differ — these notes target Linux.

### Controlling Terminal

**Description:** The **controlling terminal** (sometimes called the **controlling TTY**) is the terminal device a process is attached to for keyboard input and signal delivery. It's how `Ctrl+C`, `Ctrl+Z`, and `Ctrl+\` reach the right job — the kernel routes those keystrokes through the TTY driver into the **foreground process group** of the terminal's **session**. A process **without** a controlling terminal — typical for daemons — shows up as `?` in the `TTY` column of `ps`.

**How TTYs appear in `ps`:**

| `TTY` value     | Meaning                                                                          |
| --------------- | -------------------------------------------------------------------------------- |
| `tty1`–`tty6`   | Local **virtual console** on the physical machine (Ctrl+Alt+F1…F6)               |
| `pts/0`, `pts/1`| **Pseudo-terminal** — every SSH session, terminal emulator, `tmux` pane gets one |
| `console`       | The kernel's primary console — boot messages, single-user mode                   |
| `?`             | **No controlling terminal** — daemon, kernel thread, or process detached via `setsid` |

**Who controls what:**

- Each **session** has at most **one** controlling terminal.
- Each controlling terminal has at most **one foreground process group** at a time — the one that receives keyboard signals.
- Background jobs (`cmd &`) share the same TTY but are **not** in the foreground group; they get `SIGTTIN` / `SIGTTOU` if they try to read from / write to the terminal.
- The shell's **job control** (`fg`, `bg`) is just the shell moving job groups in and out of the terminal's foreground slot via `tcsetpgrp(2)`.

**Inspecting and detaching:**

```bash
tty
# Print the TTY of the current shell, e.g. /dev/pts/3

ps -o pid,tty,stat,cmd
# See which TTY each process is on, and whether it's foreground (`+` in STAT)

ps -eo pid,tty,user,cmd | awk '$2 == "?"'
# Every process with NO controlling terminal — daemons, kernel threads

who
# Logged-in users and the TTYs they're attached to

setsid ./long_job.sh &
# Start the job in a NEW session with no controlling terminal —
# stronger than `nohup` because there's no TTY to send SIGHUP from

stty -a
# Dump the current terminal's settings — line discipline, control chars
# (this is what maps Ctrl+C → SIGINT for your TTY)
```

**Examples:**

```bash
sleep 1000 &
ps -o pid,tty,stat,cmd -p $!
#   PID TT       STAT CMD
#  4321 pts/3    S    sleep 1000
# Same TTY as the shell, but state is `S` (not `S+`) — background, no `+`.

# Daemons typically show no TTY:
ps -eo pid,tty,cmd | grep -E 'sshd|cron|systemd' | head
#   1 ?        /sbin/init
# 712 ?        /usr/sbin/sshd -D
# 813 ?        /usr/sbin/cron -f
```

**Notes:**

- The `+` in the **STAT** column (`R+`, `S+`) means the process is in the **foreground group** of its controlling terminal — it'll catch your `Ctrl+C`. Without `+`, it's a background job.
- **Closing a terminal sends `SIGHUP`** to its session leader (usually your shell), which by default propagates to every job in that session. That's the exact mechanism [nohup and disown](#nohup--disown) protect against.
- **`setsid` is stronger than `nohup`** — it creates a brand-new session with no controlling terminal at all, so `SIGHUP` has nowhere to originate from. Modern service managers like `systemd` use this internally.
- **Daemons explicitly detach** via the classic `fork → setsid → fork` dance to guarantee they never reacquire a TTY — important because a process *with* a controlling terminal can die unexpectedly when that terminal goes away.
- The kernel exposes the TTY in **`/proc/<pid>/stat`** (field 7, `tty_nr`) — `ps` decodes it back into a name. A `0` there means no controlling terminal.

### Process Details

**Description:** Sometimes you've already pinned down **which PID** you care about — now you want everything about it: its full command line, who started it, where it's running from, what files it has open, how much memory it's using. This subsection collects the everyday tools for that drill-down. Every one of them is a wrapper around **`/proc/<pid>/`** (see [/proc Filesystem](#proc-filesystem)) plus a few syscalls.

**The toolkit:**

| Tool / Path                          | What it tells you                                                          |
| ------------------------------------ | -------------------------------------------------------------------------- |
| `pidof <name>`                       | PID(s) of every process running `<name>`                                   |
| `pgrep -a <pattern>`                 | PIDs **plus** the command line — handier than `pidof` for fuzzy matches    |
| `ps -fp <pid>`                       | Full **one-line** summary of one PID (user, PPID, start time, command)     |
| `ps -o pid,ppid,user,etime,cmd -p N` | Custom columns — start with `etime` (elapsed run time) and `cmd`           |
| `pwdx <pid>`                         | Current **working directory** of a process                                 |
| `lsof -p <pid>`                      | Every **open file / socket / pipe** the process holds                      |
| `lsof -i :<port>`                    | Who's listening on or connected to that port (reverse lookup)              |
| `fuser <file>`                       | Which PIDs have **this file** open — e.g. who's holding `/var/log/...`     |
| `readlink /proc/<pid>/exe`           | Path to the actual **executable** on disk                                  |
| `readlink /proc/<pid>/cwd`           | Same idea for **cwd** (what `pwdx` reports)                                |
| `cat /proc/<pid>/status`             | Human-readable: state, UIDs, threads, memory, signal masks                 |
| `cat /proc/<pid>/cmdline`            | Full argv (null-byte separated — pipe through `tr '\0' ' '`)               |
| `cat /proc/<pid>/environ`            | Environment variables the process started with                             |
| `ls -l /proc/<pid>/fd`               | Every open file descriptor, as symlinks to the underlying target           |

**Examples:**

```bash
pidof sshd
# 712 698 654 ...   — every sshd process at once

pgrep -a "python.*train"
# 4321 python train.py --epochs 50   — PID plus matching command line

ps -fp 4321
# UID    PID  PPID  C STIME TTY      TIME     CMD
# tarek 4321  4100  3 14:02 pts/3    00:00:42 python train.py --epochs 50

ps -o pid,etime,user,cmd -p 4321
#   PID     ELAPSED USER     CMD
#  4321    00:42:18 tarek    python train.py --epochs 50

pwdx 4321
# 4321: /home/tarek/projects/ml-experiment

readlink /proc/4321/exe
# /usr/bin/python3.11   — even survives if the binary was upgraded mid-run

lsof -p 4321 | head
# Open files: the script, libraries (.so), log files, sockets, /dev/null, ...

lsof -i :8080
# Who is listening on (or connected to) port 8080

fuser -v /var/log/app.log
# Every PID that currently has app.log open — find the writer before rotating

ls -l /proc/4321/fd
# lr-x------ ... 0 -> /dev/null
# l-wx------ ... 1 -> /home/tarek/job.log
# l-wx------ ... 2 -> /home/tarek/job.log
# lrwx------ ... 3 -> 'socket:[12345678]'

tr '\0' '\n' < /proc/4321/environ | grep -E '^(PATH|HOME|LD_)'
# Useful slice of the process's environment — debug "why isn't it finding X?"
```

**Putting it together — typical "what is this process actually doing?" combo:**

```bash
PID=4321
ps -fp "$PID"                           # who / when / what command
pwdx "$PID"                             # where it's running from
readlink /proc/$PID/exe                 # which binary on disk
ls -l /proc/$PID/fd                     # open files & sockets
awk '/State|Uid|Threads|VmRSS/' /proc/$PID/status   # state + memory snapshot
```

**Notes:**

- **`lsof` needs root** to see other users' open files in full — without it you only see your own processes.
- **`pidof` matches only the basename of the executable** (the `comm` field, max 15 chars). For scripts run via interpreters (`python foo.py`), `pidof foo.py` returns nothing — use `pgrep -f` instead.
- **`/proc/<pid>/cmdline` is empty for kernel threads** (PIDs in square brackets in `ps`, like `[kworker/0:1]`). They have no user-space command line.
- The **`exe` symlink survives upgrades** — if a long-running process was started from `/usr/bin/python3.10` and the package is replaced, `readlink` still shows the path with a ` (deleted)` suffix, telling you the running binary no longer matches the file on disk. Good early warning for "needs restart after upgrade."
- For a **live, top-style breakdown of one PID** (CPU, memory, syscalls, I/O), look at `pidstat -p <pid> 1`, `top -p <pid>`, or `strace -p <pid>` — each is a deeper drill-down than the snapshot tools above.

### Process Creation

**Description:** A new process is born when an existing one calls **`fork()`** and (almost always) follows it with **`exec()`**. `fork()` creates a near-perfect copy of the caller — same memory, same open file descriptors, same working directory — but with a new **PID** and a **PPID** pointing back at the parent. `exec()` then replaces the cloned program with a brand-new executable, keeping the file descriptors and identity intact. Every command you run from the shell, every service `systemd` launches, every worker a web server spawns is some variation of this two-step dance.

**The fork / exec / wait pipeline:**

| Syscall                | What it does                                                                       |
| ---------------------- | ---------------------------------------------------------------------------------- |
| `fork()`               | Clones the caller. Returns **`0` to the child**, the **child's PID to the parent**, `-1` on failure. |
| `clone()`              | Lower-level variant — what threads use (flags choose what's shared: memory, FDs, signals, ...). |
| `vfork()`              | Legacy fast `fork()` — parent is suspended until child `exec`s or exits.           |
| `exec*()` family       | Replaces the current process image with a new program. On success **never returns**. |
| `wait()` / `waitpid()` | Parent blocks until a child exits and collects its **exit status**.                |
| `posix_spawn()`        | Shortcut for the common `fork+exec` pair — skips the page-table copy entirely.     |

**The lifecycle in one diagram:**

```
parent ──fork()──▶ child (exact copy, new PID)
                     │
                     └── exec("/usr/bin/ls") ──▶ ls now runs in the child
                                                   │
parent ──wait()──◀───────────────────── exit(0) ──┘
            (reaps the child's exit status)
```

**Examples:**

```bash
ps -eo pid,ppid,cmd --forest | head -20
# Parent / child hierarchy of every process — the tree your shell sits inside

strace -f -e trace=fork,vfork,clone,execve,wait4 ls /tmp 2>&1 | head
# clone(...)                      = 4322     — fork
# execve("/usr/bin/ls", [...])              — exec replaces the cloned program
# wait4(-1, ...)                  = 4322     — parent reaps the child

# Run the same command from two different shells and watch the PIDs differ:
bash -c 'echo "child pid=$$  ppid=$PPID"'
# child pid=4811  ppid=4100      — 4100 is the calling shell

# Confirm fork() returns twice (once per process):
python3 -c 'import os; pid=os.fork()
print("hello from", "child" if pid==0 else "parent", "pid=", os.getpid())'
# hello from parent pid= 4900
# hello from child  pid= 4901
```

**Cost of `fork()` — copy-on-write:**

- Linux doesn't physically copy the parent's memory at `fork()` time. It marks every page **read-only** and shares them; the kernel clones a page only on the **first write**. That's why forking a 4 GB process is still cheap.
- Because `exec()` almost always follows, the COW pages are usually **discarded before they're ever written** — `exec()` blows away the cloned memory map and loads the new program.
- **`posix_spawn()`** skips the page-table walk entirely for the `fork+exec` case and is what `bash`, `python`'s `subprocess`, and most modern runtimes use under the hood.

**Notes:**

- After `fork()`, the **only differences** between parent and child are: the return value of `fork()` itself, the **PID** / **PPID**, pending signals, file locks, and timers. Everything else (env, cwd, umask, open FDs, signal handlers) is inherited.
- File descriptors inherited across `fork()` share their **file offsets** — both processes reading the same FD advance the same cursor. That's how shell pipelines (`a | b`) actually pass data.
- **PID 1** (`systemd` / `init`) is the only process the kernel creates directly. Every other process traces its ancestry back to PID 1 through `fork()`.
- `fork()` can fail with **`EAGAIN`** when the system hits `kernel.pid_max` or the user's `RLIMIT_NPROC` — that's exactly what a **fork bomb** triggers.
- **Threads are not processes** — they're created with `clone()` and share the address space, FD table, and signal handlers of the calling task. They show up in `ps -eLf` as separate **LWPs** with the same TGID.

### Process Termination

**Description:** A process ends one of two ways: it **exits voluntarily** by calling `exit()` / `_exit()` (or `return`ing from `main`), or it's **terminated by a signal** like `SIGTERM`, `SIGKILL`, or `SIGSEGV`. Either way the kernel keeps a tiny **`task_struct`** around — holding the exit status — until the parent calls **`wait()`** to reap it. The brief window between "exited" and "reaped" is the **zombie** state. Once reaped, the slot is freed and the PID becomes reusable.

**Exit paths:**

| Path                                                  | What happens                                                                  |
| ----------------------------------------------------- | ----------------------------------------------------------------------------- |
| `exit(N)` / `return N` from `main`                    | Normal exit — status `N` (low 8 bits) returned to the parent via `wait()`.    |
| `_exit(N)`                                            | Same, but **skips** stdio flushing and `atexit()` handlers — used after `fork()`. |
| Uncaught signal (`SIGTERM`, `SIGKILL`, `SIGINT`, ...) | Kernel terminates the process; `wait()` reports `WTERMSIG` instead of `WEXITSTATUS`. |
| Fatal fault (`SIGSEGV`, `SIGABRT`, `SIGFPE`)          | Same as above, plus a **core dump** if `ulimit -c` allows it.                 |
| Parent dies first                                     | Child is **reparented to PID 1**, which always reaps. No zombie ever accumulates. |

**Exit status conventions (shell `$?`):**

| Code      | Meaning                                                                |
| --------- | ---------------------------------------------------------------------- |
| `0`       | Success                                                                |
| `1`       | Generic error                                                          |
| `2`       | Misuse / bad usage (bash convention)                                   |
| `126`     | Command found but **not executable**                                   |
| `127`     | Command **not found**                                                  |
| `128 + N` | Killed by signal **N** (e.g. `137` = `128 + 9` = `SIGKILL`)            |
| `130`     | Killed by `SIGINT` (Ctrl+C — `128 + 2`)                                |
| `143`     | Killed by `SIGTERM` (`128 + 15`)                                       |

**The zombie / orphan distinction:**

| Term       | State of the process | What's going on                                                                          |
| ---------- | -------------------- | ---------------------------------------------------------------------------------------- |
| **Zombie** | **Exited**, not yet reaped | Parent is still alive but hasn't called `wait()`. Shows as `Z` (or `<defunct>`) in `ps`. |
| **Orphan** | **Still running**          | Parent **died first**. Kernel reparents the child to PID 1, which always reaps on exit. |

**Examples:**

```bash
ls /no/such/path; echo "exit=$?"
# ls: cannot access ...: No such file or directory
# exit=2

bash -c 'kill -9 $$'; echo "exit=$?"
# Killed
# exit=137                  — 128 + SIGKILL(9)

sleep 100 &
kill -INT $!
wait $!; echo "exit=$?"
# exit=130                  — 128 + SIGINT(2)

# Find zombies on the system right now:
ps -eo pid,ppid,stat,cmd | awk '$3 ~ /^Z/'
#   PID  PPID STAT CMD
# 18234  4100 Z    [worker] <defunct>
# PPID = 4100 → that's the buggy parent that isn't reaping its children

# Create a zombie on purpose (for testing):
bash -c 'sleep 5 & exec sleep 30'   # parent execs into sleep — never reaps the bg child
# In another terminal: ps -eo pid,ppid,stat,cmd | grep Z
```

**Notes:**

- **You can't kill a zombie** — it's already dead. The fix is to kill (or restart) the **parent**, which lets PID 1 adopt and reap it.
- A flood of zombies can exhaust **`kernel.pid_max`** (default 4 194 304 on 64-bit). The symptom is `fork()` returning `EAGAIN` system-wide — even `ssh` and `ps` start failing.
- `bash` reaps its **direct children** automatically when job control is on. Long-running daemons that fork helpers must run their own `wait()` loop, install a `SIGCHLD` handler, or set `SA_NOCLDWAIT` to tell the kernel "don't bother me with zombies."
- **`exit(0)` vs `_exit(0)`**: `exit()` flushes `stdio` buffers and runs `atexit()` hooks before calling `_exit()`. After `fork()`, the child should call `_exit()` directly — otherwise both parent and child flush the same buffered output and you get **doubled output**.
- The status returned by `wait()` is **encoded in 16 bits**: low byte = signal number (if any), high byte = exit code. Use `WIFEXITED` / `WEXITSTATUS` / `WIFSIGNALED` / `WTERMSIG` in C, or just `$?` in shell.
- A **core dump** lands wherever `kernel.core_pattern` says (often `/var/lib/systemd/coredump/` on systemd distros, viewable via `coredumpctl list`).

### Process States

**Description:** At any instant, every process in the kernel's task list is in **exactly one state** — running, sleeping, stopped, or dead-but-not-reaped. The state is what the scheduler uses to decide whether to run, skip, or wake the process. It's exposed as a **single letter** in the `STAT` column of `ps` (and the `S` column of `top`), and as a more readable phrase in `/proc/<pid>/status`. Knowing what each state means is the difference between "this process is stuck" and "this process is doing exactly what it should."

**The state table:**

| Code | Name                       | Meaning                                                                              |
| ---- | -------------------------- | ------------------------------------------------------------------------------------ |
| `R`  | **Running** / runnable     | Currently on a CPU **or** in the run queue waiting for one. The only "actively executing" state. |
| `S`  | **Interruptible sleep**    | Blocked on an event (`read()`, `select()`, `sleep()`), and **can** be woken by a signal. Most processes live here. |
| `D`  | **Uninterruptible sleep**  | Blocked deep in the kernel (usually disk / NFS I/O); **ignores all signals**, even `SIGKILL`. |
| `T`  | **Stopped**                | Paused by `SIGSTOP` / `SIGTSTP` (e.g. Ctrl+Z) — won't be scheduled until `SIGCONT`.  |
| `t`  | **Traced**                 | Stopped by a debugger via `ptrace` — `gdb`, `strace`, `perf` put their targets here. |
| `Z`  | **Zombie** / defunct       | Exited, waiting for the parent's `wait()`. Holds only a `task_struct`, no memory.    |
| `X`  | **Dead**                   | Transient — about to vanish. You almost never see it in `ps`.                        |
| `I`  | **Idle** kernel thread     | Like `S` but **excluded from load average** — used for kernel worker threads.        |

**STAT-column suffix flags (BSD `ps`):**

| Flag | Meaning                                                                |
| ---- | ---------------------------------------------------------------------- |
| `+`  | In the **foreground process group** of its controlling terminal.       |
| `s`  | **Session leader** (top of a session — usually the shell).             |
| `l`  | **Multi-threaded** (process has more than one task / LWP).             |
| `<`  | **High priority** — negative nice value.                               |
| `N`  | **Low priority** — positive nice value.                                |
| `L`  | Pages **locked** in memory (`mlock` / real-time).                      |

**State transitions in one diagram:**

```
                       fork()
                         │
                         ▼
            wakeup     ┌───┐    schedule
        ┌─────────────▶│ R │─────────────▶ on CPU
        │              └───┘
        │                │  I/O / sleep            exit()
   ┌────┴────┐           ▼                            │
   │    S    │◀──── interruptible                     ▼
   └─────────┘                                     ┌───┐    wait()
        ▲                                          │ Z │──────────▶ reaped
        │  I/O complete                            └───┘
        │
   ┌────┴────┐  uninterruptible (disk / NFS)
   │    D    │
   └─────────┘

         SIGSTOP / Ctrl+Z       SIGCONT
   ┌───┐ ────────────────▶ ┌───┐ ────────▶ back to R / S
   │ R │                   │ T │
   └───┘ ◀──────────────── └───┘
```

**Examples:**

```bash
# System-wide state histogram:
ps -eo stat,cmd | awk '{print $1}' | sort | uniq -c | sort -rn
#  248 Ss      — sessions sleeping
#   42 S       — regular sleepers
#   11 R+      — running, foreground
#    3 Z       — three zombies (find their parent!)
#    1 D       — one stuck in uninterruptible I/O

# Find anything stuck in D (sign of a hung disk / NFS mount):
ps -eo pid,stat,wchan,cmd | awk '$2 ~ /^D/'
#   PID STAT WCHAN        CMD
#  4321 D    io_schedule  dd if=/dev/sdb of=/tmp/dump.bin
# WCHAN tells you exactly which kernel function it's blocked in.

# Watch the state flip live:
sleep 1000 &
PID=$!
ps -o pid,stat,cmd -p $PID    # S    sleep 1000
kill -STOP $PID
ps -o pid,stat,cmd -p $PID    # T    sleep 1000     — Stopped
kill -CONT $PID
ps -o pid,stat,cmd -p $PID    # S    sleep 1000     — back to sleep

# Human-readable state from /proc:
grep '^State:' /proc/$PID/status
# State:  S (sleeping)
```

**Notes:**

- **`D` state can't be killed** — not even by `SIGKILL`. The process resumes only when the kernel operation it's blocked on returns. If that never happens (broken NFS, dead disk, frozen driver), the only fix is a reboot. Check `cat /proc/<pid>/wchan` or `ps -o wchan` to see which kernel function it's parked in.
- **`R` doesn't mean "using CPU"** — it means **runnable**. A box with 1000 `R` processes on 8 cores has 992 of them sitting in the run queue. High `R` count = CPU-bound workload; high `D` count = I/O-bound or stuck.
- **Zombies (`Z`) cost almost nothing individually** — just a `task_struct` (a few KB) — but they each hold a **PID slot**. Thousands of them can starve the PID space; see [Process Termination](#process-termination) for the fix.
- A **multi-threaded process** in `ps -eLf` may show different states **per thread** — the process-level state is the "most active" one (e.g. one thread `R`, the others `S` → process reports `Rl`).
- **`top` shows the state as a single letter** in the `S` column, same codes as `ps`. **`htop`** shows the long name (`Running`, `Sleeping`, ...) in the same place.
- For the most human-readable form, use **`/proc/<pid>/status`**'s `State:` line; for "what is this `S` or `D` process *actually* waiting on", look at **`/proc/<pid>/wchan`**.

### top

**Description:** `top` is the classic **real-time** process viewer — it redraws every few seconds and shows CPU, memory, load average, and a sortable per-process table. It ships on every Linux system, so it's the fallback when you can't install [htop](#htop).

**Syntax:**

```bash
top [options]
```

**Common Options:**

| Option        | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| `-d <secs>`   | Refresh **delay** in seconds (default ~3)                                |
| `-n <count>`  | Exit after `<count>` refreshes (useful for scripting)                    |
| `-u <user>`   | Only show processes owned by `<user>`                                    |
| `-p <pids>`   | Watch only specific PIDs                                                 |
| `-H`          | Show **threads** instead of just processes                               |
| `-b`          | **Batch** mode — print to stdout (no curses), good for logging           |
| `-o <field>`  | Sort by the given field — e.g. `-o %MEM`                                 |

**Interactive keys (while top is running):**

| Key       | Action                                                                |
| --------- | --------------------------------------------------------------------- |
| `P`       | Sort by **CPU%** (the default)                                        |
| `M`       | Sort by **memory** (RES)                                              |
| `T`       | Sort by **TIME+** (cumulative CPU time)                               |
| `k`       | **Kill** a process — prompts for PID, then signal                     |
| `r`       | **Renice** a process — prompts for PID, then new nice value           |
| `u`       | Filter by **user**                                                    |
| `1`       | Toggle **per-CPU** breakdown in the header                            |
| `c`       | Toggle **full command line** vs short command name                    |
| `H`       | Toggle thread view                                                    |
| `q`       | Quit                                                                  |

**Examples:**

```bash
top
# Standard interactive view

top -d 1
# Refresh every 1 second (default is ~3s) — heavier but more responsive

top -bn1 | head -20
# One-shot batch dump — useful in scripts and ssh-loops
# `-b` = batch mode, `-n1` = a single iteration

top -u www-data
# Only show processes owned by the web server user
```

**Notes:**

- The header shows **load averages** (1 / 5 / 15-minute) — a load above your CPU count means there's a queue, not just busy CPUs.
- **CPU% in `top` can exceed 100%** for multi-threaded processes — `100%` = one full core. A process pinning four cores will read `400%`.
- **`Shift+E`** toggles memory units in the header (KB / MB / GB / TB); **`e`** toggles them in the per-process column.
- `top` reads its config from `~/.config/procps/toprc` — press **`W`** while running to save your current layout (columns, sort, refresh) for next time.
- For continuous logging, prefer **`top -b -d 5 >> top.log`** over piping the interactive view.

### htop

**Description:** `htop` is a **friendlier `top` replacement** — colorized, mouse-aware, with built-in tree view, easy multi-selection, and visible CPU / memory bars in the header. It's not installed by default on most distros (`apt install htop`, `dnf install htop`).

**Syntax:**

```bash
htop [options]
```

**Common Options:**

| Option        | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| `-d <secs>`   | Refresh delay in **tenths** of a second (so `-d 10` = 1s)                |
| `-u <user>`   | Only show `<user>`'s processes                                           |
| `-p <pids>`   | Only show specific PIDs                                                  |
| `-t`          | Start in **tree** view                                                   |
| `-s <col>`    | Sort by column at startup — e.g. `-s PERCENT_MEM`                        |

**Interactive keys:**

| Key       | Action                                                                |
| --------- | --------------------------------------------------------------------- |
| `F2`      | Setup — customize meters, columns, colors                             |
| `F3`      | Search (like `vim`'s `/`) — jumps to matching process                 |
| `F4`      | Filter — only matching processes shown                                |
| `F5`      | Toggle **tree** view                                                  |
| `F6`      | Pick sort column                                                      |
| `F7 / F8` | Decrease / increase nice value of selected process                    |
| `F9`      | Send signal (kill menu)                                               |
| `F10`     | Quit                                                                  |
| `Space`   | Tag a process (act on multiple at once)                               |
| `U`       | Untag all                                                             |
| `H`       | Toggle user-thread display                                            |
| `K`       | Toggle kernel-thread display                                          |

**Examples:**

```bash
htop
# Default interactive view

htop -u tarek
# Only show your own processes

htop -t
# Start directly in tree view — handy for tracing parent-child relationships
```

**Notes:**

- The CPU / memory / swap **bars** at the top are the headline feature — instant load visibility without parsing numbers.
- **Tagging with `Space`** then pressing `F9` lets you kill or renice many processes at once — useful when a runaway service has spawned dozens of workers.
- htop relies on `/proc`; inside an unprivileged container it may show host-level numbers in the header but only the container's processes in the list — don't trust the CPU bars from inside Docker without checking cgroup limits.
- Config lives at `~/.config/htop/htoprc` — back it up across machines for a consistent layout.

### pstree

**Description:** `pstree` prints the **process hierarchy as a tree** — a much easier way to see parent / child relationships than scrolling through `ps` looking for matching PPIDs. Useful for understanding how a shell, daemon, or container's processes are structured.

**Syntax:**

```bash
pstree [options] [pid | user]
```

**Common Options:**

| Option        | Description                                                              |
| ------------- | ------------------------------------------------------------------------ |
| `-p`          | Show **PIDs** next to each process name                                  |
| `-a`          | Show full **command-line arguments**                                     |
| `-u`          | Show the process **user** in parentheses when it changes                 |
| `-T`          | Hide **threads** (default on newer versions)                             |
| `-H <pid>`    | Highlight the given PID in the tree                                      |
| `-n`          | Sort children by **PID** rather than name                                |
| `-s <pid>`    | Show only the **ancestors** of `<pid>`                                   |

**Examples:**

```bash
pstree
# Tree from PID 1 down — quick overview of the whole system

pstree -p
# Same, with PIDs in parentheses next to each name

pstree -ap $$
# Tree starting at your current shell ($$), with arguments and PIDs
# Great for seeing your own background jobs and subshells

pstree -s 1234
# Walk from PID 1234 up to PID 1 — find a process's ancestry chain
```

**Notes:**

- Identical sibling processes are **collapsed** with a count, like `nginx───4*[nginx]` — pass `-c` to expand them.
- **`pstree -ap | less`** is the fastest way to audit "what is this machine actually running" after SSHing into an unfamiliar box.
- The forest view in `ps --forest` or `ps f` produces similar output and is available when `pstree` isn't installed.

### pgrep & pkill

**Description:** `pgrep` finds PIDs **by name or pattern**; `pkill` does the same but **sends a signal** to each match. Together they replace the clunky `ps aux | grep ... | awk '{print $2}' | xargs kill` pipeline that everyone writes once and then never wants to write again.

**Syntax:**

```bash
pgrep [options] <pattern>
pkill [options] [-SIGNAL] <pattern>
```

**Common Options (shared):**

| Option         | Description                                                              |
| -------------- | ------------------------------------------------------------------------ |
| `-u <user>`    | Only processes owned by `<user>`                                         |
| `-U <uid>`     | Same, by numeric UID                                                     |
| `-f`           | Match against the **full command line**, not just the program name       |
| `-x`           | **Exact** match on the name (no substring)                               |
| `-n`           | Only the **newest** matching process                                     |
| `-o`           | Only the **oldest** matching process                                     |
| `-c`           | Print **count** of matches instead of PIDs                               |
| `-l`           | (`pgrep` only) Also show process names                                   |
| `-a`           | (`pgrep` only) Show full command lines                                   |
| `-SIGNAL`      | (`pkill` only) Signal to send — default is `SIGTERM`                     |

**Examples:**

```bash
pgrep nginx
# Print PIDs of every nginx process

pgrep -a sshd
# PIDs + full command lines for sshd workers

pgrep -u tarek -f "python.*train.py"
# PIDs of my python training jobs (full cmdline match)

pkill -HUP nginx
# Send SIGHUP to every nginx process — tells nginx to reload its config

pkill -9 -u alice
# Force-kill every process owned by alice
# (-9 = SIGKILL; only use after a polite SIGTERM has failed)

pkill -f "node.*server.js"
# Kill node processes whose full command line matches — useful when the
# binary is just 'node' but you want to target a specific script
```

**Notes:**

- Without `-f`, the pattern only matches the **process name** (first 15 chars, the `comm` field). Use `-f` whenever you care about arguments — e.g. distinguishing two `python` processes by their script name.
- `pkill` returns **0 if it signaled at least one process**, non-zero otherwise — handy in scripts: `pkill myapp || echo "not running"`.
- Always **start polite** — `pkill myapp` (SIGTERM) lets the program clean up; `pkill -9 myapp` (SIGKILL) is for processes that ignored the polite request.
- **Test patterns with `pgrep` first** before running `pkill` — same flags, no side effects. `pgrep -af '^java'` shows you exactly what `pkill -f '^java'` would hit.
- These are **part of `procps`** on most distros — installed by default alongside `ps`.

### kill

**Description:** `kill` sends a **signal** to a process by PID. The name is a historical leftover — by default it sends `SIGTERM` (a polite "please exit"), not `SIGKILL`. Most everyday uses are reload (`-HUP`) and termination (`-TERM` or `-KILL`).

**Syntax:**

```bash
kill [-SIGNAL | -s NAME] <pid>...
kill -l                          # list all signal names
```

**Common Options:**

| Option            | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `-l`              | List signal **names** and numbers                                        |
| `-<N>`            | Send signal **number** N (e.g. `-9`)                                     |
| `-<NAME>`         | Send signal by **name** without the `SIG` prefix (e.g. `-TERM`, `-HUP`)  |
| `-s <NAME>`       | POSIX form of `-<NAME>`                                                  |
| `-0 <pid>`        | Send **no signal** — just check whether the PID exists / you can signal it |

**Examples:**

```bash
kill 4321
# Send SIGTERM to PID 4321 — the polite default

kill -HUP 4321
# Send SIGHUP — typically asks daemons to reload their config

kill -9 4321
# Send SIGKILL — kernel kills the process; cannot be caught or ignored
# Use this only after SIGTERM has been ignored

kill -STOP 4321
# Pause the process (like Ctrl+Z) without ending it

kill -CONT 4321
# Resume a previously stopped process

kill -0 4321 && echo "still running"
# Check whether PID 4321 exists and you have permission to signal it,
# without actually disturbing it

kill -- -4321
# Negative PID = send to entire process **group** 4321
# (the `--` stops kill from parsing `-4321` as a flag)

kill -l
# Print the full signal table
```

**Notes:**

- **Always try `-TERM` first**, then `-KILL`. `SIGTERM` lets the program flush buffers, close files, and exit cleanly; `SIGKILL` can corrupt state.
- **`SIGKILL` (9) and `SIGSTOP` cannot be caught, blocked, or ignored** — that's by design. A process stuck in **`D` state** (uninterruptible I/O wait) won't even die from `-9` until the I/O completes.
- **You can only signal your own processes** (real UID match), unless you're root.
- The **shell built-in `kill`** (in bash / zsh) accepts **job specs** like `kill %1` in addition to PIDs — see [Job Control](#job-control).
- A **negative PID** signals an entire **process group** — handy for killing a whole pipeline. The leader's PID is the group ID.

### Signals

**Description:** A **signal** is an asynchronous notification the kernel delivers to a process — telling it to terminate, pause, resume, reload, or just "something happened." Most signals can be **caught** (the program installs a handler), **ignored**, or left to the **default action**. Two — **`SIGKILL`** and **`SIGSTOP`** — cannot be touched.

**The signals you'll actually use:**

| #   | Name      | Default Action       | Typical Use                                                       |
| --- | --------- | -------------------- | ----------------------------------------------------------------- |
| 1   | `SIGHUP`  | Terminate            | "Hang-up" — daemons treat it as **reload config**                 |
| 2   | `SIGINT`  | Terminate            | **Interrupt** from keyboard (`Ctrl+C`)                            |
| 3   | `SIGQUIT` | Terminate + core     | Quit from keyboard (`Ctrl+\`) — dumps core for debugging          |
| 9   | `SIGKILL` | **Terminate** (forced) | The hammer — kernel kills the process; **cannot be caught**       |
| 15  | `SIGTERM` | Terminate            | The default for `kill` — **polite** termination request           |
| 17  | `SIGCHLD` | Ignore               | A child process changed state (exited / stopped)                  |
| 18  | `SIGCONT` | Continue             | Resume a stopped process                                          |
| 19  | `SIGSTOP` | **Stop**             | Pause the process; **cannot be caught**                           |
| 20  | `SIGTSTP` | Stop                 | "Terminal stop" — `Ctrl+Z` from the keyboard                      |
| 10  | `SIGUSR1` | Terminate            | **User-defined** — many daemons use it for log rotation / reopen  |
| 12  | `SIGUSR2` | Terminate            | Second user-defined signal                                        |
| 13  | `SIGPIPE` | Terminate            | Wrote to a pipe with no reader (e.g. `cmd | head` after head exits) |
| 14  | `SIGALRM` | Terminate            | Timer expired (set by `alarm(2)` or `setitimer`)                  |
| 11  | `SIGSEGV` | Terminate + core     | Invalid memory access — the classic segfault                      |

Signal numbers vary slightly between architectures — **always prefer names** (`-HUP`, `-TERM`) over numbers in scripts. Run `kill -l` for the canonical list on your system.

**The two unstoppable signals:**

- **`SIGKILL` (9)** — the kernel terminates the process immediately. No cleanup, no chance to flush, no handler runs. Use only when `SIGTERM` is ignored.
- **`SIGSTOP` (19)** — the kernel suspends the process. It stays in `T` state until it receives `SIGCONT`. Cannot be intercepted, which is what makes it useful for debugging frozen daemons.

**Examples:**

```bash
kill -HUP $(pgrep -f nginx.conf)
# Tell every nginx master/worker to re-read its config

kill -USR1 $(pidof rsyslogd)
# Many syslog daemons reopen their log files on SIGUSR1 — used by logrotate

kill -STOP 4321 ; sleep 30 ; kill -CONT 4321
# Pause a CPU-hungry job for 30s without losing its state

trap 'echo "got SIGTERM, cleaning up"; exit 0' TERM
# (inside a shell script) — install a handler so the script exits gracefully
# when killed
```

**Notes:**

- **Job-control terminal keys map to signals:** `Ctrl+C` → `SIGINT`, `Ctrl+Z` → `SIGTSTP`, `Ctrl+\` → `SIGQUIT`.
- A **zombie cannot be signaled** — it's already dead, just waiting to be reaped. Signal its parent (so the parent calls `wait()`) instead.
- Daemons usually treat **`SIGHUP` as reload** because they have no controlling terminal — there's no real "hangup" to handle, so the signal got repurposed.
- In containers, **`SIGTERM` is what `docker stop` sends** before falling back to `SIGKILL` after the grace period — your app should handle it cleanly to support fast shutdowns.

### Job Control

**Description:** **Job control** is the shell's mechanism for running multiple commands from a single terminal — pushing one to the **background**, pausing another, and bringing yet another to the **foreground**. Each shell maintains a small table of **jobs** (numbered `%1`, `%2`, …) backed by real PIDs.

**The toolkit:**

| Action / Command          | What it does                                                       |
| ------------------------- | ------------------------------------------------------------------ |
| `cmd &`                   | Run `cmd` in the **background** from the start                     |
| `Ctrl+Z`                  | **Suspend** the current foreground job (sends `SIGTSTP`)           |
| `jobs`                    | List the shell's jobs with their numbers and states                |
| `jobs -l`                 | Same, plus PIDs                                                    |
| `fg %1`                   | Bring job `%1` to the **foreground**                               |
| `bg %1`                   | Resume job `%1` in the **background**                              |
| `kill %1`                 | Signal job `%1` (default `SIGTERM`)                                |
| `wait %1`                 | Block until job `%1` finishes                                      |
| `%1`                      | Shortcut for `fg %1` (just type the job spec)                      |

**Job specs:**

| Spec      | Means                                            |
| --------- | ------------------------------------------------ |
| `%1`      | Job number 1                                     |
| `%+` / `%%` | The **current** (most recent) job              |
| `%-`      | The **previous** job                             |
| `%str`    | Most recent job whose command **starts with** `str` |
| `%?str`   | Most recent job whose command **contains** `str` |

**Examples:**

```bash
sleep 300 &
# Start sleep in background — shell prints "[1] 4321" (job 1, PID 4321)

jobs
# [1]+  Running   sleep 300 &

# Run a build in the foreground, then realize you want it backgrounded:
make build         # ... too long ...
^Z                 # Ctrl+Z — suspends make; shell says "Stopped"
bg                 # resumes it in the background, prompt comes back
jobs               # confirms it's "Running"

fg %1
# Pull job 1 back to the foreground (waits for it, Ctrl+C now works)

kill %2
# Politely terminate job 2 — no need to look up its PID
```

**Notes:**

- **`&` returns immediately** but the job stays attached to your **terminal** — if you log out, the shell sends `SIGHUP` and the job typically dies. Use [nohup or disown](#nohup--disown) to detach.
- **Suspended ≠ killed.** A `Ctrl+Z`'d job is still in memory (state `T`), holding its file descriptors. Use `bg` to resume it or `kill %N` to discard it.
- The job table is **per-shell** — open a new terminal and you won't see the jobs of the old one. Use `ps` / `pgrep` to find them across shells.
- The shell prints job state changes (`Done`, `Stopped`, `Terminated`) just before your **next prompt**, not at the moment they happen.
- Inside scripts, job control is off by default — use `set -m` if you actually need it, but most scripts manage children directly via `&`, `wait`, and PIDs.

### nohup & disown

**Description:** Both let a process **survive logging out**, but in different ways. **`nohup`** is a wrapper you run at the start; **`disown`** is a shell built-in you run after the fact. The problem they solve is the same: when your shell exits, it sends `SIGHUP` to every job in its job table, killing them unless they're detached or immune.

**Syntax:**

```bash
nohup <command> [args...] [&]
disown [-h] [-a] [%jobspec | pid]
```

**Common Options:**

| Option        | Tool      | Description                                                              |
| ------------- | --------- | ------------------------------------------------------------------------ |
| (`nohup` core)| `nohup`   | Ignores `SIGHUP`, **redirects stdout/stderr to `nohup.out`** if attached to a TTY, redirects stdin from `/dev/null` |
| `-h`          | `disown`  | Don't remove from job table — just **mark** it so `SIGHUP` is not sent at exit |
| `-a`          | `disown`  | Apply to **all** jobs                                                    |
| `-r`          | `disown`  | Apply only to **running** jobs                                           |

**Examples:**

```bash
nohup ./long_job.sh &
# Start long_job.sh, immune to SIGHUP, output → ./nohup.out
# Safe to close the terminal afterward.

nohup ./long_job.sh > job.log 2>&1 &
# Same idea, with explicit log destination — no nohup.out clutter

./long_job.sh &        # forgot nohup
disown %1
# Removes job 1 from the shell's job table — it survives logout
# (still keeps its stdout/stderr pointing at the current terminal)

disown -h %1
# Keep it in the job list so `jobs` still shows it, but don't SIGHUP at exit

disown -a
# Detach every backgrounded job in one shot
```

**Notes:**

- **`nohup` doesn't background by itself** — you still need the trailing `&`. It just makes the process ignore `SIGHUP` and tidies up its standard streams.
- **The output redirection matters.** If you don't redirect, `nohup` writes to `./nohup.out` (or `$HOME/nohup.out` if cwd isn't writable). For long-running jobs, redirect explicitly to a file you control.
- **`disown` only affects the current shell's job table** — once disowned, the process can't be referenced as `%N` anymore. Look it up by PID with `ps`.
- For a serious long-running job, the modern alternatives are **`systemd-run --user`**, **`tmux` / `screen`**, or wrapping the command in a proper **systemd service**. `nohup` is a quick fix, not a daemon framework.
- **SSH disconnect ≠ logout in all cases** — modern login shells often leave background jobs running after the SSH session dies anyway (the kernel hands them to init). Test before relying on it.

### nice & renice

**Description:** Adjust a process's **nice value** — a politeness score from `-20` (greedy, highest priority) to `+19` (gentle, lowest). The kernel's scheduler uses it to bias CPU time toward less-nice processes. Only **root** can lower (more negative) the value; any user can raise it on their own processes.

**Syntax:**

```bash
nice [-n <adjustment>] <command> [args...]
renice [-n] <priority> [-p <pid>...] [-u <user>...] [-g <pgid>...]
```

**Common Options:**

| Option        | Tool      | Description                                                              |
| ------------- | --------- | ------------------------------------------------------------------------ |
| `-n N`        | both      | Set / adjust the nice value to **N** (`renice`) or **by N** (`nice`)     |
| `-p`          | `renice`  | Target by **PID**                                                        |
| `-u`          | `renice`  | Target by **user**                                                       |
| `-g`          | `renice`  | Target by **process group**                                              |

**Examples:**

```bash
nice -n 10 ./encode.sh
# Start encode.sh with nice value +10 — it yields CPU to anything more important

nice ./encode.sh
# Default adjustment is +10 (so equivalent to the line above)

sudo nice -n -5 ./latency-critical
# Start with HIGHER priority — only root can pass negative values

renice -n 15 -p 4321
# Make running PID 4321 nicer (lower priority) by setting nice=+15

renice -n 5 -u tarek
# Adjust every process owned by 'tarek' to nice=+5

ps -eo pid,ni,user,cmd --sort=ni | head
# List processes by nice value — see who's been nice'd / renice'd
```

**Notes:**

- **Nice values are advisory** — they bias the scheduler, they don't guarantee anything. On a lightly loaded system, a +19 process can still get plenty of CPU.
- The kernel maps nice values to **scheduling weights**, not slices. A `-20` process gets roughly **1000×** the CPU share of a `+19` process under contention.
- **You cannot make your own process more aggressive without `sudo`** — even reverting your own +10 back to 0 may require root, depending on `RLIMIT_NICE` (set per-user in `/etc/security/limits.conf`).
- For **I/O priority** (disk bandwidth, not CPU), use **`ionice`** — a separate but conceptually similar tool.
- **`cgroups` and `systemd` slices** are the modern, more reliable way to bound a workload's resource share. `nice` is the legacy knob and is still useful for one-off jobs.

### /proc Filesystem

**Description:** `/proc` is a **virtual filesystem** the kernel exposes — its files don't live on disk; reading them returns **live data** about processes and the kernel itself. Almost every tool in this section (`ps`, `top`, `htop`, `pstree`, `pgrep`) is just a pretty wrapper around `/proc`.

**Layout:**

| Path                          | Contents                                                                  |
| ----------------------------- | ------------------------------------------------------------------------- |
| `/proc/<pid>/`                | Per-process directory — one for every running PID                         |
| `/proc/<pid>/cmdline`         | The **full command line** that started the process (null-byte separated)  |
| `/proc/<pid>/cwd`             | Symlink to the process's **current working directory**                    |
| `/proc/<pid>/exe`             | Symlink to the actual **executable** on disk                              |
| `/proc/<pid>/environ`         | Process's **environment variables** (null-byte separated)                 |
| `/proc/<pid>/status`          | Human-readable summary: UID, GID, threads, memory, **state**, signals     |
| `/proc/<pid>/stat`            | Compact, space-separated version of the same — what `ps` parses           |
| `/proc/<pid>/fd/`             | Symlinks to every **open file descriptor**                                |
| `/proc/<pid>/maps`            | The process's **memory map** — every mapped region, library, stack, heap  |
| `/proc/<pid>/limits`          | Resource limits in effect (`ulimit`)                                      |
| `/proc/<pid>/io`              | Bytes read / written from disk                                            |
| `/proc/cpuinfo`               | CPU model, cores, flags                                                   |
| `/proc/meminfo`               | Memory totals and breakdowns                                              |
| `/proc/loadavg`               | The three load averages plus running/total tasks                          |
| `/proc/uptime`                | Seconds since boot, seconds idle                                          |
| `/proc/mounts`                | Currently mounted filesystems (also `findmnt` / `mount`)                  |
| `/proc/self/`                 | Shortcut to **the reader's own** `/proc/<pid>/` — handy in scripts        |

**Examples:**

```bash
cat /proc/$$/status | head
# Show the status of the current shell ($$) — Name, State, PID, PPID, UID, ...

tr '\0' ' ' < /proc/$$/cmdline ; echo
# Print the shell's command line with spaces instead of NULs

ls -l /proc/$(pgrep -n nginx)/fd
# Every file descriptor the newest nginx worker has open
# (sockets, log files, /dev/null, ...)

cat /proc/loadavg
# 0.34 0.21 0.18 1/523 18432
# 1-min, 5-min, 15-min load averages; running/total tasks; last PID issued

cat /proc/meminfo | head -5
# Live memory stats — what `free`, `top`, and `vmstat` are all reading

readlink /proc/self/exe
# /usr/bin/cat   (or whatever binary just ran this command)
```

**Notes:**

- `/proc/<pid>/` **disappears** the instant the process exits — racing against the kernel is a common gotcha when scripting. Capture the data, then process it.
- **`/proc/<pid>/exe` is the canonical way to find a binary's real path**, even if the original file was deleted or replaced — the symlink still points to the inode the kernel has open.
- Many `/proc` files are **null-byte separated** (`cmdline`, `environ`) — pipe through `tr '\0' '\n'` or `tr '\0' ' '` to make them readable.
- Writing to `/proc/sys/...` tunes **runtime kernel parameters** (the same knobs `sysctl` exposes). Don't poke around in `/proc/sys` without knowing what you're changing.
- `/sys` is the modern cousin — it exposes **device and driver state** in a more structured tree. `/proc` is older and a bit of a junk drawer, but it's the one every tool still reads.

---

## Packages

Notes on Linux **packages** — how software is bundled, shipped, installed, updated, and (when needed) compiled from source. Every distro answers the same questions differently: which **format** do packages use (`.rpm` vs `.deb`), which **tool** installs them (`rpm` / `dpkg`), and which **front-end** resolves dependencies and talks to repositories (`yum`/`dnf` vs `apt`). This section walks that stack from the bottom (raw tarballs) to the top (a one-line `apt install` that pulls in 40 dependencies).

### One Shot Revision

| Command                                         | Short Description                                                            |
| ----------------------------------------------- | ---------------------------------------------------------------------------- |
| [Software Distribution](#software-distribution) | How Linux software is shipped — source, tarballs, **`.rpm`** / **`.deb`**, Snap/Flatpak |
| [Package Repositories](#package-repositories)   | Central servers of packages — `/etc/apt/sources.list`, `/etc/yum.repos.d/`, GPG keys |
| [tar and gzip](#tar-and-gzip)                   | Bundle and compress files — the `.tar.gz` (tarball) workflow                 |
| [Package Dependencies](#package-dependencies)   | Shared libraries, version pinning, and how dependency hell happens           |
| [rpm and dpkg](#rpm-and-dpkg)                   | **Low-level** package tools — install one file, query, list — **no** dependency resolution |
| [yum and apt](#yum-and-apt)                     | **High-level** front-ends — resolve dependencies, talk to repos, upgrade the system |
| [Compile Source Code](#compile-source-code)     | The classic `./configure && make && make install` workflow                   |
| [How to Build NGINX from Source](#how-to-build-nginx-from-source) | Real-world source build: deps → configure → make → install → systemd |

### Software Distribution

**Description:** Linux software reaches your machine in one of four shapes: as **source code** (a tarball you compile yourself), as a **binary package** (`.rpm` for the Red Hat family, `.deb` for the Debian family), as a **distro-agnostic bundle** (Snap, Flatpak, AppImage), or as a **container image** (Docker / OCI). Each form trades off install speed, isolation, distro coupling, and how easy it is to upgrade. Knowing which one you're dealing with tells you which tool to reach for.

**The shapes of Linux software:**

| Form                 | Example file              | Installed with                | Notes                                                                  |
| -------------------- | ------------------------- | ----------------------------- | ---------------------------------------------------------------------- |
| **Source tarball**   | `foo-1.2.3.tar.gz`        | `./configure && make && make install` | Most flexible, slowest, no automatic upgrades. See [Compile Source Code](#compile-source-code). |
| **RPM package**      | `foo-1.2.3-1.el9.x86_64.rpm` | `rpm` (low-level) / `yum`/`dnf` (high-level) | RHEL, CentOS, Fedora, Rocky, Alma, openSUSE.                  |
| **DEB package**      | `foo_1.2.3-1_amd64.deb`   | `dpkg` (low-level) / `apt` (high-level) | Debian, Ubuntu, Mint, Kali, Pop!_OS.                              |
| **Snap**             | `foo_42.snap`             | `snap install foo`            | Canonical's distro-agnostic format; auto-updates; sandboxed.           |
| **Flatpak**          | `org.foo.App.flatpak`     | `flatpak install ...`         | Cross-distro desktop apps; user-level installs; runtime-based.         |
| **AppImage**         | `foo-1.2.3.AppImage`      | `chmod +x && ./foo.AppImage`  | Single-file portable binary — no install step at all.                  |
| **Container image**  | `foo:1.2.3` (OCI)         | `docker run` / `podman run`   | Full userspace + app, isolated from the host.                          |
| **Language registries** | `pip install`, `npm i`, `cargo install`, `go install` | Per-ecosystem | Install *into* an existing system — not OS packages.            |

**Where each form lives on disk (typical):**

```
/usr/bin/                ← binaries from distro packages (rpm/deb)
/usr/lib/                ← shared libraries from distro packages
/usr/share/              ← arch-independent data (docs, icons, locales)
/etc/                    ← config files owned by packages
/usr/local/bin/          ← binaries you compiled from source (don't conflict with the package manager)
/opt/<vendor>/           ← self-contained third-party software (Slack, Chrome, custom RPMs)
/var/lib/snapd/snaps/    ← Snap squashfs files
/var/lib/flatpak/        ← Flatpak runtimes and apps
~/.local/bin/            ← per-user installs (pip --user, cargo, language tools)
```

**Examples:**

```bash
# Identify what a downloaded file actually is:
file ./mystery-download
# foo-1.2.3.tar.gz:       gzip compressed data, from Unix
# foo-1.2.3-1.x86_64.rpm: RPM v3.0 bin i386/x86_64 foo-1.2.3-1
# foo_1.2.3-1_amd64.deb:  Debian binary package (format 2.0)

# Find out which "family" your distro belongs to:
cat /etc/os-release | grep -E '^ID|ID_LIKE'
# ID=ubuntu             ID_LIKE=debian      → use apt / dpkg
# ID=rocky              ID_LIKE="rhel centos fedora"  → use dnf / yum / rpm

# Which package owns a file already on disk?
# (Debian)
dpkg -S /usr/bin/ls
# coreutils: /usr/bin/ls
# (RPM)
rpm -qf /usr/bin/ls
# coreutils-9.0-5.el9.x86_64
```

**Notes:**

- **Pick the right form for the job.** Distro packages give you automatic security updates and dependency resolution. Snap/Flatpak win when you need a newer version than the distro ships. Source builds win when nothing else exists. Containers win when you don't want to touch the host.
- **Never mix and match for the same software.** Installing `nginx` from a tarball *and* from `apt` puts two copies on disk; only one will be on your `$PATH`, and the package manager won't know about the other.
- **`/usr/local`** is the convention for "I built this from source" — it's not managed by `apt` / `yum`, so it never fights with the package manager.
- **AppImages don't auto-update** — you're responsible for replacing the file when a new version drops. Tools like `appimaged` / `AppImageUpdate` add that layer.
- **Language package managers (`pip`, `npm`, `gem`, `cargo`) are not OS package managers** — they install into a language-specific tree (`site-packages`, `node_modules`, ...) and ignore the system package database. Mixing `pip install` with `apt install python3-foo` is a classic source of breakage; that's why modern Python pushes `venv` / `pipx` / `uv`.

### Package Repositories

**Description:** A **repository** is a server (or a mirror of one) that hosts packages plus a **signed index** describing what's available, which versions, and how the packages depend on each other. When you run `apt install nginx` or `dnf install nginx`, the front-end downloads that index, finds `nginx` and its dependencies, fetches the right `.deb` / `.rpm` files, verifies the GPG signatures, and installs them. Configuring repos correctly — official, third-party, version-pinned — is what separates a maintainable box from a fragile one.

**Where repos are configured:**

| Family       | Config location                          | Index file the tool downloads                          |
| ------------ | ---------------------------------------- | ------------------------------------------------------ |
| **Debian / Ubuntu** | `/etc/apt/sources.list` + `/etc/apt/sources.list.d/*.list` | `Packages.gz` / `Release` per suite & component        |
| **RHEL / Fedora**   | `/etc/yum.repos.d/*.repo`                | `repodata/repomd.xml` + `primary.xml.gz`               |
| **GPG keys (Debian)** | `/etc/apt/trusted.gpg.d/*.gpg` or `/etc/apt/keyrings/*.gpg` | Used to verify the `Release` file's signature |
| **GPG keys (RPM)**  | `/etc/pki/rpm-gpg/`                      | Referenced from each `.repo` file via `gpgkey=`        |

**Anatomy of a Debian source line:**

```
deb [signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu jammy stable
 │                                            │                                       │      │
 └─ type (deb / deb-src)                       └─ base URL                              │      └─ component
                                                                                       └─ suite (release codename)
```

**Anatomy of an RPM `.repo` file:**

```ini
[docker-ce-stable]
name=Docker CE Stable - $basearch
baseurl=https://download.docker.com/linux/centos/$releasever/$basearch/stable
enabled=1
gpgcheck=1
gpgkey=https://download.docker.com/linux/centos/gpg
```

**Examples:**

```bash
# Debian: list every configured source
grep -hrE '^deb ' /etc/apt/sources.list /etc/apt/sources.list.d/

# RHEL: list every enabled repo
dnf repolist enabled        # or: yum repolist enabled

# Refresh the local index (always do this before installing on Debian):
sudo apt update
# Reading package lists... Done
# All packages are up to date.

# Add a third-party repo the modern (keyring-based) way on Debian/Ubuntu:
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list
sudo apt update

# Add a repo on RHEL/Fedora:
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo rpm --import https://download.docker.com/linux/centos/gpg
sudo dnf install docker-ce

# Which repo did a given package come from?
apt-cache policy nginx        # Debian — shows priority and origin URL
dnf info nginx                # RPM — shows "From repo : ..."
```

**Common repository types:**

| Repo                | Family       | What's in it                                                         |
| ------------------- | ------------ | -------------------------------------------------------------------- |
| `main` / `universe` / `multiverse` / `restricted` | Ubuntu | Ubuntu's four standard components (license + support tier).         |
| `BaseOS` / `AppStream` / `CRB`                  | RHEL 9 | The split that replaced the old single `base` repo.                  |
| **EPEL** (Extra Packages for Enterprise Linux)  | RHEL    | Community-maintained extras not in RHEL itself — `htop`, `jq`, etc. |
| **RPM Fusion**                                  | Fedora  | Codecs and software with licensing issues.                           |
| **PPAs** (`ppa:user/name`)                      | Ubuntu  | Personal Package Archives — third-party repos hosted on Launchpad.   |

**Notes:**

- **Always verify GPG signatures.** A repo without a key is a repo that can ship you anything. Modern Debian rejects unsigned repos by default; modern RHEL uses `gpgcheck=1` in every `.repo` file.
- **Run `apt update` before `apt install`.** APT only knows what was in the index at the last update — installing without refreshing can pull stale or missing-from-mirror versions.
- **`apt-key` is deprecated** — the `signed-by=` syntax pointing at a file in `/etc/apt/keyrings/` is the new way (Debian 11+, Ubuntu 22.04+).
- **EPEL is almost mandatory on RHEL.** Many common tools (`htop`, `jq`, `ncdu`, `tmux` on older releases) live there, not in BaseOS.
- **Don't enable random copy-pasted repos as root** without reading them first — a malicious `.repo` or `sources.list` line can pull packages that overwrite system files. Pin third-party repos to **only the packages you actually want** (`apt-pinning`, `dnf includepkgs=`).
- For air-gapped boxes, you can host a **local mirror** with `apt-mirror`, `reposync`, or just an `nginx` serving a directory of `.deb` / `.rpm` files plus the generated metadata.

### tar and gzip

**Description:** **`tar`** ("tape archive") bundles many files into one — preserving paths, permissions, timestamps, and ownership — but does **not** compress. **`gzip`** compresses a single file. Together they form the canonical **`.tar.gz`** (a.k.a. **tarball**) workflow: source releases, backups, and the raw payload inside every `.rpm` / `.deb` are all just tarballs underneath. Modern `tar` calls the compressor for you (`-z` for gzip, `-j` for bzip2, `-J` for xz), so you rarely run `gzip` directly.

**Syntax:**

```bash
tar [operation][options] [-f archive] [files...]
gzip [options] <file>          # in-place: creates <file>.gz, removes original
gunzip <file.gz>               # in-place: restores <file>, removes .gz
```

**`tar` cheat sheet — the verbs:**

| Flag | Long              | What it does                                       |
| ---- | ----------------- | -------------------------------------------------- |
| `-c` | `--create`        | **Create** a new archive                           |
| `-x` | `--extract`       | **Extract** files from an archive                  |
| `-t` | `--list`          | **List** archive contents without extracting       |
| `-r` | `--append`        | Append to an existing (uncompressed) archive       |
| `-u` | `--update`        | Append only files newer than what's in the archive |

**`tar` cheat sheet — the modifiers:**

| Flag       | What it does                                                             |
| ---------- | ------------------------------------------------------------------------ |
| `-f FILE`  | Use `FILE` as the archive (use `-` for stdin/stdout)                     |
| `-v`       | Verbose — list every file as it's processed                              |
| `-z`       | Compress / decompress with **gzip** (`.tar.gz`, `.tgz`)                  |
| `-j`       | Compress / decompress with **bzip2** (`.tar.bz2`)                        |
| `-J`       | Compress / decompress with **xz** (`.tar.xz`)                            |
| `-C DIR`   | `cd` into `DIR` before doing anything                                    |
| `--strip-components=N` | Drop `N` leading path components on extract (handy for vendored tarballs) |
| `-p`       | Preserve permissions on extract (default when run as root)               |

**`gzip` essentials:**

| Flag      | What it does                                                |
| --------- | ----------------------------------------------------------- |
| `-k`      | **Keep** the original file (default behavior is to delete it) |
| `-d`      | Decompress — same as `gunzip`                               |
| `-1` .. `-9` | Trade speed for ratio (`-1` fastest, `-9` smallest)      |
| `-l`      | List compression info for a `.gz` file                      |
| `-c`      | Write to stdout (let you pipe / redirect)                   |

**Examples:**

```bash
# Create a gzipped tarball of a directory:
tar -czvf backup.tar.gz /home/tarek/project
# c=create  z=gzip  v=verbose  f=output file

# Inspect without extracting:
tar -tzvf backup.tar.gz | head
# -rw-r--r-- tarek/tarek  1024 2026-06-10 14:22 project/README.md
# ...

# Extract into the current directory:
tar -xzvf backup.tar.gz

# Extract somewhere specific, stripping the top folder:
mkdir -p /opt/app
tar -xzvf app-1.2.3.tar.gz -C /opt/app --strip-components=1
# Drops "app-1.2.3/" from every path — files land directly in /opt/app/

# Just compress a single file:
gzip -k report.log
# Creates report.log.gz, keeps report.log (without -k it'd delete the original)

# Decompress without removing the .gz:
gunzip -k report.log.gz

# Stream a tarball over SSH (no temp file on either side):
tar -czf - ./src | ssh user@host 'tar -xzf - -C /opt/dest'

# Compare the contents of a tarball against the live filesystem:
tar -dzvf backup.tar.gz -C /home/tarek/project
# d=diff — shows files that have changed since the archive was made
```

**Notes:**

- The flag order **does not require dashes** historically — `tar czvf foo.tar.gz dir/` is the same as `tar -czvf foo.tar.gz dir/`. Both still work.
- **`tar` does not compress on its own** — `tar -cf x.tar dir/` produces an uncompressed archive. The `-z` / `-j` / `-J` flag is what calls `gzip` / `bzip2` / `xz`.
- **Auto-detect on extract:** modern `tar` (GNU `tar` ≥ 1.15) detects the compression automatically — `tar -xf archive.???` works for `.tar`, `.tar.gz`, `.tar.bz2`, `.tar.xz` without specifying which.
- **`xz` (`-J`) is ~30% smaller than gzip** but much slower to compress. It's now the default for kernel and many distro tarballs.
- **`tar` preserves UID/GID by number, not by name.** Extracting an archive made on another system as root can produce files owned by a UID that doesn't exist locally — use `--no-same-owner` (default for non-root) to extract as the current user.
- **`zcat`, `zless`, `zgrep`** read a `.gz` file without explicitly decompressing — handy for searching gzipped logs (`zgrep ERROR /var/log/nginx/access.log.*.gz`).
- For directory-tree archives where you'll later want to **extract just one file**, `tar` is fine; for random access into a huge archive, prefer `zip` (per-file compression, indexed) or `squashfs`.

### Package Dependencies

**Description:** Almost no real software is self-contained — a single `.deb` or `.rpm` typically declares a list of **other packages it needs** (`libssl`, `python3`, `glibc ≥ 2.34`, ...) and the package manager's job is to walk that graph, resolve all the transitive needs, pick compatible versions, and install everything in the right order. When that graph has no solution — two packages need conflicting versions of the same library, a needed package was removed from the repo, a downgrade would break something else — you've hit **dependency hell**. Modern front-ends (`apt`, `dnf`) are mostly about preventing it.

**Kinds of dependency relationships:**

| Term                | Example                                              | Meaning                                                            |
| ------------------- | ---------------------------------------------------- | ------------------------------------------------------------------ |
| **Depends / Requires** | `nginx` depends on `libssl3`                       | Must be installed for this package to work at all.                 |
| **Recommends**      | `git` recommends `less`                              | Strongly suggested — `apt` installs it by default; `--no-install-recommends` skips. |
| **Suggests**        | `vim` suggests `ctags`                               | Optional add-on — never installed automatically.                   |
| **Conflicts**       | `sendmail` conflicts with `postfix`                  | Can't coexist — installing one removes the other.                  |
| **Provides**        | `postfix` provides `mail-transport-agent`            | A **virtual package** name that anything in the same role can satisfy. |
| **Replaces / Obsoletes** | `apt` replaces / obsoletes `apt-utils-old`       | This package supersedes another — used during upgrades.            |
| **Pre-Depends**     | (Debian) `dpkg` pre-depends on `tar`                 | Must be **fully configured** before this package is even unpacked. |

**Shared libraries — the real dependency layer:**

Most "this package needs that package" rules exist because the binary inside dynamically links to a **shared library** (`.so`). The package manager doesn't read the ELF headers itself — the *package builder* declared the dependency — but the underlying truth lives in `ldd`:

```bash
ldd /usr/bin/nginx
#   linux-vdso.so.1
#   libssl.so.3 => /lib/x86_64-linux-gnu/libssl.so.3
#   libcrypto.so.3 => /lib/x86_64-linux-gnu/libcrypto.so.3
#   libpthread.so.0 => /lib/x86_64-linux-gnu/libpthread.so.0
#   libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6
#   ...

# Which package provides that library?
dpkg -S /lib/x86_64-linux-gnu/libssl.so.3
# libssl3:amd64: /usr/lib/x86_64-linux-gnu/libssl.so.3
```

**Examples:**

```bash
# Show what a package depends on:
apt-cache depends nginx                  # Debian
dnf repoquery --requires nginx           # RPM

# Show what depends on a given package (reverse deps):
apt-cache rdepends libssl3
dnf repoquery --whatrequires libssl3

# Find every broken dependency on the system:
sudo apt --fix-broken install            # Debian
sudo dnf check                           # RPM
# `dnf check` reports unresolved deps, duplicates, and conflicts.

# Hold a package at its current version (prevent upgrade):
sudo apt-mark hold nginx                 # Debian
sudo dnf versionlock add nginx           # RPM (needs the versionlock plugin)

# Why did apt want to install all these extras?
apt install nginx --dry-run
# The following additional packages will be installed:
#   libssl3 nginx-common nginx-core ...

# Don't pull in "Recommends" (smaller install footprint):
sudo apt install --no-install-recommends nginx
```

**Dependency hell — the classic shapes:**

| Symptom                                                       | What's happening                                                            |
| ------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `Depends: foo (>= 1.5) but 1.3 is to be installed`            | The repo doesn't carry a new enough version — add a backports / EPEL repo.  |
| `Conflicts: bar but baz is already installed`                 | Two packages claim the same files or the same role — pick one.              |
| `Held broken packages`                                        | You ran a half-finished install — `apt --fix-broken install` to resolve.    |
| `Requires: libfoo.so.1()(64bit)` and no package provides it   | A library that used to ship with the distro was renamed/removed — find the new package via `dnf provides */libfoo.so.1`. |
| `error: Failed dependencies` from `rpm -i ...`                | You're using the low-level tool, which **does no resolution**. Use `dnf` instead. |

**Notes:**

- **The package manager solves a SAT problem.** `apt`'s solver and `dnf`'s `libsolv` are both real constraint solvers — when they refuse to install something, they have a reason. Read the error before forcing.
- **`Recommends` defaults to ON in Debian/Ubuntu.** That's why `apt install foo` sometimes pulls in 30 packages instead of 5. `--no-install-recommends` is a common flag in `Dockerfile`s and container images.
- **Held packages can wreck upgrades.** If `apt upgrade` refuses to upgrade something, check `apt-mark showhold` and `dpkg --get-selections | grep hold`.
- **Don't `--force` your way through.** `rpm -i --nodeps`, `dpkg -i --force-depends`, `apt-get install --allow-unauthenticated` — these *appear* to work and silently break later. Almost always the right answer is to add the missing repo or fix the conflict.
- **Snap / Flatpak / containers sidestep dependency hell** by bundling their own runtime — at the cost of disk space and slower security patching (every bundled `libssl` is its own update problem).
- **Pinning** (Debian: `/etc/apt/preferences.d/`, RPM: `versionlock`) is how you keep one package at version X while everything else moves — useful for production servers that need a specific kernel or DB version.

### rpm and dpkg

**Description:** **`rpm`** (Red Hat family) and **`dpkg`** (Debian family) are the **low-level** package tools — they install, remove, query, and inspect a *single* package file you've already downloaded. They do **not** talk to repositories, and they do **not** resolve dependencies for you — if `foo.rpm` needs `libbar`, `rpm -i foo.rpm` fails with `Failed dependencies` and stops. That's why everyday work uses [yum and apt](#yum-and-apt) on top. Reach for `rpm` / `dpkg` when you need to query the package database, inspect a downloaded file, or install a one-off `.deb` / `.rpm` that isn't in any repo.

**Syntax:**

```bash
rpm  <operation> [options] <package-or-query>
dpkg <operation> [options] <package-or-query>
```

**Common `rpm` operations:**

| Command                  | What it does                                                       |
| ------------------------ | ------------------------------------------------------------------ |
| `rpm -ivh foo.rpm`       | **Install** package (`v` verbose, `h` progress hashes)             |
| `rpm -Uvh foo.rpm`       | **Upgrade** (install if missing, else replace)                     |
| `rpm -e foo`             | **Erase** (uninstall) a package                                    |
| `rpm -q foo`             | Is `foo` installed? (and which version)                            |
| `rpm -qa`                | List **all** installed packages                                    |
| `rpm -ql foo`            | List every **file** that `foo` installed                           |
| `rpm -qf /path/to/file`  | Which package owns this file?                                      |
| `rpm -qi foo`            | Full **info** — version, license, summary, vendor, install date    |
| `rpm -qp foo.rpm` (+ above flags) | Query **a `.rpm` file** that isn't installed yet          |
| `rpm -V foo`             | **Verify** — show files that have changed since install            |

**Common `dpkg` operations:**

| Command                   | What it does                                                       |
| ------------------------- | ------------------------------------------------------------------ |
| `dpkg -i foo.deb`         | **Install** a `.deb` file                                          |
| `dpkg -r foo`             | **Remove** (keep config files)                                     |
| `dpkg -P foo`             | **Purge** (remove + delete config files)                           |
| `dpkg -l`                 | List **all** installed packages                                    |
| `dpkg -l foo`             | Show status of `foo` (`ii` = installed, `rc` = removed-config-left)|
| `dpkg -L foo`             | List every **file** that `foo` installed                           |
| `dpkg -S /path/to/file`   | Which package owns this file?                                      |
| `dpkg -s foo`             | **Status** — info about an installed package                       |
| `dpkg -I foo.deb`         | Show metadata of a `.deb` **file** (before installing)             |
| `dpkg -c foo.deb`         | List the files **inside** a `.deb` without installing              |
| `dpkg --configure -a`     | Finish configuring any half-installed packages                     |

**Examples:**

```bash
# Install a one-off .rpm you downloaded:
sudo rpm -ivh google-chrome-stable_current_x86_64.rpm
# error: Failed dependencies:
#   liberation-fonts is needed by google-chrome-stable-...
# → rpm tells you what's missing; install with dnf instead:
sudo dnf install ./google-chrome-stable_current_x86_64.rpm
# (dnf resolves the deps and uses rpm under the hood)

# Same idea on Debian:
sudo dpkg -i ./code_1.95.0-amd64.deb
# Errors were encountered while processing:
#   code depends on libnss3 (>= 3.26); ...
sudo apt --fix-broken install        # pulls the missing deps
# (or use `apt install ./code_*.deb` directly — apt accepts a local file)

# Find which package owns a file:
rpm -qf /usr/bin/curl
# curl-7.76.1-26.el9.x86_64
dpkg -S /usr/bin/curl
# curl: /usr/bin/curl

# List every file a package put on disk:
rpm -ql nginx | head
dpkg -L nginx | head

# Inspect a .deb you haven't installed yet:
dpkg -I ./somepackage.deb     # metadata
dpkg -c ./somepackage.deb     # file list

# What changed since install? (great for detecting tampering or config drift)
rpm -V openssh-server
# S.5....T.  c /etc/ssh/sshd_config
# S=size differs, 5=md5 differs, T=mtime differs, c=config file

# Pending half-installed packages causing apt errors:
sudo dpkg --configure -a
```

**Notes:**

- **`rpm -i` and `dpkg -i` do not resolve dependencies.** When they fail, don't add `--nodeps` / `--force` — let `dnf` or `apt` handle the install instead. They use the low-level tool under the hood **and** read the repo metadata.
- **`apt install ./file.deb`** is the modern shortcut for "install a downloaded `.deb` with dependency resolution." Same for `dnf install ./file.rpm`. You almost never need raw `dpkg -i` or `rpm -i` directly.
- **`-U` (upgrade) is safer than `-i` (install) for `rpm`** — it handles "install or upgrade" in one shot.
- The **package database** lives at `/var/lib/rpm/` (RPM) and `/var/lib/dpkg/` (Debian). Corruption is rare but recoverable: `rpm --rebuilddb`, `dpkg --configure -a`.
- `dpkg -l` first-column status codes: `ii` = installed, `rc` = removed but config remains, `un` = never installed, `iU` = unpacked but unconfigured.
- **`rpm -V`** is a quick poor-man's tripwire — it shows every file that's been modified since the package was installed, including config files. The leading flag letters (`S`/`5`/`T`/`M`/`U`/`G`/`L`/`c`) decode in `man rpm`.

### yum and apt

**Description:** **`apt`** (Debian / Ubuntu) and **`yum`** / **`dnf`** (RHEL / Fedora) are the **high-level** front-ends — they read your configured [package repositories](#package-repositories), resolve [dependencies](#package-dependencies), download the right `.deb` / `.rpm` files, verify their GPG signatures, and hand them off to [dpkg / rpm](#rpm-and-dpkg) to install. They also handle **search**, **upgrade**, and **removal** in one fluent CLI. `yum` is the older RHEL tool; **`dnf`** is its modern replacement (RHEL 8+, Fedora) and has the same commands. This is the layer you use every day.

**Syntax:**

```bash
apt <command> [options] [packages...]
dnf <command> [options] [packages...]      # yum <command> works the same
```

**Side-by-side cheat sheet:**

| Goal                          | Debian / Ubuntu (`apt`)           | RHEL / Fedora (`dnf` / `yum`)         |
| ----------------------------- | --------------------------------- | ------------------------------------- |
| Refresh repo metadata         | `apt update`                      | `dnf check-update` (auto on most cmds)|
| Install a package             | `apt install <pkg>`               | `dnf install <pkg>`                   |
| Install a local file          | `apt install ./file.deb`          | `dnf install ./file.rpm`              |
| Upgrade one package           | `apt install --only-upgrade <pkg>`| `dnf upgrade <pkg>`                   |
| Upgrade **everything**        | `apt upgrade` / `apt full-upgrade`| `dnf upgrade`                         |
| Remove a package              | `apt remove <pkg>`                | `dnf remove <pkg>`                    |
| Remove + delete config files  | `apt purge <pkg>`                 | (config files aren't tracked the same way) |
| Clean up unused dependencies  | `apt autoremove`                  | `dnf autoremove`                      |
| Search for a package          | `apt search <term>`               | `dnf search <term>`                   |
| Show package details          | `apt show <pkg>`                  | `dnf info <pkg>`                      |
| Which package owns a file?    | `apt-file search /path` (after `apt-file update`) | `dnf provides /path`        |
| List installed packages       | `apt list --installed`            | `dnf list installed`                  |
| History of transactions       | `cat /var/log/apt/history.log`    | `dnf history`                         |
| Undo last transaction         | (none built-in)                   | `dnf history undo <id>`               |

**Examples:**

```bash
# Day-one install flow on Debian/Ubuntu:
sudo apt update                              # refresh the index FIRST
sudo apt install -y nginx                    # install
sudo apt upgrade -y                          # bring everything else up to date

# Same flow on Fedora/RHEL:
sudo dnf install -y nginx
sudo dnf upgrade -y                          # also refreshes metadata automatically

# Search for a package by topic:
apt search "json processor"
# jq/jammy 1.6-2.1 amd64 — lightweight and flexible command-line JSON processor
dnf search json | head

# Look up which package would provide a missing library:
dnf provides */libssl.so.3
# openssl-libs-3.0.7-25.el9.x86_64 : A general purpose cryptography library...
apt-file search libssl.so.3                  # needs `apt install apt-file` first

# Remove a package and its unused dependencies:
sudo apt remove nginx && sudo apt autoremove
sudo dnf remove nginx

# Inspect what would change before upgrading (Debian):
apt list --upgradable
apt-get -s upgrade                           # -s = simulate, no changes

# `dnf` has a real undo system:
sudo dnf history
#  ID | Command line                | Date and time    | Action(s)     | Altered
# ----------------------------------------------------------------------------
#   42 | install nginx              | 2026-06-10 14:22 | Install       | 7
sudo dnf history undo 42
# Rolls back transaction 42 — uninstalls nginx and its newly-pulled deps.

# Hold a package at its current version:
sudo apt-mark hold nginx                     # Debian
sudo dnf versionlock add nginx               # RPM (needs versionlock plugin)
```

**`apt` vs `apt-get` / `apt-cache`:**

- **`apt`** is the modern, user-facing wrapper (Ubuntu 16.04+). Colored output, progress bar, sensible defaults — use it interactively.
- **`apt-get`** is the older, stable, **scriptable** front-end. Use it in shell scripts, Dockerfiles, and CI — its output format is guaranteed not to change.
- **`apt-cache`** is the search/query half (`apt-cache search`, `apt-cache policy`, `apt-cache depends`). `apt` rolled some of these into itself.

**Notes:**

- **Always `apt update` before `apt install`.** On RPM systems `dnf` refreshes metadata automatically on most operations, so the extra step isn't needed.
- **`apt upgrade` vs `apt full-upgrade` (`dist-upgrade`)**: `upgrade` will *never* remove packages to satisfy dependencies — if an upgrade needs a removal, it just skips that package. `full-upgrade` *will* remove things. Use `upgrade` for routine patching, `full-upgrade` for major version bumps.
- **`autoremove` cleans up orphans** — packages that were pulled in as dependencies and are no longer needed. Run it after `remove` to keep the disk tidy. Beware: a misconfigured manual install can land important packages on the "autoremove" list — read the list before confirming.
- **`-y` accepts all prompts** non-interactively. Standard in scripts and Dockerfiles, but it also accepts destructive things like "remove this list of 47 packages" — don't use `-y` interactively when running broad operations.
- **`dnf` is `yum`** for all practical purposes on RHEL 8+ / Fedora — every command above works under either name. RHEL 9 ships `yum` as a symlink to `dnf`.
- **Idempotent scripts:** use `apt-get install -y --no-install-recommends` in Dockerfiles, follow it with `rm -rf /var/lib/apt/lists/*` to shrink the image. On RPM: `dnf clean all`.

### Compile Source Code

**Description:** When a package isn't in any repo, or you need a version newer/older than what your distro ships, or you want to patch it — you build from source. The classic **autotools** workflow is **`./configure && make && sudo make install`**: a shell script that probes your system, a `Makefile`-driven compile, and an install step that copies the resulting binaries into place. Modern projects use **CMake**, **Meson**, or language-native build systems (`cargo`, `go build`, `setup.py`) — but the *shape* is the same: configure → build → install.

**The classic autotools workflow:**

```bash
tar -xzvf foo-1.2.3.tar.gz       # 1. unpack
cd foo-1.2.3
./configure --prefix=/usr/local  # 2. probe the system, decide where to install
make -j"$(nproc)"                # 3. compile (parallel — one job per core)
sudo make install                # 4. copy binaries / libs / man pages into --prefix
```

**The phases in detail:**

| Step               | What happens                                                                  |
| ------------------ | ----------------------------------------------------------------------------- |
| `./configure`      | Checks for required headers, libs, tools (e.g. "does `libssl` ≥ 3.0 exist?"). Generates a `Makefile` matching your system. Common flags: `--prefix=`, `--with-FEATURE`, `--without-FEATURE`, `--enable-FEATURE`, `--disable-FEATURE`. |
| `make`             | Reads the generated `Makefile`, runs the compiler (`gcc` / `clang`), and links objects into the final binary. `-j N` runs `N` jobs in parallel. |
| `make install`     | Copies the artifacts into `--prefix` (default `/usr/local`) — binaries to `bin/`, libs to `lib/`, headers to `include/`, man pages to `share/man/`. Needs `sudo` unless `--prefix` is in your home. |
| `make uninstall`   | If the project supports it — deletes whatever `make install` put down.        |
| `make clean` / `distclean` | Remove build artifacts; `distclean` also removes `./configure`-generated files. |

**Common build-time dependencies:**

| Package family                 | Why you need it                                                |
| ------------------------------ | -------------------------------------------------------------- |
| `build-essential` (Debian) / `@"Development Tools"` (RHEL) | `gcc`, `g++`, `make`, the C library headers — the bare minimum |
| `autoconf`, `automake`, `libtool` | If the project ships only `configure.ac` (no `./configure`) — you regenerate it via `autoreconf -i` |
| `pkg-config`                   | The `./configure` script uses it to locate library `.pc` files                  |
| **`-dev` / `-devel` packages** | Header files and `.pc` files for any library you link against (e.g. `libssl-dev`, `openssl-devel`) |
| `cmake`, `ninja`, `meson`      | For projects that use those build systems instead of autotools |

**Examples:**

```bash
# Bootstrap a build environment:
sudo apt install -y build-essential autoconf automake libtool pkg-config   # Debian
sudo dnf groupinstall -y "Development Tools"                                # RHEL/Fedora
sudo dnf install -y pkgconf-pkg-config                                      # RHEL/Fedora extras

# Build into /opt so you can throw it away cleanly:
./configure --prefix=/opt/foo-1.2.3
make -j"$(nproc)"
sudo make install
# Binaries land in /opt/foo-1.2.3/bin/ — add to PATH or symlink into /usr/local/bin/

# See every option ./configure accepts:
./configure --help | less

# Build with extra warnings or a specific compiler:
CC=clang CFLAGS="-O2 -march=native" ./configure
make -j"$(nproc)"

# CMake projects (the modern equivalent):
mkdir build && cd build
cmake .. -DCMAKE_INSTALL_PREFIX=/usr/local -DCMAKE_BUILD_TYPE=Release
cmake --build . -j"$(nproc)"
sudo cmake --install .

# Meson projects:
meson setup build --prefix=/usr/local
meson compile -C build
sudo meson install -C build

# Track what `make install` puts on disk so you can remove it later:
sudo make install DESTDIR=/tmp/staging
find /tmp/staging -type f | sed 's|/tmp/staging||' > install.list
# install.list now contains every path that was installed.
```

**Wrapping a source build into a real package:**

For anything you'll deploy to more than one machine, wrap the build into an `.rpm` or `.deb` so the package manager can track it:

| Tool         | What it does                                                                       |
| ------------ | ---------------------------------------------------------------------------------- |
| `checkinstall` | Watches `make install` and produces a `.deb` / `.rpm` from the resulting files.  |
| `fpm`        | "Effing Package Management" — builds `.deb` / `.rpm` / `tar` from a directory.     |
| `debuild` / `dpkg-buildpackage` | Build a proper `.deb` from a Debian source package.                |
| `rpmbuild`   | Build an `.rpm` from a `.spec` file.                                               |

**Notes:**

- **Always install source builds into `/usr/local/` or `/opt/`** — never `/usr/`. Anything under `/usr/` is "owned by the package manager" territory; dropping files there shadows distro binaries and breaks future upgrades.
- **`-dev` / `-devel` packages are the most common source of `./configure: error: ... not found`** — the runtime package (`libssl3`) doesn't ship headers, you need `libssl-dev` (Debian) or `openssl-devel` (RHEL).
- **`make -j$(nproc)`** speeds up builds dramatically — `-j` runs N compile jobs in parallel, `nproc` returns your core count. Without `-j`, `make` builds one file at a time.
- **`sudo make install` is dangerous and untracked.** It scatters files across `/usr/local` with no record. Prefer building into a `--prefix` you can `rm -rf`, or using `checkinstall` / `fpm` to produce a real package.
- **Reproducibility matters.** Save the exact source tarball, the `./configure` flags you used, and your distro version. Six months later you'll need to rebuild and the upstream may have moved on.
- **For one-off binaries, language tooling often beats configure/make** — `cargo install <crate>`, `go install <module>@latest`, `pipx install <pkg>`. They build into per-user trees (`~/.cargo/bin`, `~/go/bin`, `~/.local/bin`) so `sudo` isn't needed.

### How to Build NGINX from Source

**Description:** Building NGINX from source lets you choose exactly which modules to compile in, use a version newer than your distro ships, or apply a patch before the upstream release. It follows the standard **autotools** workflow (`./configure → make → make install`) with NGINX-specific flags for modules and paths.

**Step 1 — Install build dependencies:**

```bash
# Debian / Ubuntu
sudo apt update
sudo apt install -y build-essential libpcre2-dev zlib1g-dev libssl-dev libgd-dev

# RHEL / Fedora / Rocky / Alma
sudo dnf groupinstall -y "Development Tools"
sudo dnf install -y pcre2-devel zlib-devel openssl-devel gd-devel
```

| Library | Why NGINX needs it |
| ------- | ------------------ |
| `libpcre2` / `pcre2-devel` | Regular expressions in `location` blocks and `rewrite` rules |
| `zlib` / `zlib-devel` | `gzip` compression (`gzip on;`) |
| `libssl` / `openssl-devel` | TLS/HTTPS (`ssl_certificate`, `ssl_certificate_key`) |
| `libgd` / `gd-devel` | `ngx_http_image_filter_module` (optional) |

**Step 2 — Download and verify the source tarball:**

```bash
# Check the latest stable version at nginx.org/en/download.html
NGINX_VERSION=1.26.1

curl -O https://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz
curl -O https://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz.asc

# Verify the GPG signature (optional but recommended)
gpg --keyserver keyserver.ubuntu.com --recv-keys 520A9993A1C052F8
gpg --verify nginx-${NGINX_VERSION}.tar.gz.asc nginx-${NGINX_VERSION}.tar.gz

tar -xzvf nginx-${NGINX_VERSION}.tar.gz
cd nginx-${NGINX_VERSION}
```

**Step 3 — Configure with modules and paths:**

```bash
./configure \
  --prefix=/etc/nginx \
  --sbin-path=/usr/sbin/nginx \
  --modules-path=/usr/lib64/nginx/modules \
  --conf-path=/etc/nginx/nginx.conf \
  --error-log-path=/var/log/nginx/error.log \
  --http-log-path=/var/log/nginx/access.log \
  --pid-path=/var/run/nginx.pid \
  --lock-path=/var/run/nginx.lock \
  --with-http_ssl_module \
  --with-http_v2_module \
  --with-http_gzip_static_module \
  --with-http_stub_status_module \
  --with-stream \
  --with-stream_ssl_module \
  --with-pcre
```

**Key `./configure` flags:**

| Flag | What it enables |
| ---- | --------------- |
| `--with-http_ssl_module` | HTTPS support — requires `libssl` |
| `--with-http_v2_module` | HTTP/2 support |
| `--with-http_gzip_static_module` | Serve pre-compressed `.gz` files |
| `--with-http_stub_status_module` | `/nginx_status` endpoint for metrics |
| `--with-stream` | TCP/UDP proxying (Layer 4 load balancing) |
| `--with-stream_ssl_module` | TLS for stream proxy |
| `--with-pcre` | Link PCRE statically (needed for regex in `location`) |
| `--add-module=/path/to/module` | Compile a third-party module in statically |
| `--add-dynamic-module=/path/to/module` | Build a third-party module as a `.so` loaded at runtime |

See all available flags:

```bash
./configure --help | less
```

**Step 4 — Compile and install:**

```bash
make -j"$(nproc)"
sudo make install
```

Verify the binary is in place and check the compiled-in modules:

```bash
nginx -v                  # version only
nginx -V                  # version + full ./configure arguments used
```

**Step 5 — Create a systemd service unit:**

NGINX built from source does not ship a `.service` file. Create one manually:

```bash
sudo tee /etc/systemd/system/nginx.service > /dev/null <<'EOF'
[Unit]
Description=NGINX HTTP Server
After=network.target

[Service]
Type=forking
PIDFile=/var/run/nginx.pid
ExecStartPre=/usr/sbin/nginx -t
ExecStart=/usr/sbin/nginx
ExecReload=/bin/kill -s HUP $MAINPID
ExecStop=/bin/kill -s QUIT $MAINPID
PrivateTmp=true

[Install]
WantedBy=multi-user.target
EOF
```

Enable and start the service:

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now nginx
sudo systemctl status nginx
```

**Step 6 — Test and manage the running process:**

```bash
# Test the configuration before applying it
sudo nginx -t

# Reload config without dropping connections (graceful)
sudo systemctl reload nginx
# or directly:
sudo kill -HUP $(cat /var/run/nginx.pid)

# Graceful shutdown (waits for in-flight requests to finish)
sudo kill -QUIT $(cat /var/run/nginx.pid)

# Fast shutdown
sudo kill -TERM $(cat /var/run/nginx.pid)
```

**Upgrading NGINX in-place (zero downtime):**

When a new version is released, you can swap the binary without any downtime using NGINX's hot-upgrade mechanism:

```bash
# 1. Build and install the new binary (old master is still running)
make -j"$(nproc)" && sudo make install

# 2. Send USR2 to the old master — it forks a new master with the new binary
sudo kill -USR2 $(cat /var/run/nginx.pid)

# 3. Tell the old master to gracefully shut down its workers
sudo kill -WINCH $(cat /var/run/nginx.pid.oldbin)

# 4. If the new master looks healthy, quit the old master
sudo kill -QUIT $(cat /var/run/nginx.pid.oldbin)
```

**Notes:**

- **Never install into `/usr/`** — use `--sbin-path=/usr/sbin/nginx` for the binary but keep config, logs, and modules under `/etc/nginx/`, `/var/log/nginx/`, and `/usr/lib64/nginx/modules/`. This mirrors what distro packages do and avoids conflicts if you ever switch to a package-managed NGINX.
- **`nginx -V` is the source of truth** for what modules your binary has.  If a directive fails with "unknown directive", the required module was not compiled in — rebuild with the right `--with-*` flag.
- **Dynamic modules** (`--add-dynamic-module`) produce `.so` files loaded with `load_module /path/to/module.so;` in `nginx.conf`. They let you add features without a full recompile.
- **`ExecStartPre=/usr/sbin/nginx -t`** in the service unit makes systemd test the config before starting, so a bad config file never silently prevents NGINX from coming up after a reboot.

---

## Devices

Notes on Linux **devices** — how the kernel exposes hardware (disks, USB sticks, network cards, terminals, even pseudo-random bytes) as **files** under `/dev`. The Unix mantra "everything is a file" is most visible here: you read a webcam by `open()`-ing `/dev/video0`, zero out a disk by writing to `/dev/sdb`, and probe the kernel's view of devices through `/sys`. This section covers the directory layout, device types, naming rules, the **sysfs** kernel view, the **udev** rule engine that names devices on hotplug, and the bus-specific listing tools.

### One Shot Revision

| Command                                                   | Short Description                                                            |
| --------------------------------------------------------- | ---------------------------------------------------------------------------- |
| [/dev directory](#dev-directory)                          | Where device files live — block, character, pseudo, and virtual devices      |
| [Device Types](#device-types)                             | **Block** vs **character** devices, and how to tell them apart in `ls -l`    |
| [Device Names](#device-names)                             | Naming conventions — `sdX`, `nvmeXnY`, `ttyN`, `loopN`, and persistent IDs   |
| [sysfs](#sysfs)                                           | `/sys` — the kernel's structured view of every device, driver, and bus       |
| [udev](#udev)                                             | The hotplug daemon — names, permissions, and symlinks on device arrival      |
| [lsusb / lspci / lsscsi](#lsusb--lspci--lsscsi)           | List devices on the USB, PCI, and SCSI buses                                 |
| [dd](#dd)                                                 | The byte-level read/write tool — bootable USBs, disk imaging, careful wipes  |

### /dev directory

**Description:** **`/dev`** is the kernel's "device folder" — every piece of hardware (or virtual hardware) the kernel knows about appears here as a **special file**. Reading or writing one of these files turns into a syscall into the matching driver. On modern Linux the directory is **not on disk at all** — it's a `devtmpfs` filesystem populated by the kernel at boot and continuously updated by **[udev](#udev)** as devices come and go.

**What you find inside:**

| Path / pattern              | Kind                | What it is                                                             |
| --------------------------- | ------------------- | ---------------------------------------------------------------------- |
| `/dev/sda`, `/dev/sda1`     | Block (SCSI/SATA)   | First SCSI/SATA disk and its first partition                           |
| `/dev/nvme0n1`, `/dev/nvme0n1p1` | Block (NVMe)    | First NVMe device, namespace 1, partition 1                            |
| `/dev/mmcblk0`, `/dev/mmcblk0p1` | Block (eMMC/SD)| First MMC/SD card and its first partition                              |
| `/dev/loop0`–`loop7`        | Block (virtual)     | **Loopback** devices — mount a file as if it were a disk               |
| `/dev/dm-0`, `/dev/mapper/*`| Block (virtual)     | Device-mapper targets — LVM volumes, dm-crypt, multipath               |
| `/dev/tty`, `/dev/tty1`–`tty6` | Character (TTY)  | The current controlling terminal + virtual consoles                    |
| `/dev/pts/0`, `/dev/pts/1`  | Character (PTY)     | Pseudo-terminals (one per SSH session / terminal emulator / tmux pane) |
| `/dev/null`                 | Character (virtual) | The bit bucket — writes vanish, reads return EOF                       |
| `/dev/zero`                 | Character (virtual) | Infinite stream of `\0` bytes                                          |
| `/dev/random`, `/dev/urandom` | Character (virtual) | Kernel cryptographic RNG (`random` blocks if low entropy; use `urandom`) |
| `/dev/stdin`, `/dev/stdout`, `/dev/stderr` | Symlinks | Per-process FDs 0/1/2, served by `/proc/self/fd/{0,1,2}`         |
| `/dev/shm/`                 | Directory (tmpfs)   | POSIX shared memory — RAM-backed files                                 |
| `/dev/disk/by-id/`, `by-uuid/`, `by-label/`, `by-path/` | Symlinks | **Persistent device names** — survive hotplug reordering              |

**Examples:**

```bash
ls /dev | head -20
# autofs    block     bus       char      console   core      cpu      cpu_dma_latency
# disk      dri       fd        full      hugepages hwrng     ...

ls -l /dev/sda /dev/null /dev/tty
# brw-rw----  1 root disk  8,  0 ...  /dev/sda      ← b = block
# crw-rw-rw-  1 root root  1,  3 ...  /dev/null     ← c = character
# crw-rw-rw-  1 root tty   5,  0 ...  /dev/tty      ← c = character
# The two numbers in place of "size" are MAJOR, MINOR — see "Device Types".

# Persistent identifiers — survive across reboots and hotplug:
ls -l /dev/disk/by-id/
# ata-Samsung_SSD_870_EVO_500GB_S5RRNF0... -> ../../sda
# nvme-WD_BLACK_SN850X_1TB_...             -> ../../nvme0n1

# Some classic "device files that aren't really devices":
cat /dev/null    # returns immediately, nothing to read
echo "drop"  > /dev/null    # silently consumed
head -c 16 /dev/urandom | xxd    # 16 random bytes from the kernel RNG
```

**Notes:**

- `/dev` is **`devtmpfs`** — a RAM-backed pseudo-filesystem the kernel populates. **Files created there don't persist across reboots**; udev re-creates them every boot.
- The `crw-` / `brw-` first character of `ls -l` is the **easiest way to tell device class** at a glance (`c` = character, `b` = block). See [Device Types](#device-types).
- **`/dev/null` writes are free** — the syscall returns immediately. It's the canonical way to discard output (`cmd > /dev/null 2>&1`).
- **Prefer `/dev/urandom` over `/dev/random`** for everything except very early-boot key generation. Modern kernels treat the two identically once initialized; `/dev/random` only blocks on a cold boot before the entropy pool is seeded.
- **Use `/dev/disk/by-id/` or `by-uuid/` in `/etc/fstab` and scripts**, never `/dev/sdX`. The `sdX` letters can shift if you add a disk, plug in a USB, or change the boot order; the `by-id/` symlinks are stable.

### Device Types

**Description:** Every device file is either a **block** device or a **character** device — that's the kernel's most fundamental classification. **Block devices** are addressed in fixed-size chunks (sectors / 512 B blocks) and the kernel caches their I/O — disks, SSDs, CD-ROMs, USB sticks, loopback mounts. **Character devices** are streams of bytes with no random access and no caching — terminals, serial ports, keyboards, mice, audio cards, `/dev/null`. The kernel routes I/O to a driver using two integers stored in the device file itself: the **major** number picks the driver, the **minor** number picks the specific device that driver manages.

**Telling them apart in `ls -l`:**

```
brw-rw----  1 root disk    8,   0 Jun 12 09:14 /dev/sda
^                          ^    ^
│                          │    └── minor number  (which sda* — 0=whole disk, 1=sda1, ...)
│                          └─────── major number  (8 = SCSI/SATA disk driver)
└──────────────────────── 'b' = block device

crw-rw-rw-  1 root root    1,   3 Jun 12 09:14 /dev/null
^                          ^    ^
│                          │    └── minor (3 = null)
│                          └─────── major (1 = mem driver: null, zero, random, ...)
└──────────────────────── 'c' = character device
```

**The two families side by side:**

| Aspect             | Block device                                | Character device                                 |
| ------------------ | ------------------------------------------- | ------------------------------------------------ |
| Addressing         | Fixed-size **blocks** (512 B / 4 KB sectors)| **Byte stream**                                  |
| Random access      | **Yes** — seek anywhere by block number     | Usually **no** — read what arrives next          |
| Kernel page cache  | **Yes** — reads/writes go through it        | **No** — typically direct to driver              |
| Common users       | Filesystems mount on top                    | `read()` / `write()` / `ioctl()` directly        |
| Examples           | `sda`, `nvme0n1`, `loop0`, `dm-0`           | `tty`, `pts/0`, `null`, `zero`, `random`         |
| `mknod` flag       | `b`                                         | `c`                                              |

**A few common major numbers (Linux):**

| Major  | Driver / family                              |
| ------ | -------------------------------------------- |
| `1`    | `mem` — `/dev/null`, `/dev/zero`, `/dev/random`, `/dev/urandom`, `/dev/mem` |
| `4`    | TTY (`/dev/tty1`..`tty63`)                   |
| `5`    | TTY auxiliary (`/dev/tty`, `/dev/console`)   |
| `7`    | `loop` (loopback block devices)              |
| `8`    | `sd` — SCSI/SATA disks (`sda`..`sdh` etc.)   |
| `9`    | `md` — software RAID                         |
| `136+` | `pts` — pseudo-terminal slaves               |
| `259`  | NVMe block devices                           |
| `253`  | Device-mapper (LVM, dm-crypt — dynamic)      |

The authoritative list lives in **`/proc/devices`** (and `Documentation/admin-guide/devices.txt` in the kernel source).

**Examples:**

```bash
cat /proc/devices
# Character devices:
#   1 mem
#   4 /dev/vc/0
#   5 /dev/tty
# ...
# Block devices:
#   7 loop
#   8 sd
# 259 blkext

# Find every block device on the system:
find /dev -type b 2>/dev/null | head
# /dev/sda  /dev/sda1  /dev/loop0  /dev/nvme0n1  ...

# Find every character device:
find /dev -type c 2>/dev/null | head

# Create a device file by hand (rare — udev does this for you):
sudo mknod /dev/mynull c 1 3      # character device, major=1, minor=3 → same as /dev/null
ls -l /dev/mynull
# crw-r--r-- 1 root root 1, 3 ... /dev/mynull
sudo rm /dev/mynull
```

**Notes:**

- **`ls -l` reports major,minor in place of size** for device files — it's the easiest at-a-glance lookup. The same numbers appear under `Maj:Min` in `lsblk` and in `/sys/dev/block/<maj>:<min>/`.
- **Filesystems sit on block devices.** You can't `mount` a character device — `mount /dev/null /mnt` fails with `wrong fs type`. Block-vs-character is enforced at the syscall layer.
- **`mknod` is almost never needed by hand** — `udev` (via `devtmpfs`) creates device nodes automatically. The exception is **inside containers** that don't run udev, or when bootstrapping a minimal rootfs.
- **Pseudo / virtual devices count.** `/dev/null`, `/dev/zero`, `/dev/urandom` are character devices backed by kernel code, not hardware. `/dev/loop0` is a block device backed by a file on disk.
- The **major number is fixed per driver** by `Documentation/admin-guide/devices.txt`, but **modern allocations are dynamic** — device-mapper (253), NVMe (259), and most new subsystems request a major at module load time. Hardcoding major numbers in scripts is a bug.

### Device Names

**Description:** Linux uses a small set of **naming conventions** for device files — `sdX` for SCSI/SATA disks, `nvmeXnYpZ` for NVMe, `mmcblkX` for SD cards, `ttyN` for virtual consoles, `pts/N` for pseudo-terminals, `loopN` for loopback. These names are **not stable** across reboots once you add or remove hardware — a USB stick that was `sdb` today can become `sdc` after the next plug-in. For anything that needs to survive a reboot or a hotplug, use the **persistent symlinks** under `/dev/disk/`.

**The naming map:**

| Pattern               | What it names                                                            |
| --------------------- | ------------------------------------------------------------------------ |
| `sda`, `sdb`, `sdc`…  | SCSI / SATA / USB-attached disks, in **discovery order**                 |
| `sda1`, `sda2`, …     | Partitions on `sda`                                                      |
| `nvme0n1`             | NVMe controller 0, namespace 1                                           |
| `nvme0n1p1`           | First partition on that namespace (note the `p`)                         |
| `mmcblk0`, `mmcblk0p1`| SD / eMMC card 0 and its first partition                                 |
| `vda`, `vdb`…         | **Virtio** disks — typical inside KVM/QEMU guests                        |
| `xvda`, `xvdb`…       | **Xen** virtual block devices                                            |
| `dm-0`, `dm-1`…       | Device-mapper devices (LVM logical volumes, dm-crypt). Use `/dev/mapper/<name>` instead. |
| `md0`, `md1`…         | Software RAID arrays (`mdadm`)                                           |
| `loop0`–`loop7`       | Loopback devices (mount a file as if it were a disk)                     |
| `tty0`–`tty63`        | Virtual consoles (Ctrl+Alt+F1…F6)                                        |
| `pts/0`, `pts/1`, …   | Pseudo-terminals — one per SSH session / terminal emulator / tmux pane   |
| `ttyS0`, `ttyS1`      | Hardware serial ports                                                    |
| `ttyUSB0`, `ttyACM0`  | USB-to-serial adapters                                                   |
| `eth0`, `enp3s0`, `wlp2s0` | Network interfaces — see [systemd predictable names](https://systemd.io/PREDICTABLE_INTERFACE_NAMES/) |

**Persistent identifiers — what to use in `/etc/fstab` and scripts:**

| Directory                  | What its symlinks key on                                                |
| -------------------------- | ----------------------------------------------------------------------- |
| `/dev/disk/by-uuid/`       | Filesystem **UUID** (stable until you reformat). **Best default.**      |
| `/dev/disk/by-label/`      | Filesystem **label** — human-readable but only if you set one          |
| `/dev/disk/by-id/`         | Vendor + model + serial number — stable even across reformats           |
| `/dev/disk/by-path/`       | Physical port / bus path — stable if you don't move the cable           |
| `/dev/disk/by-partuuid/`   | GPT **partition** UUID — for partition-level pinning                    |

**Examples:**

```bash
# Map device → persistent ID (and vice versa):
lsblk -o NAME,SIZE,TYPE,FSTYPE,LABEL,UUID,MOUNTPOINT
# NAME    SIZE TYPE FSTYPE LABEL  UUID                                  MOUNTPOINT
# sda     500G disk
# ├─sda1    1G part vfat   EFI    A1B2-C3D4                             /boot/efi
# └─sda2  499G part ext4   root   1234abcd-...-ef56                     /

# Find every persistent symlink to a device:
ls -l /dev/disk/by-*/ | grep -E 'sda1\b|sda2\b'
# by-uuid/A1B2-C3D4                -> ../../sda1
# by-uuid/1234abcd-...-ef56        -> ../../sda2
# by-id/ata-Samsung_SSD_870_EVO_..-part2 -> ../../sda2
# by-label/EFI                     -> ../../sda1

# Get just the UUID of a device:
blkid /dev/sda2
# /dev/sda2: LABEL="root" UUID="1234abcd-...-ef56" TYPE="ext4"

# Resolve the other direction:
findfs UUID=1234abcd-...-ef56
# /dev/sda2

# Why an NVMe layout looks weird:
ls /dev/nvme0n1*
# /dev/nvme0n1   /dev/nvme0n1p1   /dev/nvme0n1p2
# - nvme0    = controller 0
# - n1       = namespace 1 (most consumer SSDs have just one)
# - p1, p2   = partitions (note the `p` — sd disks just use sda1, no `p`)
```

**Notes:**

- **`sdX` letters are not persistent.** Linux assigns them in the order disks are detected at boot. Add or remove a drive (or boot with a USB stick plugged in) and the letter assignments can shift. **Always use UUID or by-id in `/etc/fstab`.**
- **NVMe drives use `p` between namespace and partition** (`nvme0n1p1`), but SATA drives don't (`sda1`, not `sdap1`). Loopback and mmcblk match NVMe (`loop0p1`, `mmcblk0p1`).
- **`/dev/disk/by-*/` symlinks are managed by udev** — they reappear automatically after a reboot or hotplug.
- **Network interface naming is its own game.** `eth0`/`wlan0` was the old scheme; modern systemd uses **predictable names** like `enp3s0` (PCI slot 3, port 0) or `wlp2s0` (wireless, PCI slot 2). They survive hotplug; `eth0` did not.
- **LVM and crypto layers expose friendly names.** `/dev/mapper/vg_root-lv_home` is the symlink you should use, not the underlying `/dev/dm-2`.

### sysfs

**Description:** **`/sys`** is the kernel's **structured, hierarchical view of every device, driver, and bus** on the system. Where `/proc` is the old junk-drawer of "everything running," `/sys` is the modern, tidy answer to "what hardware exists and how is it wired together." It's a virtual filesystem (`sysfs`) — directories are kernel objects, files are their attributes. Most attribute files are tiny (a single line) and writing to them tunes runtime hardware behavior — LED brightness, fan PWM, CPU governor, USB power management.

**The top-level layout:**

| Path                      | Contains                                                                   |
| ------------------------- | -------------------------------------------------------------------------- |
| `/sys/devices/`           | **The canonical tree** — every device, organized by physical topology      |
| `/sys/bus/`               | One subdir per bus (`pci/`, `usb/`, `scsi/`, `i2c/`) — symlinks to devices |
| `/sys/class/`             | One subdir per **device class** (`block/`, `net/`, `tty/`, `power_supply/`) |
| `/sys/block/`             | One subdir per block device — `sda/`, `nvme0n1/`, `loop0/`                 |
| `/sys/module/`            | One subdir per loaded kernel module                                        |
| `/sys/firmware/`          | Firmware tables — ACPI, EFI, device tree                                   |
| `/sys/fs/`                | Per-filesystem-type knobs and counters                                     |
| `/sys/kernel/`            | Misc kernel-wide tunables (slab info, debugfs mount, kobjects)             |
| `/sys/power/`             | Suspend / hibernate controls                                               |

**Examples:**

```bash
# Size of every block device, in 512 B sectors:
cat /sys/block/sda/size
# 976773168                    — × 512 = ~500 GB

# Rotational? (1 = spinning HDD, 0 = SSD)
cat /sys/block/sda/queue/rotational

# What scheduler is sda using right now?
cat /sys/block/sda/queue/scheduler
# [none] mq-deadline bfq kyber           ← brackets = active

# Switch to a different scheduler (live, no reboot):
echo bfq | sudo tee /sys/block/sda/queue/scheduler

# CPU temperature (one of the most-asked sysfs queries):
cat /sys/class/thermal/thermal_zone0/temp
# 47000                        — millidegrees Celsius → 47 °C

# Current CPU frequency governor on every core:
for f in /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor; do
  echo "$f: $(cat "$f")"
done

# Battery state on a laptop:
cat /sys/class/power_supply/BAT0/{status,capacity,energy_now,energy_full}
# Discharging
# 74
# 35720000
# 48190000

# Find every network interface and its MAC:
for i in /sys/class/net/*; do
  echo "$(basename "$i"): $(cat "$i/address")"
done

# Walk back from a device to its driver:
ls -l /sys/class/net/eth0
# -> ../../devices/pci0000:00/0000:00:1f.6/net/eth0
ls -l /sys/class/net/eth0/device/driver
# -> ../../../../bus/pci/drivers/e1000e

# Unbind a device from its driver (advanced):
echo 0000:03:00.0 | sudo tee /sys/bus/pci/drivers/e1000e/unbind
```

**Notes:**

- **`/sys/devices/` is the source of truth** — every other path under `/sys` is either a symlink into it (`/sys/class/`, `/sys/block/`, `/sys/bus/*/devices/`) or a different way of grouping the same kobjects.
- **Read-only attributes are reads; writable ones tune the kernel.** A file with `0644` and contents `1` is a runtime toggle — `echo 0 | sudo tee <file>` flips it. Changes are usually **not persistent across reboots** — use `udev` rules or `tuned`/`tlp` to make them stick.
- **Don't `cat` everything.** Some files are debug interfaces (`/sys/kernel/debug/...`) and reading them can be slow or have side effects. Stick to documented attributes.
- **Hotplug events come from sysfs.** When the kernel creates a kobject under `/sys`, it sends a `uevent` netlink message that **[udev](#udev)** consumes — that's how `/dev` nodes appear in real time.
- **`/proc/sys/` is different from `/sys/`.** `/proc/sys/` is `sysctl` (kernel tunables); `/sys/` is the device model. Easy to confuse — the names rhyme but the contents don't overlap.

### udev

**Description:** **`udev`** is the **device manager** — the userspace daemon (`systemd-udevd` on modern systems) that listens for kernel **uevents** and, for every device that appears or disappears, creates / removes the matching `/dev` node, sets its ownership and permissions, runs match-and-act **rules**, and creates the persistent symlinks under `/dev/disk/`, `/dev/serial/by-id/`, etc. It's the reason plugging in a USB stick "just works" — the kernel emits the event, udev names the device, creates `/dev/sdb`, and (on a desktop) the file manager auto-mounts it.

**Where the rules live:**

| Path                                  | Purpose                                                              |
| ------------------------------------- | -------------------------------------------------------------------- |
| `/lib/udev/rules.d/`                  | Distribution / package-shipped rules — don't edit                    |
| `/run/udev/rules.d/`                  | Runtime rules (lost at reboot)                                       |
| `/etc/udev/rules.d/`                  | **Your custom rules** — override the distro ones                     |

Rules are loaded in **lexical order** across all three directories. A file in `/etc/udev/rules.d/` with the same name as one in `/lib/udev/rules.d/` **replaces** it; that's the standard override pattern.

**Anatomy of a rule:**

```
SUBSYSTEM=="usb", ATTRS{idVendor}=="2341", ATTRS{idProduct}=="0043", \
    SYMLINK+="arduino", MODE="0660", GROUP="dialout"
└──────────────── match keys ───────────────┘   └──────── actions ─────────┘
```

| Operator | Meaning                                                             |
| -------- | ------------------------------------------------------------------- |
| `==`     | **Match** — rule applies only if the value matches                  |
| `!=`     | Negated match                                                       |
| `=`      | **Assign** — set the value                                          |
| `+=`     | Append to a list (e.g. `SYMLINK+=`)                                 |
| `:=`     | Assign and **forbid further changes** to this key                   |

Common match / action keys: `KERNEL`, `SUBSYSTEM`, `DRIVER`, `ATTR{...}`, `ATTRS{...}` (walks up the parent chain), `ENV{...}`, `ACTION` (`add`, `remove`, `change`); on the action side: `NAME`, `SYMLINK+=`, `MODE`, `OWNER`, `GROUP`, `RUN+=`, `TAG+=`, `ENV{...}`.

**Examples:**

```bash
# Watch udev events live (plug a USB stick in another terminal):
sudo udevadm monitor --udev --property
# UDEV  [12345.678] add /devices/.../block/sdb (block)
#   ACTION=add
#   DEVNAME=/dev/sdb
#   ...

# Dump every attribute udev sees for a given device — your reference for writing rules:
udevadm info -a -n /dev/sdb
# looking at device '/devices/.../block/sdb':
#     KERNEL=="sdb"
#     SUBSYSTEM=="block"
#     ATTR{size}=="61057024"
#     ATTR{removable}=="1"
#     ...

# Verify what udev thinks about a device right now:
udevadm info -q all -n /dev/sda
# Shows every property: DEVPATH, DEVNAME, ID_FS_UUID, ID_SERIAL, SYMLINKs, ...

# Reload rules and re-trigger events without rebooting:
sudo udevadm control --reload
sudo udevadm trigger --action=change /dev/sdb

# Test what a rule *would* do without committing:
sudo udevadm test /sys/class/block/sdb 2>&1 | head -40
```

**A real custom rule — `/etc/udev/rules.d/99-arduino.rules`:**

```
# Give every member of the `dialout` group rw access to the Arduino,
# and create a stable /dev/arduino symlink so scripts don't chase ttyUSBN reordering.
SUBSYSTEM=="tty", ATTRS{idVendor}=="2341", ATTRS{idProduct}=="0043", \
    SYMLINK+="arduino", MODE="0660", GROUP="dialout"
```

After saving:

```bash
sudo udevadm control --reload
sudo udevadm trigger
# Unplug + replug the Arduino — /dev/arduino appears.
```

**Notes:**

- **Custom rules go in `/etc/udev/rules.d/`** with a numeric prefix (`70-`, `99-`) that controls load order. Lower numbers run first; the `99-` prefix is the convention for "last-word" user rules.
- **One file = one logical purpose.** Don't dump everything into one rule file — the lexical-order override behavior gets confusing.
- **Predictable network interface names** (`enp3s0`, `wlp2s0`) are produced by `/lib/udev/rules.d/80-net-setup-link.rules` + systemd. If you want to force a name, drop a `.link` file into `/etc/systemd/network/` (the modern way) rather than fighting the udev rule.
- **`udevadm info -a`** is the workflow when writing a rule — find the unique attribute set for your device first, *then* write the matcher.
- **Rules are not for one-shot side effects.** Don't `RUN+=` long-running scripts — udev waits on them and can hang the whole device-arrival path. Use a `systemd` unit (`SYSTEMD_WANTS=`) instead.
- **`udevadm trigger`** replays "add" events for already-present devices — handy after rule changes so you don't have to physically unplug.

### lsusb / lspci / lsscsi

**Description:** Three sibling tools that **enumerate devices on a specific bus** and print a human-readable summary. `lspci` lists everything on the **PCI / PCIe** bus (graphics card, NVMe, NIC, audio, USB host controllers); `lsusb` lists **USB** devices (keyboards, mice, webcams, thumb drives); `lsscsi` lists **SCSI** devices, which on Linux includes SATA and USB-mass-storage too. They all read from `/sys` underneath — they're just nicely formatted views.

**`lspci` — PCI / PCIe:**

| Flag       | What it does                                                          |
| ---------- | --------------------------------------------------------------------- |
| (no flags) | One device per line — slot, class, vendor:device, friendly name       |
| `-v`       | **Verbose** — IRQ, memory regions, kernel driver in use               |
| `-vv`      | More verbose still — capabilities, link speed                         |
| `-vvv`     | Maximum verbosity — register dumps                                    |
| `-k`       | Show the **kernel driver** and modules for each device                |
| `-nn`      | Numeric **and** name — both `8086:1234` and "Intel ..." together      |
| `-tv`      | **Tree** view — show the PCI bus topology                             |

**`lsusb` — USB:**

| Flag      | What it does                                                           |
| --------- | ---------------------------------------------------------------------- |
| (no flags)| One device per line — bus, device, vendor:product, name                |
| `-v`      | **Verbose** — descriptors, endpoints, max packet size                  |
| `-t`      | **Tree** view — physical port topology, USB speeds per link            |
| `-s BUS:DEV` | Show only that bus / device                                         |
| `-d VID:PID` | Show only devices matching that vendor / product ID                 |

**`lsscsi` — SCSI / SATA / USB-mass-storage:**

| Flag      | What it does                                                           |
| --------- | ---------------------------------------------------------------------- |
| (no flags)| One device per line — host:channel:id:lun, type, vendor, model         |
| `-s`      | Include **size**                                                       |
| `-l`      | Long format — include `/sys` path and transport info                   |
| `-d`      | Include the major,minor of the resulting block device                  |
| `-H`      | Just list SCSI **hosts** (adapters)                                    |

**Examples:**

```bash
lspci -nnk | head
# 00:00.0 Host bridge [0600]: Intel ... [8086:9b53]
#         Subsystem: ... [1043:8694]
#         Kernel driver in use: skl_uncore
# 00:02.0 VGA compatible controller [0300]: Intel ... [8086:9bca]
#         Kernel driver in use: i915
#         Kernel modules: i915

lspci -tv | head
# -[0000:00]-+-00.0  Intel ... Host bridge
#            +-02.0  Intel ... VGA controller
#            +-04.0  Intel ... Power management

lsusb
# Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
# Bus 001 Device 005: ID 046d:c52b Logitech, Inc. Unifying Receiver
# Bus 001 Device 003: ID 0bda:0129 Realtek Card Reader

lsusb -t
# /:  Bus 02.Port 1: Dev 1, Class=root_hub, Driver=xhci_hcd/4p, 5000M
#     |__ Port 1: Dev 2, ... 5000M
# /:  Bus 01.Port 1: Dev 1, Class=root_hub, Driver=xhci_hcd/12p, 480M

lsscsi -s
# [0:0:0:0]  disk  ATA    Samsung SSD 870  1B6Q  /dev/sda   500GB
# [1:0:0:0]  cd/dvd HL-DT-ST DVDRAM GH24NSC0      /dev/sr0
# [6:0:0:0]  disk  Generic Mass-Storage 1.00     /dev/sdb   16.0GB

# Find which driver is bound to a specific PCI device:
lspci -k -s 00:1f.6
# 00:1f.6 Ethernet controller: Intel Corporation Ethernet Connection (12) I219-V
#         Kernel driver in use: e1000e
#         Kernel modules: e1000e
```

**Notes:**

- **`lspci`'s vendor/device IDs come from `/usr/share/hwdata/pci.ids`** (and `usb.ids` for `lsusb`). If a brand-new device shows up as "Unknown vendor", update `pci.ids` (Debian: `update-pciids`, RHEL: `update-pciids` from `pciutils`).
- **`-nnk`** is the cheat-code combo for `lspci` — it gives you numeric IDs (great for matching kernel modules by `modinfo`) **and** the kernel driver currently bound, all in one shot.
- **`lsusb -t` shows speeds per port** (`480M` = USB 2.0, `5000M` = USB 3.0, `10000M` = USB 3.1 Gen 2). Useful for diagnosing "my USB 3 device is plugged into a USB 2 port."
- **`lsscsi` reports SATA disks too.** Linux treats SATA as SCSI under the hood — the SATA driver speaks to the SCSI mid-layer, which is why your `sda` is "SCSI device 0:0:0:0."
- **`lshw -short`** is a higher-level alternative that walks PCI, USB, IDE, SCSI, and DMI into one tree — install separately on most distros.
- All three tools just **format `/sys` data nicely.** When a tool isn't installed (minimal container, embedded box), the same info is in `/sys/bus/pci/devices/`, `/sys/bus/usb/devices/`, `/sys/class/scsi_device/`.

### dd

**Description:** **`dd`** ("data duplicator", though the name predates the acronym) is the **byte-level read/write tool** — it reads from one file and writes to another, in fixed-size blocks, with no understanding of filesystems. That makes it the canonical tool for **writing an ISO to a USB stick**, **imaging or wiping a disk**, **creating sparse / zero files**, and **benchmarking raw I/O**. It also makes it **extremely dangerous**: a single typo in the `of=` target (`/dev/sda` instead of `/dev/sdb`) wipes the wrong disk. Doubly check the device name, every time.

**Syntax:**

```bash
dd if=<input> of=<output> [bs=N] [count=N] [skip=N] [seek=N] [status=progress] [conv=...]
```

**Common options:**

| Option            | What it does                                                            |
| ----------------- | ----------------------------------------------------------------------- |
| `if=FILE`         | **In**put file (default: stdin)                                         |
| `of=FILE`         | **Out**put file (default: stdout)                                       |
| `bs=N`            | **Block size** — read AND write in N-byte chunks (default 512 B)        |
| `ibs=N` / `obs=N` | Separate input / output block sizes                                     |
| `count=N`         | Stop after N input blocks                                               |
| `skip=N`          | Skip N **input** blocks before reading                                  |
| `seek=N`          | Skip N **output** blocks before writing (preserves existing data ahead) |
| `status=progress` | Show throughput and bytes copied while running (modern GNU coreutils)   |
| `conv=fsync`      | `fsync()` the output **once** at the end — guarantees data hit the disk |
| `conv=sync`       | **Pad** the last block with zeros if it's short                         |
| `conv=notrunc`    | Don't truncate the output file (important when seeking into a file)     |
| `conv=noerror`    | Continue past read errors (used in recovery — but prefer `ddrescue`)    |
| `oflag=direct`    | Bypass the kernel page cache (raw, unbuffered I/O)                      |

**Examples:**

```bash
# Write a Linux ISO to a USB stick (THE textbook dd use case):
sudo dd if=ubuntu-24.04.iso of=/dev/sdb bs=4M status=progress conv=fsync
# ⚠️  CONFIRM /dev/sdb is the USB and NOT your root disk:
lsblk
sudo umount /dev/sdb*                # unmount any auto-mounted partitions first

# Make a 1 GB file of zeros:
dd if=/dev/zero of=zerofile bs=1M count=1024 status=progress

# Make a 1 GB SPARSE file (instant — no actual data written):
dd if=/dev/zero of=sparsefile bs=1 count=0 seek=1G
ls -lh sparsefile        # logical size: 1.0G
du -h sparsefile         # disk usage:  0

# Clone a whole disk to another disk (same-size or larger target):
sudo dd if=/dev/sda of=/dev/sdb bs=4M status=progress conv=fsync

# Dump the first 512 bytes of a disk (MBR + partition table):
sudo dd if=/dev/sda of=mbr.bin bs=512 count=1
# Inspect:
hexdump -C mbr.bin | tail -10        # signature 55 AA at offset 0x1FE

# Wipe a disk's first MB (kill MBR/GPT headers — disk looks empty to OS):
sudo dd if=/dev/zero of=/dev/sdb bs=1M count=1

# Benchmark raw sequential read speed:
dd if=/dev/sda of=/dev/null bs=1M count=1024 status=progress iflag=direct
# 1073741824 bytes (1.1 GB, 1.0 GiB) copied, 2.1 s, 511 MB/s

# Resume a partial image copy from offset 200 MB:
sudo dd if=disk.img of=/dev/sdb bs=1M skip=200 seek=200 status=progress conv=notrunc
```

**Speed tips:**

- **`bs=4M` is the sweet spot** for disk-to-disk copies on modern hardware. The default `bs=512` does one syscall per sector and is glacial — use it only when you actually need byte-level precision.
- **`status=progress`** prints throughput once a second. Without it, `dd` is silent. (You can also send `SIGUSR1` to a running `dd` to print its current progress — `kill -USR1 $(pgrep ^dd$)`.)
- **`conv=fsync`** at the end of an image-to-USB write is *the* difference between "ejected cleanly" and "image is half in the page cache" — always include it.

**Notes:**

- **`dd` is dangerously unforgiving.** Mistyping `of=/dev/sda` instead of `/dev/sdb` overwrites your system disk with no confirmation prompt. Always **run `lsblk` immediately before** to confirm the target, and ideally `unmount` the target's partitions first.
- **The output device must be unmounted** for a clean write — if any partition on `/dev/sdb` is mounted, the in-flight write races against the kernel and you get a corrupt image. `sudo umount /dev/sdb*` first.
- **For damaged disks, use `ddrescue` instead of `dd conv=noerror`.** `ddrescue` (GNU) tracks bad sectors, retries them in a smart order, and produces a map file you can resume from — `dd` just blindly skips and tells you nothing.
- **Counting in MB/GB vs MiB/GiB.** `bs=1M` in GNU `dd` is `1,048,576` bytes (MiB); `bs=1MB` is `1,000,000` (MB). The lowercase suffix is the binary one.
- **Modern alternatives are often nicer.** Use `cp --sparse=always` for sparse copies, `fallocate -l 1G file` to allocate without writing, and `pv` to copy with a real progress bar (`pv input.iso > /dev/sdb`).
- **`dd` does not validate.** After writing an ISO, verify the SHA-256 of the source against `dd if=/dev/sdb bs=4M count=<iso_size_in_blocks>` — or just check the ISO's own embedded checksum.

---

## The Filesystem

Notes on **the filesystem** — how Linux turns a raw block device into a tree of files. Three layers stack on top of each other: the **disk** is split into **partitions**, each partition gets formatted with a **filesystem type** (ext4, xfs, btrfs, …), and the resulting trees are mounted into a single **unified hierarchy** rooted at `/`. This section covers all three layers, plus the standard directory layout (FHS) that makes a Linux box look the same no matter the distro.

### One Shot Revision

| Command                                             | Short Description                                                            |
| --------------------------------------------------- | ---------------------------------------------------------------------------- |
| [Filesystem Hierarchy](#filesystem-hierarchy)       | The **FHS** — what `/etc`, `/var`, `/usr`, `/home`, `/tmp` are each for      |
| [Filesystem Types](#filesystem-types)               | **ext4**, **xfs**, **btrfs**, **zfs**, **tmpfs**, **vfat**, **ntfs** — pick one |
| [Anatomy of a Disk](#anatomy-of-a-disk)             | Sectors, blocks, MBR vs GPT, superblock, inodes, journal                     |
| [Disk Partitioning](#disk-partitioning)             | `fdisk`, `parted`, `gdisk`, `mkfs`, `mount`, `/etc/fstab`                    |
| [Creating Filesystems](#creating-filesystems)       | `mkfs.<type>`, labels, UUIDs, tuning options                                 |
| [mount and umount](#mount-and-umount)               | Attach / detach filesystems, bind mounts, lazy unmount, mount options        |
| [/etc/fstab](#etcfstab)                             | The boot-time mount table — fields, options, `nofail`, `noauto`              |
| [swap](#swap)                                       | Swap partitions vs swap files, `mkswap`, `swapon`, `swappiness`              |
| [Disk Usage](#disk-usage)                           | `df`, `du`, `ncdu` — where the space went                                    |
| [Filesystem Repair](#filesystem-repair)             | `fsck`, `e2fsck`, `xfs_repair` — recovering after a crash                    |
| [Inodes](#inodes)                                   | The on-disk metadata record — `stat`, `ls -i`, running out of inodes         |
| [symlinks](#symlinks)                               | `ln -s` — soft links vs hard links, dangling links                           |

### Filesystem Hierarchy

**Description:** Linux organizes every file into **one tree rooted at `/`** — no drive letters, no per-disk namespaces. The layout follows the **Filesystem Hierarchy Standard (FHS)**, which says what each top-level directory is for so a box you've never logged into still looks familiar. Different physical disks, partitions, or even network shares can be **mounted** anywhere in the tree (`/home` on one disk, `/var` on another, `/mnt/backup` on NFS), but from a user's point of view it's all one hierarchy.

**The top-level map:**

| Path        | What lives here                                                                |
| ----------- | ------------------------------------------------------------------------------ |
| `/`         | The **root** of the tree — every other path branches from here                 |
| `/bin`      | Essential user binaries (`ls`, `cp`, `cat`) — on modern distros, a symlink to `/usr/bin` |
| `/sbin`     | Essential **system** binaries (`mount`, `fsck`, `ifconfig`) — symlink to `/usr/sbin` |
| `/lib`, `/lib64` | Essential shared libraries — symlinks to `/usr/lib`, `/usr/lib64` on modern distros |
| `/usr`      | **User**-land programs and data — `/usr/bin`, `/usr/lib`, `/usr/share`, `/usr/local` |
| `/usr/local`| Software installed **outside** the package manager — your `make install` lands here |
| `/etc`      | **System-wide configuration** — text files only, no binaries                   |
| `/var`      | **Variable** data — logs (`/var/log`), spools, package state, caches (`/var/cache`) |
| `/home`     | User home directories (`/home/tarek`, `/home/alice`)                           |
| `/root`     | The **root user's** home directory (not `/home/root`!)                         |
| `/tmp`      | World-writable temporary files — cleared on reboot on most distros             |
| `/opt`      | Self-contained third-party software (`/opt/google/chrome`, `/opt/foo/`)        |
| `/boot`     | Bootloader and **kernel images** (`vmlinuz`, `initramfs`)                      |
| `/dev`      | **Device files** — see [/dev directory](#dev-directory)                        |
| `/proc`     | Live kernel + process state — see [/proc Filesystem](#proc-filesystem)         |
| `/sys`      | Kernel device model — see [sysfs](#sysfs)                                      |
| `/run`      | Runtime data (PIDs, sockets) created at boot — tmpfs, cleared on reboot        |
| `/mnt`      | Mount point for **temporarily** mounted filesystems                            |
| `/media`    | Mount point for **removable** media — USB sticks, CDs (auto-mounted here)      |
| `/srv`      | Data served by the system — `srv/www`, `srv/ftp` (convention; not always used) |

**The `/usr` merge (modern distros):**

Since around 2012, most distros have done the **`/usr` merge** — `/bin`, `/sbin`, `/lib`, `/lib64` are now symlinks into `/usr/bin`, `/usr/sbin`, `/usr/lib`, `/usr/lib64`. There's only one place where binaries live; the old split (essential-for-recovery vs everything else) made sense when `/usr` was on a separate disk that might fail to mount, but no longer.

**Examples:**

```bash
ls -l /                          # see the layout on your own box
# bin -> usr/bin
# boot/
# dev/
# etc/
# home/
# lib -> usr/lib
# ...

# Where does a specific binary live?
which ls
# /usr/bin/ls
type ls
# ls is /usr/bin/ls          # `which` is older; `type` is built into bash

# Which package owns this path? (back-references — see Packages section)
dpkg -S /etc/ssh/sshd_config       # Debian
rpm -qf /etc/ssh/sshd_config       # RHEL

# Quick FHS sanity check — every "should be a directory" path:
for p in /etc /var /usr /home /opt /tmp /proc /sys /dev; do
  printf "%-7s %s\n" "$p" "$(test -d "$p" && echo OK || echo MISSING)"
done
```

**Notes:**

- **`/etc` is text-only on principle.** If a tool stores binary state under `/etc/`, it's a bug or a misuse — runtime state belongs in `/var/lib/<pkg>/`, not `/etc/`.
- **`/var/log` is where you go first when something breaks.** `journalctl` reads systemd's binary journal under `/var/log/journal/`; traditional syslogs live as plain text under `/var/log/syslog`, `/var/log/messages`, `/var/log/auth.log`, `/var/log/secure`.
- **`/tmp` is usually `tmpfs`** (RAM-backed) on modern systemd distros — fast but limited. Big temp data belongs in `/var/tmp`, which is on-disk and survives reboots.
- **`/opt` vs `/usr/local`**: both are for non-distro software. `/opt/<vendor>/` is for self-contained vendored drops (think Slack, Chrome). `/usr/local/` follows the FHS layout (`bin/`, `lib/`, `share/`) and is what `./configure --prefix=/usr/local` lands in.
- **Never put data on `/`** that you can't afford to be on a small partition. Many setups give `/` only 20–40 GB; user data goes on `/home`, application data on `/var/lib/<app>`, build artifacts under `/opt` or `/srv`.
- The FHS is **specified by the Linux Foundation** — see [refspecs.linuxfoundation.org/fhs.shtml](https://refspecs.linuxfoundation.org/fhs.shtml) for the full document.

### Filesystem Types

**Description:** A **filesystem** is the on-disk format that turns a raw block device into a tree of files — how blocks are allocated, how metadata is stored, how crashes are recovered. Linux can mount dozens of formats; the question is which one to **format with** when you create a new partition. The right answer is "ext4 unless you have a reason otherwise" — but xfs, btrfs, zfs, tmpfs, and vfat all earn their keep in specific situations.

**The everyday options:**

| Filesystem | Best for                                                  | Key features / trade-offs                                                  |
| ---------- | --------------------------------------------------------- | -------------------------------------------------------------------------- |
| **ext4**   | General purpose — root filesystem on most distros         | Journaled, mature, fast small-file I/O, in-place upgrades from ext2/ext3   |
| **xfs**    | Large filesystems, big files, high-throughput workloads   | Journaled, scales to exabytes, **no shrink**, fast parallel I/O. RHEL's default. |
| **btrfs**  | Snapshots, subvolumes, RAID, send/receive replication     | CoW, built-in snapshots and RAID0/1/10, transparent compression. RAID5/6 still flaky. Used by openSUSE / Fedora root by default. |
| **zfs**    | Storage servers — checksums, snapshots, native RAID-Z     | Best-in-class data integrity, but not in the upstream kernel (license) — needs `zfs-dkms` or out-of-tree. |
| **tmpfs**  | RAM-backed scratch space (`/tmp`, `/run`, `/dev/shm`)     | Lives in memory; cleared on reboot; size is dynamic up to a limit          |
| **vfat / exFAT** | USB sticks, SD cards, cross-OS sharing               | No permissions, no symlinks, but **Windows / macOS read it natively**      |
| **ntfs**   | Reading / writing Windows partitions                      | In-kernel `ntfs3` driver (5.15+) — full read/write; older systems used FUSE `ntfs-3g` |
| **iso9660 / udf** | CDs, DVDs, ISO images                              | Read-only; what you see when you mount a `.iso`                            |
| **squashfs** | Read-only compressed images (live CDs, Snap, AppImage)  | Single compressed read-only image — fast to mount, can't be modified       |
| **nfs / cifs** | Network mounts                                        | Filesystem semantics over the network; not a disk format                   |
| **overlay**  | Containers, live CDs, Docker layers                     | Stacks a read-write layer on top of a read-only one                        |

**Examples:**

```bash
# What filesystem is each mount running?
df -hT
# Filesystem     Type      Size  Used Avail Use% Mounted on
# /dev/sda2      ext4      450G  120G  310G  28% /
# /dev/sda1      vfat      512M  6.0M  506M   2% /boot/efi
# tmpfs          tmpfs     7.7G  120K  7.7G   1% /tmp
# /dev/nvme0n1p1 xfs       1.8T  300G  1.5T  17% /data

# A more compact view:
lsblk -f
# NAME    FSTYPE FSVER LABEL UUID                                 MOUNTPOINTS
# sda
# ├─sda1  vfat   FAT32 EFI   A1B2-C3D4                            /boot/efi
# └─sda2  ext4   1.0   root  1234abcd-...                         /

# Identify the filesystem of an unmounted partition:
sudo blkid /dev/sdb1
# /dev/sdb1: UUID="..." TYPE="xfs" PARTUUID="..."

# Format with each type:
sudo mkfs.ext4   -L data    /dev/sdb1
sudo mkfs.xfs    -L data    /dev/sdb1
sudo mkfs.btrfs  -L data    /dev/sdb1
sudo mkfs.vfat   -F 32 -n   data    /dev/sdb1
# -L / -n sets the filesystem label (later visible in /dev/disk/by-label/)

# Mount tmpfs explicitly with a size cap:
sudo mount -t tmpfs -o size=2G tmpfs /mnt/scratch

# Check or repair a filesystem (only on UNMOUNTED targets!):
sudo fsck.ext4  -f /dev/sdb1
sudo xfs_repair    /dev/sdb1
sudo btrfs check   /dev/sdb1
```

**Which to pick?**

- **Root filesystem, general server:** **ext4**. Boring, fast, and never surprises you.
- **Big data partition (≥ 2 TB), DB or log volume:** **xfs**. Better at parallel I/O and huge files.
- **You want snapshots and rollback:** **btrfs** (already in-tree) or **zfs** (better integrity, license-encumbered).
- **External drive shared with Windows / macOS:** **exFAT** for ≥ 32 GB, **vfat** for tiny drives.
- **Live filesystem for `/tmp`, `/run`, `/dev/shm`:** **tmpfs** — that's already what your distro does.

**Notes:**

- **You can't shrink an `xfs` filesystem.** Grow with `xfs_growfs`, but to make one smaller you must back up, recreate, and restore. Plan partition sizes accordingly.
- **`btrfs` and `zfs` are CoW** — overwriting a file is actually "write a new block, repoint metadata." That gives free snapshots but also means **`df` and `du` can disagree** with each other and with `btrfs filesystem df`.
- **`vfat` / `exFAT` have no Unix permissions.** Every file appears as 0777 owned by the mount-time user. They're fine for sneakernet, terrible for a Linux root.
- **`fsck` an unmounted filesystem only.** Running `fsck` on a mounted, in-use partition will corrupt it. The boot-time `fsck` works because it runs before `/` is remounted read-write.
- **Journaling does not equal "can't lose data."** It guarantees the **filesystem metadata** stays consistent across a crash — your *file contents* can still be lost if they weren't `fsync`-ed.
- The **canonical authority for "what filesystems can I mount?"** is `/proc/filesystems`. Anything listed there (or any module the kernel can load on demand) is fair game.

### Anatomy of a Disk

**Description:** Underneath every filesystem is a **block device** divided into fixed-size **sectors** (historically 512 B, now usually 4 KiB on modern drives — "Advanced Format"). The very first sectors hold the **partition table** (MBR or GPT) that says where each partition starts and how long it is. Inside each partition, the filesystem lays down its own structures — a **superblock** describing the layout, **inodes** holding per-file metadata, **data blocks** holding the actual bytes, and (on journaled filesystems) a **journal** that lets it recover from a crash.

**The layers, from physical to logical:**

```
┌─────────────────────────────────────────────────────────────┐
│  /home/tarek/file.txt   ← path you see in the shell          │
├─────────────────────────────────────────────────────────────┤
│  inode #12345 + data blocks   ← filesystem (ext4 / xfs / ...) │
├─────────────────────────────────────────────────────────────┤
│  partition 2 (sda2: starts at sector 1050624, length …)      │
├─────────────────────────────────────────────────────────────┤
│  MBR / GPT partition table (first sectors of the disk)        │
├─────────────────────────────────────────────────────────────┤
│  sectors (512 B / 4 KiB each)                                  │
├─────────────────────────────────────────────────────────────┤
│  physical platters / NAND cells                                │
└─────────────────────────────────────────────────────────────┘
```

**Partition tables — MBR vs GPT:**

| Aspect           | **MBR** (Master Boot Record)              | **GPT** (GUID Partition Table)                  |
| ---------------- | ----------------------------------------- | ----------------------------------------------- |
| First sector     | 446 B boot code + 64 B partition table + 2 B `55 AA` signature | LBA 0 = "protective MBR" for legacy tools; real table at LBA 1+ |
| Max disk size    | **2 TiB** (32-bit LBA × 512 B sectors)    | **9.4 ZiB** (64-bit LBA)                        |
| Max primary partitions | **4** (or 3 primary + 1 extended)   | **128** by default, expandable                  |
| Redundancy       | **None** — one table, corruption is fatal | **Two copies** (start and end of disk) + CRC32 checksums |
| Boot method      | Legacy BIOS                               | UEFI (BIOS can boot GPT via a "BIOS boot" partition) |
| Today's default  | Legacy; only on old machines / USB sticks | Standard on every disk made since ~2010         |

**Filesystem internals (using ext4 as the canonical example):**

| Structure       | What it holds                                                              |
| --------------- | -------------------------------------------------------------------------- |
| **Superblock**  | "Identity card" of the filesystem — block size, total blocks, free blocks, UUID, label, magic number. Backed up multiple times across the disk. |
| **Inode**       | All metadata for **one file**: type, permissions, owner, size, timestamps, and pointers to data blocks. **No filename** — the name lives in the parent directory. |
| **Directory**   | A file whose data is a list of `(filename, inode_number)` pairs            |
| **Data blocks** | The actual file contents — allocated in extents on ext4/xfs                |
| **Bitmap**      | Tracks which blocks / inodes are free vs in use                            |
| **Journal**     | Recent metadata changes — replayed after a crash to keep the FS consistent |

A **hard link** is just another directory entry pointing to the same inode — that's why `rm`ing a hard-linked file only decrements the link count and the bytes survive until the last link is gone.

**Examples:**

```bash
# Sector size and disk geometry:
sudo fdisk -l /dev/sda | head
# Disk /dev/sda: 465.76 GiB, 500107862016 bytes, 976773168 sectors
# Disk model: Samsung SSD 870 EVO 500GB
# Units: sectors of 1 * 512 = 512 bytes
# Sector size (logical/physical): 512 bytes / 512 bytes

# Detect MBR vs GPT:
sudo parted /dev/sda print | grep "Partition Table"
# Partition Table: gpt

# Or with fdisk:
sudo fdisk -l /dev/sda | grep -i 'disklabel\|partition table'
# Disklabel type: gpt

# Inspect a filesystem's superblock (ext4):
sudo dumpe2fs -h /dev/sda2 | head -20
# Filesystem volume name:   root
# Last mounted on:          /
# Filesystem UUID:          1234abcd-...-ef56
# Filesystem magic number:  0xEF53
# Block count:              122000000
# Block size:               4096
# Inode count:              7864320
# Free blocks:              81203456

# Look up the inode of a file:
ls -i /etc/passwd
# 12345 /etc/passwd
stat /etc/passwd
#   File: /etc/passwd
#   Size: 2700    Blocks: 8      IO Block: 4096   regular file
# Device: 803h/2051d  Inode: 12345  Links: 1
# Access: (0644/-rw-r--r--)  Uid: (0/root)  Gid: (0/root)

# How many inodes are free? (running out is its own kind of "disk full")
df -ih
# Filesystem     Inodes IUsed IFree IUse% Mounted on
# /dev/sda2        7.5M  600K  6.9M    8% /

# Peek at the first 512 bytes of a disk (MBR boot code + partition table):
sudo dd if=/dev/sda of=/tmp/mbr.bin bs=512 count=1 status=none
hexdump -C /tmp/mbr.bin | tail -5
# 000001c0  ...                                            ← partition entries
# 000001f0  ...     55 aa                                  ← MBR signature
```

**Notes:**

- **Sector size matters.** On **4Kn** ("4K native") drives the sector is 4096 B, not 512 B. Tools usually report both **logical** (what the OS sees) and **physical** (what the drive uses) sector sizes; misaligned partitions on 4K drives cost performance.
- **Filenames are not in inodes.** They live in the **parent directory entry**. That's why one inode can have many names (hard links) and why renaming is cheap (it's just a directory edit).
- **"Disk full" can mean inodes, not bytes.** Running out of inodes (millions of tiny files) leaves bytes free but `touch` fails with `No space left on device`. `df -i` is the check.
- **`dumpe2fs` (ext*) and `xfs_info` (xfs)** are the "what's actually on this FS" tools — block size, inode count, journal location, feature flags.
- **Hard links can't cross filesystems** (they're just inode numbers, which are FS-local) and **can't point to directories** (would create cycles). Symlinks have neither restriction but they're a separate file with their own inode.
- **The superblock has multiple backups.** If the primary is corrupted, `e2fsck -b <backup_block>` can recover from one of them (`mke2fs -n` lists their locations without formatting).

### Disk Partitioning

**Description:** **Partitioning** carves a disk into independent regions, each of which can hold its own filesystem (or a swap area, or be left raw for LVM / dm-crypt). The partition table at the start of the disk (MBR or GPT — see [Anatomy of a Disk](#anatomy-of-a-disk)) records where each partition begins and ends. Linux ships three classic tools: **`fdisk`** (MBR & GPT, interactive, scriptable), **`gdisk`** (GPT-focused), and **`parted`** (both, fully scriptable). After partitioning you **format** each partition with `mkfs.<type>`, then **mount** it manually or via `/etc/fstab`.

**The end-to-end flow:**

```
1. Pick a disk           lsblk
2. Create partitions     sudo parted /dev/sdb / fdisk /dev/sdb
3. Reload partition table partprobe / kernel auto-detects on close
4. Format each partition sudo mkfs.ext4 /dev/sdb1
5. Mount (temporary)     sudo mount /dev/sdb1 /mnt/data
6. Mount (persistent)    add UUID entry to /etc/fstab, then `mount -a`
```

**The toolkit:**

| Tool      | Strengths                                                            |
| --------- | -------------------------------------------------------------------- |
| `lsblk`   | Tree view of every block device + partitions + mountpoints           |
| `fdisk`   | Interactive editor (`m` for menu). Works on both MBR and GPT.        |
| `gdisk`   | Like `fdisk` but GPT-only — clearer menu, better recovery options    |
| `cfdisk`  | Curses-style fdisk — friendlier UI                                   |
| `parted`  | Scriptable from the CLI in one line — great for automation           |
| `partprobe` | Tell the kernel to re-read the partition table without rebooting   |
| `mkfs.*`  | Format a partition (`mkfs.ext4`, `mkfs.xfs`, `mkfs.vfat`, ...)       |
| `wipefs`  | Erase filesystem **signatures** from a device (forces it to "look blank") |
| `blkid`   | Print UUID, label, and type of an existing filesystem                |

**Examples — create one partition spanning a whole new disk:**

```bash
# 0. Identify the target disk (CONFIRM IT'S BLANK):
lsblk -f
# /dev/sdb  ← 32G stick, no children → safe to overwrite

# 1. With `parted` (scriptable, one-liner per step):
sudo parted /dev/sdb --script mklabel gpt
sudo parted /dev/sdb --script mkpart primary ext4 1MiB 100%
sudo parted /dev/sdb --script print
# Partition Table: gpt
# Number  Start   End     Size    File system  Name     Flags
#  1      1049kB  32.0GB  32.0GB               primary

# 2. Format:
sudo mkfs.ext4 -L data /dev/sdb1

# 3. Get its UUID:
sudo blkid /dev/sdb1
# /dev/sdb1: LABEL="data" UUID="9f2e..." TYPE="ext4" PARTUUID="..."

# 4. Mount once:
sudo mkdir -p /mnt/data
sudo mount /dev/sdb1 /mnt/data
df -h /mnt/data

# 5. Persist via /etc/fstab — by UUID, never /dev/sdb1:
echo "UUID=9f2e...  /mnt/data  ext4  defaults,nofail  0  2" \
  | sudo tee -a /etc/fstab
sudo mount -a                    # apply now without rebooting
findmnt /mnt/data                # confirm
```

**Same job with interactive `fdisk`:**

```bash
sudo fdisk /dev/sdb
# Command (m for help): g     ← create GPT label
# Command (m for help): n     ← new partition
# Partition number: 1
# First sector: <Enter>       ← default
# Last sector / +SIZE: <Enter>← use the whole disk
# Command (m for help): p     ← preview
# Command (m for help): w     ← WRITE and exit
sudo partprobe /dev/sdb        # tell the kernel about the change
sudo mkfs.ext4 -L data /dev/sdb1
```

**Resizing safely:**

```bash
# Grow ext4 on /dev/sdb1 after enlarging the partition itself:
sudo resize2fs /dev/sdb1

# Grow xfs (xfs cannot shrink):
sudo xfs_growfs /mnt/data

# Grow a partition with parted (then resize the FS):
sudo parted /dev/sdb resizepart 1 100%
sudo resize2fs /dev/sdb1
```

**An `/etc/fstab` line, decoded:**

```
UUID=9f2e...  /mnt/data  ext4  defaults,nofail  0  2
└─────┬────┘  └───┬───┘  └─┬┘  └───────┬──────┘  ┴  ┴
   what to     where to    │           │         │  └── fsck pass (0 = skip, 1 = root, 2 = others)
   mount       mount it   type   mount options   └── dump backup (almost always 0)
```

Use **`UUID=`** for stable mounts (`sdX` letters can shift); the older `/dev/sdb1` style still works but is fragile.

**Notes:**

- **Partition before you format.** `mkfs` on the raw `/dev/sdb` (no partition) "works" but is unconventional — most tools and recovery scripts expect a partition table.
- **`partprobe` (or `kpartx -a`)** tells the kernel about partition-table changes without a reboot. Some kernels also auto-reread the table on `close()` of the disk, but never rely on it.
- **Use `UUID=` or `LABEL=` in `/etc/fstab`**, never `/dev/sdXN`. The persistent IDs survive hotplug reordering and disk additions.
- **`nofail` is your friend on removable/optional disks** — without it, an unmounted `/etc/fstab` entry can drop the box into emergency mode at boot. `nofail` lets boot continue.
- **`mount -a` does a dry run of `/etc/fstab`.** After editing it, **always** `sudo mount -a` once before rebooting — better to find a typo at the shell than at the next boot.
- **You can shrink ext4 but not xfs.** Plan ahead: if you might ever want to shrink, choose ext4. xfs is a one-way grow.
- **Don't repartition a disk that's in use** — even moving partition boundaries on the live root disk requires either a live USB or LVM. For root-disk resizes, boot from a live USB and use `gparted` (graphical) or `parted` + `resize2fs`.
- **`wipefs -a /dev/sdb`** clears every filesystem and partition signature — handy when a disk has stale data that confuses installers ("Is this really a blank disk?"). The data remains on the platters until overwritten.

### Creating Filesystems

**Description:** Partitioning carves the disk; **creating a filesystem** is what actually writes the on-disk structures (superblock, inode table, journal, free-space bitmap) that turn a raw region into something the kernel can mount. The tool family is **`mkfs.<type>`** — one binary per filesystem (`mkfs.ext4`, `mkfs.xfs`, `mkfs.vfat`, `mkfs.btrfs`, ...). All of them destroy whatever was there before, so **double-check the target device** before pressing Enter.

**The everyday options that matter:**

| Option           | Effect                                                                          |
| ---------------- | ------------------------------------------------------------------------------- |
| `-L <label>`     | Human-readable label (ext4/xfs). Later visible at `/dev/disk/by-label/<label>`. |
| `-U <uuid>`      | Pin a specific UUID (ext4/xfs) — useful when restoring `/etc/fstab` after a reformat. |
| `-n` / `-N`      | **Dry run** — print what would happen without writing (ext family).             |
| `-T <usage>`     | Optimize for a workload: `mkfs.ext4 -T largefile4 /dev/sdb1` for big files.     |
| `-b <bytes>`     | Block size (default 4096). Rarely changed — 4 KiB matches the page size.        |
| `-m <pct>`       | Reserved blocks for root (ext4 default is 5%; lower it on huge data disks).     |
| `-E lazy_itable_init=0` | Force full inode-table init at format time instead of background lazy init. Slower format, no first-mount surprise. |

**Examples:**

```bash
# Format a partition as ext4 with a label:
sudo mkfs.ext4 -L data /dev/sdb1
# Creating filesystem with 8388608 4k blocks and 2097152 inodes
# Filesystem UUID: 9f2e...

# Format as xfs (no shrink later — be sure!):
sudo mkfs.xfs -L bigdata -f /dev/sdc1     # -f forces overwrite of existing FS

# Format a USB stick for cross-OS use:
sudo mkfs.vfat -F 32 -n USBKEY /dev/sdd1

# Big-file optimization on ext4 (e.g. media library, VM images):
sudo mkfs.ext4 -T largefile4 -L media /dev/sdb1

# Pin a specific UUID (handy when rebuilding to keep /etc/fstab unchanged):
sudo mkfs.ext4 -U 9f2e0000-1111-2222-3333-444455556666 /dev/sdb1

# After formatting — confirm:
sudo blkid /dev/sdb1
# /dev/sdb1: LABEL="data" UUID="9f2e..." TYPE="ext4"
lsblk -f /dev/sdb
```

**Notes:**

- **`mkfs` is destructive — there's no undo.** Always run `lsblk -f` first and confirm the target has no children you care about.
- **`mkfs.xfs` refuses to overwrite an existing FS without `-f`.** That's a feature, not a bug — it's saved more than one disk.
- **Reserved blocks (`-m`) default to 5% on ext4.** On a 4 TB data disk that's 200 GB locked away for root. Drop to 1% (`-m 1`) on non-root partitions.
- **Pick the right filesystem before formatting** — switching later means recreating the FS and copying data back. See [Filesystem Types](#filesystem-types).
- **Format the partition, not the disk.** `mkfs.ext4 /dev/sdb` (no number) wipes the partition table — works but breaks most tooling expectations.

### mount and umount

**Description:** A formatted filesystem isn't usable until you **mount** it — attach it at some point in the unified tree rooted at `/`. The kernel keeps a list of active mounts; userspace sees them as the directory contents at each mountpoint. `mount` attaches, `umount` detaches. Mounts can be **temporary** (one-off shell commands) or **persistent** (written into [/etc/fstab](#etcfstab) and applied at boot).

**The commands:**

| Command                               | Purpose                                                            |
| ------------------------------------- | ------------------------------------------------------------------ |
| `mount`                               | Show all current mounts                                            |
| `mount <src> <mountpoint>`            | Attach a filesystem at a directory                                 |
| `mount -t <type> <src> <mp>`          | Explicit filesystem type (usually auto-detected)                   |
| `mount -o <opts> <src> <mp>`          | Mount with options (`ro`, `noexec`, `nosuid`, `nodev`, `noatime`)  |
| `mount -o remount,<opts> <mp>`        | Change options on an already-mounted FS without unmounting         |
| `mount --bind <src> <dst>`            | Re-expose an existing tree at a second location                    |
| `mount -a`                            | Mount everything in `/etc/fstab` that isn't already mounted        |
| `umount <mp>` / `umount <src>`        | Detach the filesystem                                              |
| `umount -l <mp>`                      | **Lazy unmount** — detach now, finalize when last user closes      |
| `findmnt <mp>`                        | Pretty tree of mounts (replaces parsing `/proc/mounts`)            |
| `lsof <mp>` / `fuser -vm <mp>`        | Who's holding the mount busy? (essential when `umount` says "busy")|

**Examples:**

```bash
# One-off mount:
sudo mkdir -p /mnt/data
sudo mount /dev/sdb1 /mnt/data
df -h /mnt/data

# Mount read-only, no setuid, no device nodes, no exec — typical for /home or /tmp on hardened boxes:
sudo mount -o ro,nosuid,nodev,noexec /dev/sdb1 /mnt/data

# Mount with relaxed atime updates (big perf win on busy disks):
sudo mount -o noatime /dev/sdb1 /mnt/data

# Remount root read-write (single-user rescue):
sudo mount -o remount,rw /

# Bind mount — make a tree visible at a second place (useful for chroots, containers):
sudo mount --bind /var/log /srv/chroot/var/log

# Mount an ISO image as a loop device:
sudo mount -o loop ubuntu.iso /mnt/iso

# Show every active mount in a clean tree:
findmnt
# Or for one mountpoint:
findmnt /mnt/data

# Unmount — fails if anything is using it:
sudo umount /mnt/data
# umount: /mnt/data: target is busy.

# Find who's using it:
sudo lsof +D /mnt/data
sudo fuser -vm /mnt/data

# Lazy unmount when you can't kill the holder (use sparingly):
sudo umount -l /mnt/data
```

**Common mount options:**

| Option       | Meaning                                                              |
| ------------ | -------------------------------------------------------------------- |
| `ro` / `rw`  | Read-only / read-write                                               |
| `nosuid`     | Ignore setuid/setgid bits — defense-in-depth on untrusted FSes       |
| `nodev`      | Ignore device nodes on the mount — never trust foreign `/dev/sda`    |
| `noexec`     | No binaries can be executed from this mount                          |
| `noatime`    | Don't update access times on reads (big perf win)                    |
| `relatime`   | Only update atime if older than mtime/ctime (the modern default)     |
| `sync`       | All writes go straight to disk (slow but durable)                    |
| `discard`    | Issue TRIM/UNMAP on file deletion (SSDs only — usually use `fstrim` instead) |
| `defaults`   | `rw,suid,dev,exec,auto,nouser,async` — the typical baseline          |

**Notes:**

- **`umount: target is busy`** means a process has a file open or a shell `cd`'d into the mount. Use `lsof +D` or `fuser -vm` to find the holder.
- **Lazy unmount (`umount -l`)** detaches the namespace immediately but waits for last reference to disappear before actually releasing. Useful as a last resort; not a substitute for finding the real holder.
- **`mount` without arguments** prints the current mount table — quick sanity check that something landed where you expected.
- **`noatime` is essentially free perf**. Modern kernels default to `relatime`; `noatime` is even cheaper. Only the rare app (some mail spools) cares about atime.
- **Bind mounts are not symlinks.** They make the same inode visible at two paths — the kernel knows it's one filesystem, while a symlink is just a text pointer.

### /etc/fstab

**Description:** `/etc/fstab` ("**f**ile **s**ystem **tab**le") is the boot-time mount manifest. Each non-comment line tells the system: "at boot, mount **this device** at **this directory** with **these options**". `mount -a` applies the whole file; `systemd` parses it at boot and generates `*.mount` units automatically. **A typo here can keep your box from booting** — always validate before you reboot.

**The six fields:**

```
UUID=9f2e...    /mnt/data    ext4    defaults,nofail,noatime    0    2
└─────┬─────┘   └────┬───┘   └──┬┘   └────────────┬──────────┘   ┴    ┴
   1 what       2 where      3 type     4 options              5 dump 6 fsck pass
```

| # | Field      | Meaning                                                                  |
| - | ---------- | ------------------------------------------------------------------------ |
| 1 | **fs_spec**   | What to mount: `UUID=…`, `LABEL=…`, `/dev/sdb1`, or `//server/share`   |
| 2 | **fs_file**   | Where to mount it (the mountpoint must already exist as a directory)   |
| 3 | **fs_vfstype**| `ext4`, `xfs`, `vfat`, `nfs`, `tmpfs`, `swap`, …                        |
| 4 | **fs_mntops** | Comma-separated mount options (see below)                              |
| 5 | **fs_freq**   | Used by the ancient `dump` backup tool — **always `0`** in practice    |
| 6 | **fs_passno** | `fsck` order at boot: `0` = skip, `1` = root, `2` = others             |

**Useful options to know:**

| Option        | Purpose                                                                  |
| ------------- | ------------------------------------------------------------------------ |
| `defaults`    | `rw,suid,dev,exec,auto,nouser,async` — the baseline                      |
| `noauto`      | Don't mount at boot. Still mountable with `mount /mountpoint`.           |
| `nofail`      | Boot continues even if the device is missing — **essential for removable / optional disks** |
| `x-systemd.automount` | Lazy automount — mounts on first access (great for slow / network FSes) |
| `x-systemd.device-timeout=10` | Don't hang boot forever waiting on a missing disk      |
| `user`        | Allow non-root users to mount this entry                                 |
| `_netdev`     | Treat as a network FS — wait for the network online target first         |

**Examples:**

```bash
# A typical data disk by UUID:
UUID=9f2e0000-1111-2222-3333-444455556666  /mnt/data  ext4  defaults,nofail,noatime  0  2

# A USB stick that may or may not be plugged in:
LABEL=USBKEY  /mnt/usb  vfat  defaults,nofail,noauto,user  0  0

# A swap partition:
UUID=aaaa-bbbb-...  none  swap  sw  0  0

# A tmpfs mount with a 2 GiB cap:
tmpfs  /var/tmp/build  tmpfs  defaults,size=2G,noatime  0  0

# An NFS share:
nas.local:/exports/media  /srv/media  nfs  defaults,_netdev,x-systemd.automount  0  0

# A bind mount (chroot prep):
/var/log  /srv/chroot/var/log  none  bind  0  0
```

**Validate before rebooting:**

```bash
# Re-mount everything from /etc/fstab — catches typos NOW, not at boot:
sudo mount -a
# (no output = success; any error = fix before rebooting!)

# Inspect what systemd parsed:
systemctl list-units --type=mount

# What's in the current mount table:
findmnt --fstab            # what /etc/fstab says
findmnt                    # what's actually mounted
```

**Notes:**

- **Always use `UUID=` or `LABEL=`**, never `/dev/sdX1`. SCSI/SATA device letters can reshuffle when a disk is added or hotplugged.
- **`nofail` is your seatbelt.** Without it, a missing removable disk drops the box into emergency mode at boot. With it, boot continues normally.
- **`mount -a` is a free dry run.** Run it after every edit. If it errors at the shell, it will error at boot — except at boot you may have no shell to fix it from.
- **Field 5 (`dump`) is essentially obsolete** — set to `0`. Field 6 (`fsck pass`): `1` only for `/`, `2` for other ext-family FSes that should be checked, `0` for everything else (xfs auto-checks at mount time, so `0`).
- **`x-systemd.automount` is the friendly default for slow / optional / network mounts** — the mountpoint exists immediately, but the actual mount happens on first access.

### swap

**Description:** **Swap** is disk space the kernel uses as a spillover when RAM gets tight. Pages of memory that haven't been touched recently are written out to swap; when needed again they're paged back in. Swap can live on a **dedicated partition** or in a **swap file** — modern systems usually use a file because it's easy to grow or remove. Swap doesn't make a slow workload fast, but it lets a box survive a memory spike without OOM-killing your processes.

**The tools:**

| Command                          | What it does                                                       |
| -------------------------------- | ------------------------------------------------------------------ |
| `mkswap <dev-or-file>`           | Initialize a partition or file as swap (writes the swap signature) |
| `swapon <dev-or-file>`           | Activate swap                                                      |
| `swapoff <dev-or-file>`          | Deactivate swap (pages currently in swap get faulted back to RAM)  |
| `swapon --show`                  | List active swap areas, sizes, usage, priority                     |
| `free -h`                        | Show total/used/free RAM and swap                                  |
| `cat /proc/swaps`                | Same info as `swapon --show`, plain text                           |

**Create a swap file (the common case):**

```bash
# 1. Allocate a 4 GiB file. Use fallocate (fast); if FS doesn't support it, use dd:
sudo fallocate -l 4G /swapfile
# Fallback for filesystems without fallocate (btrfs may need a different recipe):
# sudo dd if=/dev/zero of=/swapfile bs=1M count=4096 status=progress

# 2. Lock it down — swap MUST be 0600 or mkswap will refuse:
sudo chmod 600 /swapfile

# 3. Format it as swap:
sudo mkswap /swapfile
# Setting up swapspace version 1, size = 4 GiB
# UUID=aaaa-bbbb-...

# 4. Activate now:
sudo swapon /swapfile
swapon --show
# NAME      TYPE  SIZE  USED PRIO
# /swapfile file  4G    0B   -2

# 5. Persist via /etc/fstab so it's there after reboot:
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```

**Create a swap partition (old-school but still valid):**

```bash
sudo mkswap /dev/sdb2
sudo swapon /dev/sdb2
# Persist:
echo "UUID=$(sudo blkid -s UUID -o value /dev/sdb2)  none  swap  sw  0  0" \
  | sudo tee -a /etc/fstab
```

**Tuning swappiness:**

```bash
# How aggressively the kernel swaps (0 = avoid, 100 = aggressive). Default = 60.
cat /proc/sys/vm/swappiness
# 60

# Lower it on a desktop / latency-sensitive box (10-20 is common):
sudo sysctl -w vm.swappiness=10
# Persist:
echo 'vm.swappiness=10' | sudo tee /etc/sysctl.d/99-swap.conf
```

**Remove swap entirely:**

```bash
sudo swapoff /swapfile          # deactivate (may take a while if heavily used)
sudo sed -i '/swapfile/d' /etc/fstab
sudo rm /swapfile
```

**Notes:**

- **How much swap?** Old rule was 2× RAM; modern rule is "as much as you need to hibernate, or 2–4 GiB otherwise". Servers often run with **no swap** and rely on the OOM killer; desktops benefit from some.
- **Swap file vs partition: functionally identical** since Linux 2.6. Files are easier to resize and remove; partitions can have a tiny edge for hibernation on some setups.
- **Swappiness 60 is fine for servers**; lower (10–20) helps desktop responsiveness; higher (100) is for memory-constrained containers where any swap is better than OOM.
- **`zram` / `zswap` are RAM-compression alternatives** to disk swap — pages are compressed in memory instead of (or in addition to) written to disk. Many distros (Fedora, Ubuntu desktop) enable zram by default.
- **Swap on SSD is fine** — modern drives have enough write endurance that swap traffic is a rounding error. The "swap kills SSDs" advice is from ~2010.

### Disk Usage

**Description:** When `df` says the disk is full, **`du`** tells you where the space went. The two tools answer different questions: `df` reports **filesystem-level** free/used space (from the superblock); `du` reports **per-directory** sizes by walking the tree and summing file sizes. They can disagree — and when they do, that's usually a clue (deleted-but-open files, hidden mounts, sparse files).

**The toolkit:**

| Tool           | What it tells you                                                       |
| -------------- | ----------------------------------------------------------------------- |
| `df -h`        | Free / used / total space per **mounted filesystem**                    |
| `df -i`        | Same, but counting **inodes** instead of bytes                          |
| `df -T`        | Add a filesystem-type column                                            |
| `du -sh <dir>` | **Summary** size of one directory                                       |
| `du -h --max-depth=1 <dir>` | Direct children of `<dir>`, sorted by size              |
| `du -ah <dir>` | Every file and directory (huge output — pipe through `sort` / `head`)   |
| `ncdu <dir>`   | Interactive TUI — browse usage, delete with `d` (install separately)    |
| `lsof +L1`     | Files with **link count 0** — deleted but still held open (the classic "space gone, can't find it" cause) |

**Examples:**

```bash
# What's the space situation overall?
df -h
# Filesystem      Size  Used Avail Use% Mounted on
# /dev/sda2       450G  430G   20G  96% /
# tmpfs           7.7G  120K  7.7G   1% /tmp
# /dev/sdb1       1.8T  300G  1.5T  17% /data

# Inodes (a partition can be "full" by inode exhaustion even with bytes free):
df -i
# Filesystem      Inodes IUsed IFree IUse% Mounted on
# /dev/sda2         7.5M  7.4M  100K   99% /
#                                       ↑ uh oh

# Top space hogs under /var:
sudo du -h --max-depth=1 /var | sort -h | tail -10
# 800M   /var/cache
# 1.2G   /var/lib
# 4.5G   /var/log

# Drill into one subtree:
sudo du -h --max-depth=1 /var/log | sort -h
sudo du -ah /var/log | sort -h | tail -20    # specific big files

# Interactive (best UX for hunting):
sudo ncdu /

# Find big files anywhere:
sudo find / -xdev -type f -size +500M -exec ls -lh {} \; 2>/dev/null

# "df says full but du says small" → look for deleted-but-open files:
sudo lsof +L1
# COMMAND  PID  USER  FD  TYPE  ...  SIZE/OFF  NLINK  NAME
# nginx    1234 root  3w  REG   ...  4294967296  0     /var/log/nginx/access.log (deleted)
#                                                ↑ space stays held until process restarts
```

**Notes:**

- **`df -h` reports filesystem free space**; `du` reports the bytes a tree's files account for. They differ because (a) deleted-but-open files hold blocks until the FD closes, (b) sparse files have fewer real bytes than apparent bytes, (c) reserved-for-root blocks (`tune2fs -m`) appear used to non-root.
- **The `-h` flag is universal** — `df -h`, `du -h`, `ls -lh`, `sort -h` (sorts `1K`, `1M`, `1G` correctly). Memorize it.
- **`-x` / `--one-file-system`** stops `du`/`find` from crossing mountpoints — essential when scanning `/` so you don't dive into `/proc`, `/sys`, network mounts, etc.
- **Inode exhaustion looks like a full disk** but `df -h` shows free bytes. Always check `df -i` when a "disk full" doesn't match `df -h`. Common cause: a tree of millions of tiny files (mail spools, build caches).
- **`ncdu` is worth installing.** `du | sort | head` is fine; `ncdu` is what you reach for in an actual outage.
- **Truncate, don't delete, log files of live processes.** `> /var/log/big.log` frees the space immediately; `rm /var/log/big.log` doesn't (the FD is still open). Or `truncate -s 0 /var/log/big.log`.

### Filesystem Repair

**Description:** Filesystems can get inconsistent after a crash, power loss, or bad shutdown. **`fsck`** ("**f**ile**s**ystem **c**hec**k**") is the front-end that dispatches to the right per-FS tool: `e2fsck` for ext2/3/4, `xfs_repair` for xfs, `btrfs check` for btrfs, etc. Journaled filesystems usually replay the journal at mount time and never need a manual `fsck`, but bigger corruption (bad blocks, controller crash, accidental write to a partition) needs an offline repair.

**The cardinal rule: never `fsck` a mounted, writable filesystem.** Either unmount it, or remount it read-only first.

**The toolkit:**

| Tool           | Filesystem    | Notes                                                    |
| -------------- | ------------- | -------------------------------------------------------- |
| `fsck`         | dispatcher    | Picks the right tool based on FS type                    |
| `e2fsck`       | ext2/3/4      | `-n` = read-only check, `-y` = answer yes to all prompts |
| `xfs_repair`   | xfs           | Must be unmounted. xfs has no equivalent to `e2fsck -n`. |
| `btrfs check`  | btrfs         | Read-only by default; `--repair` is **last resort, dangerous** |
| `tune2fs`      | ext family    | Adjust ext FS parameters (mount counts, reserved blocks, label, UUID) |
| `dumpe2fs`     | ext family    | Dump superblock and block-group info                     |
| `xfs_info`     | xfs           | Inspect xfs geometry (block size, journal, AGs)          |

**Examples:**

```bash
# Boot to single-user / rescue and the root FS is dirty:
# (first remount read-only — or boot from a USB live env)
sudo mount -o remount,ro /
sudo fsck -y /

# Check (don't modify) an ext4 partition:
sudo e2fsck -n /dev/sdb1
# Pass 1: Checking inodes, blocks, and sizes
# Pass 2: Checking directory structure
# ...
# /dev/sdb1: 12345/7864320 files (0.0% non-contiguous), 600000/31250000 blocks

# Force a check even if the FS looks clean:
sudo e2fsck -f /dev/sdb1

# Repair (interactive, asks before each change):
sudo e2fsck /dev/sdb1
# Or assume-yes to all (only after a read-only -n pass!):
sudo e2fsck -y /dev/sdb1

# Repair xfs — MUST be unmounted:
sudo umount /mnt/data
sudo xfs_repair /dev/sdb1
# Phase 1 - find and verify superblock...
# Phase 2 - using internal log
# ...

# Re-tune an ext4 FS without recreating:
sudo tune2fs -L newlabel /dev/sdb1        # change label
sudo tune2fs -m 1 /dev/sdb1               # set reserved blocks to 1%
sudo tune2fs -c 50 /dev/sdb1              # force fsck every 50 mounts
sudo tune2fs -l /dev/sdb1 | head          # print superblock summary
```

**Recovering from a corrupt superblock (ext4):**

```bash
# Find backup superblocks:
sudo mke2fs -n /dev/sdb1
# Superblock backups stored on blocks: 32768, 98304, 163840, ...

# Try a backup superblock for fsck:
sudo e2fsck -b 32768 /dev/sdb1
```

**Notes:**

- **`fsck` on a mounted RW filesystem will corrupt it.** This is one of the easiest ways to destroy data on Linux. Always unmount first, or `mount -o remount,ro`, or boot from a rescue USB.
- **For the root FS, repair from a live USB** or from the initramfs rescue shell (some distros also let you append `fsck.mode=force` to the kernel cmdline).
- **xfs journals replay automatically at mount.** If `mount` fails with "Structure needs cleaning", you need `xfs_repair`. xfs has no read-only check — `xfs_repair -n` is the closest equivalent.
- **`e2fsck -n` first, `e2fsck -y` only after.** The dry run tells you what's wrong; only then decide if blind auto-repair is acceptable. Real corruption often deserves a hand on the wheel.
- **`tune2fs -c 0 -i 0`** disables time/mount-count-based forced fsck — useful on busy servers where you don't want a 30-minute fsck triggered at the next reboot. On modern journaled FSes the boot-time check is largely cosmetic.
- **Image the disk before deep recovery.** `ddrescue` (not plain `dd`) copies a failing disk into an image you can `fsck` repeatedly without grinding the original further.

### Inodes

**Description:** Every file on a Unix filesystem is represented by an **inode** — a fixed-size on-disk record holding the file's **metadata** (size, owner, permissions, timestamps, link count, and pointers to the data blocks). What's *not* in the inode? The **filename**. Names live in **directories**, which are tables mapping names to inode numbers. That separation is why a file can have many names (hard links), why renames are free, and why `ls -l` reports a link count.

**What an inode holds:**

| Field        | What it stores                                                          |
| ------------ | ----------------------------------------------------------------------- |
| Inode number | Unique ID within the filesystem (printed by `ls -i`)                    |
| Mode         | File type + permission bits (`-rw-r--r--`, `drwxr-xr-x`)                |
| Owner/Group  | UID and GID                                                             |
| Size         | Bytes                                                                   |
| Timestamps   | `atime` (access), `mtime` (modify), `ctime` (metadata change)           |
| Link count   | How many directory entries point at this inode (`nlink`)                |
| Block pointers | Where the actual data lives (direct, indirect, double-indirect, ...)  |

**What an inode does NOT hold:** the **filename** (lives in the parent directory) and the **file's contents** (live in the data blocks the inode points at).

**Examples:**

```bash
# Show inode number alongside filename:
ls -li /etc/passwd
# 12345 -rw-r--r-- 1 root root 2700 May 22 14:30 /etc/passwd
#  ↑ inode number

# Detailed metadata:
stat /etc/passwd
#   File: /etc/passwd
#   Size: 2700        Blocks: 8       IO Block: 4096   regular file
# Device: 803h/2051d  Inode: 12345    Links: 1
# Access: (0644/-rw-r--r--)  Uid: (0/root)  Gid: (0/root)
# Access: 2026-06-19 09:01:23
# Modify: 2026-06-18 17:44:01
# Change: 2026-06-18 17:44:01

# How many inodes total / free on each FS?
df -i
# Filesystem      Inodes IUsed IFree IUse% Mounted on
# /dev/sda2         7.5M  600K  6.9M    8% /

# Two filenames sharing one inode (a hard link):
echo hello > original.txt
ln original.txt alias.txt
ls -li *.txt
# 12346 -rw-r--r-- 2 user user 6 ... alias.txt
# 12346 -rw-r--r-- 2 user user 6 ... original.txt
#  ↑ same inode    ↑ nlink=2

# Delete one name — file lives on (nlink decreases):
rm alias.txt
ls -li original.txt
# 12346 -rw-r--r-- 1 user user 6 ... original.txt

# Find files by inode (e.g., who else points at this one?):
find / -xdev -inum 12346 2>/dev/null
```

**Notes:**

- **Inodes are a fixed pool, allocated at `mkfs` time.** A filesystem can be "full" two ways: out of blocks (bytes) **or** out of inodes (files). `df -h` shows one, `df -i` shows the other. Tree of millions of tiny files? Likely inode exhaustion.
- **`rm` removes a directory entry, not a file.** The kernel only reclaims the inode and data blocks when **link count hits 0 AND no process has the file open**. That's why removing an open log file doesn't free space until the process closes (or restarts).
- **Hard links share an inode.** Soft links ([symlinks](#symlinks)) don't — they're a separate inode whose data block is the path of the target.
- **`ctime` ≠ creation time.** It's *change* time — when the inode itself was last modified (perms changed, owner changed, link count changed). Linux only added a real **birth time** with ext4 / xfs and a separate `statx()` syscall.
- **Inodes are per-filesystem.** Inode 12345 on `/dev/sda2` is unrelated to inode 12345 on `/dev/sdb1`. Hard links across filesystems are impossible because there's no shared inode space — that's why `ln` fails across mounts.
- **xfs / btrfs allocate inodes dynamically**; ext2/3/4 do not. So "out of inodes" is mostly an ext family problem. If you regularly fill with tiny files, format with `mkfs.ext4 -i <bytes-per-inode>` to bump the inode count.

### symlinks

**Description:** A **symbolic link** (a.k.a. **soft link** or **symlink**) is a tiny special file whose contents are a **path** pointing to another file. Unlike a hard link (which is a second name for the *same* inode), a symlink has its own inode and just stores the text of the target's path. Symlinks can cross filesystems, point at directories, and even point at things that don't exist (**dangling links**) — the resolution happens every time the path is followed.

**Symlink vs hard link:**

|                              | Symlink (`ln -s`)              | Hard link (`ln`)             |
| ---------------------------- | ------------------------------ | ---------------------------- |
| Own inode?                   | Yes, separate                   | No — same inode as target    |
| Can cross filesystems?       | **Yes**                         | No                           |
| Can point to a directory?    | **Yes**                         | No (only root can, rarely)   |
| Can point to non-existent target? | Yes — becomes "dangling"   | No (target must exist at creation) |
| Survives deletion of target? | Becomes dangling                | Yes (data lives until last link gone) |
| Shown by `ls -l`             | `lrwxrwxrwx ... link -> target` | Indistinguishable from a regular file |

**Examples:**

```bash
# Create a symlink: `ln -s <target> <linkname>`
ln -s /usr/local/bin/myapp ~/bin/myapp
ls -l ~/bin/myapp
# lrwxrwxrwx 1 user user 21 Jun 20 10:30 /home/user/bin/myapp -> /usr/local/bin/myapp

# Symlink to a directory — works the same way:
ln -s /var/log/myapp ~/logs

# Read what a symlink points to:
readlink ~/bin/myapp
# /usr/local/bin/myapp

# Resolve all symlinks to a real path:
readlink -f ~/bin/myapp
# /usr/local/bin/myapp

# Dangling symlink — target doesn't exist:
ln -s /tmp/does-not-exist /tmp/broken
ls -l /tmp/broken
# lrwxrwxrwx 1 user user 21 Jun 20 10:31 /tmp/broken -> /tmp/does-not-exist
file /tmp/broken
# /tmp/broken: broken symbolic link to /tmp/does-not-exist

# Replace a symlink atomically (the only safe way to update one in place):
ln -sfn /usr/local/app-v2 /opt/app    # -f = force, -n = don't follow if dst is a symlink

# Find all symlinks under a tree:
find /etc -type l

# Find dangling symlinks:
find / -xtype l 2>/dev/null

# Hard link for contrast — same inode, no arrow:
ln original.txt hardlink.txt
ls -li *.txt
# 12346 -rw-r--r-- 2 user user 6 ... hardlink.txt
# 12346 -rw-r--r-- 2 user user 6 ... original.txt
```

**Relative vs absolute targets:**

```bash
# Absolute — works from anywhere, but breaks if you move the whole tree:
ln -s /home/user/projects/data ~/data-abs

# Relative — survives moving the parent dir intact, but only resolves correctly
# from the symlink's own directory:
cd ~
ln -s projects/data data-rel
readlink data-rel        # projects/data
```

**Notes:**

- **`ln -s <target> <linkname>`** — the order is "what it points to, where the link goes". Easy to get backwards; if you do, you'll create a link in the wrong place. The arrow in `ls -l` (`link -> target`) is your mnemonic.
- **`-n` matters when replacing a symlink to a directory.** Without `-n`, `ln -sf newtarget existingdir-symlink` follows the existing symlink and creates a link **inside** the target dir instead of replacing the symlink. Always `ln -sfn` for "replace this symlink".
- **Symlinks store the literal target string.** Move the target, the symlink dangles. Move the symlink (with a relative target) to somewhere where the relative path no longer resolves, the symlink dangles.
- **`readlink -f` resolves the full chain**, including symlinks-to-symlinks. Use it when you need a canonical absolute path — for example, before logging a "real" file location.
- **Permissions on a symlink itself are usually `lrwxrwxrwx` and ignored** — what matters is the permissions of the **target**. (`chmod` on the link follows to the target by default; `chmod -h` would modify the link's own bits on the rare FS that honors them.)
- **Avoid hard-linking config files between packages** — package managers replace files by `unlink + rename`, which breaks the hard link silently. Symlinks survive that pattern.

---

## Boot the System

Notes on **what happens between power-on and login prompt**. The boot path is a relay race — firmware hands control to the bootloader, the bootloader loads the kernel, the kernel mounts a root filesystem and starts the init system, and init brings up the rest of userspace. Understanding the handoffs is what lets you fix a box that won't boot — most "broken machines" are stuck at exactly one of these stages.

### One Shot Revision

| Topic                                                         | Short Description                                                                |
| ------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| [Boot Process Overview](#boot-process-overview)               | The five stages — firmware → bootloader → kernel → init → login                  |
| [Boot Process: BIOS](#boot-process-bios)                      | **BIOS / UEFI** — POST, firmware, MBR vs ESP, boot order                         |
| [Boot Process: Bootloader](#boot-process-bootloader)          | **GRUB2** / systemd-boot — kernel selection, `grub.cfg`, kernel cmdline          |
| [Boot Process: Kernel](#boot-process-kernel)                  | `vmlinuz`, `initramfs`, kernel cmdline, `dmesg`                                  |
| [Boot Process: Init](#boot-process-init)                      | **systemd** (and SysV before it) — units, targets, `systemctl`, `journalctl`     |

### Boot Process Overview

**Description:** Linux boot is a **five-stage relay**. Each stage loads, initializes, and hands off to the next. When a machine "won't boot", the most useful first question is *which stage is it stuck at* — the diagnostic tools and fixes are completely different at each layer.

**The five stages, in order:**

```
1. Firmware (BIOS / UEFI)
   Power on → POST (memory, CPU, devices) → pick a boot device → load first-stage code
                                                       ↓
2. Bootloader (GRUB2, systemd-boot, ...)
   Read its config → show menu (optional) → load kernel + initramfs into RAM
                                                       ↓
3. Kernel (vmlinuz)
   Decompress → init drivers from initramfs → mount real root FS → exec /sbin/init
                                                       ↓
4. Init (systemd / SysVinit)
   PID 1 → bring up units in dependency order → reach default.target (multi-user / graphical)
                                                       ↓
5. Login
   getty on TTYs / display manager (gdm, sddm) → user logs in → shell or desktop
```

**Quick map: which logs go with which stage?**

| Stage      | Where to look when it breaks                                                  |
| ---------- | ----------------------------------------------------------------------------- |
| Firmware   | Screen messages, BIOS/UEFI setup, `dmidecode`, beep codes                     |
| Bootloader | GRUB rescue prompt, `/boot/grub/grub.cfg`, `/boot/loader/entries/*.conf`      |
| Kernel     | `dmesg`, `journalctl -k`, kernel panic on screen, `/var/log/kern.log`         |
| Init       | `journalctl -b` (current boot), `systemctl --failed`, `systemctl status <unit>` |
| Login      | `journalctl -u getty@tty1`, `journalctl -u gdm`, `~/.xsession-errors`         |

**Examples — inspecting the most recent boot end to end:**

```bash
# What firmware did we boot from? (UEFI if /sys/firmware/efi exists, else legacy BIOS)
[ -d /sys/firmware/efi ] && echo UEFI || echo "legacy BIOS"

# How long did each stage take?
systemd-analyze
# Startup finished in 2.3s (firmware) + 1.1s (loader) + 3.5s (kernel) + 4.2s (userspace)
#                    = 11.1s
# multi-user.target reached after 4.2s in userspace

# What's the slowest unit?
systemd-analyze blame | head
# 3.412s NetworkManager-wait-online.service
# 1.220s plymouth-quit-wait.service
# ...

# Plot a boot timeline (SVG):
systemd-analyze plot > boot.svg

# All kernel messages from this boot:
journalctl -k -b

# All log messages from this boot, oldest first:
journalctl -b

# The previous boot (use -1 for one back, -2 for two back, ...):
journalctl -b -1
```

**Notes:**

- **The single most useful diagnostic command is `journalctl -b`** — every message from PID 1 onwards in the current boot. Add `-k` for kernel-only, `-p err` for errors-only, `-u <unit>` for one service.
- **`systemd-analyze` is a one-liner that splits the boot into firmware / loader / kernel / userspace.** If userspace is 30 seconds, `blame` will tell you which units to look at.
- **"Won't boot" almost always means stuck in one of stages 2–4.** Stage 1 failures usually mean dead hardware or a missing disk; stage 5 failures mean you booted fine but no login appeared.
- **Rescue boot** is a graphical-less / single-user variant: append `systemd.unit=rescue.target` (or `single`) to the kernel cmdline from the GRUB menu. `emergency.target` is even more minimal (just root, no most-mounts).

### Boot Process: BIOS

**Description:** **Firmware** is the first code that runs after power-on. On older PCs it's the **BIOS** ("**B**asic **I**nput/**O**utput **S**ystem"); on modern machines (anything since ~2012) it's **UEFI** ("**U**nified **E**xtensible **F**irmware **I**nterface"). Either way, the job is the same: run **POST** (Power-On Self Test) to verify hardware, look at a configured **boot order**, and hand control to the first bootable thing it finds. BIOS and UEFI differ in *how* they find that thing.

**BIOS vs UEFI:**

|                          | Legacy BIOS                          | UEFI                                                |
| ------------------------ | ------------------------------------ | --------------------------------------------------- |
| Year introduced          | 1981                                  | ~2005 (mainstream ~2012)                            |
| Partition table          | MBR (max 2 TiB / 4 primary parts)    | GPT (>2 TiB, ~128 parts)                            |
| How it finds the loader  | Reads first 512 B (MBR) of boot disk | Reads **EFI System Partition** (ESP), parses FAT, loads `.efi` binaries |
| Boot entries             | One per disk (MBR boot code)         | Many, stored in **NVRAM** (managed by `efibootmgr`) |
| Secure Boot              | No                                   | Yes (signed bootloaders only)                       |
| Where the bootloader lives | `/boot/grub/` + the disk's MBR     | `/boot/efi/EFI/<distro>/grubx64.efi` (or similar)   |

**The handoff:**

```
BIOS:    POST → look at MBR (first 512 B of boot disk) → jump to boot code
                                                          ↓
                                                       Stage 1.5 / 2 of GRUB
UEFI:    POST → read NVRAM boot entries → load chosen .efi from ESP → execute
                                                          ↓
                                                       GRUB / systemd-boot / ...
```

**Examples — inspecting firmware state:**

```bash
# Am I on UEFI or legacy BIOS?
[ -d /sys/firmware/efi ] && echo "UEFI" || echo "legacy BIOS"

# UEFI boot entries (the ones the firmware would offer at next boot):
sudo efibootmgr -v
# BootCurrent: 0001
# Timeout: 1 seconds
# BootOrder: 0001,0000,0002
# Boot0000* Windows Boot Manager  HD(1,GPT,...)/File(\EFI\Microsoft\Boot\bootmgfw.efi)
# Boot0001* ubuntu                HD(1,GPT,...)/File(\EFI\ubuntu\shimx64.efi)
# Boot0002* UEFI: USB Stick       ...

# Change the default boot entry order:
sudo efibootmgr -o 0001,0000,0002

# The ESP (EFI System Partition) is normally mounted at /boot/efi:
mount | grep efi
# /dev/sda1 on /boot/efi type vfat (...)

# What's in it?
ls -R /boot/efi/EFI/
# /boot/efi/EFI/:
# BOOT  ubuntu  Microsoft
# /boot/efi/EFI/ubuntu:
# grubx64.efi  shimx64.efi  grub.cfg

# Firmware info (vendor, version, settings the OS can see):
sudo dmidecode -t bios
# BIOS Information
#   Vendor: American Megatrends Inc.
#   Version: 1.30
#   Release Date: 03/15/2024
#   ...

# Is Secure Boot on?
sudo mokutil --sb-state
# SecureBoot enabled
```

**Notes:**

- **`/sys/firmware/efi` is the litmus test for UEFI.** If it exists, you're on UEFI; if not, you booted in legacy mode (even on a UEFI machine — many can do either).
- **The ESP is just a FAT32 partition** flagged as the EFI System Partition. You can read and write it from any OS, which is how recovery USBs put a bootloader on disk.
- **`efibootmgr` is your friend on UEFI** — adding, reordering, and removing boot entries doesn't require touching disks, only the firmware's NVRAM. It also doesn't survive a CMOS reset, which is why distro installers write the entry on every kernel install.
- **Secure Boot blocks unsigned `.efi` binaries.** That's why custom kernels need to be signed, or you need to enroll a **MOK** (Machine Owner Key) with `mokutil` — or disable Secure Boot in firmware setup.
- **No EFI on a board's NVRAM = no boot.** Some cheap firmwares "forget" entries when the battery dies. The `/boot/efi/EFI/BOOT/BOOTX64.EFI` fallback path is the universal backup — copy your bootloader there as `BOOTX64.EFI` for a firmware-independent fallback.

### Boot Process: Bootloader

**Description:** The **bootloader** is the small program firmware hands control to. Its job: pick a kernel, load it (and its **initramfs**) into RAM, set up a **kernel command line**, and jump to the kernel's entry point. On Linux this is overwhelmingly **GRUB2** ("**GR**and **U**nified **B**ootloader"). Lightweight alternatives include **systemd-boot** (UEFI only, minimal), **rEFInd**, and **syslinux/isolinux** (live media).

**GRUB2 at a glance:**

| Piece                            | What it is                                                              |
| -------------------------------- | ----------------------------------------------------------------------- |
| `/boot/grub/grub.cfg`            | The actual config GRUB reads at boot. **Generated** — do not hand-edit. |
| `/etc/default/grub`              | High-level settings (timeout, default entry, kernel cmdline defaults)   |
| `/etc/grub.d/`                   | Scripts that compose `grub.cfg` (each one contributes menu entries)     |
| `update-grub` / `grub2-mkconfig` | Regenerate `grub.cfg` from `/etc/default/grub` + `/etc/grub.d/`         |
| `grub-install`                   | Write the bootloader code to the disk (MBR) or ESP (UEFI)               |

**The boot menu lives here:**

```
GRUB                  ← interactive menu (Esc / Shift to see it)
  Ubuntu              ← default entry → loads /boot/vmlinuz + /boot/initrd.img
  Ubuntu (recovery)
  Memory test
  Windows Boot Manager
```

**Examples — common operations:**

```bash
# What's the current default kernel cmdline (as recorded in /etc/default/grub)?
grep GRUB_CMDLINE_LINUX /etc/default/grub
# GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"
# GRUB_CMDLINE_LINUX=""

# What did the kernel ACTUALLY get on the cmdline at this boot?
cat /proc/cmdline
# BOOT_IMAGE=/boot/vmlinuz-6.8.0-31-generic root=UUID=... ro quiet splash

# Change the menu timeout / default / cmdline:
sudo vi /etc/default/grub
# GRUB_TIMEOUT=5
# GRUB_DEFAULT=0
# GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset"   # add nomodeset for graphics issues
sudo update-grub                     # Debian/Ubuntu
# sudo grub2-mkconfig -o /boot/grub2/grub.cfg   # RHEL/Fedora

# (Re-)install GRUB to a disk's MBR (legacy BIOS):
sudo grub-install /dev/sda

# Reinstall on UEFI (writes /boot/efi/EFI/<distro>/grubx64.efi):
sudo grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=ubuntu

# Show available menu entries (handy for setting GRUB_DEFAULT by name):
sudo awk -F\' '/menuentry / {print $2}' /boot/grub/grub.cfg
# Ubuntu
# Advanced options for Ubuntu
# Ubuntu, with Linux 6.8.0-31-generic
# Ubuntu, with Linux 6.8.0-31-generic (recovery mode)
```

**Editing a kernel cmdline at boot (one-shot, no config change):**

```
At the GRUB menu:
  - Highlight an entry, press `e` to edit
  - Find the `linux` line ending with `quiet splash`
  - Append flags: e.g. `single`, `systemd.unit=rescue.target`, `init=/bin/bash`
  - Press Ctrl-X (or F10) to boot this entry once
```

**Useful kernel cmdline flags:**

| Flag                            | Effect                                                            |
| ------------------------------- | ----------------------------------------------------------------- |
| `quiet`                         | Suppress most kernel boot messages                                |
| `splash`                        | Show graphical boot splash (Plymouth)                             |
| `nomodeset`                     | Disable kernel-mode-setting — workaround for broken graphics drivers |
| `single` / `systemd.unit=rescue.target` | Boot into single-user / rescue mode                       |
| `systemd.unit=emergency.target` | Even more minimal — just root FS, nothing else                    |
| `init=/bin/bash`                | Skip init entirely — drop into a root shell. Last-resort recovery. |
| `ro` / `rw`                     | Mount root read-only / read-write at boot                         |
| `root=UUID=…`                   | Which device is the root filesystem                                |

**Notes:**

- **Never hand-edit `/boot/grub/grub.cfg`** — it's regenerated. Edit `/etc/default/grub` and run `update-grub` (Debian) or `grub2-mkconfig -o /boot/grub2/grub.cfg` (RHEL).
- **`/proc/cmdline` is ground truth.** Whatever's there is what the running kernel actually received — useful when you're not sure if your `update-grub` actually took.
- **Editing at the GRUB menu (`e`) is one-shot** — it only affects this boot. Reboot and you're back to the saved entries. Perfect for rescue / "did that flag fix it" experiments.
- **`init=/bin/bash` is the ultimate "I can't even boot" rescue.** Drops you into a root shell with no init, no journal, nothing — but you can edit `/etc/fstab`, `passwd`, etc. Remount `/` with `mount -o remount,rw /` first.
- **systemd-boot is simpler than GRUB** — one `.conf` per entry under `/boot/loader/entries/`, no scripting, no theme system. UEFI-only. Many minimalist distros (Arch with `bootctl`) use it.

### Boot Process: Kernel

**Description:** Once the bootloader jumps to the kernel, the kernel **decompresses itself into memory**, initializes core subsystems (memory management, scheduler, drivers compiled in), and then unpacks the **initramfs** ("**init**ial **RAM** **f**ile **s**ystem") — a tiny temporary root containing just enough drivers and tools to find and mount the **real** root filesystem. Once the real root is mounted, the kernel pivots into it and executes the init system (PID 1). All kernel messages are visible via `dmesg` / `journalctl -k`.

**Key files in `/boot`:**

| File                                  | What it is                                                             |
| ------------------------------------- | ---------------------------------------------------------------------- |
| `vmlinuz-<version>`                    | Compressed kernel image                                                |
| `initrd.img-<version>` / `initramfs-<version>.img` | Initramfs — drivers, modprobe rules, `/init` script         |
| `config-<version>`                     | The `.config` the kernel was built with                                |
| `System.map-<version>`                 | Symbol map (kernel-space addresses) — used to decode oopses            |
| `/lib/modules/<version>/`              | Loadable kernel modules for that kernel                                |

**The pivot:**

```
Bootloader loads vmlinuz + initramfs into RAM
        ↓
Kernel decompresses, brings up CPUs / memory / built-in drivers
        ↓
Kernel mounts initramfs as a temporary root (/)
        ↓
initramfs's /init runs:
   - load modules needed to see the real root disk (NVMe, RAID, LUKS, LVM, ...)
   - mount the real root FS at /sysroot
   - switch_root /sysroot → real root becomes /, initramfs is freed
        ↓
Kernel execs /sbin/init (PID 1, normally systemd)
```

**Examples — inspecting what's running and how it booted:**

```bash
# Which kernel am I running?
uname -r
# 6.8.0-31-generic
uname -a    # full info: kernel name, host, version, arch

# Available kernels installed:
ls -lh /boot/vmlinuz-*

# All kernel boot messages from this boot:
dmesg | less              # may require sudo on some distros
journalctl -k -b          # same data via systemd journal

# Kernel messages from the previous boot:
journalctl -k -b -1

# Errors-only (good for "what went wrong during boot"):
journalctl -k -p err -b

# Find / debug a hardware driver that didn't load:
dmesg | grep -i nvme
dmesg | grep -iE "error|fail|warn"

# What modules are loaded right now?
lsmod | head
# Module                  Size  Used by
# nvme                  ...
# ext4                  ...
# ...

# Load / unload a module manually:
sudo modprobe i915        # load
sudo modprobe -r i915     # unload

# Inspect initramfs contents (Debian/Ubuntu):
lsinitramfs /boot/initrd.img-$(uname -r) | head -20
# Or extract for forensic poking:
mkdir /tmp/initrd && cd /tmp/initrd && \
  zstdcat /boot/initrd.img-$(uname -r) | cpio -idmv

# Rebuild initramfs (after a driver / fstab change):
sudo update-initramfs -u            # Debian/Ubuntu
# sudo dracut -f                    # RHEL/Fedora/Arch

# Live kernel parameters (sysctl):
sysctl vm.swappiness
# vm.swappiness = 60
sudo sysctl -w net.ipv4.ip_forward=1
# Persist via /etc/sysctl.d/*.conf
```

**Notes:**

- **The kernel can only see disks it has drivers for.** If your root FS is on NVMe, the NVMe driver must either be built into the kernel **or** present in the initramfs. Mismatch = "can't find root" panic. After changing storage hardware, rebuild the initramfs.
- **`dmesg` vs `journalctl -k`:** same data (the kernel ring buffer), different front ends. `dmesg` is older; `journalctl -k -b` lets you filter by boot.
- **Kernel panics print on the console, not the journal.** If the kernel dies before the journal exists (initramfs phase), grab the message from the screen or take a photo — it's the only copy.
- **`/proc/cmdline` is what got passed in**; `dmesg` shows what the kernel did with it. Add `debug` to the cmdline temporarily to firehose extra info on the next boot.
- **Always keep one known-good kernel installed.** Distros usually keep the previous one — never `apt autoremove` away your last fallback. The "Advanced options" GRUB submenu lets you boot it on demand.
- **`initramfs` is regenerated automatically** on kernel install/upgrade and on `update-initramfs -u`. Manual builds are rare — usually only when adding a driver / encryption module that the kernel needs at very-early boot.

### Boot Process: Init

**Description:** **Init** is **PID 1** — the first userspace process the kernel starts, and the ancestor of every other process. Its job: bring up everything else (filesystems, networking, services, login prompts) in the right order, supervise long-running services, and shut everything down cleanly. On modern Linux, init is **systemd**; older / minimalist systems use **SysVinit**, **OpenRC**, or **runit**. systemd organizes the world as **units** (services, mounts, sockets, timers, targets) and brings up a configured **default target** (usually `multi-user.target` or `graphical.target`).

**The systemd unit zoo:**

| Unit type    | What it represents                                                  |
| ------------ | ------------------------------------------------------------------- |
| `.service`   | A long-running process (`nginx.service`, `sshd.service`)            |
| `.socket`    | A socket activated on demand (starts the service when connected to) |
| `.mount`     | A mountpoint (auto-generated from `/etc/fstab`)                     |
| `.timer`     | A scheduled trigger (modern cron replacement)                       |
| `.target`    | A "named state" — group of units to reach together                  |
| `.path`      | A filesystem-watch trigger                                          |

**The boot targets that matter:**

| Target                  | Old SysV runlevel | Meaning                                |
| ----------------------- | ----------------- | -------------------------------------- |
| `poweroff.target`       | 0                  | Halt the machine                       |
| `rescue.target`         | 1 / `single`       | Single-user, root shell, no network    |
| `multi-user.target`     | 3                  | Full text-mode boot, networking on     |
| `graphical.target`      | 5                  | Multi-user + display manager           |
| `reboot.target`         | 6                  | Reboot                                 |
| `emergency.target`      | —                  | Even more minimal than rescue (root FS only, read-only) |
| `default.target`        | —                  | Symlink → whichever of the above is the default for this box |

**Examples — daily systemd:**

```bash
# What target am I in?
systemctl get-default
# graphical.target

# Change the default target (persist across reboots):
sudo systemctl set-default multi-user.target

# Switch right now (no reboot):
sudo systemctl isolate rescue.target

# Service control:
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl reload nginx          # reread config without restart, if supported
sudo systemctl enable nginx          # start on boot
sudo systemctl enable --now nginx    # enable AND start
sudo systemctl disable nginx
sudo systemctl status nginx          # state, recent log lines, main PID

# Anything in a failed state?
systemctl --failed

# All units of a given type:
systemctl list-units --type=service
systemctl list-unit-files --type=service     # everything installed, enabled or not

# What does this unit depend on / what depends on it?
systemctl list-dependencies nginx
systemctl list-dependencies --reverse nginx

# Read or edit a unit (creates an override, doesn't touch the original):
systemctl cat nginx
sudo systemctl edit nginx             # opens an override snippet in $EDITOR
sudo systemctl daemon-reload          # reload after editing

# Inspect logs for a unit (current boot only):
journalctl -u nginx -b
journalctl -u nginx -f                # follow (like tail -f)
journalctl -u nginx --since "10 min ago"
```

**Boot timing & diagnosis:**

```bash
# How long did boot take, broken down?
systemd-analyze
systemd-analyze blame                 # slowest units
systemd-analyze critical-chain        # critical path through dependencies
systemd-analyze plot > boot.svg       # full graphical timeline

# Why is a unit failing?
systemctl status sshd                 # short
journalctl -u sshd -b                 # full logs this boot
```

**SysVinit, briefly (for legacy systems):**

```bash
# Runlevel-based — /etc/init.d/<service> scripts, /etc/rc<N>.d/ symlinks
sudo service nginx start              # SysV-style (works on systemd too as a shim)
sudo /etc/init.d/nginx restart
runlevel                              # show previous and current runlevels
sudo telinit 3                        # switch to runlevel 3 (multi-user, no GUI)
```

**Notes:**

- **`systemctl status <unit>` is the single most useful command** when something is wrong. It shows state, the last few log lines, and the main PID. 80% of "service won't start" debugging starts and ends here.
- **`journalctl -u <unit> -b` is the second most useful.** Same idea but full logs for the current boot. Add `-f` to tail it live.
- **`systemctl edit <unit>` is the right way to customize a packaged unit.** It creates an override snippet under `/etc/systemd/system/<unit>.d/override.conf`, leaving the distro-provided unit file untouched so package upgrades don't fight you.
- **Targets are the systemd answer to runlevels** — but multiple targets can be active at once (a target is just "this set of units is up"). `systemctl isolate <target>` deactivates everything that isn't required by the new target.
- **Always `daemon-reload` after editing a unit file** (`/etc/systemd/system/...` or after `systemctl edit`). Otherwise systemd is still running the old definition.
- **PID 1 must never die.** If init crashes, the kernel panics. That's why systemd is paranoid about its own internals — and why running systemd-the-init under heavy custom config requires care.
- **For containers, init looks different.** Most containers run a single process as PID 1 (no init). If that process spawns children, you may need a tiny init (`tini`, `dumb-init`) to reap zombies — outside of full-OS containers like systemd-in-a-container.

---

## Kernel

Notes on **the Linux kernel** — the resident program that owns the CPU, RAM, and every piece of hardware. Userspace can't touch hardware directly; everything goes through the kernel via **system calls**. This section covers what the kernel is, how the **user/kernel privilege split** works on x86, how syscalls cross the boundary, and how to install, locate, and extend the kernel with **loadable modules**.

### One Shot Revision

| Topic                                                | Short Description                                                            |
| ---------------------------------------------------- | ---------------------------------------------------------------------------- |
| [Overview of the Kernel](#overview-of-the-kernel)    | What a kernel is, monolithic vs microkernel, what Linux's kernel does        |
| [Privilege Levels](#privilege-levels)                | **Kernel mode** vs **user mode** — rings, context switches, why it matters   |
| [System Calls](#system-calls)                        | The user → kernel API: `syscall`, `strace`, libc wrappers                    |
| [Kernel Installation](#kernel-installation)          | `apt install linux-image`, `dnf install kernel`, building from source        |
| [Kernel Location](#kernel-location)                  | `/boot/vmlinuz`, `/lib/modules/`, `/proc`, `/sys`                            |
| [Kernel Modules](#kernel-modules)                    | `lsmod`, `modprobe`, `insmod`, `rmmod`, `modinfo`                            |

### Overview of the Kernel

**Description:** The **kernel** is the part of the operating system that runs with full hardware access. It owns the CPU scheduler, memory manager, filesystem layer, network stack, and device drivers. Everything else (shells, daemons, browsers) runs as a userspace process and asks the kernel — via **system calls** — whenever it needs to read a file, send a packet, or fork a process. Linux is specifically a **monolithic kernel with loadable modules**: the core is one big binary, but drivers and optional subsystems can be loaded and unloaded at runtime.

**What the kernel does:**

| Subsystem               | Responsibility                                                          |
| ----------------------- | ----------------------------------------------------------------------- |
| **Scheduler**           | Decides which process runs on which CPU and for how long                |
| **Memory management**   | Virtual memory, paging, address spaces, swap                            |
| **VFS / filesystems**   | Uniform `open/read/write` over ext4, xfs, NFS, procfs, ...              |
| **Block I/O layer**     | Talks to disks, SSDs, RAID                                              |
| **Network stack**       | TCP/IP, UDP, sockets, netfilter / iptables                              |
| **Device drivers**      | Concrete code for each piece of hardware (NIC, GPU, NVMe, USB, ...)     |
| **Syscall interface**   | The boundary userspace crosses to ask for any of the above              |
| **IPC**                 | Pipes, signals, shared memory, semaphores                               |

**Monolithic vs microkernel (one-line):**

```
Monolithic (Linux):   one big kernel binary, drivers run in kernel space → fast, less isolation
Microkernel (Mach):   tiny core + drivers as separate userspace servers   → slower IPC, stronger isolation
Hybrid (XNU/macOS, NT/Windows): mostly monolithic in practice
```

**Examples:**

```bash
# What kernel am I running?
uname -r
# 6.8.0-31-generic
uname -a    # full name, version, build date, arch

# Where the kernel exposes itself to userspace:
ls /proc/sys      # tunables (sysctl reads these)
ls /sys           # device tree, drivers
cat /proc/version
# Linux version 6.8.0-31-generic ... (gcc 12.3.0) #31-Ubuntu SMP ...

# Kernel build config (often shipped at /boot):
zcat /proc/config.gz 2>/dev/null | head   # if CONFIG_IKCONFIG_PROC is on
ls /boot/config-$(uname -r)
```

**Notes:**

- **Linux is the kernel, not the OS.** "A Linux distribution" = the Linux kernel + GNU coreutils + systemd + libc + your distro's package set. Without userspace, the kernel boots and panics looking for `/sbin/init`.
- **Drivers live in the kernel address space.** A buggy driver can crash the whole machine — there is no userspace isolation between, say, the NVMe driver and the scheduler. This is what people mean when they criticize monolithic kernels.
- **The "Linux Way" of extension is loadable modules**, not recompilation. You almost never rebuild the kernel today — you `modprobe` what you need.
- **`/proc` and `/sys` are not real files** — they're virtual filesystems exposing kernel data structures. Reading `/proc/cpuinfo` calls into the kernel, which formats the answer on the fly.
- **Kernel APIs are stable for userspace, unstable internally.** The syscall ABI (e.g. `read(2)`) hasn't broken since the 90s. Internal driver APIs change every few releases — that's why out-of-tree drivers (NVIDIA, ZFS) need DKMS to rebuild on each kernel update.

### Privilege Levels

**Description:** Modern CPUs run code at different **privilege levels** so a misbehaving program can't take down the whole machine. On x86 these are called **rings**: ring 0 is the most privileged (kernel mode), ring 3 is the least (user mode). The kernel runs in ring 0 and can execute any instruction, touch any memory, talk to any device. Userspace programs run in ring 3 and can only do what the kernel allows — reaching the kernel requires a controlled handoff called a **context switch**.

**The rings (x86):**

| Ring | Who runs here       | Can do                                                       |
| ---- | ------------------- | ------------------------------------------------------------ |
| 0    | The kernel          | Anything — privileged instructions, all memory, all I/O      |
| 1    | (unused on Linux)   | —                                                            |
| 2    | (unused on Linux)   | —                                                            |
| 3    | Userspace (`ls`, browsers, daemons) | Only user-accessible memory, no `in`/`out`/`hlt`/etc. |

Hypervisors added **ring -1** (VMX root, "hardware virtualization") in 2005; SMM is informally "**ring -2**". Linux uses just 0 and 3 — keep it simple.

**Crossing the boundary (user → kernel → user):**

```
userspace process            kernel
    │
    │  read(fd, buf, n)      ← libc wrapper invokes `syscall` instruction
    │  ─────────────────►
    │                        ┌── CPU switches to ring 0
    │                        ├── Saves user registers, enters syscall handler
    │                        ├── Looks up syscall 0 (read) in the table
    │                        ├── Validates fd, copies bytes from kernel buffer
    │                        ├── Returns count (or -errno) in RAX
    │                        └── Switches back to ring 3, restores user regs
    │  ◄─────────────────
    │  control resumes after the `syscall` instruction
```

**Examples — see the boundary in action:**

```bash
# Watch a process talk to the kernel — every syscall printed:
strace -c ls /tmp
# % time     seconds  usecs/call     calls    errors syscall
# ------ ----------- ----------- --------- --------- ----------------
#   24.78    0.000022           1        20           openat
#   18.02    0.000016           1        15           read
#   ...

# Time spent in user mode vs kernel mode for a command:
/usr/bin/time -v find /usr -name "*.so" > /dev/null
# User time (seconds): 0.30
# System time (seconds): 1.21        ← time spent in ring 0 on this process's behalf
# Percent of CPU this job got: 98%

# What % of total CPU is the system spending in kernel vs user mode right now?
mpstat 1 3
# %usr   %nice    %sys  %iowait    %irq   %soft  %steal   %idle
#  6.20    0.00    2.10     0.50    0.00    0.10    0.00   91.10
#                  ↑ %sys = ring 0
```

**Notes:**

- **Context switches are expensive.** A syscall is ~tens of nanoseconds plus cache pollution. High-perf code (databases, packet pipelines) often batches syscalls or uses `io_uring` / `epoll` to amortize them.
- **`%sys` is "time in the kernel on your behalf"** — not the kernel doing its own thing. If `%sys` is 30% for your workload, your code is calling the kernel a lot (lots of small reads, lots of `gettimeofday`, etc.).
- **You can never directly call kernel code.** The `syscall` instruction (or `int 0x80` on old 32-bit) is the only door. Everything that "feels like" calling the kernel (`read`, `open`, `socket`) is a libc wrapper around `syscall`.
- **Hardware virtualization (ring -1) is what lets KVM run guest OSes** at "full ring 0" speed inside another OS — the hypervisor traps the privileged things the guest does and emulates them.
- **Ring 3 cannot do `cli`, `hlt`, port I/O, MSR access**, or change page tables. Try any of these and you get **SIGSEGV**.

### System Calls

**Description:** A **system call** is the controlled, narrow API the kernel exposes to userspace. Everything a userspace program does that touches the outside world — open a file, send a packet, allocate memory, fork a process, exit — is ultimately one or more system calls. There are roughly **400** of them on modern Linux/x86-64. They're identified by a small integer (the **syscall number**), invoked via the `syscall` instruction, and almost always wrapped by **libc** so you write `open("file", ...)` in C rather than assembly.

**The categories:**

| Group              | Examples                                                          |
| ------------------ | ----------------------------------------------------------------- |
| File I/O           | `open`, `read`, `write`, `close`, `lseek`, `stat`, `unlink`       |
| Process            | `fork`, `execve`, `exit`, `wait4`, `getpid`, `getppid`            |
| Memory             | `mmap`, `munmap`, `brk`, `mprotect`, `madvise`                    |
| IPC / signals      | `pipe`, `kill`, `rt_sigaction`, `futex`, `shmget`                 |
| Networking         | `socket`, `bind`, `listen`, `accept`, `connect`, `sendto`, `recvfrom` |
| Time               | `clock_gettime`, `nanosleep`, `time`                              |
| Privileges / sec   | `setuid`, `setgid`, `capset`, `prctl`, `seccomp`                  |

**Examples:**

```bash
# Trace every syscall a command makes:
strace ls /etc 2>&1 | head
# execve("/usr/bin/ls", ["ls", "/etc"], ...) = 0
# brk(NULL)                               = 0x55c...
# openat(AT_FDCWD, "/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3
# fstat(3, {st_mode=S_IFREG|0644, st_size=104867, ...}) = 0
# mmap(NULL, 104867, PROT_READ, MAP_PRIVATE, 3, 0) = 0x7f...
# ...

# Count syscalls + errors for a process:
strace -c -p $(pidof nginx) -e openat,read,write &
sleep 5; kill %1
# Summary table: syscall, count, errors, total time

# Trace only specific syscalls:
strace -e openat,connect curl -s example.com >/dev/null

# Trace I/O on the network:
strace -e network -p $(pidof sshd) 2>&1 | head

# Look up a syscall's manual page (section 2 = syscalls):
man 2 read
man 2 mmap

# List all syscall numbers on x86-64:
ausyscall --dump | head
# 0    read
# 1    write
# 2    open
# 3    close
# ...
```

**Inside a syscall (simplified):**

```c
// Userspace:
#include <unistd.h>
ssize_t n = read(fd, buf, count);   // libc wrapper

// What libc does on x86-64 (roughly):
mov rax, 0          // syscall number 0 = read
mov rdi, fd         // arg 1
mov rsi, buf        // arg 2
mov rdx, count      // arg 3
syscall             // ← trap into the kernel
// On return, rax = bytes read (or -errno as a negative number)
```

**Notes:**

- **`strace` is the workhorse debugging tool.** Use it to find why a program is hanging (stuck in `read`?), failing (`ENOENT` on a config file?), or being slow (`-c` for a per-syscall histogram).
- **System call numbers are stable, libc wrappers aren't.** `read(2)` syscall #0 will be #0 in 30 years. But Go, Rust, and other non-glibc runtimes sometimes call `syscall` directly to skip libc — same syscall, different path in.
- **`man 2 <name>` is the syscall manual**; `man 3 <name>` is the libc/library function. They often have the same name (`read`) — section number disambiguates.
- **vDSO** is a tiny shared library the kernel maps into every process so a few hot syscalls (`gettimeofday`, `clock_gettime`) can be answered without crossing into ring 0. Free perf.
- **seccomp** is a syscall whitelist mechanism: a process can promise the kernel "I'll only ever call read/write/exit", and any other syscall becomes an instant kill or error. Used by Docker, browsers, and systemd to lock services down.

### Kernel Installation

**Description:** On any mainstream distro the kernel is a regular package — you install it like anything else and the package manager handles writing `/boot/vmlinuz`, generating an **initramfs**, and updating GRUB. You almost never need to compile a kernel from source. The exceptions: bleeding-edge hardware, a specific bug-fix you can't wait for, custom security patches, or an embedded/tiny build.

**Distro packages:**

| Distro family    | Install command                                          | Where it lands                          |
| ---------------- | -------------------------------------------------------- | --------------------------------------- |
| Debian / Ubuntu  | `sudo apt install linux-image-generic`                   | `/boot/vmlinuz-<ver>`, `/lib/modules/<ver>/` |
| RHEL / Fedora    | `sudo dnf install kernel`                                | `/boot/vmlinuz-<ver>`, `/lib/modules/<ver>/` |
| Arch             | `sudo pacman -S linux`                                   | same                                    |
| openSUSE         | `sudo zypper install kernel-default`                     | same                                    |

**Examples — keeping kernels current:**

```bash
# Show currently-running kernel:
uname -r
# 6.8.0-31-generic

# All installed kernels (Debian/Ubuntu):
dpkg -l | grep linux-image
# RHEL/Fedora:
rpm -qa kernel

# Install latest available:
sudo apt update && sudo apt install linux-image-generic linux-headers-generic
# sudo dnf install kernel kernel-devel    # RHEL/Fedora

# Reboot into it (GRUB picks the newest by default):
sudo reboot

# After reboot, confirm:
uname -r

# Remove an old kernel (NEVER remove the running one!):
sudo apt remove linux-image-6.5.0-21-generic linux-headers-6.5.0-21-generic
# Or let the distro clean up:
sudo apt autoremove --purge
# RHEL/Fedora — keep the last N kernels:
sudo dnf install yum-utils
sudo package-cleanup --oldkernels --count=2
```

**Building from source (the rare case):**

```bash
# 1. Get the source:
cd /usr/src
sudo wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.8.0.tar.xz
sudo tar -xJf linux-6.8.0.tar.xz
cd linux-6.8.0

# 2. Start from your running config (sane default):
sudo cp /boot/config-$(uname -r) .config
sudo make olddefconfig            # apply defaults to any new options

# 3. (Optional) Customize:
sudo make menuconfig              # ncurses UI

# 4. Build — go get coffee:
sudo make -j$(nproc) bzImage modules

# 5. Install:
sudo make modules_install         # → /lib/modules/<ver>/
sudo make install                 # → /boot/vmlinuz-<ver>, updates initramfs + GRUB

# 6. Reboot, select the new kernel from GRUB
```

**Notes:**

- **Always keep a known-good kernel installed.** GRUB's "Advanced options" submenu lets you boot the previous kernel if the new one is broken — but only if you didn't `autoremove` it.
- **Headers are required for out-of-tree modules** (NVIDIA, VirtualBox, DKMS). `linux-headers-$(uname -r)` (Debian) / `kernel-devel` (RHEL).
- **DKMS** (Dynamic Kernel Module Support) recompiles out-of-tree modules every time the kernel updates — so NVIDIA, ZFS, and VirtualBox keep working through upgrades.
- **Source builds take ~20–60 minutes** on modern hardware with `-j$(nproc)`. The output is huge (~5 GB), so prune the tree after.
- **`make oldconfig` / `olddefconfig`** is the right way to start from your distro's `.config` — preserves your distro's choices and just asks (or accepts defaults for) new options.
- **Test in a VM first** when rolling your own kernel. The cost of "boots, but no network" on a remote box is much higher than 10 minutes in `qemu-system-x86_64`.

### Kernel Location

**Description:** A running Linux system spreads the kernel across **several directories**, each with a specific role: the **boot image** lives in `/boot`, **modules** in `/lib/modules`, **headers** in `/usr/src`, and the kernel's live state is exposed at `/proc` and `/sys`. Knowing the map makes it obvious where to look when something doesn't add up.

**The map:**

| Path                                          | What lives here                                                       |
| --------------------------------------------- | --------------------------------------------------------------------- |
| `/boot/vmlinuz-<version>`                     | The compressed kernel image — what the bootloader loads               |
| `/boot/initrd.img-<version>` / `initramfs-<version>.img` | Initramfs (drivers + tools to mount the real root FS)      |
| `/boot/System.map-<version>`                  | Symbol table (kernel-space addresses) — used to decode oopses         |
| `/boot/config-<version>`                      | The `.config` the kernel was built with                               |
| `/lib/modules/<version>/`                     | Loadable kernel modules (`.ko` files), grouped by subsystem           |
| `/lib/modules/<version>/build`                | Symlink to headers, needed to compile out-of-tree modules             |
| `/usr/src/linux-headers-<version>/`           | Kernel headers (only with `linux-headers-...` / `kernel-devel`)       |
| `/proc/`                                      | **Virtual** FS exposing per-process and kernel state                  |
| `/sys/`                                       | **Virtual** FS exposing the kernel's device model                     |
| `/proc/sys/`                                  | Runtime tunables (`sysctl` reads/writes here)                         |
| `/etc/sysctl.conf` + `/etc/sysctl.d/*.conf`   | Persistent tunables applied at boot                                   |

**Examples:**

```bash
# Inventory the current install:
ls -lh /boot
# vmlinuz-6.8.0-31-generic        13M
# initrd.img-6.8.0-31-generic     93M
# config-6.8.0-31-generic        260K
# System.map-6.8.0-31-generic    7.5M

# How big is the module tree for the running kernel?
du -sh /lib/modules/$(uname -r)
# 360M    /lib/modules/6.8.0-31-generic/

# Where would a built-in subsystem expose itself?
ls /sys/class
# bdi  block  drm  graphics  hwmon  input  net  power_supply  scsi_host  sound  tty  ...

# Live kernel tunables:
sysctl -a 2>/dev/null | head
# Read one:
cat /proc/sys/vm/swappiness
# Write one (live):
sudo sysctl -w net.ipv4.ip_forward=1
# Persist:
echo 'net.ipv4.ip_forward=1' | sudo tee /etc/sysctl.d/99-forward.conf
sudo sysctl --system

# Process-specific state lives under /proc/<pid>:
ls /proc/$$            # the current shell
# cmdline  cwd  environ  exe  fd  maps  status  ...
```

**Notes:**

- **`/boot` and `/lib/modules/<version>/` must agree.** If you delete `/lib/modules/6.8.0-31-generic/` but leave `/boot/vmlinuz-6.8.0-31-generic`, the kernel boots but `modprobe` finds nothing — half the drivers don't load.
- **`/proc` and `/sys` take zero disk space** — they're rendered on the fly by the kernel when you `cat` them.
- **`/proc/<pid>/` is the per-process gold mine.** `cmdline` (what was invoked), `cwd` (current dir as a symlink), `fd/` (every open file), `maps` (memory layout), `status` (UID/GID/memory).
- **`sysctl` writes are immediate but not persistent.** Anything you want at next boot goes in `/etc/sysctl.d/99-mything.conf` so it's reapplied automatically.
- **`/sys` reflects the device tree, not the user view.** Want to know which network interfaces exist? `ls /sys/class/net/`. Want to know what driver claims a device? `readlink /sys/class/net/eth0/device/driver`.

### Kernel Modules

**Description:** **Kernel modules** (`.ko` files) are pieces of kernel code that can be loaded and unloaded at runtime without rebooting. Most drivers ship as modules — only a small core is built into `vmlinuz`. When you plug in a USB device or load a filesystem, the kernel either auto-loads the relevant module (via `udev`) or you can do it explicitly with `modprobe`. This is what gives Linux its enormous hardware compatibility without a 500 MB kernel binary.

**The toolkit:**

| Command              | Purpose                                                                  |
| -------------------- | ------------------------------------------------------------------------ |
| `lsmod`              | List currently loaded modules                                            |
| `modinfo <module>`   | Show metadata: description, author, license, parameters, dependencies    |
| `modprobe <module>`  | Load a module **plus its dependencies** (preferred)                      |
| `modprobe -r <module>` | Unload a module (and unused deps)                                      |
| `insmod <file.ko>`   | Load a single `.ko` file — no dep resolution (rarely the right tool)     |
| `rmmod <module>`     | Unload a single module — no dep check (use `modprobe -r` instead)         |
| `depmod`             | Rebuild the module dependency database (after dropping a new `.ko` in)   |
| `/etc/modprobe.d/`   | Drop-in configs: module options, aliases, blacklists                     |
| `/etc/modules-load.d/` | Modules to auto-load at boot                                           |

**Examples:**

```bash
# What's loaded right now?
lsmod | head
# Module                  Size  Used by
# nvme                  ...
# ext4                  ...
# bluetooth             ...

# Tell me about a module:
modinfo nvme
# filename: /lib/modules/.../nvme.ko
# license: GPL
# description: NVM Express device driver
# parm: nvme_core_io_timeout:int     ← tunable parameters
# depends: nvme-core

# Load a module:
sudo modprobe i915                     # Intel graphics
# Same with custom parameter:
sudo modprobe i915 enable_dpcd_backlight=1

# Unload (only if no one is using it):
sudo modprobe -r i915

# Persist module options across reboots:
echo 'options i915 enable_dpcd_backlight=1' | sudo tee /etc/modprobe.d/i915.conf

# Auto-load a module at boot:
echo 'br_netfilter' | sudo tee /etc/modules-load.d/br_netfilter.conf

# Blacklist a module (prevent auto-load — useful for replacing buggy drivers):
echo 'blacklist nouveau' | sudo tee /etc/modprobe.d/blacklist-nouveau.conf
sudo update-initramfs -u               # Debian/Ubuntu, rebuild initramfs

# Drop a custom .ko into the modules tree:
sudo cp my_driver.ko /lib/modules/$(uname -r)/extra/
sudo depmod -a                         # rebuild the dep DB
sudo modprobe my_driver
```

**Notes:**

- **Use `modprobe`, not `insmod`/`rmmod`.** `modprobe` resolves dependencies, looks up aliases, and reads `/etc/modprobe.d/`. The low-level tools are for situations where you really know what you're doing.
- **`lsmod`'s "Used by" column matters.** A module with non-zero use count can't be unloaded until whoever's using it releases it (often: unmount the filesystem, unplug the device, kill the process).
- **`depmod` is what `make modules_install` runs** at the end. If you copy a `.ko` in by hand and modprobe says "module not found", you forgot `depmod -a`.
- **Blacklisting is "don't auto-load"**, not "you can't load it". `modprobe` still works manually — blacklisting only blocks udev / kernel hot-plug from pulling the module in.
- **Module parameters can be read at runtime** under `/sys/module/<name>/parameters/`. Some can be written there too (no reload needed).
- **Out-of-tree modules (NVIDIA, ZFS, VirtualBox) need DKMS** — see [Kernel Installation](#kernel-installation). Without DKMS they break on every kernel upgrade.

---

## Init

Notes on **init systems** — the userspace PID 1 that the kernel hands control to once the root filesystem is mounted. Linux has lived through three eras: **System V** (1983–2010s, scripts + runlevels), **Upstart** (2006–2014, event-driven, Ubuntu's interim choice), and **systemd** (2010 onward, dependency-driven units). All modern distros use systemd; the older two come up because legacy systems and embedded distros still ship them — and because the concepts (runlevels, services, dependencies) survived into systemd's vocabulary.

### One Shot Revision

| Topic                                       | Short Description                                                            |
| ------------------------------------------- | ---------------------------------------------------------------------------- |
| [System V Overview](#system-v-overview)     | The classic init — `/etc/inittab`, runlevels 0–6, `/etc/rc<N>.d/` symlinks   |
| [System V Service](#system-v-service)       | `/etc/init.d/<name>` scripts, `service`, `chkconfig` / `update-rc.d`         |
| [Upstart Overview](#upstart-overview)       | Event-driven init from Canonical (Ubuntu 6.10 → 14.10)                       |
| [Upstart Jobs](#upstart-jobs)               | `/etc/init/*.conf`, `start`, `stop`, `initctl`                               |
| [Systemd Overview](#systemd-overview)       | Modern init — units, targets, dependency-driven parallel boot                |
| [Systemd Goals](#systemd-goals)             | What systemd was built to fix — speed, dependencies, integration             |
| [Power States](#power-states)               | ACPI states S0–S5, suspend, hibernate, hybrid sleep                          |

### System V Overview

**Description:** **System V init** (often just **SysV init**) was the dominant init on Linux from the early 90s until ~2014. It's a small PID-1 binary plus a convention: `/etc/inittab` defines **runlevels** (numeric system states), and each runlevel has a directory of **symlinks to shell scripts** that get run on entry and exit. It's slow (everything is sequential), brittle (each script is independent shell, often hundreds of lines), and hard to express dependencies in — but it's also small, transparent, and easy to debug.

**The runlevels:**

| Runlevel | Meaning                                                                   |
| -------- | ------------------------------------------------------------------------- |
| 0        | Halt — shut the system down                                               |
| 1 / `S`  | Single-user / maintenance mode — root shell only, no networking            |
| 2        | Multi-user, no network (rarely used)                                      |
| 3        | Multi-user with networking, **no GUI** — the server default                |
| 4        | Unused / distro-specific                                                  |
| 5        | Multi-user with networking + **display manager** (GUI login)              |
| 6        | Reboot                                                                    |

**The on-disk layout:**

```
/etc/inittab          ← which runlevel is default, what to spawn on each TTY
/etc/init.d/          ← the actual service scripts (init scripts)
/etc/rc0.d/           ← symlinks → scripts to run when ENTERING runlevel 0
/etc/rc1.d/                                                          ... 1
/etc/rc2.d/                                                          ... 2
/etc/rc3.d/                                                          ... 3
/etc/rc4.d/                                                          ... 4
/etc/rc5.d/                                                          ... 5
/etc/rc6.d/                                                          ... 6

Naming convention in /etc/rcN.d/:
  S20networking    ← S = Start, runs in numeric order (lowest first)
  K30networking    ← K = Kill, runs on EXIT from the level
```

**Examples (on a SysV system):**

```bash
# What runlevel am I in? (works on systemd too, as a shim)
runlevel
# N 5            ← previous N (none, fresh boot), current 5

# What's the default runlevel?
grep ^id: /etc/inittab
# id:3:initdefault:        ← multi-user, no GUI

# Switch runlevel right now:
sudo telinit 3              # drop to multi-user, no GUI
sudo telinit 6              # reboot
sudo telinit 0              # halt

# What runs when entering runlevel 3?
ls /etc/rc3.d/
# S01sysstat  S20networking  S25rsyslog  S99ondemand  K10postgresql ...
```

**Notes:**

- **PID 1 is `/sbin/init`** on a SysV system; it reads `/etc/inittab` once at boot and then spawns `getty` on the configured TTYs forever.
- **Runlevels are linear, not a dependency graph.** That's why boot is sequential and slow — each script blocks the next.
- **The numeric prefix is everything.** `S20` runs before `S30` runs before `S99`. Want a service to start later? Rename the symlink.
- **Modern distros ship a SysV shim** — `service nginx start` still works on a systemd box because systemd recognizes `/etc/init.d/<name>` and wraps each as a unit. The shim is for compatibility; new services should ship a `.service` file.
- **Embedded Linux still uses SysV (or `BusyBox init`)** — fast enough on a single-CPU device, tiny binary, no D-Bus dependency.

### System V Service

**Description:** A **System V service** is just a **shell script** in `/etc/init.d/` that accepts `start`, `stop`, `restart`, `status`, and optionally `reload` as the first argument. PID 1 invokes these scripts when entering / leaving a runlevel; admins invoke them via the `service` command. Adding a service means dropping a script in `/etc/init.d/`, making it executable, and using `chkconfig` (RHEL) or `update-rc.d` (Debian) to symlink it into the right `/etc/rcN.d/` directories.

**Anatomy of an init script:**

```bash
#!/bin/sh
### BEGIN INIT INFO
# Provides:          myapp
# Required-Start:    $network $remote_fs
# Required-Stop:     $network $remote_fs
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: My example service
### END INIT INFO

DAEMON=/usr/local/bin/myapp
PIDFILE=/var/run/myapp.pid

case "$1" in
  start)   start-stop-daemon --start --background --pidfile $PIDFILE --exec $DAEMON ;;
  stop)    start-stop-daemon --stop  --pidfile $PIDFILE ;;
  restart) $0 stop; sleep 1; $0 start ;;
  status)  [ -e $PIDFILE ] && echo "running (PID $(cat $PIDFILE))" || echo "stopped" ;;
  *)       echo "Usage: $0 {start|stop|restart|status}"; exit 1 ;;
esac
```

**Daily commands:**

| Action                          | Debian/Ubuntu                          | RHEL/CentOS                              |
| ------------------------------- | -------------------------------------- | ---------------------------------------- |
| Start a service now             | `sudo service nginx start`             | same (or `/etc/init.d/nginx start`)     |
| Stop a service                  | `sudo service nginx stop`              | same                                     |
| Status                          | `sudo service nginx status`            | same                                     |
| Enable at boot                  | `sudo update-rc.d nginx defaults`      | `sudo chkconfig nginx on`                |
| Disable at boot                 | `sudo update-rc.d -f nginx remove`     | `sudo chkconfig nginx off`               |
| Show on/off per runlevel        | `ls /etc/rc?.d/ \| grep nginx`         | `chkconfig --list nginx`                 |

**Examples:**

```bash
# Status of every service the box knows about:
sudo service --status-all              # Debian/Ubuntu
sudo chkconfig --list                  # RHEL/CentOS

# Manually run an init script:
sudo /etc/init.d/nginx start

# Verify symlinks line up with what you expect:
ls -l /etc/rc{3,5}.d/ | grep nginx
# lrwxrwxrwx ... S91nginx -> ../init.d/nginx
# lrwxrwxrwx ... K09nginx -> ../init.d/nginx
```

**Notes:**

- **The `### BEGIN INIT INFO` block is mandatory on Debian**. `update-rc.d` and `insserv` use it to compute dependency-aware start order. Without it, your service may run too early or too late.
- **Init scripts run as root.** Drop privileges inside the script (`start-stop-daemon --chuid`) — don't run the daemon as root just because the script does.
- **`service <name>` works on systemd too** — it transparently calls `systemctl`. Useful for muscle memory and for scripts that need to work on both eras.
- **PID file management is the #1 source of init-script bugs**: stale PID files after a crash, daemons that don't write a PID file, race conditions when starting. Modern alternatives (systemd) read the PID from the cgroup, sidestepping the issue.
- **No parallelism.** Scripts in `/etc/rcN.d/` run **in order**, one at a time. A 30-second `S25database` script delays everything after it. This was systemd's #1 performance pitch.

### Upstart Overview

**Description:** **Upstart** is the init system **Canonical** built when they decided SysV was too slow and unflexible. It was Ubuntu's PID 1 from **6.10 (Edgy, 2006)** until **14.10 (Utopic, 2014)**, and shipped on RHEL 6 (alongside the older SysV scripts). Its key idea: instead of runlevels, **events**. When the kernel comes up, an event fires; when networking goes online, an event fires; when a service crashes, an event fires. Jobs declare which events they care about, and Upstart starts/stops them when the events happen.

**SysV vs Upstart vs systemd, in one row:**

| Era         | Model               | Granularity                | Notable Quirk                          |
| ----------- | ------------------- | -------------------------- | -------------------------------------- |
| SysV        | Runlevels + scripts | "Run all of these in order" | Sequential, hard to express deps      |
| **Upstart** | **Events**          | "Start when X happens"      | Event firehose, no formal dep graph    |
| systemd     | Dependencies + units | "Start once A, B, C are up" | Big binary, many subsystems, opinionated |

**Where you might still meet Upstart:**

- **Ubuntu 14.04 LTS** (server image, support ended April 2024 unless paid ESM)
- **RHEL 6** (support ended November 2020 unless paid ELS)
- Some appliances and routers stuck on older firmware
- Container base images frozen at older releases

**Examples — on a box running Upstart:**

```bash
# What's PID 1?
ps -p 1 -o comm
# init                     ← could be SysV or Upstart; check further:

# Is it Upstart? (presence of /etc/init/*.conf is a giveaway)
ls /etc/init/*.conf | head
# /etc/init/networking.conf
# /etc/init/rc.conf
# /etc/init/ssh.conf

initctl version
# init (upstart 1.12.1)

# Check status of a job:
sudo initctl status ssh
# ssh start/running, process 1234
```

**Notes:**

- **Upstart was the "Linux fast-boot" project before systemd ate its lunch.** Its event model worked, but each job stored its triggers independently — there was no single dependency graph you could ask "why didn't X start?".
- **Backward compatibility was a strength**: Upstart honored `/etc/init.d/` scripts via a SysV compatibility layer, so the migration was smooth.
- **Canonical retired Upstart with 15.04** because every other major distro had standardized on systemd; maintaining a separate init was costly with no upside.
- **You probably won't encounter Upstart on a greenfield install in 2026.** Knowing it exists matters only for legacy boxes and for understanding why some older docs use unfamiliar commands.

### Upstart Jobs

**Description:** An **Upstart job** is a small declarative file at `/etc/init/<name>.conf` describing **when** to start the job, **how** to start it, and **when** to stop it. Each `.conf` declares the events it reacts to (`start on`, `stop on`) and the command to run (`exec`). There's no compilation step — drop the file, run `initctl reload-configuration`, and Upstart knows about the new job.

**Anatomy of a job:**

```bash
# /etc/init/myapp.conf

description "My example application"

start on (filesystem and net-device-up IFACE!=lo)
stop  on runlevel [016]

respawn                    # restart if it crashes
respawn limit 10 5         # but give up if it crashes >10 times in 5s

env LOG_LEVEL=info
chdir /var/lib/myapp

exec /usr/local/bin/myapp --daemon=false   # run in foreground; Upstart manages backgrounding
```

**Commands:**

| Action                                  | Command                                  |
| --------------------------------------- | ---------------------------------------- |
| Start a job now                         | `sudo start myapp` / `sudo initctl start myapp` |
| Stop a job                              | `sudo stop myapp` / `sudo initctl stop myapp`   |
| Restart                                 | `sudo restart myapp`                     |
| Status                                  | `sudo status myapp`                      |
| All jobs                                | `initctl list`                           |
| Re-read all `.conf` files               | `sudo initctl reload-configuration`      |
| Emit a custom event                     | `sudo initctl emit my-event`             |

**Examples:**

```bash
# List every job, with state:
initctl list
# alsa-utils stop/waiting
# avahi-daemon start/running, process 612
# console-setup stop/waiting
# cron start/running, process 1107
# ...

# Show one job's status:
status ssh
# ssh start/running, process 1234

# Start a stopped job:
sudo start cron

# Stop a job:
sudo stop cron

# After editing /etc/init/<job>.conf:
sudo initctl reload-configuration       # re-read all jobs
sudo restart <job>                      # apply changes to the running instance

# Tail Upstart's own log:
sudo tail -f /var/log/upstart/*.log
```

**Notes:**

- **`exec` runs the command in the foreground**, and Upstart treats that process as "the service". If the binary daemonizes (forks into background), Upstart loses track — use `--foreground` flags or `expect fork` / `expect daemon` to tell Upstart what to expect.
- **`respawn` is the equivalent of systemd's `Restart=always`** — it makes Upstart restart the job if it exits. `respawn limit` prevents infinite-loop respawn storms.
- **Events are strings.** You can emit and react to anything: `start on my-custom-event`, then `initctl emit my-custom-event` to trigger.
- **No native enable/disable** — to disable a job, rename or remove its `.conf` file (or add `manual` as a stanza, which prevents auto-start while keeping the config).
- **`/var/log/upstart/<job>.log`** captures stdout/stderr per job, which is more granular than SysV's `/var/log/syslog`-only model.

### Systemd Overview

**Description:** **systemd** is the dominant Linux init system since the mid-2010s. PID 1 is `/lib/systemd/systemd`, and instead of scripts or events it manages **units** — declarative files describing services, sockets, mounts, timers, devices, and groupings called **targets**. Units have explicit **dependencies** (`Wants=`, `Requires=`, `After=`, `Before=`), which lets systemd compute a dependency graph at boot and **parallelize** anything that doesn't depend on something not-yet-running. The result: faster boot, predictable shutdown, integrated journaling, cgroup-based process tracking.

**The unit zoo:**

| Unit type     | Represents                                                          |
| ------------- | ------------------------------------------------------------------- |
| `.service`    | A long-running process or one-shot command                          |
| `.socket`     | A listening socket; systemd starts the matching `.service` on connect |
| `.mount`      | A mountpoint — auto-generated from `/etc/fstab`, can be hand-written |
| `.automount`  | Lazy automount — mounts the FS on first access                      |
| `.timer`      | A scheduled trigger (modern cron replacement)                       |
| `.target`     | A grouping — a "named state" of the system                          |
| `.path`       | A filesystem watch — fires when a path appears/changes              |
| `.slice`      | A cgroup hierarchy node for resource control                        |
| `.swap`       | A swap partition / file                                             |
| `.device`     | An auto-generated unit per device (from udev)                       |

**A minimal `.service` file:**

```ini
# /etc/systemd/system/myapp.service
[Unit]
Description=My example application
After=network.target

[Service]
ExecStart=/usr/local/bin/myapp --foreground
Restart=on-failure
User=myapp
WorkingDirectory=/var/lib/myapp

[Install]
WantedBy=multi-user.target
```

**Daily commands (already covered in [Boot Process: Init](#boot-process-init); here in summary):**

```bash
# Lifecycle:
sudo systemctl start | stop | restart | reload <unit>
sudo systemctl enable | disable <unit>
sudo systemctl enable --now <unit>     # enable AND start

# State:
systemctl status <unit>
systemctl is-active <unit>             # one-word: active / inactive / failed
systemctl is-enabled <unit>            # enabled / disabled / static
systemctl --failed                     # everything in a failed state

# Discovery:
systemctl list-units --type=service
systemctl list-unit-files              # all units, including disabled
systemctl list-dependencies <unit>
systemctl cat <unit>                   # show the full effective unit file (incl overrides)

# Editing:
sudo systemctl edit <unit>             # creates an override snippet
sudo systemctl daemon-reload           # re-read unit files after editing

# Logs (systemd's own logger):
journalctl -u <unit>                   # all logs for one unit
journalctl -u <unit> -f                # follow (tail -f)
journalctl -u <unit> --since "1 hour ago"
```

**Notes:**

- **systemd is more than init.** It bundles a logging daemon (journald), a login manager (logind), a network manager (networkd, on some distros), a time sync (timesyncd), a DNS resolver (resolved), and more. Whether that's "elegant integration" or "scope creep" depends who you ask.
- **Units are declarative.** No more "did the init script fork correctly?" — systemd tracks the service via its **cgroup**, so it always knows every descendant process, even ones the daemon forked off after start.
- **Drop-ins are the right way to customize**. `systemctl edit foo` creates `/etc/systemd/system/foo.service.d/override.conf` — your changes survive package upgrades because the original unit file is untouched.
- **Service hardening is one-line directives**: `PrivateTmp=yes`, `ProtectSystem=strict`, `NoNewPrivileges=yes`, `CapabilityBoundingSet=`, `ReadOnlyPaths=`, `MemoryMax=`. Use them — most distro services already do.
- **Logs are binary by default** (`/var/log/journal/`). Use `journalctl` to read them. If you want plain text, install / configure `rsyslog` alongside, or set `Storage=persistent` and pipe through `journalctl -o cat`.

### Systemd Goals

**Description:** systemd wasn't designed in a vacuum — it was a deliberate response to what SysV and Upstart did badly. Understanding the **design goals** explains why systemd looks the way it does (units, cgroups, the journal, the integrated subsystems) and why some choices are controversial.

**The goals, point by point:**

| Goal                        | What it means in practice                                                       |
| --------------------------- | ------------------------------------------------------------------------------- |
| **Fast boot via parallelism** | Compute a dep graph at startup, run independent units in parallel               |
| **Socket activation**       | Open sockets in PID 1, hand them to the service on first connect — services don't need to be "up" until used |
| **D-Bus activation**        | Start services lazily when something calls their D-Bus interface                |
| **Aggressive process tracking** | Every service lives in its own **cgroup** — systemd always knows every descendant, no "lost PID" ever |
| **Declarative units**       | No more shell-script idiosyncrasies; everything is an INI-style key/value file  |
| **Strong dependency model** | `After=`, `Before=`, `Wants=`, `Requires=`, `Conflicts=`, `BindsTo=`           |
| **Integrated logging**      | `journald` captures every unit's stdout/stderr, plus syslog, plus the kernel ring buffer |
| **On-demand mounts**        | `.automount` units mount on first access — boot doesn't wait for slow / network FSes |
| **Resource control**        | Per-unit `MemoryMax=`, `CPUQuota=`, `TasksMax=`, all via cgroups v2             |
| **Service hardening**       | One-line directives for sandboxing: namespaces, syscall filters, read-only paths |
| **Consistent shutdown**     | Same code path for orderly shutdown as for orderly startup, in reverse           |

**The cost (real, even if often worth it):**

- **Big binary, many subsystems.** Tight integration means harder to audit and replace piecewise.
- **D-Bus dependency.** systemd needs D-Bus for many features; embedded systems prefer something tinier (busybox-init, OpenRC, runit).
- **Distro lock-in to systemd-adjacent tools.** Once your scripts use `journalctl`, `systemd-tmpfiles`, `systemd-networkd` — switching back to "just files" requires effort.
- **Learning curve.** "What does `Wants=` vs `Requires=` actually mean?" is a real question; "how do I add a service?" used to be `cp` + `chmod`.

**Examples — features you can demo on any modern box:**

```bash
# Watch the dependency graph for a service:
systemctl list-dependencies sshd        # what sshd needs to be up first
systemctl list-dependencies --reverse sshd   # what depends on sshd

# Critical path through the boot — slowest sequential chain:
systemd-analyze critical-chain
# graphical.target @4.567s
# └─multi-user.target @4.566s
#   └─cron.service @4.430s +136ms
#     └─...

# Socket activation in action — define a service that doesn't run until used:
# /etc/systemd/system/echo.socket
# [Socket]
# ListenStream=12345
# Accept=yes
# [Install]
# WantedBy=sockets.target
# Then echo@.service handles each connection on demand

# Resource limits without touching cgroups by hand:
sudo systemctl set-property nginx.service MemoryMax=512M CPUQuota=50%
systemctl show nginx.service -p MemoryMax,CPUQuota
```

**Notes:**

- **The big efficiency win is parallelism, not raw speed.** Each unit isn't faster than its SysV equivalent — but ten of them running concurrently finish in ~1× the slowest's time, not Σ.
- **Socket activation is the most underused systemd feature** — services that take a second to start can sit "stopped" until first use, with zero perceived latency to clients.
- **cgroup-based tracking solved a 30-year-old bug**: SysV scripts could lose forked daemons and leave zombies / orphans. systemd just walks the cgroup.
- **Service hardening directives are essentially free security**. `ProtectSystem=strict` + `PrivateTmp=yes` + `NoNewPrivileges=yes` on every internet-facing service buys you defense-in-depth for zero perf cost.
- **The criticism is real, and the dominance is also real.** Every major distro defaults to systemd in 2026; the alternatives (OpenRC, runit, s6, dinit) are healthy niches but not mainstream.

### Power States

**Description:** Modern x86 hardware exposes a set of **ACPI power states** describing how much of the system is awake. Linux maps these to commands you actually use: `systemctl suspend` (S3, RAM is alive, everything else off), `systemctl hibernate` (S4, state written to swap, machine off), and `systemctl poweroff` (S5). Knowing the levels — and what each preserves — is what lets you pick the right one and debug "won't resume" issues.

**ACPI sleep states:**

| State | Name             | What's powered                             | Resume time            |
| ----- | ---------------- | ------------------------------------------ | ---------------------- |
| **S0** | Working          | Everything on                              | n/a                    |
| S1    | "Standby" (rare) | CPU stopped, RAM refreshed, devices on     | < 1 s                  |
| S2    | (rarely implemented) | CPU off, RAM on                       | < 2 s                  |
| **S3** | **Suspend to RAM** | Only RAM is powered                      | ~1–3 s                 |
| **S4** | **Suspend to Disk** (hibernate) | Nothing powered; RAM saved to swap | ~10–30 s (boot-ish)  |
| **S5** | Soft off (poweroff) | Nothing powered, no state saved         | full cold boot         |

**The systemctl verbs:**

| Command                          | ACPI state | What it does                                              |
| -------------------------------- | ---------- | --------------------------------------------------------- |
| `systemctl suspend`              | S3         | RAM stays powered; tiny battery draw                      |
| `systemctl hibernate`            | S4         | Writes RAM to swap, powers off — needs swap ≥ RAM size    |
| `systemctl hybrid-sleep`         | S3 + S4    | Suspend to RAM, **also** write RAM to swap as insurance   |
| `systemctl suspend-then-hibernate` | S3 then S4 | Suspend now; if still suspended after a timeout, hibernate |
| `systemctl poweroff`             | S5         | Clean shutdown, machine off                               |
| `systemctl reboot`               | —          | Clean shutdown, then warm boot                            |
| `systemctl halt`                 | —          | Stop the OS, leave the hardware powered (rarely useful)   |

**Examples:**

```bash
# What sleep states does this hardware claim to support?
cat /sys/power/state
# freeze mem disk            ← freeze (S0ix), mem (S3), disk (S4)

# What's the deeper menu?
cat /sys/power/mem_sleep
# [s2idle] deep              ← bracketed one is the default

# Suspend right now:
sudo systemctl suspend

# Hibernate (needs swap ≥ RAM):
sudo systemctl hibernate

# Check that resume is configured (for hibernate):
cat /sys/power/resume                # should point to your swap device

# When did the last suspend/resume happen?
journalctl -b | grep -iE "suspend|resume" | tail

# Trigger a power button event from the CLI (acpid translates it):
sudo acpi_listen                     # in another terminal — watch events flow

# Schedule wakeup after N seconds (rtcwake):
sudo rtcwake -m mem -s 60            # suspend to RAM, wake in 60 s
```

**Notes:**

- **Hibernate needs swap at least the size of RAM** (give or take compression) — that's where the RAM image is written. No swap, no hibernate.
- **"Modern Standby" / S0ix** is Intel's newer connected-standby state — the machine looks off but tiny tasks (mail check, OTA updates) can run. Linux support is mixed; older S3 is more battery-friendly when it works.
- **The #1 "won't resume" cause is a buggy GPU or NIC driver.** Check `journalctl -b -1 | tail` after a failed resume — the last lines before the freeze usually finger the driver.
- **`rtcwake` is invaluable for testing.** Set a 60-second wakeup before suspending so you don't have to physically poke the box if it dies.
- **`logind.conf` controls what the laptop does on lid close / power button / docking**: `/etc/systemd/logind.conf`, options `HandleLidSwitch=`, `HandlePowerKey=`. Default for lid-close is `suspend`; servers often want `ignore`.
- **`shutdown -h now` / `shutdown -r now` / `init 0` / `init 6` all still work** — they're shims that call `systemctl poweroff` / `systemctl reboot`.

---

## Process Utilization

Notes on **measuring what a Linux box is actually doing** — which processes are running hot, which ones are stuck on disk, who's eating the memory, what's chewing CPU at 3 AM. This section covers the daily-driver tools (`top`, `lsof`, `fuser`), the deeper monitors (`mpstat`, `iostat`, `vmstat`, `pidstat`, `sar`), and the **scheduled-job** side of "process utilization" (cron, systemd timers). The pattern is always: get a top-down view first (`top` / `htop`), then drill into one process or subsystem with a specialized tool.

### One Shot Revision

| Topic                                                    | Short Description                                                        |
| -------------------------------------------------------- | ------------------------------------------------------------------------ |
| [Tracking processes: top](#tracking-processes-top)       | `top` / `htop` — live snapshot of CPU, memory, the busiest processes     |
| [lsof and fuser](#lsof-and-fuser)                        | Who has this file / port / mount open?                                   |
| [Process Threads](#process-threads)                      | Processes vs threads, `ps -L`, `/proc/<pid>/task/`                       |
| [CPU Monitoring](#cpu-monitoring)                        | `uptime`, `mpstat`, `pidstat`, load average vs CPU%                      |
| [I/O Monitoring](#io-monitoring)                         | `iostat`, `iotop`, `pidstat -d`, `%iowait` vs queue depth                |
| [Memory Monitoring](#memory-monitoring)                  | `free`, `vmstat`, `/proc/meminfo`, RSS vs VSZ, swap pressure             |
| [Continuous Monitoring](#continuous-monitoring)          | `watch`, `sar`, `atop`, `glances`, Prometheus node_exporter              |
| [Cron Jobs](#cron-jobs)                                  | `crontab -e`, `/etc/cron.*/`, systemd `.timer` units                     |

### Tracking processes: top

**Description:** **`top`** is the classic interactive process monitor — it updates every few seconds, showing CPU usage, memory, load average, and a sortable list of processes. Every Unix has it; many people start with the friendlier **`htop`** instead. Both answer the same question: *what is this box doing right now?* The headers tell you the **aggregate** state (load, CPU, memory); the table tells you which **processes** account for it.

**Reading `top`'s header:**

```
top - 10:42:31 up  5:12,  3 users,  load average: 0.32, 0.41, 0.55
Tasks: 247 total,   1 running, 246 sleeping,   0 stopped,   0 zombie
%Cpu(s):  6.1 us,  2.3 sy,  0.0 ni, 91.4 id,  0.2 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  15824.6 total,   8104.2 free,   4210.1 used,   3510.3 buff/cache
MiB Swap:   4096.0 total,   4096.0 free,      0.0 used.  11000.5 avail Mem
```

- **load average** `0.32 0.41 0.55` — 1 / 5 / 15-minute averages. Compare to `nproc` (CPU count): if load is consistently > `nproc`, you're CPU-saturated.
- **%Cpu(s)**: `us` = user-mode, `sy` = system (kernel), `ni` = niced procs, `id` = idle, `wa` = waiting on I/O, `hi/si` = hardware/software IRQs, `st` = stolen by hypervisor (look at this on a VM).
- **MiB Mem / Swap**: `used` is real demand; `buff/cache` is reclaimable. `avail` is the realistic "how much can a new process grab without swapping" number.

**Interactive hotkeys (`top`):**

| Key       | What it does                                            |
| --------- | ------------------------------------------------------- |
| `P`       | Sort by `%CPU`                                          |
| `M`       | Sort by `%MEM`                                          |
| `T`       | Sort by total CPU time                                  |
| `c`       | Toggle full command line                                |
| `1`       | Per-CPU breakdown instead of aggregate                  |
| `u`       | Filter by user                                          |
| `k`       | Send a signal (kill) to a PID                           |
| `r`       | Renice a PID                                            |
| `H`       | Show threads instead of processes                       |
| `W`       | Save current layout to `~/.toprc`                       |
| `q`       | Quit                                                    |

**Examples:**

```bash
# Run top once and exit (batch mode — perfect for scripts):
top -b -n 1 | head -20

# Watch one process only:
top -p $(pidof nginx)

# Sort by memory immediately:
top -o %MEM

# htop — friendlier, same job:
htop                                # arrow keys, F-keys, tree view (F5)

# A one-line snapshot — load + top 5 CPU processes:
uptime; ps -eo pid,user,%cpu,%mem,comm --sort=-%cpu | head -6
```

**Notes:**

- **Load average is NOT CPU%.** Load includes processes blocked on I/O. A box with load 8 but %CPU idle 70% is **I/O-bound**, not CPU-bound. Check `wa` and `iostat`.
- **`%CPU` per process can exceed 100%** — it's per-core. A multi-threaded process pegging 4 cores shows `400%`. Press `1` in `top` for the per-core breakdown.
- **`st` (steal time) on a VM is the hypervisor stealing your CPU** to give to other tenants. If `st` is consistently > 5%, the host is oversubscribed.
- **`htop` is worth installing.** Tree view (F5), incremental search (F3), kill (F9) with signal picker, tagging multiple processes — all friendlier than `top`'s key mnemonics.
- **For long-running observation, `top -b` (batch)** is what you want — pipe into a file, grep for outliers later.

### lsof and fuser

**Description:** Two tools answer "**who's using this thing?**". **`lsof`** ("**l**i**s**t **o**pen **f**iles") lists every open file descriptor on the system: regular files, directories, network sockets, devices, pipes — everything. **`fuser`** is the smaller, faster tool that just answers "which PID(s) have this file/port/mount open?". Both are essential for unsticking "umount: busy", finding port collisions, and tracking down which process is holding a deleted file's space.

**`lsof` cheat sheet:**

| Command                    | What it shows                                                        |
| -------------------------- | -------------------------------------------------------------------- |
| `lsof -p <pid>`            | Every FD a process has open                                          |
| `lsof <path>`              | Every process with `<path>` open                                     |
| `lsof +D <dir>`            | Every process with **anything inside** `<dir>` open                  |
| `lsof -i`                  | All network sockets (TCP + UDP)                                      |
| `lsof -i :22`              | Who's listening on port 22? (or has a connection on it)              |
| `lsof -i tcp:80`           | Same but TCP only                                                    |
| `lsof -u <user>`           | All FDs owned by a user                                              |
| `lsof -c <name>`           | All FDs for processes whose command starts with `<name>`             |
| `lsof +L1`                 | **Deleted but still open** files (the classic "df full, du clean")   |

**Examples:**

```bash
# What's using port 80?
sudo lsof -i :80
# COMMAND  PID  USER  FD   TYPE   ...  NAME
# nginx    1234 root  6u   IPv4   ...  *:http (LISTEN)

# Every open file under /var/log/nginx (good for "what's locked"):
sudo lsof +D /var/log/nginx

# Why can't I umount /mnt/data?
sudo lsof +D /mnt/data            # find the holders
# Or:
sudo fuser -vm /mnt/data
#                      USER        PID ACCESS COMMAND
# /mnt/data:           tarek      4567 ..c..  bash
#                                ↑ "c" = working directory; cd out and umount again

# Deleted-but-open log file holding 4 GB:
sudo lsof +L1 | grep '(deleted)'
# nginx 1234 root 9w REG 8,2 4294967296 0 12345 /var/log/nginx/access.log (deleted)
# → restart nginx (or send SIGUSR1 if it supports log reopen) to free the space

# Every TCP connection a process has open:
lsof -p $(pidof sshd) -i tcp
```

**`fuser` quick reference:**

```bash
# Who has /var open?
sudo fuser -vm /var
# (verbose, mount-aware)

# Who's listening on port 80?
sudo fuser 80/tcp -v

# Kill everything using a port (rough — use only when sure):
sudo fuser -k 8080/tcp           # sends SIGKILL to every PID

# Wait until a file is no longer in use, then proceed:
sudo fuser -s /var/lock/mylock || echo "lock is free"
```

**Notes:**

- **`lsof` requires root for the full picture.** Without it you only see your own processes' FDs. Most admin workflows need `sudo`.
- **Output is large** — pipe through `grep`, `wc -l`, or use `-i` / `+D` filters from the start.
- **A "**deleted**" annotation in `lsof` output** is gold: it means a process is holding bytes the filesystem can no longer reach via path. Restart the process or close the FD to free the space.
- **`fuser -k` is the "evict everyone" hammer.** Use it when you absolutely need to free a mount/port — but it sends SIGKILL by default. Add `-HUP` or `-TERM` to be gentler.
- **`ss -lntp` is a faster `lsof -i`** for "what's listening" — it reads `/proc/net/tcp` directly instead of walking every process. See the Networking section.

### Process Threads

**Description:** A **thread** is a unit of execution that shares the address space (memory) with other threads in the same process. From the kernel's perspective, threads and processes are nearly the same thing — both are scheduled entities created by **`clone(2)`** with different flag combinations. A process is a thread with its own memory; threads inside a process share memory. Every Linux process has at least one thread (itself); multi-threaded apps (databases, browsers, JVMs) have many.

**The kernel's view:**

```
Process              ← collection of threads sharing memory + open FDs
   ├── Thread 1 (TID = PID, the "main" thread)
   ├── Thread 2 (TID 6789)
   ├── Thread 3 (TID 6790)
   └── ...

Each thread has its own:
  - register state (PC, SP, ...)
  - stack
  - TID (thread ID, exposed by gettid())

Each thread shares with siblings:
  - address space (heap, code, mmap'd regions)
  - open file descriptors
  - signal handlers (mostly)
  - the PID (the "tgid" — thread group ID)
```

**Examples:**

```bash
# How many threads does this process have?
ps -o nlwp -p $(pidof firefox)
# 78

# List every thread of a process (one row per thread):
ps -L -p $(pidof firefox) | head
#  PID    LWP TTY          TIME CMD
# 4567   4567 ?        00:00:12 firefox
# 4567   4568 ?        00:00:00 gmain
# 4567   4569 ?        00:00:00 gdbus
# 4567   4570 ?        00:00:00 JS Helper
# ...
#                      ↑ LWP = light-weight process = TID

# Thread view in top: press 'H'
top -H -p $(pidof java)

# Or htop with tree-mode (F5) shows threads as children

# /proc shows each thread:
ls /proc/$(pidof java)/task/
# 4567  4568  4569  4570 ...        ← one dir per TID

# What's each thread doing? (the per-thread status):
cat /proc/$(pidof java)/task/4568/status | head
# Name:   GC Thread#0
# State:  S (sleeping)
# Tgid:   4567                       ← thread group ID = process PID
# Pid:    4568                       ← this thread's TID

# What syscalls is one thread making?
sudo strace -p 4568
```

**Notes:**

- **In Linux, a thread is `clone()` with shared address space.** The `pthread_create` library call wraps that. There's no special "thread object" in the kernel.
- **TID = PID for the main thread**; subsequent threads have their own TIDs but the same TGID (process ID). `getpid()` returns the TGID; `gettid()` returns the TID.
- **`ps` shows processes by default**, not threads. Add `-L` (or `-T`) for one row per thread. `top` defaults to processes; press **`H`** to toggle thread view.
- **Each thread has its own stack** (typically 8 MB virtual, growing on demand). 1000 threads ≈ 8 GB of virtual memory just for stacks — tune `ulimit -s` for highly threaded apps.
- **"This process is 1200% CPU"** on a multi-core box is one process with twelve busy threads. Per-thread `top -H` shows which one is hot.
- **CPU affinity is per-thread.** `taskset -p <mask> <pid>` sets the whole process; `taskset -p <mask> <tid>` pins one thread.

### CPU Monitoring

**Description:** "CPU is the bottleneck" gets thrown around for a lot of different problems. The right tool depends on whether you mean: (a) the system is **using** all its CPU, (b) processes are **waiting** for CPU, or (c) one specific process / thread is hot. Quick stack: **`uptime`** for load, **`mpstat`** for per-CPU breakdown, **`pidstat`** for per-process CPU over time, **`top` / `htop`** for live.

**The toolkit:**

| Tool             | Question it answers                                                  |
| ---------------- | -------------------------------------------------------------------- |
| `uptime`         | What's the 1/5/15-minute load average?                               |
| `nproc`          | How many CPU cores do I have? (compare to load)                      |
| `top` / `htop`   | What processes are using CPU right now?                              |
| `mpstat`         | What's the per-core utilization? (from `sysstat` pkg)                |
| `mpstat -P ALL 1` | Per-core, refreshing every second                                   |
| `pidstat`        | Per-process CPU over time (from `sysstat`)                          |
| `pidstat 1 5`    | Refresh every 1 s for 5 samples                                      |
| `sar -u`         | Historical CPU stats (cron-collected; see [Continuous Monitoring](#continuous-monitoring)) |
| `vmstat`         | One-line system summary including CPU, memory, I/O                   |
| `perf top`       | Per-function CPU profile (kernel + userspace)                        |

**Examples:**

```bash
# How loaded is the box?
uptime
# 10:42:31 up  5:12,  3 users,  load average: 4.32, 2.11, 1.05
nproc
# 8
# load 4.32 on 8 cores = ~54% utilized; load 12 on 8 = oversubscribed

# Per-core breakdown:
mpstat -P ALL 1 3
# CPU    %usr   %nice    %sys %iowait    %irq   %soft  %steal   %idle
# all   12.50    0.00    3.20    1.10    0.00    0.20    0.00   82.00
#   0   24.00    0.00    5.00    0.00    0.00    0.50    0.00   70.50    ← CPU 0 is hot
#   1   11.00    0.00    3.10    0.00    0.00    0.10    0.00   85.80
#   ...

# Who is eating CPU, sampled every second?
pidstat 1 5
# Time   UID    PID    %usr  %system  %guest  %CPU  CPU  Command
# ...    1000   4567   95.0    3.0     0.0    98.0    0  python   ← culprit

# Top 10 CPU users right now:
ps -eo pid,user,%cpu,comm --sort=-%cpu | head -11

# Quick "what's the system doing" line (refresh every 2s):
vmstat 2 5
# r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
# 2  0      0  504552  78212 8910040   0    0     8    20  500  900 12  3 84  1  0
#    ↑ r = runnable threads; if r > nproc consistently, CPU bottleneck

# Where is the kernel spending CPU? (root, perf must be installed):
sudo perf top
```

**Notes:**

- **Load is *runnable + uninterruptible*, not just CPU%.** A box stuck in I/O has high load with low CPU%. Always pair `uptime` with `mpstat` / `vmstat`.
- **load / nproc ≈ saturation.** Less than 1 = headroom; ~1 = saturated but not queueing; > 1 = work piling up.
- **`%steal` on a VM** is your hypervisor stealing CPU. Persistent > 5% means the host is oversubscribed; talk to your provider or pick a different instance.
- **`%iowait` is not "wasted CPU"** — it's "this CPU was idle, *but* there was at least one process waiting on I/O." High `wa` plus low `us`+`sy` means you're disk-bound, not CPU-bound.
- **`pidstat 1` is what you reach for** when you need to know who's hot and *also* see them in context (their syscalls, child processes, etc.) — combine with `pidstat -d` for I/O and `pidstat -r` for memory.
- **`perf top` is the deep-dive tool** — function-level CPU usage including kernel symbols. Needs `linux-tools-common` (Debian) or `perf` (RHEL).

### I/O Monitoring

**Description:** I/O bottlenecks look like "the box feels slow" without obvious CPU pressure. The diagnosis stack: **`vmstat`** / **`mpstat`** to confirm `%iowait` is high, **`iostat`** to see per-disk activity, **`iotop`** to see per-process I/O, **`pidstat -d`** for non-interactive per-process I/O over time. The two numbers that matter most: **utilization** (% of time the disk was busy) and **await** (average wait time per I/O).

**The toolkit:**

| Tool                | What it shows                                                       |
| ------------------- | ------------------------------------------------------------------- |
| `iostat -xz 1`      | Per-disk extended stats, refreshing every second                    |
| `iotop`             | Like `top`, but for I/O (per-process read/write rates) — needs root |
| `pidstat -d 1`      | Per-process I/O, in tabular form                                    |
| `vmstat 1`          | System-wide; `bi`/`bo` = blocks in/out, `wa` = %iowait              |
| `dstat -d --top-io` | All-in-one dashboard (deprecated upstream but still useful)         |
| `biolatency` (bcc)  | I/O latency histogram from eBPF — modern, precise                   |
| `iostat -p`         | Per-partition (not just per-disk) breakdown                         |

**Reading `iostat -xz 1`:**

```
Device     r/s     w/s     rkB/s    wkB/s    rrqm/s wrqm/s  %rrqm  %wrqm  r_await w_await aqu-sz %util
sda       45.0    12.0    1800.0    480.0      2.0    1.0    4.2    7.7      0.6    0.8     0.05  4.50
nvme0n1  120.0   850.0   12000.0  102000.0    10.0    5.0    7.7    0.6      0.3    0.4     1.20 89.20
                                                                                                    ↑
                                                                                            nvme0n1 is BUSY
```

| Column   | Meaning                                                              |
| -------- | -------------------------------------------------------------------- |
| `r/s`, `w/s` | I/O operations per second (read, write)                          |
| `rkB/s`, `wkB/s` | Throughput in KiB/s                                          |
| `r_await`, `w_await` | Average wait per I/O in ms (including queue + service)  |
| `aqu-sz` | Average outstanding I/O queue depth                                  |
| `%util`  | Percent of time the device had I/O in flight                         |

**Examples:**

```bash
# Live per-disk view:
iostat -xz 1

# Who is generating that I/O?
sudo iotop -o                          # -o = only processes actively doing I/O

# Same idea, scriptable:
sudo pidstat -d 1
# Time      UID  PID  kB_rd/s  kB_wr/s  kB_ccwr/s iodelay Command
# ...     1000  2345     0.00 12340.00       0.00     12 mysqld

# Where is the time going — kernel-level latency histogram (needs bcc-tools):
sudo biolatency-bpfcc 5 1
#       msecs        : count     distribution
#         0 -> 1     : 1234     |***********************************
#         2 -> 3     : 567      |***********
#         4 -> 7     : 89       |**
#         8 -> 15    : 12       |
#        16 -> 31    : 3        |

# One-shot system summary (CPU/IO/memory):
vmstat 1 5
```

**Notes:**

- **`%util = 100%` doesn't always mean "saturated"** for modern SSDs and arrays — they handle parallel queues. **`aqu-sz`** and `await` are better saturation signals.
- **`await` is queue + service time.** If `await` is 20 ms and `svctm` (older `iostat` versions) is 2 ms, the disk is fast but queueing — too many concurrent requests, not slow hardware.
- **For SSDs, latency matters more than throughput**. A spinning disk at 500 IOPS is busy; an NVMe at 50 000 IOPS may still be loafing. Always cross-check `iotop` with workload context.
- **`iotop` requires CAP_NET_ADMIN / root** to read per-process I/O stats — they live in `/proc/<pid>/io` and aren't world-readable.
- **`pidstat -d` is the headless `iotop`.** Use it in scripts and over SSH where you don't want a curses UI.
- **eBPF-based tools (`biolatency`, `biosnoop`, `ext4slower`) are the modern stack** for deep I/O analysis. They sample at the kernel layer instead of polling `/proc`, so they catch microsecond-scale latency spikes.

### Memory Monitoring

**Description:** Linux memory accounting is famously confusing. The TL;DR: **`buff/cache` is reclaimable**, so "used memory" in `free` isn't what your processes have committed — it's the kernel using free RAM for disk caches (which speeds everything up and gets evicted on demand). The number to watch is **`available`**, not `free`. Per-process: **RSS** (resident set size, real RAM) is what matters, not VSZ (virtual size, can be huge and meaningless).

**The toolkit:**

| Tool                | What it answers                                                       |
| ------------------- | --------------------------------------------------------------------- |
| `free -h`           | Total / used / free / available, in human units                       |
| `cat /proc/meminfo` | Every detail the kernel exposes                                       |
| `vmstat 1`          | System-wide memory + swap + I/O + CPU in one line                     |
| `ps aux --sort=-rss \| head` | Top memory hogs                                              |
| `pidstat -r 1`      | Per-process memory over time                                          |
| `smem`              | "Real" memory per process (PSS — proportional set size)               |
| `slabtop`           | Kernel slab allocator stats                                           |
| `pmap <pid>`        | Memory map of a process (every mapping, size, RSS)                    |

**Reading `free -h`:**

```
               total        used        free      shared  buff/cache   available
Mem:            15Gi       4.1Gi       8.0Gi       450Mi       3.4Gi        11Gi
Swap:          4.0Gi          0B       4.0Gi
                                                                              ↑
                                                                  the number that matters
```

- `total` — installed RAM
- `used` — kernel + processes (not counting cache)
- `free` — completely unused (often small, that's fine)
- `buff/cache` — disk caches; reclaimable on demand
- **`available`** — realistic "how much can a new process use without swapping" estimate

**Per-process memory:**

| Field | Meaning                                                            |
| ----- | ------------------------------------------------------------------ |
| VSZ   | Virtual size (everything mapped, including not-yet-touched mmaps)  |
| RSS   | Resident set size — real RAM pages                                 |
| PSS   | Proportional set size — shared pages divided by # of users (smem)  |
| USS   | Unique set size — only pages not shared with anyone                |

**Examples:**

```bash
# Quick snapshot:
free -h
free -m -s 2          # refresh every 2 seconds, in MiB

# Detailed:
grep -E 'MemTotal|MemAvailable|Cached|SwapTotal|SwapFree|Dirty|Writeback' /proc/meminfo

# Top 5 memory users by RSS:
ps -eo pid,user,rss,vsz,comm --sort=-rss | head -6
# PID  USER  RSS     VSZ      COMMAND
# 4567 user  812340  4523412  firefox
# 2345 mysql 460100  1244888  mysqld
# ...

# Per-process memory over time:
pidstat -r 1 5
# Time   UID    PID  minflt/s  majflt/s     VSZ      RSS  %MEM   Command
# ...    1000  4567     50.0       0.2  4523412   812340   5.0   firefox

# "Real" memory (PSS) — what each process actually costs:
sudo smem -tk
# (shows USS, PSS, RSS per process and per-user totals)

# Memory map of a process (every mapping, with sizes):
sudo pmap -X $(pidof nginx) | head

# Swap pressure — is the kernel swapping under load?
vmstat 1 5
# si  so   bi    bo   in   cs us sy id wa st
#  0   0   12    24  500  900 10  2 88  0  0
# ↑ si = swap-in, so = swap-out. Anything sustained > 0 = swapping under pressure.
```

**Notes:**

- **`buff/cache` shrinks automatically when processes need memory.** A box showing "used: 15 GB of 16 GB" but `available: 8 GB` is fine — most of "used" is reclaimable cache.
- **VSZ is meaningless for "how much RAM is this using"**. A program can `mmap` a 100 GB file and have VSZ 100 GB while using 4 KB of RSS. Always look at RSS or PSS.
- **OOM-killer** kicks in when the kernel truly runs out of memory. It picks a process to kill based on a heuristic (`oom_score`). Check `dmesg | grep -i oom` after a mysterious process death.
- **`smem -tk` is the right tool for "where did the memory really go"** — shared libraries get double-counted by RSS-based tools, PSS fixes that.
- **Swap *being used* isn't a problem; swap *churn* is.** `vmstat`'s `si`/`so` columns sustained > 0 indicate the kernel is paging actively — that's the real symptom.
- **`echo 3 > /proc/sys/vm/drop_caches`** force-flushes caches (root only). Useful for benchmarks; never useful in production — the kernel manages caches better than you do.

### Continuous Monitoring

**Description:** Snapshot tools (`top`, `iostat`) show you "now". **Continuous monitoring** is "what was happening at 3 AM last Tuesday?" — historical data, trends, alerts. The classic Linux answer is **`sar`** (System Activity Reporter, from the `sysstat` package) which polls every 10 minutes and keeps weeks of history. Live alternatives: **`watch`** wraps any command in a refreshing loop; **`atop`** / **`glances`** are full dashboards. For production, **Prometheus + Grafana** with **node_exporter** is the industry standard.

**The hierarchy:**

```
Now:           top, htop, iostat, vmstat, free
Continuous live: watch <cmd>, atop, glances
Historical:    sar (sysstat, 7-day default), atop (logs to /var/log/atop/)
Production:    Prometheus + node_exporter → Grafana, or Datadog / NewRelic / Zabbix
```

**Examples:**

```bash
# Repeat any command every 2 seconds:
watch -n 2 'df -h /var; echo; free -h'
watch -d 'ss -lntp'            # -d highlights what changed

# `sar` (install sysstat first):
sudo apt install sysstat
sudo systemctl enable --now sysstat
# Now stats are collected every 10 minutes into /var/log/sysstat/

# CPU history for today:
sar -u
# 09:00:01  CPU   %user   %nice  %system %iowait  %steal   %idle
# 09:10:01  all     5.2     0.0      2.1     0.5     0.0    92.2
# 09:20:01  all     6.0     0.0      2.4     0.4     0.0    91.2
# ...

# Yesterday's stats:
sar -u -f /var/log/sysstat/sa$(date -d yesterday +%d)

# I/O history:
sar -d -p              # per-device, friendly names

# Memory:
sar -r                 # mem stats
sar -B                 # paging stats

# Network:
sar -n DEV             # per-interface traffic

# atop — live dashboard with built-in log:
sudo atop              # current
sudo atop -r /var/log/atop/atop_$(date +%Y%m%d)   # replay today's log

# glances — friendly, all-in-one, web-server mode optional:
glances
glances -w             # serves a web UI on :61208
```

**For production monitoring (one-liner orientation):**

```bash
# Install Prometheus node_exporter (collects ~1000 metrics):
sudo apt install prometheus-node-exporter        # Debian/Ubuntu
# Pull /metrics from another machine:
curl http://node.local:9100/metrics | head
# Then point Prometheus at it, and Grafana at Prometheus.
```

**Notes:**

- **`sar` is the "go back in time" tool.** When ops asks "what was the box doing at 3 AM?", `sar -u -f /var/log/sysstat/saNN` (NN = day of month) is the answer.
- **`sysstat` retention defaults to 7 days** on Debian/Ubuntu — bump it via `/etc/sysstat/sysstat` (`HISTORY=28` for 4 weeks). RHEL keeps a month by default.
- **`atop`'s killer feature is full-process history** — `top` shows now; `atop -r` lets you scroll backwards through past 10-second slices, seeing which processes were alive at any given moment, even if they've since exited.
- **`watch -d` highlights changes between refreshes.** Great for spotting which counter jumped (`watch -d -n 1 'cat /proc/net/dev'`).
- **Prometheus + node_exporter is the modern default for fleet monitoring.** node_exporter exposes hundreds of metrics on `:9100/metrics`; Prometheus scrapes it on an interval and Grafana renders dashboards.

### Cron Jobs

**Description:** **cron** is the original Unix scheduler — a daemon that reads tables of "run this command at this time" and forks the commands at the right minute. Every distro has it. The modern alternative is **systemd `.timer` units**, which integrate with the rest of systemd (journal logs, dependencies, randomized delays). For most tasks, cron is still the right tool; for boot-aware, dependency-aware, or per-user-service tasks, systemd timers are cleaner.

**Where cron jobs live:**

| Location                  | Who owns it       | Format                                                  |
| ------------------------- | ----------------- | ------------------------------------------------------- |
| `crontab -e` (per-user)   | The current user  | 5-field schedule + command                              |
| `/etc/crontab`            | root              | 5-field + **user** + command                            |
| `/etc/cron.d/<name>`      | root              | Same as `/etc/crontab` — drop-in files                  |
| `/etc/cron.{hourly,daily,weekly,monthly}/` | root | Just executables — cron runs everything in the dir      |
| `/var/spool/cron/<user>`  | root (managed via `crontab -e`) | The actual file edited by `crontab -e`       |

**The crontab time fields:**

```
*       *       *       *       *       command
│       │       │       │       │
│       │       │       │       └─── day of week (0–7; 0 and 7 = Sunday)
│       │       │       └─────────── month (1–12)
│       │       └─────────────────── day of month (1–31)
│       └─────────────────────────── hour (0–23)
└─────────────────────────────────── minute (0–59)

Shortcuts: @reboot, @hourly, @daily, @weekly, @monthly, @yearly
Step: */5 in the minute field = every 5 minutes
Ranges/lists: 1-5, 1,15,30
```

**Examples:**

```bash
# Edit MY crontab:
crontab -e
# Add a line:
# 0 3 * * * /usr/local/bin/backup.sh

# List MY crontab:
crontab -l

# List someone else's (root only):
sudo crontab -l -u alice

# A system-wide cron job (note the extra USER field!):
echo '*/15 * * * * root /usr/local/bin/healthcheck.sh' | sudo tee /etc/cron.d/healthcheck

# Drop a daily script (no schedule — runs daily by cron.daily's schedule):
sudo cp myreport.sh /etc/cron.daily/myreport
sudo chmod +x /etc/cron.daily/myreport

# Common patterns:
# Every minute:            * * * * *
# Every 5 minutes:         */5 * * * *
# At 02:30 every day:      30 2 * * *
# At 02:30 on Sundays:     30 2 * * 0
# 1st of each month:       0 0 1 * *
# After reboot:            @reboot

# Logs (Debian/Ubuntu — cron logs go to /var/log/syslog):
sudo grep CRON /var/log/syslog | tail
# On systemd-only distros:
journalctl -u cron -n 50

# Avoid silently dropping output — always redirect:
# 0 3 * * * /usr/local/bin/backup.sh >> /var/log/backup.log 2>&1
```

**systemd timers (the modern equivalent):**

```ini
# /etc/systemd/system/backup.timer
[Unit]
Description=Daily backup

[Timer]
OnCalendar=*-*-* 03:00:00
RandomizedDelaySec=10m         # spread load across machines
Persistent=true                # run on next boot if missed

[Install]
WantedBy=timers.target
```

```ini
# /etc/systemd/system/backup.service
[Unit]
Description=Daily backup

[Service]
Type=oneshot
ExecStart=/usr/local/bin/backup.sh
User=backup
```

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now backup.timer

# List all timers and when they fire next:
systemctl list-timers
```

**Notes:**

- **cron's environment is tiny.** No `$PATH` beyond `/usr/bin:/bin`, no shell aliases, no `.bashrc`. Always **use absolute paths** in cron commands, or `cd` first and set `PATH=` at the top of the crontab.
- **Redirect output** (`>> /var/log/mycron.log 2>&1`) — by default cron emails the user any output, which often goes nowhere on a server (no MTA). Silent failures are the #1 cron pitfall.
- **`/etc/crontab` and `/etc/cron.d/` have an extra USER field**; per-user crontabs (`crontab -e`) don't. Mixing them up means your job runs as the wrong user.
- **`@reboot` runs once per boot** — handy for "start this thing at boot" if you don't want a systemd unit. But it runs early; if your job needs networking, prefer a systemd unit with `After=network-online.target`.
- **systemd timers are better for**: failure handling (`OnFailure=`), randomized delays (`RandomizedDelaySec`), boot-catch-up (`Persistent=yes`), and per-user services (`systemctl --user enable foo.timer`).
- **`anacron` runs jobs that were *missed* while the box was off** (laptops). Cron only fires while the daemon is running; anacron catches up after.

---

## Logging

Notes on **what gets logged, by whom, and where to find it**. Linux has two parallel logging stacks: the **traditional syslog** stack (rsyslog or syslog-ng writing text to `/var/log/*`) and the **systemd journal** (binary log read by `journalctl`). Most modern distros ship both — journald collects everything from PID 1 down, and forwards to rsyslog for the human-readable `/var/log/syslog`. This section maps where each piece writes, how the **facility / severity** model works, how to read kernel and auth logs, and how to keep log volumes from filling the disk.

### One Shot Revision

| Topic                                              | Short Description                                                        |
| -------------------------------------------------- | ------------------------------------------------------------------------ |
| [System Logging](#system-logging)                  | The big picture: journald + rsyslog, what writes where                   |
| [syslog](#syslog)                                  | The syslog **protocol** — facilities, severities, `logger`, `/dev/log`   |
| [General Logging](#general-logging)                | `/var/log/` tour — `syslog`, `messages`, app-specific subdirs            |
| [Kernel Logging](#kernel-logging)                  | `dmesg`, `/proc/kmsg`, `journalctl -k`, the kernel ring buffer           |
| [Authentication Logging](#authentication-logging)  | `/var/log/auth.log` / `secure`, `last`, `lastb`, `who`, `journalctl -u sshd` |
| [Managing Log Files](#managing-log-files)          | `logrotate`, journald retention, `vacuum-size` / `vacuum-time`           |

### System Logging

**Description:** A modern Linux box has **two log sinks running side by side**: **`systemd-journald`** (binary journal at `/var/log/journal/` or `/run/log/journal/`) and a classic **syslog daemon** (`rsyslog` on Debian/Ubuntu/RHEL, `syslog-ng` on a few others). systemd captures **everything from PID 1 and the kernel** into the journal; rsyslog reads from the journal (or `/dev/log` directly) and writes the text files most admins still grep — `/var/log/syslog` on Debian, `/var/log/messages` on RHEL.

**Who writes where:**

```
Kernel ─────────► /dev/kmsg ─┐
                             ├──► systemd-journald ──► /var/log/journal/*  (binary)
Services (PID 1's children) ─┘                            │
                                                          ▼
                                                       rsyslog
                                                          │
                                                          ▼
                                              /var/log/syslog
                                              /var/log/auth.log
                                              /var/log/kern.log
                                              /var/log/<app>/...
```

**Two front-ends, same data:**

| Tool         | Reads from                                | Best for                                  |
| ------------ | ----------------------------------------- | ----------------------------------------- |
| `journalctl` | The journal (`/var/log/journal/`)         | Per-unit logs, time-windowed queries, kernel + service combined |
| `grep` / `less` / `tail -F` | `/var/log/*` text files    | Quick text search, shell pipelines, scripts |

**Examples — the two ways to ask the same question:**

```bash
# What did sshd log in the last hour?
journalctl -u sshd --since "1 hour ago"
# vs.
sudo grep sshd /var/log/auth.log | awk -v d="$(date -d '1 hour ago' '+%b %d %H:%M')" '$0 > d'

# Everything from this boot, errors only:
journalctl -b -p err

# Tail every log:
sudo tail -F /var/log/syslog /var/log/auth.log /var/log/kern.log
# Or:
journalctl -f

# What's the journal disk usage?
journalctl --disk-usage
# Archived and active journals take up 320.0M in the file system.

# Where's the journal stored — persistent or volatile?
ls /var/log/journal 2>/dev/null && echo "persistent" || echo "volatile (will lose on reboot)"

# Make it persistent (if it's not):
sudo mkdir -p /var/log/journal && sudo systemctl restart systemd-journald
```

**Notes:**

- **Both stacks are running on most distros.** rsyslog reads from the journal (`imjournal` plugin) by default, so you have both binary searchable logs **and** plain text files.
- **Journald is volatile by default on some distros** (Ubuntu desktop) — only `/run/log/journal/` exists, which is RAM-backed and wiped at reboot. To keep logs across reboots, ensure `/var/log/journal/` exists.
- **`journalctl -u <unit>` is the killer feature** — combining unit, kernel, and syslog into one searchable view. No more `grep`ing six files to find what happened around an event.
- **Text logs are easier in pipelines.** `awk` / `sed` / `cut` are friendlier than `journalctl -o json` for ad-hoc work. Keep both stacks; they're complementary.
- **Remote logging is a one-liner change**: rsyslog forwards to a remote `@syslog.internal:514` (UDP) or `@@syslog.internal:514` (TCP) target. journald has `systemd-journal-upload` for the same purpose.

### syslog

**Description:** **syslog** is the *protocol*: every message has a **facility** (who sent it: kernel, auth, cron, mail, user, local0..7) and a **severity** (how bad: emerg, alert, crit, err, warning, notice, info, debug). Daemons write to `/dev/log` (a Unix socket); the syslog daemon reads from there and routes messages to files / remote hosts based on **facility + severity** filters in `/etc/rsyslog.conf` (or `/etc/syslog-ng/syslog-ng.conf`).

**Facilities and severities:**

| Severity (numeric) | Name      | Meaning                                |
| ------------------ | --------- | -------------------------------------- |
| 0                  | `emerg`   | System unusable                        |
| 1                  | `alert`   | Take action immediately                |
| 2                  | `crit`    | Critical                               |
| 3                  | `err`     | Error                                  |
| 4                  | `warning` | Warning                                |
| 5                  | `notice`  | Normal but significant                 |
| 6                  | `info`    | Informational                          |
| 7                  | `debug`   | Debug                                  |

| Facility   | Source                                       |
| ---------- | -------------------------------------------- |
| `kern`     | Kernel                                       |
| `user`     | Generic userspace                            |
| `mail`     | Mail subsystem                               |
| `daemon`   | System daemons                               |
| `auth`     | Login / authentication (logins, sudo)        |
| `authpriv` | Sensitive auth (passwords, keys)             |
| `cron`     | The cron daemon                              |
| `local0`–`local7` | Reserved for site-specific use        |

**Examples:**

```bash
# Send a message to syslog from the shell — useful in scripts:
logger "Backup started"
logger -p user.warning "Disk usage above 80%"
logger -t myapp -p local0.info "Custom app message with a tag"
sudo tail /var/log/syslog
# Jun 20 10:15:01 host myapp: Custom app message with a tag

# rsyslog rules — typical /etc/rsyslog.d/50-default.conf entries:
# auth,authpriv.*            /var/log/auth.log    ← all auth, any severity
# *.*;auth,authpriv.none    -/var/log/syslog      ← everything except auth
# kern.*                     /var/log/kern.log    ← all kernel
# cron.*                     /var/log/cron.log    ← all cron
# mail.err                   /var/log/mail.err    ← mail errors only

# Forward everything to a remote syslog server:
echo '*.*  @@logs.internal:514' | sudo tee /etc/rsyslog.d/90-forward.conf
sudo systemctl restart rsyslog

# Check that rsyslog is picking up your config:
sudo rsyslogd -N1                    # config check (-N1 = parse only)

# Live-tail rsyslog's view of incoming messages:
sudo tail -F /var/log/syslog
```

**Notes:**

- **The `-` before a filename in rsyslog rules** (e.g. `-/var/log/syslog`) means "don't fsync after every write" — much faster, fine for non-critical logs.
- **`auth,authpriv.*` vs `auth.*;authpriv.none`** is a frequent gotcha: facilities are listed by comma; severity follows the dot; `none` excludes. Read the config carefully.
- **`logger` is great in shell scripts** — `logger -p user.err "Backup FAILED"` puts your error in the same place sysadmins are already watching.
- **`local0`–`local7` are yours to use.** Many ops teams pick one for their custom application logs so they get their own facility filter.
- **`/dev/log` is a Unix socket, not a file.** Programs write to it via the `syslog()` libc function; rsyslog/syslog-ng reads it.

### General Logging

**Description:** The tour of `/var/log/` — what file usually contains what. Even on a systemd box where the journal is canonical, rsyslog mirrors most of this to text. Treat this as the map for "I'm hunting a problem; which file do I `tail`?"

**The usual suspects:**

| File / dir                          | What lives here                                                       |
| ----------------------------------- | --------------------------------------------------------------------- |
| `/var/log/syslog` (Debian)          | Everything except auth (the "general" log)                            |
| `/var/log/messages` (RHEL)          | Same idea on Red Hat–family systems                                   |
| `/var/log/auth.log` (Debian)        | Login, sudo, ssh, PAM — see [Authentication Logging](#authentication-logging) |
| `/var/log/secure` (RHEL)            | RHEL equivalent of `auth.log`                                         |
| `/var/log/kern.log`                 | Kernel-only messages (also `dmesg` and `journalctl -k`)               |
| `/var/log/dmesg` / `dmesg.0`        | Captured kernel ring buffer from boot                                 |
| `/var/log/cron.log` / `journalctl -u cron` | Cron job activity                                              |
| `/var/log/mail.log` / `mail.err`    | Mail subsystem (Postfix, Sendmail)                                    |
| `/var/log/boot.log`                 | Console output from boot (services starting/failing)                  |
| `/var/log/wtmp` / `btmp`            | Binary — login history (`last`) / failed logins (`lastb`)             |
| `/var/log/lastlog`                  | Binary — last login per user (`lastlog`)                              |
| `/var/log/apt/`                     | Debian/Ubuntu — package operations (history, term)                    |
| `/var/log/dnf.log` / `yum.log`      | RHEL/Fedora — package operations                                      |
| `/var/log/nginx/` `apache2/` `mysql/` `redis/` ... | One subdir per major service                           |
| `/var/log/journal/`                 | systemd binary journal (read via `journalctl`)                        |
| `/var/log/`*`.gz`* / `.1` / `.N`    | Rotated, compressed logs from `logrotate`                             |

**Examples — common log hunts:**

```bash
# General "what happened recently?"
sudo tail -F /var/log/syslog               # Debian
sudo tail -F /var/log/messages             # RHEL
# Or unified:
journalctl -f

# Search every (recent + rotated) log for a string:
sudo zgrep -h "out of memory" /var/log/syslog*
sudo zgrep -h "Failed password" /var/log/auth.log* | wc -l

# Last 100 errors from the journal:
journalctl -p err -n 100

# Per-service:
sudo tail -F /var/log/nginx/access.log /var/log/nginx/error.log
journalctl -u nginx -f

# Apt / dnf history — what got installed/upgraded and when:
sudo less /var/log/apt/history.log
sudo dnf history
```

**Notes:**

- **`/var/log/wtmp`, `btmp`, `lastlog` are binary.** Don't `cat` them — use `last`, `lastb`, `lastlog` respectively.
- **Rotated logs (`*.1`, `*.2.gz`, `*.3.gz`...) are still searchable.** `zgrep` reads `.gz` directly; `zless` pages compressed files.
- **`/var/log/dmesg` is captured at boot**; it's a frozen copy. Live kernel messages are in the ring buffer (`dmesg`) and the journal (`journalctl -k`).
- **App-specific subdirs (`/var/log/nginx/`)** usually have their own rotation managed by `/etc/logrotate.d/<app>`. Check that config when a log is missing — it may have rotated.
- **For containers, logs are different.** Docker captures stdout/stderr to `/var/lib/docker/containers/<id>/...-json.log`; Kubernetes node logs go to `/var/log/pods/`. The application-level `/var/log/` inside the container is usually irrelevant.

### Kernel Logging

**Description:** The kernel has its own log buffer — a **fixed-size ring** in kernel memory (`/dev/kmsg`, read out as `dmesg`). Everything the kernel prints goes here: driver init at boot, hardware errors, OOM kills, panics. The buffer is a ring (oldest entries get overwritten), but `systemd-journald` continuously copies new entries into the persistent journal, so you can review old kernel events with `journalctl -k`.

**The two views:**

| Tool                | Source                                          | Notes                                      |
| ------------------- | ----------------------------------------------- | ------------------------------------------ |
| `dmesg`             | Live kernel ring buffer (`/dev/kmsg`)           | Snapshot — gets overwritten on busy boxes  |
| `journalctl -k`     | Persistent journal copy of kernel messages      | Per-boot, time-windowed, persistent        |
| `/var/log/kern.log` | rsyslog-archived kernel messages (text)         | Grep-friendly, rotated by logrotate        |

**Examples:**

```bash
# Recent kernel messages with human timestamps:
sudo dmesg -T | tail -30

# Watch new kernel messages live (kernel "tail -f"):
sudo dmesg -w

# All kernel messages from this boot:
journalctl -k -b

# Kernel messages from the previous boot:
journalctl -k -b -1

# Errors only from this boot:
journalctl -k -b -p err

# Find a specific hardware/driver event:
dmesg | grep -i nvme
dmesg | grep -iE "error|fail|warn"

# Did the OOM-killer fire?
dmesg | grep -i "killed process"
# Or:
journalctl -k --grep "Out of memory"

# Check thermal throttling:
dmesg | grep -i thermal

# Lost a USB device? Plug it in and watch:
sudo dmesg -w &        # in another shell
# (now plug in the device — events appear)

# Clear the ring buffer (rarely useful):
sudo dmesg -c
```

**Notes:**

- **The kernel ring is a fixed size** (`dmesg --buffer-size` or in build config, typically 1 MiB). On a chatty box, it wraps in minutes — that's why the journal copy matters.
- **`dmesg` may require root on hardened systems.** Some distros set `kernel.dmesg_restrict=1` so users can't see kernel addresses (kASLR leakage). Use `sudo`.
- **Kernel panics print on the console**, and to the journal if it gets that far. If the box is hung with no journal entries near the freeze, take a photo of the screen — it's often the only diagnostic you'll have.
- **`dmesg -T` adds human-readable timestamps**. Old `dmesg` showed nanosecond-since-boot floats which are useless for correlating with wall-clock events.
- **`dmesg --level=err,warn`** shows only error/warning severity messages — much shorter than the full firehose.
- **eBPF tracepoints** (`bpftrace`, `bcc`) are the modern way to instrument the kernel without printing to the log — for production-grade observation that doesn't fill the ring buffer.

### Authentication Logging

**Description:** Every login, sudo invocation, ssh session, and PAM event lands in **`/var/log/auth.log`** (Debian/Ubuntu) or **`/var/log/secure`** (RHEL/Fedora). These files are gold for security incident review: who logged in from where, who tried and failed, who used sudo for what. Three small helper commands — **`last`**, **`lastb`**, **`who`** — read the binary login databases (`wtmp`, `btmp`, `utmp`) directly.

**The files:**

| Path                                       | What it holds                                                |
| ------------------------------------------ | ------------------------------------------------------------ |
| `/var/log/auth.log` (Debian) / `/var/log/secure` (RHEL) | sshd, login, su, sudo, PAM (text)                |
| `/var/log/wtmp`                            | Binary — every successful login/logout (`last`)              |
| `/var/log/btmp`                            | Binary — every **failed** login (`lastb`)                    |
| `/var/run/utmp`                            | Binary — currently-logged-in users (`who`)                   |
| `/var/log/lastlog`                         | Binary — most recent login per user (`lastlog`)              |
| `journalctl -u sshd` / `-u systemd-logind` | Same info from the journal, per-unit                         |

**Examples — incident reading:**

```bash
# Who logged in successfully, most recent first:
last | head -20

# Who's logged in right now?
who
# tarek    pts/0   2026-06-20 09:15 (192.168.1.42)
# tarek    pts/1   2026-06-20 09:20 (192.168.1.42)

# Anyone failing logins? (the most common security warning sign):
sudo lastb | head -20

# Specifically failed ssh logins (often = brute-force probes):
sudo grep "Failed password" /var/log/auth.log | tail -20

# Count failed-login attempts per source IP:
sudo grep "Failed password" /var/log/auth.log \
  | awk '{print $(NF-3)}' | sort | uniq -c | sort -rn | head

# When did user 'alice' last log in (per machine)?
lastlog -u alice

# Every sudo invocation today:
sudo journalctl -t sudo --since today
# Or:
sudo grep -E "sudo:.*COMMAND" /var/log/auth.log

# Watch ssh activity live:
journalctl -u sshd -f
```

**Notes:**

- **`lastb` requires root** — `/var/log/btmp` is mode 600 because failed-login attempts may include typed-as-password real passwords (someone typoing into the username prompt).
- **Failed ssh attempts on an internet-facing box are constant background noise.** Hundreds per day on a default-port sshd is normal — install **fail2ban** to drop the brute-forcers, or move ssh off port 22.
- **`pam_tally2` / `pam_faillock`** can lock accounts after N failed logins. Check `/etc/pam.d/sshd` and `/etc/pam.d/login` to see if it's enabled.
- **Sudo logs the command, not the argv expansion.** If you run `sudo bash`, the log says `bash` — what you did inside that shell is **not** logged here. For audit-grade sudo, enable **sudo I/O logging** (`Defaults log_input,log_output` in sudoers).
- **For ongoing security monitoring**, ship `auth.log` to a central syslog server or an SIEM (Splunk, ELK, Loki). Local logs can be erased by an attacker; remote ones generally can't.

### Managing Log Files

**Description:** Logs grow forever if left alone — and full `/var` is one of the easiest ways to take a server down. **`logrotate`** is the classic answer: a cron-driven tool that rotates (renames + compresses + truncates) text logs on a schedule. **journald** does its own rotation internally, bounded by total disk usage or age. Knowing both, plus how to free space immediately when a log explodes, is what keeps disks healthy.

**logrotate at a glance:**

| File                            | Role                                                          |
| ------------------------------- | ------------------------------------------------------------- |
| `/etc/logrotate.conf`           | Global defaults                                               |
| `/etc/logrotate.d/<package>`    | Per-package rotation configs (each package installs its own)  |
| `/var/lib/logrotate/status`     | Tracks "when was each log last rotated?"                      |

**A typical logrotate snippet (`/etc/logrotate.d/nginx`):**

```
/var/log/nginx/*.log {
    daily                          # rotate every day
    missingok                       # OK if a log is absent
    rotate 14                       # keep 14 rotations (then delete oldest)
    compress                        # gzip rotated files
    delaycompress                   # don't compress the most recent rotation (so apps can still write)
    notifempty                      # don't rotate empty logs
    create 0640 www-data adm        # create the new log with these perms
    sharedscripts
    postrotate
        /usr/sbin/nginx -s reopen >/dev/null 2>&1 || true
    endscript
}
```

**Examples:**

```bash
# Test a logrotate config (debug, no changes):
sudo logrotate -d /etc/logrotate.d/nginx

# Force rotation now (regardless of schedule):
sudo logrotate -f /etc/logrotate.d/nginx

# When did logrotate last touch a given log?
sudo cat /var/lib/logrotate/status | grep nginx

# Find the biggest logs:
sudo du -h /var/log/* | sort -h | tail -10

# Truncate (not delete!) a runaway log of a running process:
sudo truncate -s 0 /var/log/some-runaway-app.log
# Or:
sudo : > /var/log/some-runaway-app.log
# (Deleting with rm DOESN'T free space until the process closes the FD —
#  see [Disk Usage](#disk-usage) and lsof +L1.)
```

**journald retention:**

```bash
# Current journal size:
journalctl --disk-usage

# Trim to N: by size, by age, by file-count:
sudo journalctl --vacuum-size=500M
sudo journalctl --vacuum-time=2weeks
sudo journalctl --vacuum-files=5

# Persistent retention config — /etc/systemd/journald.conf:
# [Journal]
# SystemMaxUse=500M           ← cap total disk
# SystemMaxFileSize=50M       ← cap one journal file
# MaxRetentionSec=4weeks      ← drop entries older than 4 weeks
# Storage=persistent          ← keep across reboots

# After editing journald.conf:
sudo systemctl restart systemd-journald
```

**Notes:**

- **Always restart or reopen the writing process after rotating its log** — the `postrotate` hook is for exactly that. Without it, the daemon keeps writing to the (renamed) old file forever.
- **`copytruncate` is the alternative** when a daemon can't reopen its log on signal. logrotate copies the file then truncates the original in-place — no FD change. Some data can be lost between copy and truncate; use only when you must.
- **Disk fills overnight?** It's usually one log: `du -h /var/log/* | sort -h | tail`. Truncate the offender, then fix the logrotate config.
- **journald defaults to "10% of /var" or 4 GiB, whichever is smaller** — fine on most boxes, can be a lot on small VPS instances. Tune `SystemMaxUse=` if your `/var` is tight.
- **For containers and modern stacks, you usually don't rotate inside the container** — the runtime (`docker`, `containerd`, `kubelet`) handles log rotation at the host level. Inside the container, log to stdout/stderr and let the runtime route it.
- **Centralized logging changes the math.** If everything ships to a central log server, local retention can be aggressive (1–3 days) since the master copy lives elsewhere.

---

## Common Interview Questions

**50 commonly asked Linux interview questions** for DevOps roles — **10 Easy** (junior), **20 Medium** (mid-level), **20 Hard** (senior). Curated to cover the topics that come up most in real interviews: filesystem, processes, permissions, networking, boot/init, performance, security, and containers/Linux internals.

### Easy (Junior Level)

**1. What is Linux, and how is it different from Unix?**

Linux is an open-source, Unix-like operating system kernel created by Linus Torvalds in 1991, paired with GNU userspace tools to form a complete OS. Unix is the original 1970s AT&T-developed OS family (commercial: AIX, Solaris, HP-UX). They share POSIX APIs and shell conventions, but Linux is free, has a single kernel codebase used everywhere from phones to supercomputers, and is community-driven; Unix variants are vendor-specific and closed-source.

**2. What is the kernel?**

The **kernel** is the core program that runs in privileged mode (ring 0), owns the hardware, and exposes a system-call API to userspace. It manages CPU scheduling, memory, filesystems, networking, and devices. Linux is a **monolithic kernel with loadable modules** — drivers run in kernel space but can be loaded/unloaded at runtime via `modprobe`.

**3. What is a shell? Name common shells.**

A **shell** is a command interpreter that reads user input and runs programs. Common shells: **bash** (default on most distros), **zsh** (modern, plugin-rich, default on macOS), **sh** (POSIX-minimal, often a symlink), **dash** (fast POSIX shell, Ubuntu's `/bin/sh`), **fish** (user-friendly, not POSIX-compliant). Check yours with `echo $SHELL`.

**4. How do you check the current working directory?**

Use `pwd` (print working directory):

```bash
pwd
# /home/tarek/projects
```

The environment variable `$PWD` holds the same value.

**5. What command lists all files, including hidden ones?**

`ls -la`:

```bash
ls -la
# drwxr-xr-x  5 tarek tarek 4096 Jun 20 10:00 .
# drwxr-xr-x 20 tarek tarek 4096 Jun 19 09:30 ..
# -rw-------  1 tarek tarek  220 Jan 15  2024 .bashrc
# -rw-r--r--  1 tarek tarek  100 Jun 20 09:55 file.txt
```

Hidden files in Linux start with a `.` — `-a` shows them; `-l` adds the long listing (perms, owner, size, mtime).

**6. How do you check disk space usage?**

- **`df -h`** — free/used space per **mounted filesystem** (human-readable).
- **`du -sh <dir>`** — total size of one directory.
- **`du -h --max-depth=1 /var | sort -h`** — top hogs under `/var`.
- **`df -i`** — inode usage (a partition can be "full" by inodes even with bytes free).

**7. How do you create, copy, move, and delete files in Linux?**

```bash
touch file.txt              # create empty file
cp file.txt copy.txt        # copy
cp -r dir/ newdir/          # copy directory recursively
mv file.txt /tmp/           # move (also used to rename)
rm file.txt                 # delete
rm -rf dir/                 # delete dir + contents (DANGEROUS)
mkdir -p a/b/c              # create dir + parents
```

**8. What is the difference between absolute and relative paths?**

- **Absolute path** starts from the root `/`: `/home/tarek/file.txt`. Same meaning from anywhere.
- **Relative path** starts from the **current working directory**: `./file.txt`, `../docs/readme.md`. `.` is "current dir", `..` is "parent dir", `~` is "home dir".

**9. What does `ls -l` output show?**

```
-rw-r--r-- 1 tarek tarek 100 Jun 20 09:55 file.txt
│└┬┘└┬┘└┬┘ │  │     │     │      │          │
│ │  │  │  │  │     │     │      │          └── filename
│ │  │  │  │  │     │     │      └── modification time
│ │  │  │  │  │     │     └── size in bytes
│ │  │  │  │  │     └── group
│ │  │  │  │  └── owner (user)
│ │  │  │  └── number of hard links
│ │  │  └── other permissions (r--)
│ │  └── group permissions (r--)
│ └── owner permissions (rw-)
└── file type (- regular, d directory, l symlink, c char device, b block device)
```

**10. How do you read large log files efficiently?**

Don't `cat` them — they'll flood your terminal. Use:

- **`less <file>`** — page through, search with `/`, follow with `Shift+F`.
- **`tail -F /var/log/syslog`** — live tail (survives log rotation).
- **`head -100 file.log`** / **`tail -100 file.log`** — first / last 100 lines.
- **`grep "ERROR" file.log`** — only matching lines.
- **`zless` / `zgrep`** for `.gz`-compressed rotated logs.

---

### Medium (Mid-Level)

**11. What's the difference between a hard link and a symbolic link?**

| Aspect              | Hard link                      | Symbolic link (symlink)     |
| ------------------- | ------------------------------ | --------------------------- |
| Inode               | Same as target (shared)        | Own inode; points by path   |
| Cross filesystem?   | No                              | Yes                         |
| Link to directory?  | No (root only, restricted)      | Yes                         |
| Survives target delete? | Yes — data lives until last link gone | Becomes dangling     |
| Created by          | `ln source link`                | `ln -s source link`         |

A hard link is **another name for the same file**; a symlink is **a tiny file containing a path** to follow.

**12. Explain file permissions and how to change them.**

Each file has three permission classes (**owner**, **group**, **other**) with three bits each (**read**, **write**, **execute**) → 9 bits, shown as `rwxr-xr--`. In **octal**: `r=4, w=2, x=1`, so `rwxr-xr--` = `754`.

```bash
chmod 755 script.sh        # rwxr-xr-x
chmod u+x script.sh        # add execute for owner
chmod g-w file             # remove write for group
chown alice:devs file      # change owner and group
```

Special bits: **setuid** (`4xxx`), **setgid** (`2xxx`), **sticky** (`1xxx`).

**13. What's the purpose of `/etc/passwd` vs `/etc/shadow`?**

- **`/etc/passwd`** — world-readable; holds username, UID, GID, home, shell. **No passwords** (the `x` is a placeholder).
- **`/etc/shadow`** — root-only (mode 0640); holds hashed passwords, password-aging info, account-expiry.

Splitting them lets `getent passwd` work for everyone without exposing hashes to dictionary attacks.

**14. How do you find files larger than 100 MB?**

```bash
find / -xdev -type f -size +100M -exec ls -lh {} \; 2>/dev/null

# Or sorted by size:
sudo find / -xdev -type f -size +100M -printf '%s %p\n' 2>/dev/null \
  | sort -nr | head -20 | awk '{printf "%.0f MB\t%s\n", $1/1048576, $2}'
```

`-xdev` stops `find` from crossing mountpoints (avoids diving into `/proc`, `/sys`, network mounts).

**15. What's the difference between `grep`, `egrep`, and `fgrep`?**

- **`grep`** — basic regular expressions (BRE).
- **`grep -E` / `egrep`** — extended regex (ERE): `+`, `?`, `|`, `()` without backslashes.
- **`grep -F` / `fgrep`** — fixed strings, no regex, fastest.

`egrep` and `fgrep` are deprecated wrappers; modern usage is `grep -E` and `grep -F`.

**16. Explain process states.**

| State | Meaning                                                          |
| ----- | ---------------------------------------------------------------- |
| **R** | Running or runnable (on the run queue)                            |
| **S** | Interruptible sleep (waiting on I/O, signal, or event)            |
| **D** | Uninterruptible sleep (usually waiting on disk — **can't be killed**) |
| **Z** | Zombie — terminated, but parent hasn't `wait()`ed yet             |
| **T** | Stopped (SIGSTOP / Ctrl+Z) or being traced                        |
| **I** | Idle kernel thread (kernel ≥ 4.2)                                  |

See states with `ps aux` — the `STAT` column.

**17. What is a zombie process? How do you remove it?**

A **zombie** is a process that has exited but whose parent hasn't called `wait()` to reap its exit status. It holds only a PID + exit code, no memory or file descriptors. You **can't `kill` a zombie** (it's already dead). The fix: send **`SIGCHLD`** to the parent (asks it to reap), or kill the parent — the kernel will re-parent the zombie to `init` (PID 1), which reaps it immediately.

**18. Explain the difference between SIGTERM, SIGKILL, and SIGHUP.**

| Signal     | #  | Catchable? | Use                                                |
| ---------- | -- | ---------- | -------------------------------------------------- |
| **SIGTERM** | 15 | Yes | Polite "please exit" — process can clean up first. **Default for `kill <pid>`.** |
| **SIGKILL** |  9 | **No**  | Immediate kernel-level kill. No cleanup. Last resort. |
| **SIGHUP**  |  1 | Yes | Originally "terminal hang-up"; now commonly used as "reload config" (nginx, sshd). |

Always try `SIGTERM` first, then `SIGKILL` if it doesn't exit in a few seconds.

**19. How does cron work? Where do you configure jobs?**

`cron` is a daemon that reads time-based schedules and forks commands at the right minute. Schedules live in:

- **`crontab -e`** — per-user (`/var/spool/cron/<user>`)
- **`/etc/crontab`** — system-wide, with extra **user** field
- **`/etc/cron.d/<file>`** — drop-in system jobs
- **`/etc/cron.{hourly,daily,weekly,monthly}/`** — just drop executables

Format: `min hour day-of-month month day-of-week command`. Modern alternative: **systemd timers** (`.timer` units) for dependency-aware, journaled scheduling.

**20. What's the difference between `su` and `sudo`?**

- **`su`** — "switch user"; opens a new shell as another user (default: root). Requires the **target user's** password.
- **`sudo`** — "do as another user"; runs **one command** as another user. Requires **your own** password, authorized by `/etc/sudoers`.

`sudo` logs every command (`/var/log/auth.log`), supports fine-grained policies, and doesn't require sharing the root password. `sudo -i` opens a root shell similar to `su -`.

**21. How do you check which ports are open on a system?**

```bash
ss -lntp                   # listening TCP, with PID/program — preferred
ss -lnup                   # UDP version
sudo lsof -i -P -n         # all sockets, numeric, with PID
sudo netstat -tlnp         # older equivalent (net-tools)
nmap -sT localhost         # external scan from another box
```

`ss` is the modern replacement for `netstat` — faster, reads `/proc/net/tcp` directly.

**22. What is the `/proc` filesystem?**

`/proc` is a **virtual filesystem** that exposes live kernel and per-process state as files. Reading them invokes kernel code that formats data on the fly — they take zero disk space. Examples:

- `/proc/cpuinfo`, `/proc/meminfo`, `/proc/version`
- `/proc/<pid>/cmdline`, `/proc/<pid>/status`, `/proc/<pid>/fd/`
- `/proc/sys/...` — tunables (`sysctl` reads/writes here)

Sibling `/sys` exposes the kernel's device model.

**23. Explain `umask` and how it affects new files.**

`umask` is a **bit mask of permissions to remove** from newly created files. Default permissions:

- New files: `0666` (rw-rw-rw-) → masked → typical result `0644`
- New dirs:  `0777` (rwxrwxrwx) → masked → typical result `0755`

With `umask 022`, the mask removes write from group + other:
- File: `0666 & ~022 = 0644` (rw-r--r--)
- Dir:  `0777 & ~022 = 0755` (rwxr-xr-x)

Stricter `umask 077` makes files private to the owner.

**24. How do you find which process is using a specific port?**

```bash
sudo ss -lntp 'sport = :80'
sudo lsof -i :80
sudo fuser 80/tcp -v
```

All three show the PID + command holding the port.

**25. What is swap space, and how do you create a swap file?**

**Swap** is disk space used as overflow when RAM is full — the kernel pages out inactive memory and reads it back when needed. Modern systems prefer **swap files** (easy to resize/remove) over swap partitions.

```bash
sudo fallocate -l 4G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```

Tune **`vm.swappiness`** (default 60) — lower it (10–20) on latency-sensitive workloads.

**26. What's the difference between `df` and `du`?**

- **`df`** — reports **filesystem-level** free space from the superblock. Fast, includes all mounted FSes.
- **`du`** — walks the directory tree and **sums file sizes**. Slow, but per-directory.

They can disagree because (a) deleted-but-still-open files hold blocks (`lsof +L1` finds them), (b) sparse files have fewer real than apparent bytes, (c) reserved blocks for root appear used to non-root.

**27. Explain the Linux boot process.**

1. **Firmware (BIOS/UEFI)** — POST, picks a boot device, loads first-stage code (MBR or `.efi` from the ESP).
2. **Bootloader (GRUB2)** — picks a kernel, loads `vmlinuz` + `initramfs` into RAM, jumps to kernel.
3. **Kernel** — decompresses, brings up CPUs/memory/built-in drivers, mounts initramfs as `/`, runs `/init`.
4. **Initramfs** — loads drivers needed to mount the real root FS, then `switch_root` into it.
5. **Init (PID 1, systemd)** — brings up units in dependency order until reaching `default.target` (multi-user / graphical).
6. **Login** — `getty` on TTYs or display manager (gdm/sddm).

`systemd-analyze` breaks down the time spent in each stage.

**28. What is systemd, and how is it different from SysV init?**

**systemd** is a modern init system (PID 1) using declarative **unit files**, an explicit **dependency graph**, and **parallel** unit startup. **SysV init** used numbered shell scripts in `/etc/rc<N>.d/` run sequentially.

| SysV init                       | systemd                              |
| ------------------------------- | ------------------------------------ |
| Shell scripts in `/etc/init.d/` | INI-style `.service` / `.target` units |
| Sequential boot                 | Parallel boot via dep graph          |
| Runlevels (0–6)                 | Targets (multi-user.target, etc.)    |
| Hard to track child processes   | cgroup-based — always knows every descendant |
| `service` / `chkconfig`         | `systemctl` / `journalctl`           |

**29. How do you redirect stdout, stderr, both, and to a file?**

```bash
cmd > file              # stdout → file (truncate)
cmd >> file             # stdout → file (append)
cmd 2> file             # stderr → file
cmd > out 2> err        # stdout + stderr to separate files
cmd > file 2>&1         # both to one file
cmd &> file             # same (bash shorthand)
cmd < input.txt         # stdin from file
cmd | other             # pipe stdout into another command
cmd 2>&1 | tee log      # log both streams and see them live
cmd > /dev/null 2>&1    # silence everything
```

**30. Explain how to securely set up SSH key authentication.**

```bash
# 1. On client: generate a key pair (Ed25519 preferred over RSA)
ssh-keygen -t ed25519 -C "you@host"
# Produces ~/.ssh/id_ed25519 (private — NEVER share) and id_ed25519.pub

# 2. Copy the public key to the server:
ssh-copy-id user@server
# Or manually: append id_ed25519.pub to ~/.ssh/authorized_keys on the server

# 3. Lock down server-side:
sudo vi /etc/ssh/sshd_config
#   PasswordAuthentication no
#   PermitRootLogin prohibit-password   # or no
#   PubkeyAuthentication yes
sudo systemctl restart sshd

# 4. Protect the private key:
chmod 600 ~/.ssh/id_ed25519
```

Best practice: use **separate keys per machine**, protect private keys with a **passphrase** + `ssh-agent`, and rotate keys periodically.

---

### Hard (Senior Level)

**31. Explain how Linux memory management works (paging, swap, OOM killer).**

Linux uses **virtual memory** — each process sees a private 64-bit address space backed by physical pages. The kernel splits memory into 4 KiB **pages**, mapped via per-process page tables. Unused pages get **paged out to swap**; frequently-accessed disk blocks are kept in the **page cache** to speed reads.

When physical RAM is exhausted **and** swap is exhausted (or fast filling), the **OOM killer** runs. It picks a victim using `oom_score` (computed from RSS + `oom_score_adj`) and sends SIGKILL. To favor or protect a process:

```bash
echo -1000 > /proc/<pid>/oom_score_adj   # never kill (range -1000..1000)
```

Tune with **`vm.swappiness`** (paging aggressiveness), **`vm.overcommit_memory`** (allocation policy), and **`vm.dirty_ratio`** (dirty page flush threshold).

**32. What are cgroups and namespaces? How are they used in containers?**

Both are kernel features that together enable containers.

- **Namespaces** isolate **what a process can see**: PID, network, mount, UTS (hostname), IPC, user, cgroup. A process in a new PID namespace sees its own PID 1; in a new network namespace it has its own interfaces.
- **cgroups** ("control groups") limit **what resources a process can use**: CPU shares, memory caps, I/O bandwidth, PIDs count. cgroups v2 is the modern unified hierarchy.

Docker / Podman / Kubernetes combine namespaces (isolation) + cgroups (limits) + a layered filesystem (overlayfs) + capabilities/seccomp/AppArmor (security) to build a container. A container is not a VM — it shares the host kernel.

**33. How does copy-on-write `fork()` work?**

`fork()` creates a child process that's a near-exact copy of the parent. Naive implementation: copy every page. Linux uses **copy-on-write (COW)**: the child shares the parent's pages, marked read-only. Both processes can read freely; the first **write** triggers a page fault, the kernel allocates a fresh page, copies the original, marks both writable, and resumes. Pages that are never written are never duplicated.

That's why `fork()` followed immediately by `execve()` is cheap — `execve` discards the address space before any writes happen, so almost nothing is actually copied.

**34. Explain inodes. What happens when you run out of inodes?**

An **inode** is the on-disk record holding a file's metadata: type, permissions, owner, size, timestamps, link count, and pointers to data blocks. The **filename is not in the inode** — it lives in a directory entry that maps a name → inode number.

Ext2/3/4 allocate inodes at `mkfs` time (fixed pool); XFS/Btrfs allocate dynamically. If you create millions of tiny files on ext4, you can **exhaust inodes** even with bytes free — `df -h` shows free space, but `df -i` shows 100%. The fix: delete files, or reformat with `mkfs.ext4 -i <bytes-per-inode>` to allocate more inodes per byte.

**35. How would you debug high load average with low CPU usage?**

**Load average includes runnable + uninterruptible (D-state) processes.** Low CPU + high load = processes blocked on I/O, not CPU.

Diagnosis order:

```bash
uptime               # confirm high load
mpstat 1 5           # see %iowait — if high, it's disk
vmstat 1 5           # b column = blocked procs; wa = iowait
iostat -xz 1         # per-disk %util, await — find the busy disk
iotop -o             # which PROCESS is doing the I/O
ps -eo pid,stat,wchan,cmd | awk '$2 ~ /D/'   # processes stuck in D state
```

Common culprits: failing disk (check `dmesg`), NFS hang, swap thrashing, a misbehaving database flush.

**36. What's the difference between Buffer and Cache in `free` output?**

Historically:
- **Buffers** = raw block-device cache (e.g. filesystem metadata blocks read by `dd if=/dev/sda`).
- **Cache** = page cache (file contents read by `cat /etc/passwd`).

Modern Linux unifies them — both are reclaimable. The number that actually matters is **`available`**, which estimates how much memory a new process can grab without forcing swap. "Used" memory in `free` includes cache; that's not memory pressure.

**37. How does filesystem journaling work?**

A **journal** is a log of pending filesystem changes written **before** the changes are applied to the main FS structures. After a crash, the FS replays the journal at mount time, finishing or discarding in-progress operations — so the FS is always recoverable to a consistent state.

ext4 journal modes:
- **`data=writeback`** — metadata journaled, data not. Fastest, can leak stale data after crash.
- **`data=ordered`** (default) — metadata journaled; data written before its metadata commit.
- **`data=journal`** — both data and metadata journaled. Safest, slowest.

XFS and Btrfs have their own designs; both are crash-safe by construction.

**38. What happens step-by-step when you type a command and press Enter?**

1. **Shell reads** the line, performs **word splitting**, **glob expansion** (`*.txt`), **variable expansion** (`$HOME`), **command substitution** (`$(...)`), **pipe/redirect setup**.
2. Shell looks up the command: **builtins** first (`cd`, `echo`), then **functions/aliases**, then **`$PATH`** lookup.
3. Shell calls **`fork()`** → child process is created via COW.
4. Child calls **`execve("/usr/bin/cmd", argv, envp)`** — kernel replaces the child's address space with the binary.
5. Kernel loads the **dynamic linker** (`ld-linux.so`), which maps shared libraries.
6. Binary's `main()` runs; it makes **syscalls** (open, read, write) via the `syscall` instruction.
7. On exit, child calls **`exit()`**; kernel reaps resources and stores the **exit code**.
8. Parent shell's `wait()` returns; **`$?`** is set to the exit code; shell prints the prompt.

**39. How would you find which process is consuming the most I/O?**

```bash
# Live, per-process:
sudo iotop -oP             # -o: only active, -P: processes (not threads)

# Scriptable / non-curses:
sudo pidstat -d 1 5

# Per-disk view first, then drill down:
iostat -xz 1               # find the busy device (%util, await)
sudo lsof <device-or-mount>   # who has it open?

# Kernel-level eBPF (most precise):
sudo biosnoop-bpfcc         # per-I/O latency + offending process
sudo biolatency-bpfcc       # histogram of I/O latencies
```

**40. Explain LVM and its benefits.**

**LVM** (Logical Volume Manager) is an abstraction layer between physical disks and filesystems:

```
Physical Volumes (PVs)   ← raw disks/partitions (pvcreate /dev/sdb1)
        ↓
Volume Group (VG)        ← pool of PV storage (vgcreate vg0 /dev/sdb1)
        ↓
Logical Volumes (LVs)    ← carved out of VG, looks like a partition (lvcreate -L 100G vg0)
        ↓
Filesystem (ext4/xfs)    ← mkfs.ext4 /dev/vg0/data
```

Benefits: **online resize** (grow `/` without reboot), **snapshots** (consistent point-in-time copies for backups), **adding disks to existing volumes** (extend VG with `vgextend`), **thin provisioning**, **mirroring/striping** built in.

**41. How does SSH key-based authentication work cryptographically?**

1. Client sends "I'd like to authenticate as user X with this **public key** fingerprint".
2. Server checks its `~user/.ssh/authorized_keys`. If the fingerprint matches an entry:
3. Server generates a **random challenge**, encrypts it with the **public key**, sends it.
4. Client decrypts with its **private key** (only the holder can do this), signs the result, returns it.
5. Server verifies the signature using the public key — if valid, authentication succeeds.

It's **public-key cryptography**: the public key encrypts (or verifies); only the private key can decrypt (or sign). The private key never leaves the client. Modern setups use **Ed25519** or **ECDSA**; RSA is still common but requires ≥ 3072-bit keys.

**42. What is SELinux/AppArmor, and how do they differ from traditional permissions?**

Traditional Unix permissions are **discretionary** (DAC) — the file owner controls access. **SELinux** and **AppArmor** add **mandatory access control** (MAC) — a system-wide policy decides what every process can do, on top of DAC.

- **SELinux** (Red Hat ancestry, default on RHEL/Fedora) — labels every file/process with a **security context** (`user:role:type:level`). Policy says "processes of type `httpd_t` can only read files of type `httpd_config_t`". Powerful but complex.
- **AppArmor** (default on Ubuntu/SUSE) — **path-based** profiles per binary. `/usr/sbin/nginx` is restricted by `/etc/apparmor.d/usr.sbin.nginx`. Simpler than SELinux, less granular.

Even **root** is restricted by MAC — that's the point.

**43. Explain the difference between threads and processes in Linux.**

In Linux, both threads and processes are created by **`clone(2)`**. The difference is the flags:

- A **process** has its own address space, file descriptors, and PID. `clone()` without `CLONE_VM` / `CLONE_FILES` (or equivalently `fork()`).
- A **thread** shares the address space, file descriptors, signal handlers, and PID with siblings, but has its own TID and stack. `clone(CLONE_VM | CLONE_FILES | CLONE_SIGHAND | CLONE_THREAD | ...)`.

Threads are cheaper to create (no page-table copy) and communicate via shared memory; processes are more isolated. `ps -eLf` shows threads; `/proc/<pid>/task/` lists them. `getpid()` returns the TGID (process); `gettid()` returns the TID.

**44. What is eBPF, and how is it used in production?**

**eBPF** ("extended Berkeley Packet Filter") is a tiny safe VM **inside the Linux kernel** that lets you attach programs to kernel events (syscalls, tracepoints, network packets, scheduler events) without writing a kernel module. Programs are verified for safety before loading, so they can't crash the kernel.

Production uses:
- **Observability**: `bpftrace`, `bcc-tools` (`biolatency`, `tcpconnect`, `execsnoop`) — low-overhead tracing
- **Networking**: **Cilium** (Kubernetes CNI), **Katran** (L4 load balancer at Meta)
- **Security**: **Falco** (runtime threat detection), syscall filtering, audit replacement
- **Performance**: profiling without `perf` overhead, custom histograms in production

eBPF is what "observability platforms" (Datadog, Pixie, Groundcover) use under the hood.

**45. How does a system call actually work? (user → kernel → return)**

```
Userspace:
  mov rax, 0          ; syscall number (0 = read)
  mov rdi, fd         ; arg 1 → first 6 args go in registers
  mov rsi, buf        ; arg 2
  mov rdx, count      ; arg 3
  syscall             ; ← traps into ring 0

Kernel:
  - CPU switches CS to kernel code segment, RSP to kernel stack
  - entry_SYSCALL_64 saves user registers
  - Looks up rax in sys_call_table → calls sys_read()
  - sys_read does the work, returns result in rax
  - Restores user registers
  - sysretq → CPU back to ring 3

Userspace:
  - rax now holds bytes read (or -errno as a negative number)
  - libc wrapper converts -errno → sets errno, returns -1
```

`strace -c` shows you which syscalls a program uses and how often. The vDSO maps a few hot syscalls (`gettimeofday`, `clock_gettime`) directly into user space to skip the trap.

**46. How would you debug a kernel panic?**

A kernel panic prints a stack trace to the console (and sometimes the journal). Recovery steps:

1. **Capture the panic** — photo of the screen, or enable **`kdump`** to write a `vmcore` to `/var/crash/` on next boot.
2. **Read the trace** — top frame is usually the offender. Look for `[<addr>] function_name+0xNN/0xMM`.
3. **Match to a module** — `lsmod`-equivalent in `vmcore` shows which driver was active.
4. **Check recent changes** — new kernel? new module? new hardware? Rolling back is often the fastest fix.
5. **Reproduce in a VM** with the same kernel, then `crash` / `gdb vmlinux vmcore` to inspect state.
6. **Boot the previous kernel** from GRUB's "Advanced options" while investigating.

Common causes: bad RAM (run `memtester` / `memtest86`), bad disk controller, buggy out-of-tree driver (NVIDIA, ZFS), kernel bug.

**47. Explain how `strace` works under the hood.**

`strace` uses **`ptrace(2)`** — a syscall that lets a tracer attach to a tracee. When the tracee enters or exits a syscall, the kernel stops it and notifies the tracer. The tracer reads registers (syscall number, args) and the tracee's memory (string contents) via `ptrace(PTRACE_PEEKDATA, ...)`.

```bash
strace -p <pid>           # attach to a running process
strace -f cmd             # follow forks
strace -c cmd             # summary table at end
strace -e openat cmd      # only specific syscalls
```

Overhead is high — every syscall doubles in cost (entry + exit stop). For production tracing, use **eBPF-based tools** (`execsnoop`, `opensnoop`) instead — kernel-level, near-zero overhead.

**48. What's the difference between a container and a VM at the kernel level?**

| Aspect          | Virtual machine                       | Container                                    |
| --------------- | ------------------------------------- | -------------------------------------------- |
| Kernel          | Each VM has its own kernel             | Shares the host kernel                       |
| Hardware        | Emulated/virtualized via hypervisor    | None — direct syscalls to host kernel        |
| Boot time       | Tens of seconds                        | Milliseconds                                 |
| Memory overhead | Hundreds of MB per VM                  | Megabytes per container                      |
| Isolation       | Strong — hardware-level (Ring -1, VT-x) | Kernel-level (namespaces + cgroups + seccomp) |
| Density         | ~10s per host                          | ~100s–1000s per host                         |
| Cross-OS        | Yes (Linux VM on Windows host)         | No — Linux container needs Linux kernel      |

A container is fundamentally a **regular Linux process** with restricted views (namespaces) and resource caps (cgroups). It's not "lightweight virtualization"; it's process isolation.

**49. How do you tune a Linux server for high-performance networking?**

```bash
# 1. Increase socket buffer sizes:
sysctl -w net.core.rmem_max=134217728
sysctl -w net.core.wmem_max=134217728
sysctl -w net.ipv4.tcp_rmem="4096 87380 134217728"
sysctl -w net.ipv4.tcp_wmem="4096 65536 134217728"

# 2. Bump backlog queues:
sysctl -w net.core.somaxconn=4096
sysctl -w net.core.netdev_max_backlog=10000
sysctl -w net.ipv4.tcp_max_syn_backlog=8192

# 3. Reuse TIME_WAIT sockets (short-lived connections):
sysctl -w net.ipv4.tcp_tw_reuse=1

# 4. BBR congestion control (better than cubic for high-bandwidth):
sysctl -w net.ipv4.tcp_congestion_control=bbr

# 5. NIC tuning:
ethtool -K eth0 gro on tso on gso on
ethtool -G eth0 rx 4096 tx 4096      # ring buffer sizes
ethtool -L eth0 combined $(nproc)    # multi-queue, one per CPU

# 6. IRQ affinity — spread NIC interrupts across CPUs:
sudo systemctl restart irqbalance
# Or pin manually via /proc/irq/<N>/smp_affinity

# 7. Raise file descriptor limits:
ulimit -n 1048576                    # session
# Persistent: /etc/security/limits.conf
```

Persist via `/etc/sysctl.d/99-network.conf`. Always benchmark before/after with `iperf3` / `wrk`.

**50. Explain how the OOM killer chooses which process to kill.**

When memory is exhausted and swap is full (or filling fast), the OOM killer walks every process and computes an **`oom_score`** (0–1000) for each. The process with the **highest score gets SIGKILL**.

Score is roughly:

```
oom_score = (RSS + swap usage) / total memory × 1000   + oom_score_adj
```

So it favors killing **big memory consumers**. Adjustments:

- **`/proc/<pid>/oom_score_adj`** — range −1000 to +1000. `-1000` = "never kill", `+1000` = "always pick me first".
- **systemd**: set `OOMScoreAdjust=` in a unit file.
- **Critical services** (sshd, init): typically `oom_score_adj=-1000`.

Check who was killed:

```bash
dmesg | grep -i "killed process"
journalctl -k --grep="Out of memory"
```

OOM events also indicate that you need **more RAM**, **lower memory cgroup limits**, or **a leak fix** — not just a higher score adjustment.

---

## Useful Tips & Tricks

- Use `man <command>` to view the manual for any command.
- Use `command --help` for a quick options summary.
- Use `history` to see previously executed commands.
- Use `Ctrl + R` to search through command history.

---

## References

- [Linux Journey on LabEx](https://labex.io/linuxjourney)
- [tldr pages](https://tldr.sh/)
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
