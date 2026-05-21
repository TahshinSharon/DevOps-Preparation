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
  <img src="https://img.shields.io/badge/Sections-4-blue?style=flat-square" alt="Sections">
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
