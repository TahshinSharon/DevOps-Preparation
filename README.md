<h1 align="center">DevOps Preparation</h1>

<p align="center">
  A personal knowledge base of notes, commands, and concepts<br>
  compiled while preparing for DevOps interviews and day-to-day work.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Bash">
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Actively%20Updated-brightgreen?style=flat-square" alt="Status">
  <img src="https://img.shields.io/badge/Topics-3-blue?style=flat-square" alt="Topics">
  <img src="https://img.shields.io/badge/Made%20For-DevOps%20Prep-orange?style=flat-square" alt="Made For">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="./Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Networking/README.md"><b>Networking Notes</b></a>
</p>

---

## Table of Contents

- [About This Repository](#about-this-repository)
- [Repository Structure](#repository-structure)
- [How to Read This Repo](#how-to-read-this-repo)
- [Sections](#sections)
  - [Linux](#linux)
  - [Git & GitHub](#git--github)
  - [Networking](#networking)
- [Conventions](#conventions)
- [Contributing / Personal Use](#contributing--personal-use)
- [References](#references)

---

## About This Repository

This repo is my **DevOps learning journal** — a growing collection of focused notes on the tools and concepts that show up most often in real-world DevOps work and interviews. Every page follows the same template so revision feels predictable: a short concept intro, a **One Shot Revision** table for fast recall, then a deep dive on each command with syntax, options, examples, and gotchas.

**Why this exists:**

- Force me to **explain** what I learn (the best way to retain it).
- Keep one searchable reference instead of scattered scratch notes.
- Share the structure with anyone else preparing for DevOps roles.

---

## Repository Structure

```
DevOps-Preparation/
├── README.md                ← you are here
├── Linux/
│   └── README.md            ← Linux commands, text formating, user management, ...
├── Git-Github/
│   └── README.md            ← Git workflows, branching, GitHub & gh CLI, Actions, ...
└── Networking/
    └── README.md            ← OSI/TCP-IP, ip/ss/dig/curl/ssh, firewalls, packet capture, ...
```

Every topic folder holds a single `README.md` that acts as the full reference for that subject. New topics (Docker, Kubernetes, CI/CD, Networking, Cloud, etc.) will be added the same way — one folder, one self-contained `README.md`.

---

## How to Read This Repo

Each section README is structured for **two reading modes**:

1. **Quick revision (5–10 min)** — open a section and read just the **One Shot Revision** table at the top of each subsection. It's a compact list of every command in that section with one-line descriptions.
2. **Deep dive** — click any command in the One Shot Revision table to jump to its full entry: description, syntax, options table, examples, and notes.

Inside every command entry you'll find:

| Block            | What it gives you                                                    |
| ---------------- | -------------------------------------------------------------------- |
| **Description**  | One or two sentences on what the command does and when to use it.    |
| **Syntax**       | The general form, including common flags.                            |
| **Common Options** | Table of the flags you actually use in practice.                   |
| **Examples**     | Runnable snippets with a comment explaining what each one does.      |
| **Notes**        | Edge cases, related commands, and "gotchas" worth remembering.       |

**Recommended path:**

1. Skim a section's **Table of Contents** to see what's covered.
2. Read the **One Shot Revision** table for a high-level map.
3. Drill into the specific commands you don't already know cold.
4. Come back and re-skim the One Shot Revision before an interview.

---

## Sections

### Linux

Foundational shell skills — the bread and butter of any DevOps role.

- **Basic Commands** — `pwd`, `cd`, `ls`, `cp`, `mv`, `rm`, `find`, `man`, ...
- **Text-Formating** — pipes, redirection, `cut`, `sort`, `uniq`, `grep`, `wc`, ...
- **Advanced Text-Formating** — regular expressions and the `vim` editor.
- **User Management** — `/etc/passwd`, `/etc/shadow`, `useradd`, `usermod`, `sudo`, root.
- **Permissions** — file permission bits (`rwx`), user/group/other classes, symbolic vs octal notation.

→ [Open the Linux notes](./Linux/README.md)

### Git & GitHub

Distributed version control plus the collaboration layer on top.

- **Git Basics** — `init`, `clone`, `config`, `status`.
- **Working with Changes** — `add`, `commit`, `diff`, `log`, `.gitignore`.
- **Branching & Merging** — `branch`, `switch`, `merge`, `rebase`, `cherry-pick`.
- **Remote Repositories** — `remote`, `fetch`, `pull`, `push`, SSH vs HTTPS.
- **Undoing Changes** — `restore`, `reset`, `revert`, `clean`, `reflog`.
- **Stashing & Tagging** — `stash`, `tag`.
- **Advanced Git** — `bisect`, `blame`, `submodule`, `worktree`, hooks.
- **GitHub & Collaboration** — SSH keys, PR workflow, `gh` CLI, GitHub Actions.

→ [Open the Git & GitHub notes](./Git-Github/README.md)

### Networking

The Linux networking stack and the tools used to inspect, configure, and troubleshoot it.

- **Network Sharing** — file sharing overview, `rsync`, simple HTTP server, NFS, Samba.
- **Networking Fundamentals** — network basics (components, LAN/WAN/WLAN, hosts & packets), OSI/TCP-IP models, per-layer deep-dives (application, transport, network, link), IP addressing, DHCP, ports, ARP.
- **Subnetting** — subnets & broadcast domains, subnet math, mental-math cheats, CIDR & supernetting, IPv4 with VLSM, NAT (SNAT/DNAT/PAT/CGNAT), IPv6 (`/64`, SLAAC, NDP).
- **Network Configuration** — `ip`, `ifconfig`, `hostname`, `/etc/hosts`, `nmcli`.
- **Connectivity & Diagnostics** — `ping`, `traceroute`, `mtr`, `telnet`, `nc`.
- **DNS Tools** — `dig`, `nslookup`, `host`.
- **Sockets & Ports** — `ss`, `netstat`, `lsof`.
- **HTTP & Transfer Tools** — `curl`, `wget`.
- **Remote Access** — `ssh`, `scp`, `rsync`, SSH keys & config.
- **Firewall & Security** — `iptables`, `nftables`, `ufw`, `firewalld`.
- **Packet Analysis** — `tcpdump`, `wireshark`/`tshark`, `nmap`.

→ [Open the Networking notes](./Networking/README.md)

---

## Conventions

A few patterns I follow throughout the repo so things stay consistent:

- **Markdown only** — no slide decks or PDFs; everything is plain text so it diffs cleanly in Git.
- **GitHub-flavored Markdown** — tables, fenced code blocks (` ```bash `), and anchor links.
- **Bold for emphasis**, _italics_ for terms being defined, `inline code` for commands and paths.
- **Imperative, present-tense** descriptions ("Print the working directory", not "This will print...").
- **Examples are runnable** — every snippet should be safe to copy-paste into a terminal.
- **Notes call out gotchas** — anything destructive, surprising, or commonly forgotten lives at the bottom of an entry under **Notes**.
- **Commit messages follow `Type: Subject`** — e.g. `Chore: Complete User Management section`, `Fix: Correct grep example`.

---

## Contributing / Personal Use

This is primarily a **personal learning repo**, but feel free to:

- Fork it and adapt the structure for your own DevOps prep.
- Open an issue if you spot a factual mistake or a broken link.
- Suggest a new section via a pull request — keep the same structure (One Shot Revision + per-command entries).

---

## References

- [BongoDev](https://www.bongodev.com/)
- [BongoDev on GitHub](https://github.com/bongodev)
- [Linux Journey on LabEx](https://labex.io/linuxjourney)
- [Pro Git book (free)](https://git-scm.com/book/en/v2)
- [GitHub Docs](https://docs.github.com/)
- [tldr pages](https://tldr.sh/)

---

<p align="center">
  <sub>Built and maintained by <b>Tahshin Sharon</b></sub>
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/TahshinSharon"><b>GitHub</b></a>
</p>

<p align="center">
  <sub>If this helped you, consider giving the repo a star — it keeps me writing.</sub>
</p>
