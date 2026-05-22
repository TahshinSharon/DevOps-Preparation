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
  <img src="https://img.shields.io/badge/Sections-5-blue?style=flat-square" alt="Sections">
  <img src="https://img.shields.io/badge/Level-Beginner→Intermediate-orange?style=flat-square" alt="Level">
  <img src="https://img.shields.io/badge/Status-Actively%20Updated-brightgreen?style=flat-square" alt="Status">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="../README.md"><b>Back to DevOps Prep</b></a>
  &nbsp;·&nbsp;
  <a href="../Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
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
