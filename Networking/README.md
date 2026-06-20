<h1 align="center">Networking Learning Notes</h1>

<p align="center">
  A personal collection of Networking commands, concepts,<br>
  and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Networking-0078D4?style=for-the-badge&logo=cisco&logoColor=white" alt="Networking">
  <img src="https://img.shields.io/badge/TCP%2FIP-1A73E8?style=for-the-badge&logo=internetexplorer&logoColor=white" alt="TCP/IP">
  <img src="https://img.shields.io/badge/DNS-4285F4?style=for-the-badge&logo=cloudflare&logoColor=white" alt="DNS">
  <img src="https://img.shields.io/badge/SSH-000000?style=for-the-badge&logo=openssh&logoColor=white" alt="SSH">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-10-blue?style=flat-square" alt="Sections">
  <img src="https://img.shields.io/badge/Level-Beginner→Intermediate-orange?style=flat-square" alt="Level">
  <img src="https://img.shields.io/badge/Status-Actively%20Updated-brightgreen?style=flat-square" alt="Status">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="../README.md"><b>Back to DevOps Prep</b></a>
  &nbsp;·&nbsp;
  <a href="../Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
</p>

---

## Table of Contents

- [Introduction](#introduction)
- [Command Note Template](#command-note-template)
- [Network Sharing](#network-sharing)
  - [One Shot Revision](#one-shot-revision)
  - [File Sharing Overview](#file-sharing-overview)
  - [rsync](#rsync)
  - [Simple HTTP Server](#simple-http-server)
  - [NFS](#nfs)
  - [Samba](#samba)
- [Networking Fundamentals](#networking-fundamentals)
  - [One Shot Revision](#one-shot-revision-1)
  - [OSI Model](#osi-model)
  - [TCP/IP Model](#tcpip-model)
  - [IP Addressing](#ip-addressing)
  - [Subnetting & CIDR](#subnetting--cidr)
  - [Ports & Protocols](#ports--protocols)
  - [MAC Addresses & ARP](#mac-addresses--arp)
- [Network Configuration](#network-configuration)
  - [One Shot Revision](#one-shot-revision-2)
  - [ip](#ip)
  - [ifconfig](#ifconfig)
  - [hostname](#hostname)
  - [/etc/hosts](#etchosts)
  - [/etc/resolv.conf](#etcresolvconf)
  - [NetworkManager (nmcli)](#networkmanager-nmcli)
- [Connectivity & Diagnostics](#connectivity--diagnostics)
  - [One Shot Revision](#one-shot-revision-3)
  - [ping](#ping)
  - [traceroute](#traceroute)
  - [mtr](#mtr)
  - [telnet](#telnet)
  - [nc (netcat)](#nc-netcat)
- [DNS Tools](#dns-tools)
  - [One Shot Revision](#one-shot-revision-4)
  - [DNS Concepts](#dns-concepts)
  - [dig](#dig)
  - [nslookup](#nslookup)
  - [host](#host)
- [Sockets & Ports](#sockets--ports)
  - [One Shot Revision](#one-shot-revision-5)
  - [ss](#ss)
  - [netstat](#netstat)
  - [lsof](#lsof)
- [HTTP & Transfer Tools](#http--transfer-tools)
  - [One Shot Revision](#one-shot-revision-6)
  - [curl](#curl)
  - [wget](#wget)
- [Remote Access](#remote-access)
  - [One Shot Revision](#one-shot-revision-7)
  - [ssh](#ssh)
  - [scp](#scp)
  - [rsync](#rsync-1)
  - [SSH Keys & Config](#ssh-keys--config)
- [Firewall & Security](#firewall--security)
  - [One Shot Revision](#one-shot-revision-8)
  - [iptables](#iptables)
  - [nftables](#nftables)
  - [ufw](#ufw)
  - [firewalld](#firewalld)
- [Packet Analysis](#packet-analysis)
  - [One Shot Revision](#one-shot-revision-9)
  - [tcpdump](#tcpdump)
  - [wireshark / tshark](#wireshark--tshark)
  - [nmap](#nmap)
- [Useful Tips & Tricks](#useful-tips--tricks)
- [References](#references)

---

## Introduction

Brief notes about Networking, the layers involved, and the goal of these notes.

- **Focus:** Linux networking stack and the tools used to inspect, configure, and troubleshoot it.
- **Scope:** OSI/TCP-IP fundamentals → addressing → diagnostics → DNS → sockets → HTTP → remote access → firewalls → packet capture.
- **Goal:** Build strong networking fundamentals for DevOps interview prep and day-to-day debugging.

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
command-name -l target
```

**Notes:**

- Any edge cases, gotchas, or related commands.

---

## Network Sharing

Make files and directories reachable from other machines on the network — from a quick one-off transfer to a permanently mounted share.

### One Shot Revision

| Topic                                            | Short Description                                                       |
| ------------------------------------------------ | ----------------------------------------------------------------------- |
| [File Sharing Overview](#file-sharing-overview)  | When to pick `scp` vs `rsync` vs HTTP vs NFS vs Samba                   |
| [`rsync`](#rsync)                                | Incremental, delta-based file sync — local or over SSH                  |
| [Simple HTTP Server](#simple-http-server)        | One-line file server with `python3 -m http.server`                      |
| [NFS](#nfs)                                      | Unix-native shared filesystem — mount a remote directory as if local    |
| [Samba](#samba)                                  | SMB/CIFS shares — interoperate with Windows clients                     |

### File Sharing Overview

**Description:** A quick map of the common ways to move or share files over a network on Linux, and when each one is the right tool.

| Method                  | Best For                                              | Transport      | Persistent Mount? |
| ----------------------- | ----------------------------------------------------- | -------------- | ----------------- |
| `scp`                   | One-shot file copy over SSH                           | SSH (TCP/22)   | No                |
| `rsync`                 | Repeated syncs — copies only what changed             | SSH or rsyncd  | No                |
| `python3 -m http.server`| Quick read-only download server for a directory       | HTTP (TCP)     | No                |
| **NFS**                 | Sharing dirs between Linux/Unix hosts                 | NFS (TCP/2049) | Yes (`mount`)     |
| **Samba (SMB/CIFS)**    | Sharing dirs with Windows/macOS clients               | SMB (TCP/445)  | Yes (`mount`)     |

**How to choose:**

- **Need it once?** Use `scp` or a simple HTTP server.
- **Need to keep two trees in sync (backups, deploys)?** Use `rsync`.
- **Need it to look like a local directory all the time?** Use **NFS** (Linux-only world) or **Samba** (mixed-OS world).

**Notes:**

- File sharing always sits on top of networking — if you can't `ping` or open the right port, nothing else will work.
- Always think about **permissions** on both sides: the user/group on the server has to match (or be mapped to) the user on the client.
- Open the right firewall ports: SSH `22`, HTTP `80`/`8000`, NFS `2049`, Samba `445`.

### rsync

**Description:** **Remote Sync** — copies files between two locations and only transfers the **differences** between them, making repeat copies very fast. Works locally, over SSH, or against an `rsyncd` server.

**Syntax:**

```bash
rsync [options] SOURCE DESTINATION
```

**Common Options:**

| Option         | Description                                                       |
| -------------- | ----------------------------------------------------------------- |
| `-a`           | Archive mode — preserves permissions, timestamps, symlinks, etc.  |
| `-v`           | Verbose — show files being transferred.                           |
| `-z`           | Compress data during transfer.                                    |
| `-P`           | Show progress and keep partial files on interruption.             |
| `--delete`     | Delete files on destination that no longer exist on source.       |
| `-n` / `--dry-run` | Show what would be transferred without copying anything.      |
| `-e ssh`       | Force the use of SSH as the transport (default for remote paths). |

**Examples:**

```bash
# Sync a local folder to a remote host over SSH
rsync -avzP ./site/ user@server:/var/www/site/

# Mirror a remote folder down to local, deleting local files that are gone remotely
rsync -avz --delete user@server:/var/www/site/ ./site/

# Dry-run to preview changes before actually syncing
rsync -avzn ./src/ backup:/backups/src/
```

**Notes:**

- A **trailing slash** on the source (`./site/`) means "copy the **contents** of this directory". Without it, the directory itself is copied inside the destination.
- `rsync` is idempotent — running it twice is safe; the second run does almost nothing if nothing changed.
- For very large transfers, `-P` (`--partial --progress`) lets you resume after a dropped connection.
- Also covered under [Remote Access](#rsync-1) — same tool, listed here for its file-sharing role.

### Simple HTTP Server

**Description:** A one-line, read-only file server you can spin up in any directory to share files over HTTP — perfect for quick file drops to teammates, VMs, or other machines on the LAN.

**Syntax:**

```bash
python3 -m http.server [PORT] [--bind ADDRESS] [--directory PATH]
```

**Common Options:**

| Option            | Description                                                       |
| ----------------- | ----------------------------------------------------------------- |
| `PORT`            | Port to listen on (default `8000`).                               |
| `--bind ADDRESS`  | Bind to a specific IP (default all interfaces).                   |
| `--directory DIR` | Serve files from `DIR` instead of the current directory.          |

**Examples:**

```bash
# Serve the current directory on port 8000
python3 -m http.server 8000

# Serve a specific directory on a custom port, LAN-accessible
python3 -m http.server 9000 --directory /tmp/share --bind 0.0.0.0

# On the client, download a file
curl -O http://server-ip:9000/somefile.tar.gz
# or
wget http://server-ip:9000/somefile.tar.gz
```

**Notes:**

- **Read-only and unauthenticated** — anyone who can reach the port can list and download every file in the served directory. Don't use it on untrusted networks or for sensitive data.
- Stop the server with `Ctrl + C`.
- Ports below 1024 (e.g. `80`) require `sudo`.
- For an even simpler PHP equivalent: `php -S 0.0.0.0:8000`. For Node: `npx serve`.
- This is great as a temporary share — for permanent serving use Nginx, Apache, or Caddy.

### NFS

**Description:** **Network File System** — a Unix-native protocol that lets a client `mount` a directory exported by an NFS server and use it as if it were a local filesystem.

**Server side (export a directory):**

```bash
# Install (Debian/Ubuntu)
sudo apt install nfs-kernel-server

# Add an export to /etc/exports
# Format: <path>  <client>(<options>)
# Example: share /srv/nfs with the 192.168.1.0/24 subnet, read-write
echo '/srv/nfs 192.168.1.0/24(rw,sync,no_subtree_check)' | sudo tee -a /etc/exports

# Re-read exports and (re)start the service
sudo exportfs -ra
sudo systemctl restart nfs-server
```

**Client side (mount the export):**

```bash
# Install client utilities
sudo apt install nfs-common

# Create a mount point and mount it
sudo mkdir -p /mnt/nfs
sudo mount -t nfs server-ip:/srv/nfs /mnt/nfs

# List the share now visible locally
ls /mnt/nfs

# Mount automatically at boot — add to /etc/fstab
# server-ip:/srv/nfs  /mnt/nfs  nfs  defaults  0  0
```

**Common Export Options:**

| Option              | Description                                                       |
| ------------------- | ----------------------------------------------------------------- |
| `rw` / `ro`         | Read-write or read-only access.                                   |
| `sync` / `async`    | Reply only after writes hit disk / reply immediately.             |
| `no_subtree_check`  | Skip subtree checks — faster, recommended for whole-disk exports. |
| `root_squash`       | Map remote `root` to an unprivileged user (default, safer).       |
| `no_root_squash`    | Let remote `root` act as local `root` — use with care.            |

**Notes:**

- NFS uses **TCP port 2049** — make sure the firewall on the server allows it from the client's network.
- **User mapping** matters: NFS authenticates by UID/GID by default, so user `1000` on the client maps to user `1000` on the server. Mismatched UIDs cause "permission denied" errors that look like network issues.
- Prefer **NFSv4** (default on modern distros) over NFSv3 — simpler firewalling and built-in security features.
- Check what's currently mounted: `mount | grep nfs` or `df -hT -t nfs4`.
- Unmount with `sudo umount /mnt/nfs`.

### Samba

**Description:** **Samba** implements the **SMB/CIFS** protocol on Linux, letting Linux servers share files (and printers) with Windows, macOS, and other Linux clients exactly the way Windows file shares work.

**Server side (share a directory):**

```bash
# Install Samba (Debian/Ubuntu)
sudo apt install samba

# Create a Samba user (must already exist as a Linux user)
sudo smbpasswd -a tarek

# Add a share definition to /etc/samba/smb.conf
# Append this block:
# [share]
#    path = /srv/samba/share
#    browseable = yes
#    read only = no
#    valid users = tarek

# Make the directory and fix permissions
sudo mkdir -p /srv/samba/share
sudo chown tarek:tarek /srv/samba/share

# Validate the config and restart
testparm
sudo systemctl restart smbd nmbd
```

**Client side (mount the share):**

```bash
# Install client utilities
sudo apt install cifs-utils

# List shares offered by a server
smbclient -L //server-ip -U tarek

# Mount the share
sudo mkdir -p /mnt/samba
sudo mount -t cifs //server-ip/share /mnt/samba \
    -o username=tarek,uid=$(id -u),gid=$(id -g)

# On Windows, just open:  \\server-ip\share
# On macOS Finder:        Cmd+K → smb://server-ip/share
```

**Common smb.conf Options:**

| Option            | Description                                                       |
| ----------------- | ----------------------------------------------------------------- |
| `path`            | Directory on the server being shared.                             |
| `browseable`      | Whether the share shows up in network browse lists.               |
| `read only`       | `yes` = read-only; `no` = read-write.                             |
| `valid users`     | Comma-separated list of users allowed to connect.                 |
| `guest ok`        | Allow unauthenticated access if `yes`.                            |
| `create mask`     | Default permissions for new files (e.g. `0644`).                  |

**Notes:**

- Samba uses **TCP port 445** (modern SMB). Older `139` is only needed for legacy NetBIOS.
- Samba users are **separate from Linux users** — even when the username matches, you still have to run `smbpasswd -a <user>` to set their SMB password.
- Always validate your config with `testparm` before restarting `smbd`.
- For mixed Linux/Windows shops, Samba is usually the right choice. For Linux-only, **NFS is simpler and faster**.
- Common gotcha: file permissions on the underlying directory still apply on top of Samba's rules — if Linux says "no", Samba says "no" too.

---

## Networking Fundamentals

The core concepts every command in this guide is built on — how data moves between hosts and how it's addressed.

### One Shot Revision

| Topic                                       | Short Description                                                       |
| ------------------------------------------- | ----------------------------------------------------------------------- |
| [OSI Model](#osi-model)                     | 7-layer reference model: Physical → Data Link → … → Application         |
| [TCP/IP Model](#tcpip-model)                | The 4-layer model that the real internet actually runs on               |
| [IP Addressing](#ip-addressing)             | IPv4 vs IPv6, public vs private, static vs DHCP                         |
| [Subnetting & CIDR](#subnetting--cidr)      | Splitting networks with `/24`-style masks                               |
| [Ports & Protocols](#ports--protocols)      | TCP vs UDP, well-known ports, ephemeral ports                           |
| [MAC Addresses & ARP](#mac-addresses--arp)  | Layer-2 identity and how IP maps to MAC on a LAN                        |

### OSI Model

_To be filled in._

### TCP/IP Model

_To be filled in._

### IP Addressing

_To be filled in._

### Subnetting & CIDR

_To be filled in._

### Ports & Protocols

_To be filled in._

### MAC Addresses & ARP

_To be filled in._

---

## Network Configuration

Inspect and change interface settings, addresses, routes, and name resolution on a Linux host.

### One Shot Revision

| Command                                       | Short Description                                          |
| --------------------------------------------- | ---------------------------------------------------------- |
| [`ip`](#ip)                                   | The modern Swiss-army tool for interfaces, addrs, routes   |
| [`ifconfig`](#ifconfig)                       | Legacy interface tool (still common in older distros)      |
| [`hostname`](#hostname)                       | Show or set the system hostname                            |
| [`/etc/hosts`](#etchosts)                     | Static hostname → IP overrides, queried before DNS         |
| [`/etc/resolv.conf`](#etcresolvconf)          | Configured DNS resolvers and search domains                |
| [`nmcli`](#networkmanager-nmcli)              | NetworkManager CLI — manage connections and devices        |

### ip

_To be filled in._

### ifconfig

_To be filled in._

### hostname

_To be filled in._

### /etc/hosts

_To be filled in._

### /etc/resolv.conf

_To be filled in._

### NetworkManager (nmcli)

_To be filled in._

---

## Connectivity & Diagnostics

First-line tools for answering "can I reach that host, and if not, where does it break?"

### One Shot Revision

| Command                         | Short Description                                                |
| ------------------------------- | ---------------------------------------------------------------- |
| [`ping`](#ping)                 | Send ICMP echoes to test reachability and round-trip time        |
| [`traceroute`](#traceroute)     | Show the hops packets take to reach a destination                |
| [`mtr`](#mtr)                   | Combined `ping` + `traceroute` with continuous per-hop stats     |
| [`telnet`](#telnet)             | Open a raw TCP connection to a host:port (handy for port checks) |
| [`nc`](#nc-netcat)              | Netcat — read/write TCP & UDP, simple servers, port scans        |

### ping

_To be filled in._

### traceroute

_To be filled in._

### mtr

_To be filled in._

### telnet

_To be filled in._

### nc (netcat)

_To be filled in._

---

## DNS Tools

Resolve names to addresses and inspect every layer of the lookup chain.

### One Shot Revision

| Command                       | Short Description                                            |
| ----------------------------- | ------------------------------------------------------------ |
| [DNS Concepts](#dns-concepts) | Records (A, AAAA, CNAME, MX, TXT, NS), TTL, recursion        |
| [`dig`](#dig)                 | The go-to DNS lookup tool — detailed, scriptable             |
| [`nslookup`](#nslookup)       | Interactive DNS lookup, still widely used                    |
| [`host`](#host)               | Simple, quick name → address lookups                         |

### DNS Concepts

_To be filled in._

### dig

_To be filled in._

### nslookup

_To be filled in._

### host

_To be filled in._

---

## Sockets & Ports

See which processes are listening, which connections are open, and which ports are in use.

### One Shot Revision

| Command               | Short Description                                              |
| --------------------- | -------------------------------------------------------------- |
| [`ss`](#ss)           | Modern replacement for `netstat` — fast and detailed           |
| [`netstat`](#netstat) | Legacy socket/port lister (still common in old runbooks)       |
| [`lsof`](#lsof)       | List open files & sockets, mapped to processes                 |

### ss

_To be filled in._

### netstat

_To be filled in._

### lsof

_To be filled in._

---

## HTTP & Transfer Tools

Fetch URLs, inspect HTTP headers, and move files over the network.

### One Shot Revision

| Command         | Short Description                                            |
| --------------- | ------------------------------------------------------------ |
| [`curl`](#curl) | Make HTTP(S) requests; inspect headers, status, timings      |
| [`wget`](#wget) | Download files recursively, resume interrupted downloads     |

### curl

_To be filled in._

### wget

_To be filled in._

---

## Remote Access

Log in to remote hosts and move files between them — the daily bread of any DevOps role.

### One Shot Revision

| Command                                 | Short Description                                          |
| --------------------------------------- | ---------------------------------------------------------- |
| [`ssh`](#ssh)                           | Encrypted remote shell over TCP/22                         |
| [`scp`](#scp)                           | Copy files over SSH                                        |
| [`rsync`](#rsync-1)                     | Efficient incremental file sync — local or over SSH        |
| [SSH Keys & Config](#ssh-keys--config)  | Key generation, `~/.ssh/config`, agent forwarding          |

### ssh

_To be filled in._

### scp

_To be filled in._

### rsync

_To be filled in._

### SSH Keys & Config

_To be filled in._

---

## Firewall & Security

Allow, drop, and rewrite traffic at the host level.

### One Shot Revision

| Command                   | Short Description                                            |
| ------------------------- | ------------------------------------------------------------ |
| [`iptables`](#iptables)   | Classic netfilter rule manager (still everywhere)            |
| [`nftables`](#nftables)   | Modern replacement for `iptables` — unified ruleset syntax   |
| [`ufw`](#ufw)             | Uncomplicated Firewall — Ubuntu-friendly frontend            |
| [`firewalld`](#firewalld) | Zone-based firewall daemon (RHEL/CentOS/Fedora)              |

### iptables

_To be filled in._

### nftables

_To be filled in._

### ufw

_To be filled in._

### firewalld

_To be filled in._

---

## Packet Analysis

Look at what's actually on the wire when the higher-level tools don't tell the full story.

### One Shot Revision

| Command                                    | Short Description                                            |
| ------------------------------------------ | ------------------------------------------------------------ |
| [`tcpdump`](#tcpdump)                      | CLI packet capture — filter, dump, save as `.pcap`           |
| [`wireshark / tshark`](#wireshark--tshark) | GUI / CLI deep-dive packet analysis with full dissection     |
| [`nmap`](#nmap)                            | Port scanner & host/service discovery tool                   |

### tcpdump

_To be filled in._

### wireshark / tshark

_To be filled in._

### nmap

_To be filled in._

---

## Useful Tips & Tricks

- Use `ip a` (short for `ip address show`) for a quick view of every interface and its IP.
- Use `ss -tulpn` to list every listening TCP/UDP socket with the owning process.
- Use `curl -I https://example.com` to see only response headers — great for cache and redirect debugging.
- Use `dig +short example.com` for a one-line answer instead of the full DNS dump.
- Use `traceroute -n` to skip reverse-DNS lookups when hops are slow to resolve.

---

## References

- [Linux Journey on LabEx](https://labex.io/linuxjourney)
- [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/)
- [RFC Editor](https://www.rfc-editor.org/)
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
