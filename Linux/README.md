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
</p>

---

## Table of Contents

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
