# Linux Learning Notes

A personal collection of Linux commands, concepts, and notes gathered while learning.

---

## Table of Contents

- [Introduction](#introduction)
- [Command Note Template](#command-note-template)
- [Text-Fu](#text-fu)
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
- [Advanced Text-Fu](#advanced-text-fu)
  - [regex (Regular Expressions)](#regex-regular-expressions)
  - [vim editor](#vim-editor)
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

| Option | Description |
| ------ | ----------- |
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

## Text-Fu

Notes on text processing commands in Linux — viewing, searching, filtering, and transforming text.

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
`ls -la /etc` lists `/etc`. `|` **pipes** that output into `tee`, which **saves** a full copy to `etc_listing.txt` *and* passes it on. The next `|` sends it to `grep "conf"`, which prints only lines containing `conf`.

### `env` (Environment)

**Description:** **Environment variables** are named values stored by the shell that programs can read — they hold things like your username (`USER`), home directory (`HOME`), search path (`PATH`), language (`LANG`), etc. The `env` command prints them; `export` sets new ones.

**Syntax:**
```bash
env
echo $VAR
export VAR=value
```

**Common Options / Forms:**

| Form              | Description |
| ----------------- | ----------- |
| `env`             | Lists all environment variables in the current shell. |
| `echo $VAR`       | Prints the value of a single variable. |
| `export VAR=val`  | Sets a variable and makes it available to child processes. |
| `unset VAR`       | Removes a variable from the environment. |

**Persisting env values across all sessions — Shell Configuration Files:**

`export` in a terminal only lasts for that shell session. To make a variable available **every time** you open a new shell, add the `export` line to your shell's startup config file:

| Shell | Config file |
| ----- | ----------- |
| Bash  | `~/.bashrc` (non-login interactive shells; also `~/.bash_profile` / `~/.profile` for login shells) |
| Zsh   | `~/.zshrc` |
| Fish  | `~/.config/fish/config.fish` |

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

| Option | Description |
| ------ | ----------- |
| `-d`   | Set the **delimiter** (e.g. `","`, `";"`, `":"`). Default is TAB. |
| `-f`   | Pick which **field(s)** to keep (e.g. `-f 1`, `-f 1,3`, `-f 2-4`). |
| `-c`   | Pick characters by position (e.g. `-c 1-5`). |

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

| Option | Description |
| ------ | ----------- |
| `-d`   | Set the **delimiter** between joined fields (default is TAB). |
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

| Option | Description |
| ------ | ----------- |
| `-n N` | Print the first **N** lines (instead of the default 10). |
| `-c N` | Print the first **N** bytes. |

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

| Option | Description |
| ------ | ----------- |
| `-n N` | Print the last **N** lines (instead of the default 10). |
| `-f`   | **Follow** the file — keep printing new lines as they get appended. |
| `-c N` | Print the last **N** bytes. |

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

| Option   | Description |
| -------- | ----------- |
| `-t N`   | Use **N** spaces per tab instead of 8. |
| `-i`     | Only convert tabs at the **start** of a line (leading tabs). |

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

| Option   | Description |
| -------- | ----------- |
| `-a`     | Convert **all** runs of spaces to tabs (not just leading whitespace). |
| `-t N`   | Treat **N** spaces as one tab. |

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

| Option   | Description |
| -------- | ----------- |
| `-1 N`   | Use field **N** of **file1** as the join key. |
| `-2 N`   | Use field **N** of **file2** as the join key. |
| `-t C`   | Set the field separator to character **C** (default is whitespace). |

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

| Option   | Description |
| -------- | ----------- |
| `-l N`   | Split every **N lines** per file. |
| `-b SIZE`| Split by **byte size** (e.g. `-b 1M`, `-b 500K`). |
| `-d`     | Use **numeric** suffixes (`x00`, `x01`, ...) instead of letters. |

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

| Option | Description |
| ------ | ----------- |
| `-n`   | **Numeric** sort — compare lines as numbers instead of text. |
| `-r`   | **Reverse** order. |
| `-u`   | Output only **unique** lines (drop duplicates). |
| `-k N` | Sort by **field N** (e.g. `-k 2` sorts on the 2nd column). |

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

| Option | Description |
| ------ | ----------- |
| `-d`   | **Delete** characters in SET1. |
| `-s`   | **Squeeze** repeated characters in SET1 into a single one. |
| `-c`   | **Complement** — operate on characters **not** in SET1. |

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

| Option | Description |
| ------ | ----------- |
| `-c`   | Prefix each line with its **count** of occurrences. |
| `-d`   | Print **only duplicated** lines. |
| `-u`   | Print **only unique** lines (those appearing exactly once). |
| `-i`   | Case-insensitive comparison. |

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

| Option | Description |
| ------ | ----------- |
| `-l`   | Count **lines** only. |
| `-w`   | Count **words** only. |
| `-c`   | Count **bytes**. |
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

| Option   | Description |
| -------- | ----------- |
| `-b a`   | Number **all** lines (including blank ones). |
| `-b t`   | Number only **non-empty** lines (default). |
| `-n ln`  | Number format: left-justified (`ln`), right-justified (`rn`), or zero-padded (`rz`). |
| `-w N`   | Width of the line number column. |

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

**Description:** Searches input for lines that **match a pattern** and prints them. The name comes from `g/re/p` — *globally search for a regular expression and print*. One of the most-used tools in Linux.

**Syntax:**
```bash
grep [options] PATTERN [file...]
```

**Common Options:**

| Option | Description |
| ------ | ----------- |
| `-i`   | **Case-insensitive** match. |
| `-v`   | **Invert** — show lines that do **not** match. |
| `-n`   | Show **line numbers** with each match. |
| `-r`   | **Recursively** search through directories. |
| `-w`   | Match **whole words** only. |
| `-c`   | Print only the **count** of matching lines. |
| `-E`   | Use **extended** regex (so `+`, `?`, `|`, `()` work without escaping). |

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

## Advanced Text-Fu

Notes on more advanced text-processing tools — pattern matching, scripting, and stream editing.

### `regex` (Regular Expressions)

**Description:** A **regular expression** (regex) is a mini-language for describing **patterns** in text. Tools like `grep`, `sed`, `awk`, and many programming languages use regex to search, match, and transform strings. There are two common flavors on Linux: **BRE** (Basic Regular Expressions — used by `grep` by default) and **ERE** (Extended — used by `grep -E` / `egrep`).

**Syntax:**
```bash
grep "PATTERN" file
grep -E "PATTERN" file     # extended regex
sed -E 's/PATTERN/REPL/g' file
```

**Common Metacharacters:**

| Pattern   | Meaning |
| --------- | ------- |
| `.`       | Match **any single character** (except newline). |
| `^`       | **Anchor** — start of a line. |
| `$`       | **Anchor** — end of a line. |
| `*`       | Match the previous element **0 or more** times. |
| `+`       | Match the previous element **1 or more** times (ERE). |
| `?`       | Match the previous element **0 or 1** times (ERE). |
| `[abc]`   | **Character class** — match any one of `a`, `b`, `c`. |
| `[^abc]`  | **Negated** class — match any character **not** in the set. |
| `[a-z]`   | **Range** — match any lowercase letter. |
| `\|`      | **Alternation** — match left OR right (ERE). |
| `(...)`   | **Group** patterns together (ERE). |
| `{n,m}`   | Match the previous element between **n** and **m** times. |
| `\d` `\w` `\s` | Digit / word-char / whitespace (Perl regex, `grep -P`). |

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

| Mode        | How to enter         | Purpose |
| ----------- | -------------------- | ------- |
| **Normal**  | Default / press `Esc`| Navigate, delete, copy, paste — keystrokes are **commands**, not text. |
| **Insert**  | `i`, `a`, `o`, etc.  | Type text like a normal editor. |
| **Visual**  | `v`, `V`, `Ctrl+v`   | Select text by character / line / block. |
| **Command** | `:` from Normal mode | Run `:w`, `:q`, search/replace, settings, etc. |

**Common Commands:**

| Keys / Command  | Action |
| --------------- | ------ |
| `i`             | Enter **Insert** mode at the cursor. |
| `a`             | Enter Insert mode **after** the cursor. |
| `o`             | Open a **new line below** and enter Insert mode. |
| `O`             | Open a new line **above** and enter Insert mode. |
| `Esc`           | Return to **Normal** mode. |
| `h` `j` `k` `l` | Move **left / down / up / right**. |
| `w` / `b`       | Jump to next / previous **word**. |
| `0` / `^` / `$` | Go to **start of line** / first non-blank / **end of line**. |
| `gg` / `G`      | Go to **top** / **bottom** of file. |
| `:N`            | Jump to **line N** (e.g. `:42`). |
| `x`             | **Delete** the character under the cursor. |
| `dd`            | **Delete (cut) the current line**. |
| `yy`            | **Yank (copy) the current line**. |
| `p` / `P`       | **Paste** after / before the cursor. |
| `u`             | **Undo** last change. |
| `Ctrl + r`      | **Redo**. |
| `/pattern`      | **Search** forward for `pattern` (then `n` / `N` for next / previous). |
| `:%s/old/new/g` | **Replace** every `old` with `new` in the whole file. |
| `:w`            | **Write** (save) the file. |
| `:q`            | **Quit** Vim. |
| `:wq` or `ZZ`   | Save **and** quit. |
| `:q!`           | Quit **without** saving (discard changes). |

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

## Useful Tips & Tricks


- Use `man <command>` to view the manual for any command.
- Use `command --help` for a quick options summary.
- Use `history` to see previously executed commands.
- Use `Ctrl + R` to search through command history.

---

## References

- [Linux Journey on LabEx](https://labex.io/linuxjourney)
- [tldr pages](https://tldr.sh/)
