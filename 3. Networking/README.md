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
  <img src="https://img.shields.io/badge/Sections-12-blue?style=flat-square" alt="Sections">
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
  <a href="../Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Cloud-Engineering/README.md"><b>Cloud Engineering Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Docker/README.md"><b>Docker Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Kubernetes/README.md"><b>Kubernetes Notes</b></a>
</p>

---

> 🎯 **[Common Interview Questions →](#common-interview-questions)** &nbsp;·&nbsp; 50 Networking interview questions (10 Easy · 20 Medium · 20 Hard) for DevOps / Cloud Engineer roles.

---

## Table of Contents

- [Common Interview Questions](#common-interview-questions)
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
  - [Network Basics](#network-basics)
    - [Core Network Components](#core-network-components)
    - [Understanding Network Types: WAN, LAN, and WLAN](#understanding-network-types-wan-lan-and-wlan)
    - [Hosts and Packets](#hosts-and-packets)
  - [OSI Model](#osi-model)
    - [Overview](#overview)
  - [TCP/IP Model](#tcpip-model)
    - [Basic](#basic)
    - [The Four Layers of the TCP/IP Model](#the-four-layers-of-the-tcpip-model)
  - [Network Addressing](#network-addressing)
  - [Application Layer](#application-layer)
  - [Transport Layer](#transport-layer)
  - [Network Layer](#network-layer)
  - [Link Layer](#link-layer)
  - [DHCP Overview](#dhcp-overview)
  - [Ports & Protocols](#ports--protocols)
  - [MAC Addresses & ARP](#mac-addresses--arp)
- [Subnetting](#subnetting)
  - [One Shot Revision](#one-shot-revision-2)
  - [Subnets](#subnets)
  - [Subnet Math](#subnet-math)
  - [Subnetting Cheats](#subnetting-cheats)
  - [CIDR](#cidr)
  - [IPv4](#ipv4)
  - [NAT](#nat)
  - [IPv6](#ipv6)
- [Routing](#routing)
  - [One Shot Revision](#one-shot-revision-3)
  - [Routing Basics](#routing-basics)
  - [Routing Table](#routing-table)
  - [Path of a Packet](#path-of-a-packet)
  - [Default Gateway](#default-gateway)
  - [Static vs Dynamic Routing](#static-vs-dynamic-routing)
  - [Routing Protocols](#routing-protocols)
  - [Distance Vector Protocols](#distance-vector-protocols)
  - [Link State Protocols](#link-state-protocols)
  - [Border Gateway Protocol](#border-gateway-protocol)
  - [IGP vs EGP](#igp-vs-egp)
  - [Linux Routing](#linux-routing)
- [Network Configuration](#network-configuration)
  - [One Shot Revision](#one-shot-revision-4)
  - [ip](#ip)
  - [Network Interfaces](#network-interfaces)
  - [ifconfig](#ifconfig)
  - [route](#route)
  - [hostname](#hostname)
  - [/etc/hosts](#etchosts)
  - [/etc/resolv.conf](#etcresolvconf)
  - [NetworkManager (nmcli)](#networkmanager-nmcli)
  - [dhclient](#dhclient)
  - [arp](#arp)
- [Connectivity & Diagnostics](#connectivity--diagnostics)
  - [One Shot Revision](#one-shot-revision-5)
  - [ICMP](#icmp)
  - [ping](#ping)
  - [traceroute](#traceroute)
  - [netstat](#netstat)
  - [mtr](#mtr)
  - [telnet](#telnet)
  - [nc (netcat)](#nc-netcat)
- [DNS Tools](#dns-tools)
  - [One Shot Revision](#one-shot-revision-6)
  - [What is DNS](#what-is-dns)
  - [DNS Components](#dns-components)
  - [DNS Process](#dns-process)
  - [/etc/hosts](#etchosts-1)
  - [DNS Setup](#dns-setup)
  - [DNS Tools](#dns-tools-1)
  - [dig](#dig)
  - [nslookup](#nslookup)
  - [host](#host)
- [Sockets & Ports](#sockets--ports)
  - [One Shot Revision](#one-shot-revision-7)
  - [ss](#ss)
  - [lsof](#lsof)
- [HTTP & Transfer Tools](#http--transfer-tools)
  - [One Shot Revision](#one-shot-revision-8)
  - [curl](#curl)
  - [wget](#wget)
- [Remote Access](#remote-access)
  - [One Shot Revision](#one-shot-revision-9)
  - [ssh](#ssh)
  - [scp](#scp)
  - [rsync](#rsync-1)
  - [SSH Keys & Config](#ssh-keys--config)
- [Firewall & Security](#firewall--security)
  - [One Shot Revision](#one-shot-revision-10)
  - [iptables](#iptables)
  - [nftables](#nftables)
  - [ufw](#ufw)
  - [firewalld](#firewalld)
- [Packet Analysis](#packet-analysis)
  - [One Shot Revision](#one-shot-revision-11)
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

| Topic                                           | Short Description                                                    |
| ----------------------------------------------- | -------------------------------------------------------------------- |
| [File Sharing Overview](#file-sharing-overview) | When to pick `scp` vs `rsync` vs HTTP vs NFS vs Samba                |
| [`rsync`](#rsync)                               | Incremental, delta-based file sync — local or over SSH               |
| [Simple HTTP Server](#simple-http-server)       | One-line file server with `python3 -m http.server`                   |
| [NFS](#nfs)                                     | Unix-native shared filesystem — mount a remote directory as if local |
| [Samba](#samba)                                 | SMB/CIFS shares — interoperate with Windows clients                  |

### File Sharing Overview

**Description:** A quick map of the common ways to move or share files over a network on Linux, and when each one is the right tool.

| Method                   | Best For                                        | Transport      | Persistent Mount? |
| ------------------------ | ----------------------------------------------- | -------------- | ----------------- |
| `scp`                    | One-shot file copy over SSH                     | SSH (TCP/22)   | No                |
| `rsync`                  | Repeated syncs — copies only what changed       | SSH or rsyncd  | No                |
| `python3 -m http.server` | Quick read-only download server for a directory | HTTP (TCP)     | No                |
| **NFS**                  | Sharing dirs between Linux/Unix hosts           | NFS (TCP/2049) | Yes (`mount`)     |
| **Samba (SMB/CIFS)**     | Sharing dirs with Windows/macOS clients         | SMB (TCP/445)  | Yes (`mount`)     |

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

| Option             | Description                                                       |
| ------------------ | ----------------------------------------------------------------- |
| `-a`               | Archive mode — preserves permissions, timestamps, symlinks, etc.  |
| `-v`               | Verbose — show files being transferred.                           |
| `-z`               | Compress data during transfer.                                    |
| `-P`               | Show progress and keep partial files on interruption.             |
| `--delete`         | Delete files on destination that no longer exist on source.       |
| `-n` / `--dry-run` | Show what would be transferred without copying anything.          |
| `-e ssh`           | Force the use of SSH as the transport (default for remote paths). |

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

| Option            | Description                                              |
| ----------------- | -------------------------------------------------------- |
| `PORT`            | Port to listen on (default `8000`).                      |
| `--bind ADDRESS`  | Bind to a specific IP (default all interfaces).          |
| `--directory DIR` | Serve files from `DIR` instead of the current directory. |

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

| Option             | Description                                                       |
| ------------------ | ----------------------------------------------------------------- |
| `rw` / `ro`        | Read-write or read-only access.                                   |
| `sync` / `async`   | Reply only after writes hit disk / reply immediately.             |
| `no_subtree_check` | Skip subtree checks — faster, recommended for whole-disk exports. |
| `root_squash`      | Map remote `root` to an unprivileged user (default, safer).       |
| `no_root_squash`   | Let remote `root` act as local `root` — use with care.            |

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

| Option        | Description                                         |
| ------------- | --------------------------------------------------- |
| `path`        | Directory on the server being shared.               |
| `browseable`  | Whether the share shows up in network browse lists. |
| `read only`   | `yes` = read-only; `no` = read-write.               |
| `valid users` | Comma-separated list of users allowed to connect.   |
| `guest ok`    | Allow unauthenticated access if `yes`.              |
| `create mask` | Default permissions for new files (e.g. `0644`).    |

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

| Topic                                      | Short Description                                                       |
| ------------------------------------------ | ----------------------------------------------------------------------- |
| [Network Basics](#network-basics)          | Core components, network types (LAN/WAN/WLAN), hosts and packets        |
| [OSI Model](#osi-model)                    | 7-layer reference model: Physical → Data Link → … → Application         |
| [TCP/IP Model](#tcpip-model)               | The 4-layer model that the real internet actually runs on               |
| [Network Addressing](#network-addressing)  | IPv4 vs IPv6, public vs private, static vs DHCP, special addresses      |
| [Application Layer](#application-layer)    | Layer-7 protocols apps actually speak: HTTP, DNS, SSH, SMTP, …          |
| [Transport Layer](#transport-layer)        | TCP vs UDP, ports, sockets, the three-way handshake                     |
| [Network Layer](#network-layer)            | IP routing, default gateway, ICMP, MTU & fragmentation                  |
| [Link Layer](#link-layer)                  | Frames, MAC addresses, switches, Ethernet/Wi-Fi                         |
| [DHCP Overview](#dhcp-overview)            | How hosts get IP, gateway, and DNS automatically via the DORA handshake |
| [Ports & Protocols](#ports--protocols)     | TCP vs UDP, well-known ports, ephemeral ports                           |
| [MAC Addresses & ARP](#mac-addresses--arp) | Layer-2 identity and how IP maps to MAC on a LAN                        |

### Network Basics

Before diving into models and protocols, it helps to know **what's actually on a network** and **how data moves between the pieces**.

#### Core Network Components

The building blocks every network — from a home Wi-Fi to a data center — is made of:

| Component                        | Role                                                                                      |
| -------------------------------- | ----------------------------------------------------------------------------------------- |
| **Host**                         | Any device with an IP address — laptop, server, phone, IoT sensor.                        |
| **NIC** (Network Interface Card) | Hardware that connects a host to the network (wired Ethernet or wireless radio).          |
| **Switch**                       | Forwards frames between devices on the **same LAN** using MAC addresses (Layer 2).        |
| **Router**                       | Forwards packets between **different networks** using IP addresses (Layer 3).             |
| **Access Point (AP)**            | Bridges wireless clients onto a wired LAN — what most "Wi-Fi routers" actually do.        |
| **Modem**                        | Translates the ISP's signal (DSL / cable / fiber) into Ethernet your router can use.      |
| **Firewall**                     | Filters traffic by rule — can be host-based (`iptables`, `ufw`) or a dedicated appliance. |
| **Cabling / Media**              | The physical medium — copper (Cat5e/6), fiber, or air (Wi-Fi, 4G/5G).                     |
| **Protocols**                    | The agreed rules for how data is formatted and exchanged (TCP/IP, HTTP, DNS, …).          |

**Rule of thumb:** if it has an IP, it's a **host**; if it moves traffic between hosts, it's **infrastructure** (switch / router / AP / firewall).

#### Understanding Network Types: WAN, LAN, and WLAN

Networks are usually classified by **how far they reach**.

| Type     | Full Name                 | Typical Scope                    | Example                             |
| -------- | ------------------------- | -------------------------------- | ----------------------------------- |
| **LAN**  | Local Area Network        | One building / floor / home      | Office network, home Ethernet       |
| **WLAN** | Wireless LAN              | Same scope as LAN — but wireless | Home/office Wi-Fi (802.11)          |
| **WAN**  | Wide Area Network         | City → country → worldwide       | The Internet itself, an SD-WAN link |
| **MAN**  | Metropolitan Area Network | A city                           | A citywide ISP backbone             |
| **PAN**  | Personal Area Network     | A few meters around one user     | Bluetooth phone ↔ headphones        |

**Notes:**

- A **LAN** is fast (Gbps), private, and usually owned by a single organization.
- A **WAN** is slower (latency-bound), spans multiple sites, and is rented from carriers / ISPs.
- A **WLAN** is just a LAN over Wi-Fi instead of cables — same addressing, same protocols, just a different physical layer.

#### Hosts and Packets

- A **host** is any addressable device on a network. It can be a **client** (laptop, phone), a **server** (web / database / storage), or sometimes an intermediary (a router has IPs too).
- A **packet** is the unit of data that travels across an IP network. Large messages are chopped into many small packets and reassembled at the destination.
- Each packet has two parts:
  - **Header** — metadata: source IP, destination IP, protocol, sequence number, etc.
  - **Payload** — the actual data being delivered (a chunk of an HTTP response, a DNS reply, …).
- Packets are forwarded **hop by hop**: each router inspects the destination IP and decides the next hop. Packets from the same conversation can take different paths and arrive out of order — the **Transport layer** (TCP) is what puts them back together.

### OSI Model

The **Open Systems Interconnection** model is a 7-layer reference model defined by ISO. Almost no real system implements all 7 layers cleanly, but it's the shared vocabulary every networking engineer uses to describe **where a problem lives** ("that's a Layer 2 issue", "that's a Layer 7 bug").

#### Overview

| #   | Layer            | Responsibility                                 | Examples                   |
| --- | ---------------- | ---------------------------------------------- | -------------------------- |
| 7   | **Application**  | Protocols users / apps interact with directly  | HTTP, FTP, SMTP, DNS, SSH  |
| 6   | **Presentation** | Data format, encoding, encryption, compression | TLS, JPEG, ASCII, UTF-8    |
| 5   | **Session**      | Open, manage, and close conversations          | NetBIOS, RPC               |
| 4   | **Transport**    | End-to-end delivery and reliability            | TCP, UDP                   |
| 3   | **Network**      | Logical addressing & routing between networks  | IP, ICMP                   |
| 2   | **Data Link**    | Frame delivery on the local segment            | Ethernet, ARP, MAC, Wi-Fi  |
| 1   | **Physical**     | Raw bits on the medium                         | Copper, fiber, radio waves |

**Mnemonic (top → bottom):** **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing.

**Why the model matters:**

- Gives a clean way to localize a problem: "DNS resolves but TCP won't connect" → Layer 4 / firewall; "ping works but HTTPS fails" → Layer 6 (TLS) or Layer 7.
- Each layer **hides the layer below**: HTTP doesn't care about Ethernet, IP doesn't care about whether you're on Wi-Fi or fiber.

### TCP/IP Model

The **TCP/IP Model** is the protocol stack the real internet actually runs on. It predates OSI, was developed by the US DoD for ARPANET, and collapses OSI's 7 layers into **4 practical ones**.

#### Basic

- Named after its two flagship protocols: **TCP** (Transmission Control Protocol) and **IP** (Internet Protocol).
- More pragmatic than OSI — it describes what's actually **implemented**, not an idealized model.
- Maps loosely to OSI: TCP/IP's **Application** layer covers OSI 5–7; **Network Access** covers OSI 1–2.
- Every packet on the modern internet flows **down** these four layers on the way out, and **up** them on the way in.

#### The Four Layers of the TCP/IP Model

| #   | Layer                     | OSI Equivalent               | Responsibility                               | Protocols                        |
| --- | ------------------------- | ---------------------------- | -------------------------------------------- | -------------------------------- |
| 4   | **Application**           | Session + Presentation + App | App-level data and APIs                      | HTTP, HTTPS, DNS, SSH, FTP, SMTP |
| 3   | **Transport**             | Transport                    | Process-to-process delivery using **ports**  | TCP, UDP                         |
| 2   | **Internet**              | Network                      | Logical addressing & routing across networks | IP, ICMP, ARP\*                  |
| 1   | **Network Access** (Link) | Data Link + Physical         | Frames on the local medium                   | Ethernet, Wi-Fi (802.11), PPP    |

\* ARP technically sits between Layer 2 and 3 but is usually grouped with the Internet layer in TCP/IP discussions.

**Flow of a packet (outbound):**

1. **Application** produces data — e.g. `GET /index.html` from your browser.
2. **Transport** wraps it in a TCP segment, adding source / destination **ports**.
3. **Internet** wraps that in an IP packet, adding source / destination **IP addresses**.
4. **Network Access** wraps that in an Ethernet / Wi-Fi frame with source / destination **MAC addresses** and pushes it onto the wire.

On the receiving host the process runs in reverse: the frame is unwrapped layer by layer until the application gets its data back.

### Network Addressing

Every device that talks on a network needs an **address** so packets know where to go. On modern IP networks that address comes in two flavors — **IPv4** and **IPv6** — and a host typically has both.

#### IPv4 vs IPv6

| Aspect            | IPv4                             | IPv6                                      |
| ----------------- | -------------------------------- | ----------------------------------------- |
| **Size**          | 32 bits (~4.3 billion addresses) | 128 bits (~3.4 × 10³⁸ addresses)          |
| **Notation**      | Dotted decimal — `192.168.1.10`  | Colon hex — `2001:db8::1`                 |
| **Header**        | Variable length, has checksum    | Fixed 40-byte header, no checksum         |
| **Configuration** | Manual or DHCP                   | Manual, DHCPv6, or **SLAAC** (autoconfig) |
| **Broadcast**     | Yes (`255.255.255.255`)          | No — replaced by **multicast**            |
| **NAT needed?**   | Usually (address exhaustion)     | No — every host can have a public address |

**Example IPv4 packet flow:** `192.168.1.10` → `8.8.8.8` over the public internet (NAT'd at the home router).

**Example IPv6 address parts:** `2001:0db8:0000:0000:0000:0000:0000:0001` shortens to `2001:db8::1` (consecutive zero groups collapse to `::`, exactly once per address).

#### Public vs Private Addresses

Private ranges are reserved by **RFC 1918** for use inside organizations — they are **not routable on the public internet** and need NAT to reach the outside world.

| Range                           | CIDR             | Typical Use                               |
| ------------------------------- | ---------------- | ----------------------------------------- |
| `10.0.0.0 – 10.255.255.255`     | `10.0.0.0/8`     | Large corporate networks, cloud VPCs      |
| `172.16.0.0 – 172.31.255.255`   | `172.16.0.0/12`  | Mid-size networks, Docker default bridges |
| `192.168.0.0 – 192.168.255.255` | `192.168.0.0/16` | Home and small-office LANs                |

Everything else is **public** — assigned by IANA/RIRs and globally reachable.

#### Static vs Dynamic Assignment

| Method     | How Address Is Assigned                                         | When to Use                                          |
| ---------- | --------------------------------------------------------------- | ---------------------------------------------------- |
| **Static** | Manually configured on the host (`/etc/network/...`, `nmcli`)   | Servers, routers, printers — anything you connect to |
| **DHCP**   | A DHCP server hands out a lease when the host boots             | Laptops, phones, ephemeral VMs                       |
| **SLAAC**  | IPv6 host self-generates an address from a router advertisement | Default on IPv6 LANs                                 |

A DHCP lease comes with more than just an IP — it usually also delivers the **subnet mask**, **default gateway**, and **DNS servers**.

#### Special-Purpose Addresses

| Address / Range     | Meaning                                                      |
| ------------------- | ------------------------------------------------------------ |
| `127.0.0.1` / `::1` | **Loopback** — refers to the host itself                     |
| `0.0.0.0`           | "Any address" — bind to all interfaces; also a default route |
| `255.255.255.255`   | IPv4 **limited broadcast** (current network only)            |
| `169.254.0.0/16`    | **APIPA / link-local** — assigned when DHCP fails            |
| `fe80::/10`         | IPv6 link-local — every IPv6 interface always has one        |
| `224.0.0.0/4`       | IPv4 **multicast** group addresses                           |
| `ff00::/8`          | IPv6 multicast                                               |

#### Inspecting Addresses on Linux

```bash
# Show every interface and its IPv4/IPv6 addresses
ip a

# Just one interface
ip a show eth0

# Show only IPv4 or IPv6
ip -4 a
ip -6 a

# Find the address your host uses to reach a destination
ip route get 8.8.8.8
```

**Notes:**

- A single interface can — and usually does — hold **multiple addresses** (IPv4 + IPv6, link-local + global).
- "My IP" is ambiguous: a host has a **LAN IP** (what the router sees) and a **public IP** (what the internet sees). `curl ifconfig.me` reveals the latter.
- An address alone isn't enough to route a packet — it's the address **plus its subnet mask** (see [Subnetting & CIDR](#subnetting--cidr)) that defines the network.
- IPv4 exhaustion is real — new cloud regions and mobile carriers increasingly require IPv6 connectivity end-to-end.

### Application Layer

The **Application Layer** is the top of the stack — Layer 7 in OSI, Layer 4 in TCP/IP. It's where the protocols **users and apps actually speak** live. Everything below (TCP, IP, Ethernet) exists only to deliver these messages from one process to another.

#### What Belongs at This Layer

- **Anything an application directly produces or consumes** — an HTTP request body, a DNS query, an SSH command, an SMTP `MAIL FROM:` line.
- **Format & semantics**: what the bytes mean, how a request is structured, how the other side should reply.
- It does **not** handle "how do these bytes get there?" — that's TCP/UDP's job underneath.

#### Common Application-Layer Protocols

| Protocol        | Default Port | Transport  | Purpose                                                          |
| --------------- | ------------ | ---------- | ---------------------------------------------------------------- |
| **HTTP**        | 80           | TCP        | The web — request/response for HTML, APIs, static assets         |
| **HTTPS**       | 443          | TCP (+TLS) | HTTP wrapped in TLS for confidentiality and integrity            |
| **DNS**         | 53           | UDP / TCP  | Resolve names (`example.com`) to IP addresses                    |
| **SSH**         | 22           | TCP        | Encrypted remote shell and file transfer                         |
| **FTP**         | 21 (ctrl)    | TCP        | Legacy file transfer (cleartext — use SFTP/FTPS instead)         |
| **SFTP**        | 22           | TCP        | File transfer **over SSH** — same port as ssh                    |
| **SMTP**        | 25 / 587     | TCP        | Send/relay email between mail servers                            |
| **IMAP / POP3** | 143 / 110    | TCP        | Read email from a mail server (IMAP keeps state, POP3 downloads) |
| **NTP**         | 123          | UDP        | Synchronize system clocks across hosts                           |
| **SNMP**        | 161 / 162    | UDP        | Poll devices for monitoring data and receive traps               |
| **DHCP**        | 67 / 68      | UDP        | Hand out IP leases, gateway, and DNS info to hosts at boot       |
| **LDAP**        | 389 / 636    | TCP        | Directory lookups (users, groups) — often behind auth systems    |

#### How an Application-Layer Conversation Looks

A single web request quietly touches several Layer-7 protocols:

1. **DNS** — your browser asks a resolver for the IP of `example.com`.
2. **TLS handshake** — Layer 6/7 negotiation sets up encryption with the server.
3. **HTTP** — the browser sends `GET / HTTP/1.1` and the server replies with status, headers, and a body.
4. (Optional) **WebSocket / HTTP/2 streams** — keep the connection open for further messages.

You can poke at most of these directly from the shell:

```bash
# HTTP — see request/response headers
curl -v https://example.com

# DNS — see the resolution path
dig example.com

# SSH — connect with verbose output to watch the protocol handshake
ssh -v user@host

# SMTP — talk to a mail server by hand (great for debugging)
nc smtp.example.com 25
```

**Notes:**

- **Ports are a transport-layer concept**, but each Layer-7 protocol has a **well-known port** by convention — covered next in [Ports & Protocols](#ports--protocols).
- Most modern app-layer protocols run **on top of TLS** (HTTPS, SMTPS, IMAPS, LDAPS) — same protocol, encrypted transport, different default port.
- When something "doesn't work" but `ping` and `traceroute` are fine, the bug usually lives at this layer: bad TLS cert, wrong `Host` header, a 401, a malformed DNS reply.
- HTTP/2 and HTTP/3 keep the same Layer-7 semantics (`GET`, headers, status codes) — they only change the framing below the API surface. HTTP/3 famously runs over **UDP** via QUIC instead of TCP.

### Transport Layer

The **Transport Layer** sits directly under the Application Layer — Layer 4 in OSI, Layer 3 in TCP/IP. Its job is **process-to-process delivery**: getting a stream of bytes from one program on one host to another program on another host, identified by a **port number**.

#### What This Layer Adds On Top of IP

| Service                | Provided By                                               |
| ---------------------- | --------------------------------------------------------- |
| **Multiplexing**       | Ports let many app conversations share one IP address     |
| **Reliability**        | TCP retransmits lost bytes; UDP does not                  |
| **Ordering**           | TCP delivers bytes in the order they were sent            |
| **Flow control**       | TCP receiver tells sender how much it can accept (window) |
| **Congestion control** | TCP backs off when the network is overloaded              |
| **Error detection**    | Checksum over header + payload (both TCP and UDP)         |

The Network Layer (IP) only promises **"best effort"** delivery between hosts — anything above that, including knowing _which app_ on the host should receive the data, is the Transport Layer's job.

#### TCP vs UDP

| Aspect                | **TCP**                                         | **UDP**                                          |
| --------------------- | ----------------------------------------------- | ------------------------------------------------ |
| **Connection**        | Connection-oriented (handshake before data)     | Connectionless (just send)                       |
| **Reliability**       | Guaranteed delivery + ordering + retransmission | No guarantees — packets may be lost or reordered |
| **Header size**       | 20+ bytes                                       | 8 bytes                                          |
| **Speed**             | Slower — more bookkeeping                       | Faster — minimal overhead                        |
| **Flow / Congestion** | Yes                                             | No                                               |
| **Best for**          | HTTP, SSH, SMTP, databases, file transfer       | DNS queries, NTP, VoIP, video, gaming, DHCP      |

**Rule of thumb:** _"If losing a packet would corrupt the data, use TCP. If losing one is OK because a newer one will come in a moment, use UDP."_

#### Ports & Sockets

- A **port** is a 16-bit number (0–65535) identifying a specific service/process on a host.
- A **socket** is the full endpoint: `IP:port` — e.g. `192.168.1.10:443`.
- A TCP connection is uniquely identified by a **4-tuple**: `src-IP : src-port  ↔  dst-IP : dst-port`.

| Range           | Name           | Typical Use                                       |
| --------------- | -------------- | ------------------------------------------------- |
| `0 – 1023`      | **Well-known** | Standard services (HTTP 80, HTTPS 443, SSH 22)    |
| `1024 – 49151`  | **Registered** | Apps that registered with IANA (Postgres 5432, …) |
| `49152 – 65535` | **Ephemeral**  | Temporary ports for client-side connections       |

#### TCP Three-Way Handshake

Before TCP sends any application data, the two sides agree on initial sequence numbers:

```
Client                       Server
  | --------- SYN --------> |   "I want to talk, my seq = X"
  | <----- SYN, ACK ------- |   "OK, my seq = Y, ack X+1"
  | --------- ACK --------> |   "Got it, ack Y+1"
  |        DATA flows       |
```

Closing is a similar four-way exchange (`FIN` → `ACK` → `FIN` → `ACK`).

#### Common TCP Connection States

You'll see these in `ss` / `netstat` output:

| State          | Meaning                                                            |
| -------------- | ------------------------------------------------------------------ |
| `LISTEN`       | Server is waiting for incoming connections on a port               |
| `SYN-SENT`     | Client sent SYN, waiting for SYN-ACK                               |
| `SYN-RECV`     | Server received SYN, sent SYN-ACK, waiting for final ACK           |
| `ESTABLISHED`  | Connection is open — data can flow                                 |
| `FIN-WAIT-1/2` | One side has started closing the connection                        |
| `TIME-WAIT`    | Local side closed, holding the socket briefly to absorb stragglers |
| `CLOSE-WAIT`   | Remote side closed; local app hasn't called `close()` yet          |

A pile of `CLOSE-WAIT` sockets almost always means an **application bug** — the program isn't closing its sockets.

#### Inspecting the Transport Layer on Linux

```bash
# Every listening TCP/UDP socket with its owning process
ss -tulpn

# All established TCP connections
ss -tan state established

# UDP sockets only
ss -uan

# Quick TCP port-open check
nc -zv example.com 443

# Watch the handshake on the wire
sudo tcpdump -ni any 'tcp port 443 and (tcp-syn|tcp-ack) != 0'
```

**Notes:**

- Ports `< 1024` require **root** to bind. Use a reverse proxy or `setcap` for non-root binds.
- **UDP has no "connection"** — `ss -u` shows sockets, not flows; "UDP connection refused" really means an ICMP `port unreachable` came back.
- **TLS lives just above TCP** — by the time a TLS handshake happens, the TCP handshake is already done.
- **QUIC / HTTP/3** moves transport responsibilities (reliability, ordering, congestion control) into user space on top of **UDP** — same Layer-4 _role_, different implementation.
- A common interview question: _"What happens when you type `example.com` in a browser?"_ — the answer walks through DNS (App), the TCP handshake (Transport), IP routing (Network), and back up.

### Network Layer

The **Network Layer** is Layer 3 in OSI and the **Internet** layer in TCP/IP. Its job is to get a packet from any host on any network to any other host on any other network — across switches, routers, ISPs, and continents — using **logical addresses** (IP) rather than the physical MAC addresses used by the link below.

#### What This Layer Does

| Service                     | Provided By                                                    |
| --------------------------- | -------------------------------------------------------------- |
| **Logical addressing**      | IPv4 / IPv6 addresses identify hosts independent of hardware   |
| **Routing**                 | Pick the next hop toward the destination, hop by hop           |
| **Forwarding**              | Move a packet from an input interface to the right output one  |
| **Fragmentation**           | Split a packet that's larger than the link's MTU (mostly IPv4) |
| **Error / control signals** | ICMP messages — "host unreachable", "TTL exceeded", echo reply |

It is **connectionless and best-effort** — no handshake, no guaranteed delivery, no ordering. Reliability (if needed) is added by TCP above.

#### Key Protocols at This Layer

| Protocol          | Purpose                                                              |
| ----------------- | -------------------------------------------------------------------- |
| **IPv4 / IPv6**   | The actual packet format and addressing                              |
| **ICMP / ICMPv6** | Diagnostic and error messages — what `ping` and `traceroute` ride on |
| **ARP**\*         | Maps IPv4 → MAC on the local segment (sits between L2 and L3)        |
| **NDP**           | IPv6 equivalent of ARP — neighbor discovery, router advertisements   |
| **IGMP**          | Manage IPv4 multicast group membership                               |

\* ARP is technically a Layer 2.5 protocol but is almost always discussed alongside IP.

#### Routing — How a Packet Finds Its Way

Every host (and router) keeps a **routing table**. For each outgoing packet:

1. Look up the destination IP in the table — pick the **most specific (longest-prefix)** match.
2. If the destination is on a **directly connected** network, send it out that interface.
3. Otherwise, hand the packet to the matching **next-hop router**.
4. Decrement **TTL** (IPv4) / **Hop Limit** (IPv6). If it hits 0, drop the packet and send back an ICMP "TTL exceeded".

That last bit is exactly what `traceroute` exploits — it sends packets with TTL = 1, 2, 3, … and collects the "TTL exceeded" replies from each router on the path.

```bash
# Show the routing table
ip route

# Which interface + gateway will my host use to reach 8.8.8.8?
ip route get 8.8.8.8

# Add a static route (admin)
sudo ip route add 10.20.0.0/16 via 192.168.1.1

# IPv6 routes
ip -6 route
```

A typical small routing table looks like this:

```
default via 192.168.1.1 dev wlan0       # send everything else to the home router
192.168.1.0/24 dev wlan0 proto kernel   # directly connected LAN
169.254.0.0/16 dev wlan0 scope link     # link-local
```

The `default` route (also written `0.0.0.0/0`) is the **default gateway** — the catch-all next hop when nothing more specific matches.

#### ICMP — The Network Layer's Voice

ICMP doesn't carry user data; it carries **signals about the network itself**.

| ICMP Type                   | When You See It                                                      |
| --------------------------- | -------------------------------------------------------------------- |
| **Echo Request / Reply**    | `ping` — "are you alive?"                                            |
| **Destination Unreachable** | No route, port closed (for UDP), or admin filter                     |
| **Time Exceeded**           | TTL hit 0 — fuel for `traceroute`                                    |
| **Redirect**                | Router telling you "use this other gateway instead" (often filtered) |
| **Fragmentation Needed**    | Packet too big, "Don't Fragment" bit was set                         |

Heavy ICMP filtering on the path is a frequent cause of mysterious failures: `ping` works, big TCP transfers stall — usually a **PMTU black hole** caused by dropping ICMP "Fragmentation Needed".

#### MTU & Fragmentation

- **MTU** (Maximum Transmission Unit) — the largest payload a link can carry without splitting. Ethernet default is **1500 bytes**.
- If an IPv4 packet is bigger than the next link's MTU and the **DF** (Don't Fragment) bit is **not** set, the router fragments it. If DF **is** set, the router drops it and replies with ICMP "Fragmentation Needed" — that's how **Path MTU Discovery (PMTUD)** works.
- **IPv6 never fragments in transit** — only the sender does, after PMTUD. Routers that need to fragment just drop the packet and send `Packet Too Big`.

```bash
# Check an interface's MTU
ip link show eth0 | grep mtu

# Force a specific payload size to test for MTU issues
ping -M do -s 1472 example.com    # 1472 + 28 (ICMP/IP headers) = 1500

# Find the path MTU end-to-end
tracepath example.com
```

**Notes:**

- **Routers operate at this layer**; switches operate one layer below (Layer 2, MACs). A "router" with a built-in switch is doing both.
- **NAT** (Network Address Translation) lives here too — your home router rewrites the source IP/port of outgoing packets so many private hosts can share one public IP.
- A host with **no default route** can only reach its own LAN. Adding `default via <gateway>` is what turns it into an "internet-connected" host.
- Many "the internet is slow" tickets bottom out as Layer-3 problems: asymmetric routing, a bad next hop, MTU mismatch on a VPN, or an ISP black-holing a prefix.
- `mtr` is the best single command for diagnosing Network-Layer issues — it shows per-hop loss and latency continuously.

### Link Layer

The **Link Layer** (Layer 2 in OSI, **Network Access** in TCP/IP) sits directly above the Physical layer. Its job is to move **frames** between two devices that share the same physical or wireless segment, identifying them by **MAC address** rather than IP.

#### What This Layer Does

| Service              | Provided By                                                                  |
| -------------------- | ---------------------------------------------------------------------------- |
| **Framing**          | Wrap network-layer packets in link-specific frames (Ethernet, Wi-Fi, …)      |
| **Local addressing** | MAC addresses identify NICs on the same segment                              |
| **Medium access**    | Decide who can transmit when — CSMA/CD on Ethernet, CSMA/CA on Wi-Fi         |
| **Error detection**  | Frame Check Sequence (FCS) catches corrupted bits — corrupted frames dropped |
| **Local delivery**   | Move frames within one broadcast domain — no routing here                    |

The link layer only worries about **one hop at a time** — getting a frame from your NIC to the next device that owns the destination MAC. Anything beyond that segment is the Network Layer's problem.

#### Frames vs Packets vs Segments

The same chunk of data wears a different name at each layer it passes through:

| PDU         | Layer     | Header Adds                                       |
| ----------- | --------- | ------------------------------------------------- |
| **Frame**   | Data Link | Source/destination **MAC**, EtherType, FCS        |
| **Packet**  | Network   | Source/destination **IP**, TTL, protocol          |
| **Segment** | Transport | Source/destination **port**, sequence/ack numbers |

On the wire it looks like nested envelopes: `Frame[ IP[ TCP[ HTTP-bytes ] ] ]`.

#### Common Link-Layer Technologies

| Technology           | Where You See It             | Notes                                              |
| -------------------- | ---------------------------- | -------------------------------------------------- |
| **Ethernet (802.3)** | Wired LANs, data centers     | MAC + EtherType frame; 1G / 10G / 25G / 100G+      |
| **Wi-Fi (802.11)**   | Wireless LANs                | Same MAC scheme; uses CSMA/CA and retransmits      |
| **PPP**              | DSL, dial-up, some WAN links | Point-to-point, often with built-in authentication |
| **VLAN (802.1Q)**    | Enterprise switching         | Tags frames so one switch hosts many isolated LANs |
| **MPLS**             | ISP backbones                | Label-switched forwarding — sits between L2 and L3 |

#### MAC Addresses

- A **MAC address** is a 48-bit identifier burned into (or spoofed onto) a NIC, written as six hex pairs: `aa:bb:cc:11:22:33`.
- The first 24 bits are the **OUI** — vendor identifier assigned by IEEE.
- Broadcast MAC `ff:ff:ff:ff:ff:ff` reaches every host on the segment.
- Multicast frames have the **low-order bit** of the first byte set to 1 (e.g. `01:00:5e:…`).

```bash
# Show MAC addresses for every interface
ip link

# Just one interface
ip link show eth0

# Show the neighbor table — IP ↔ MAC mappings learned via ARP
ip neigh
```

#### Switches and Broadcast Domains

- A **switch** is a Layer-2 device. It learns which MAC lives on which port and forwards frames only out the right one (unlike a hub, which floods every port).
- All ports on a switch — without VLANs — form a single **broadcast domain**: a broadcast frame reaches every host in it.
- A **router** breaks broadcast domains: each router interface is its own L2 segment.
- **VLANs** let one physical switch host several broadcast domains by tagging frames; a router or L3 switch is still needed to move traffic between them.

**Notes:**

- A "Layer-2 problem" is usually a cable, a dead NIC, a wrong VLAN tag, or a duplicate MAC — `ping` to anything off-subnet fails because the ARP step (see [MAC Addresses & ARP](#mac-addresses--arp)) can't complete.
- **MTU is a link-layer property** — that's why different links have different MTUs and IP has to deal with fragmentation above.
- Same broadcast domain → ARP works → IP works. Different broadcast domains → a router must sit in between.
- A NIC in **promiscuous mode** accepts every frame it sees on the wire, not just frames addressed to its MAC — that's how `tcpdump` and Wireshark capture other hosts' traffic on a hub or mirror port.

### DHCP Overview

**DHCP** (Dynamic Host Configuration Protocol) is how hosts get their IP configuration automatically when they boot. Instead of someone typing IPs by hand, the host shouts on the LAN and a DHCP server answers with everything needed to participate on the network.

#### What a DHCP Lease Includes

A lease isn't just an address — it's a small bundle of network config:

| Field                        | Purpose                                              |
| ---------------------------- | ---------------------------------------------------- |
| **IP address**               | The address the host may use, for a limited time     |
| **Subnet mask**              | Defines the local network (e.g. `/24`)               |
| **Default gateway**          | Router IP for off-LAN traffic                        |
| **DNS servers**              | Where to send name lookups                           |
| **Lease time**               | How long the assignment is valid (hours to days)     |
| **Domain name / NTP / WPAD** | Optional extras delivered as numbered "DHCP options" |

#### The DORA Handshake

DHCPv4 is a four-message conversation, easy to remember as **DORA**:

```
Client                                Server
  | --- DHCPDISCOVER (broadcast) --> |   "Anyone out there have an IP for me?"
  | <--- DHCPOFFER  (broadcast) ---- |   "I can give you 192.168.1.50"
  | --- DHCPREQUEST (broadcast) --> |   "I'll take that one"
  | <--- DHCPACK    (broadcast) ---- |   "Confirmed — here's your lease"
```

- All four messages run over **UDP** — client port **68**, server port **67**.
- The first packets are **broadcast** because the client has no IP yet.
- If multiple servers reply, the client picks one `OFFER`; the others release the reservation.

#### Lease Renewal

- At **T1 (~50% of lease)** the client tries to renew with its current server via a unicast `DHCPREQUEST`.
- At **T2 (~87.5%)** if renewal failed, it broadcasts a `DHCPREQUEST` to any server.
- At lease **expiry**, it must restart from `DHCPDISCOVER`.
- On clean shutdown the client may send a `DHCPRELEASE` so the address returns to the pool immediately.

#### DHCP on Linux

Most distros drive DHCP via `dhclient`, `systemd-networkd`, or `NetworkManager`.

```bash
# Force a fresh lease (NetworkManager)
sudo nmcli connection down eth0 && sudo nmcli connection up eth0

# Or with dhclient directly
sudo dhclient -r eth0     # release current lease
sudo dhclient   eth0      # renew / request a new lease

# Inspect the current lease
cat /var/lib/dhcp/dhclient.leases

# systemd-networkd view of the lease + DNS handed out
networkctl status eth0
```

#### When DHCP Fails

If no server answers, the host falls back to an **APIPA / link-local** address from `169.254.0.0/16`. Symptoms: you can ping other link-local hosts but nothing off-LAN — usually a dead DHCP server, a broken VLAN, or a misconfigured switch port.

```bash
# Spot the fallback
ip -4 a | grep 169.254
```

#### DHCPv6 and SLAAC

IPv6 has two parallel mechanisms for auto-configuration:

- **SLAAC** (Stateless Address Autoconfiguration) — the host listens to **Router Advertisements** and builds its own address from the advertised prefix. No server is needed for the address itself.
- **DHCPv6** — used when you need stateful config (specific addresses, DNS, extra options) that SLAAC alone can't deliver. Uses ports **546 / 547**.

Many networks run **SLAAC + DHCPv6** together — SLAAC for the address, DHCPv6 for DNS and domain info.

**Notes:**

- DHCP relies on **broadcasts on the local segment**. Across subnets you need a **DHCP relay** (`ip helper-address` on routers) to forward DISCOVER messages to a central server.
- A rogue DHCP server (someone plugging a home AP into the office) can hand out wrong gateways or DNS — **DHCP snooping** on managed switches is the usual defense.
- **Reservations** (static IP tied to a MAC in the DHCP server) are usually safer than fully static config — the host still picks up DNS/gateway updates automatically.
- To see what the server actually handed you: `journalctl -u NetworkManager | grep -i dhcp` or `journalctl -u systemd-networkd`.

### Ports & Protocols

_To be filled in._

### MAC Addresses & ARP

_To be filled in._

---

## Subnetting

A **subnet** is a smaller network carved out of a larger IP range. Subnetting lets you split a single block of addresses into multiple isolated networks — useful for separating teams, environments, or VLANs, and for keeping broadcast domains small.

### One Shot Revision

| Topic                                   | Short Description                                                            |
| --------------------------------------- | ---------------------------------------------------------------------------- |
| [Subnets](#subnets)                     | What a subnet is, why we subnet, broadcast domains, key terminology          |
| [Subnet Math](#subnet-math)             | Powers of two, formulas, host counts, bit-borrowing intuition                |
| [Subnetting Cheats](#subnetting-cheats) | Magic number, block size shortcut, fast mental math                          |
| [CIDR](#cidr)                           | Classless notation, supernetting, route aggregation, reserved blocks         |
| [IPv4](#ipv4)                           | 32-bit addressing, masks, network/broadcast/host math, VLSM, worked examples |
| [NAT](#nat)                             | SNAT, DNAT, PAT, CGNAT, NAT64, Linux `iptables` / `nftables` examples        |
| [IPv6](#ipv6)                           | 128-bit addressing, address types, `/64` subnets, SLAAC vs DHCPv6, NDP       |

### Subnets

A subnet is a smaller network carved out of a larger IP range. Subnetting splits one address block into many isolated networks so you can keep broadcast domains small, separate teams or environments, and tighten security boundaries.

**Why subnet?**

- **Smaller broadcast domains** — broadcasts (ARP, DHCP discovery) only reach hosts inside the same subnet. Big flat networks drown in broadcast traffic.
- **Isolation** — DMZ, prod, dev, IoT, guest Wi-Fi each live on their own subnet; routers/firewalls control traffic between them.
- **Security** — ACLs and firewall rules apply at subnet boundaries, so a compromised host can't freely reach every other host.
- **Address efficiency** — instead of giving a 50-host office a `/24` (254 hosts), give it a `/26` (62 hosts) and use the rest elsewhere.
- **Routing scalability** — backbone routers carry summary routes (a single `/16`) instead of thousands of individual host routes.

**Key terms:**

| Term                  | Meaning                                                                                              |
| --------------------- | ---------------------------------------------------------------------------------------------------- |
| **Subnet mask**       | The contiguous run of `1` bits that marks the network portion of an address (e.g., `255.255.255.0`). |
| **Prefix length**     | Same idea, written in CIDR form (e.g., `/24`).                                                       |
| **Network address**   | First address of the subnet — all host bits `0`. Not assignable to a host.                           |
| **Broadcast address** | Last address of the subnet — all host bits `1`. Not assignable to a host.                            |
| **Host addresses**    | Everything between network and broadcast — usable for endpoints.                                     |
| **Default gateway**   | The router IP a host uses to reach destinations outside its own subnet.                              |
| **Broadcast domain**  | Set of devices that receive each other's broadcasts — one per subnet on a typical L3 design.         |

Subnets only span a single L2 segment by default. To talk between subnets, traffic must pass through a router (or L3 switch).

### Subnet Math

Subnet math reduces to **powers of two** — once the table is in muscle memory, you can compute any subnet size in your head.

**Powers of two (last octet):**

| `2^n` | Value | Used for                             |
| ----- | ----- | ------------------------------------ |
| `2^1` | 2     | `/31` block / 2-host point-to-point  |
| `2^2` | 4     | `/30` block / 2 usable hosts         |
| `2^3` | 8     | `/29` block / 6 usable hosts         |
| `2^4` | 16    | `/28` block / 14 usable hosts        |
| `2^5` | 32    | `/27` block / 30 usable hosts        |
| `2^6` | 64    | `/26` block / 62 usable hosts        |
| `2^7` | 128   | `/25` block / 126 usable hosts       |
| `2^8` | 256   | `/24` block (full octet, 254 usable) |

**Core formulas:**

```
Total addresses in subnet  = 2^(host bits)
Usable host addresses      = 2^(host bits) − 2     (network + broadcast unusable)
Number of subnets borrowed = 2^(borrowed bits)
Host bits                  = 32 − prefix length
Block size (last octet)    = 256 − (mask last octet)
```

**Worked walkthrough — `172.16.20.50 /20`:**

```
Host bits   = 32 − 20 = 12        → 2^12 = 4096 addresses, 4094 usable
Mask        = 255.255.240.0       (240 = 11110000 — four mask bits in the 3rd octet)
Block step  = 256 − 240 = 16      (3rd octet steps in 16s: .0, .16, .32, ...)
Subnet      = 172.16.16.0/20      (largest multiple of 16 ≤ 20 is 16)
Broadcast   = 172.16.31.255       (subnet + block − 1 in 3rd octet, .255 in last)
Host range  = 172.16.16.1 – 172.16.31.254
```

**Bit-borrowing intuition:** every bit you borrow from the host side doubles the number of subnets and halves their size.

| Start | Borrow | Result | Subnets | Hosts each |
| ----- | ------ | ------ | ------- | ---------- |
| `/24` | 0      | `/24`  | 1       | 254        |
| `/24` | 1      | `/25`  | 2       | 126        |
| `/24` | 2      | `/26`  | 4       | 62         |
| `/24` | 3      | `/27`  | 8       | 30         |
| `/24` | 4      | `/28`  | 16      | 14         |

### Subnetting Cheats

Tricks that turn subnetting into mental arithmetic — handy under interview pressure or while debugging at 3 AM.

**The "magic number" (block size):**

```
Block size = 256 − (mask last octet)
```

Find the **interesting octet** (the one that isn't `255` or `0`) and step by the block size. That gives every subnet boundary instantly.

```
Mask 255.255.255.192  →  block = 256 − 192 = 64
Subnets: x.x.x.0, x.x.x.64, x.x.x.128, x.x.x.192
```

**Cheat table — memorize these:**

| Prefix | Mask Last Octet | Block | Hosts | Mnemonic                         |
| ------ | --------------- | ----- | ----- | -------------------------------- |
| `/25`  | `128`           | 128   | 126   | "Half a /24"                     |
| `/26`  | `192`           | 64    | 62    | "Quarter a /24"                  |
| `/27`  | `224`           | 32    | 30    | "Eighth a /24"                   |
| `/28`  | `240`           | 16    | 14    | "Sixteenth a /24"                |
| `/29`  | `248`           | 8     | 6     | "Storage networks / small links" |
| `/30`  | `252`           | 4     | 2     | "Classic point-to-point link"    |

**Fast usable-host count:** `2^(32 − prefix) − 2`. For a `/N` close to `/24`, count down from `254`: `/24` → 254, `/25` → 126, `/26` → 62, `/27` → 30, `/28` → 14… each step roughly halves.

**Finger trick — "which subnet is `X.X.X.Y` in?":**

1. Block size = `256 − mask`.
2. Largest multiple of block ≤ `Y` is the network address.
3. Network + block − 1 is the broadcast.

```
Q: 10.0.0.155 /27 — what subnet?
   Block = 256 − 224 = 32
   155 ÷ 32 = 4 remainder 27  → network = 4 × 32 = 128
   Subnet = 10.0.0.128/27, broadcast 10.0.0.159
   Host range = 10.0.0.129 – 10.0.0.158
```

**Decimal mask values you must recognize on sight:** `128, 192, 224, 240, 248, 252, 254, 255`. Anything else in a mask octet is malformed.

**Reserved gotchas:** `/31` is legal point-to-point (RFC 3021, both addresses usable, no broadcast). `/32` is a single-host route — common for loopbacks and ACL targets.

### CIDR

**CIDR** (Classless Inter-Domain Routing, RFC 4632) replaced the old **classful** (`A`/`B`/`C`) addressing scheme. Instead of fixed `/8`, `/16`, `/24` boundaries, CIDR allows any prefix length from `/0` to `/32`, written as `address/prefix-length`.

**Classful vs Classless:**

| Class | Old Range                       | Implicit Mask     | Why retired                                   |
| ----- | ------------------------------- | ----------------- | --------------------------------------------- |
| A     | `1.0.0.0` – `126.255.255.255`   | `/8` (16M hosts)  | Wasted huge blocks on small organizations.    |
| B     | `128.0.0.0` – `191.255.255.255` | `/16` (65K hosts) | Same problem — coarse boundaries.             |
| C     | `192.0.0.0` – `223.255.255.255` | `/24` (254 hosts) | Routing tables exploded as the internet grew. |

CIDR fixed both problems: arbitrary prefix lengths for right-sized allocation, plus **route aggregation** to shrink global routing tables.

**Supernetting (aggregation):** combine multiple contiguous subnets into one larger advertised prefix.

```
192.168.0.0/24
192.168.1.0/24
192.168.2.0/24
192.168.3.0/24
        ↓ aggregate
192.168.0.0/22         (four /24s combined — one route advertised)
```

For aggregation to work the blocks must be **contiguous** and **aligned** on the larger prefix boundary.

**Reading a CIDR block fast:**

```
10.20.0.0/19
  prefix /19 → host bits = 13 → 2^13 = 8192 addresses, 8190 usable
  mask = 255.255.224.0
  3rd-octet block size = 256 − 224 = 32
  → covers 10.20.0.0 – 10.20.31.255
```

**Special CIDR blocks worth knowing:**

| CIDR             | Meaning                                                    |
| ---------------- | ---------------------------------------------------------- |
| `0.0.0.0/0`      | Default route — "everything not matched elsewhere".        |
| `10.0.0.0/8`     | RFC 1918 private.                                          |
| `172.16.0.0/12`  | RFC 1918 private (covers `172.16.0.0` – `172.31.255.255`). |
| `192.168.0.0/16` | RFC 1918 private.                                          |
| `127.0.0.0/8`    | Loopback.                                                  |
| `169.254.0.0/16` | Link-local (APIPA — host couldn't reach DHCP).             |
| `100.64.0.0/10`  | Carrier-grade NAT (RFC 6598).                              |
| `224.0.0.0/4`    | Multicast.                                                 |

**Wildcard masks** (Cisco ACLs) are the bit-inverse of a subnet mask — `/24` ↔ `0.0.0.255`. Don't mix them up with subnet masks.

### IPv4

IPv4 subnetting is the art of borrowing bits from the **host** portion of an address to create more (smaller) networks. Once you can read a subnet mask in binary, the rest of the math falls out automatically.

#### Anatomy of an IPv4 Address

- An IPv4 address is **32 bits**, written as four **octets** (0–255) separated by dots: `192.168.1.10`.
- Every address is split by a **subnet mask** into two parts:
  - **Network portion** — identifies the network (shared by every host on the subnet).
  - **Host portion** — identifies a specific host inside that network.

```
 Address : 192.168.1.10       → 11000000.10101000.00000001.00001010
 Mask    : 255.255.255.0      → 11111111.11111111.11111111.00000000
 Network : 192.168.1.0        → 11000000.10101000.00000001.00000000
 Host    : .10                → 00000000.00000000.00000000.00001010
```

The mask is a contiguous run of `1`s followed by `0`s — the boundary between them is the network/host split.

#### CIDR Notation

**CIDR** (Classless Inter-Domain Routing) writes the mask as a single number after a `/` — the count of `1` bits in the mask.

| CIDR  | Subnet Mask       | Network Bits | Host Bits | Usable Hosts                 |
| ----- | ----------------- | ------------ | --------- | ---------------------------- |
| `/8`  | `255.0.0.0`       | 8            | 24        | 16,777,214                   |
| `/16` | `255.255.0.0`     | 16           | 16        | 65,534                       |
| `/24` | `255.255.255.0`   | 24           | 8         | 254                          |
| `/25` | `255.255.255.128` | 25           | 7         | 126                          |
| `/26` | `255.255.255.192` | 26           | 6         | 62                           |
| `/27` | `255.255.255.224` | 27           | 5         | 30                           |
| `/28` | `255.255.255.240` | 28           | 4         | 14                           |
| `/29` | `255.255.255.248` | 29           | 3         | 6                            |
| `/30` | `255.255.255.252` | 30           | 2         | 2                            |
| `/31` | `255.255.255.254` | 31           | 1         | 2 (point-to-point, RFC 3021) |
| `/32` | `255.255.255.255` | 32           | 0         | 1 (single host route)        |

**Formulas:**

- Total addresses in a subnet = `2^(host bits)`
- Usable host addresses = `2^(host bits) − 2` (subtract the network + broadcast addresses)
- Number of subnets when borrowing `n` bits = `2^n`

#### Network, Broadcast, and Host Addresses

Every IPv4 subnet has three special address types:

| Address               | How to Find It                                            | Usable for Hosts? |
| --------------------- | --------------------------------------------------------- | ----------------- |
| **Network address**   | All host bits set to `0` — the first address in the block | No                |
| **Broadcast address** | All host bits set to `1` — the last address in the block  | No                |
| **Host addresses**    | Everything in between                                     | Yes               |

**Example:** for `192.168.1.0/24`:

- Network address → `192.168.1.0`
- Broadcast address → `192.168.1.255`
- Usable host range → `192.168.1.1` – `192.168.1.254` (254 hosts)

#### Worked Example — Splitting `192.168.1.0/24` into Four Subnets

Borrow **2 bits** from the host portion (`/24` → `/26`) to create `2² = 4` subnets, each with `2⁶ − 2 = 62` usable hosts.

| Subnet | CIDR               | Network         | First Host      | Last Host       | Broadcast       |
| ------ | ------------------ | --------------- | --------------- | --------------- | --------------- |
| 1      | `192.168.1.0/26`   | `192.168.1.0`   | `192.168.1.1`   | `192.168.1.62`  | `192.168.1.63`  |
| 2      | `192.168.1.64/26`  | `192.168.1.64`  | `192.168.1.65`  | `192.168.1.126` | `192.168.1.127` |
| 3      | `192.168.1.128/26` | `192.168.1.128` | `192.168.1.129` | `192.168.1.190` | `192.168.1.191` |
| 4      | `192.168.1.192/26` | `192.168.1.192` | `192.168.1.193` | `192.168.1.254` | `192.168.1.255` |

**Block size shortcut:** for a `/26` mask, the last octet steps by `256 − 192 = 64`. Memorize this and you can write the table in seconds.

#### Common Block Sizes (Last Octet)

| CIDR  | Mask Last Octet | Block Size | Subnets per /24 |
| ----- | --------------- | ---------- | --------------- |
| `/25` | `128`           | 128        | 2               |
| `/26` | `192`           | 64         | 4               |
| `/27` | `224`           | 32         | 8               |
| `/28` | `240`           | 16         | 16              |
| `/29` | `248`           | 8          | 32              |
| `/30` | `252`           | 4          | 64              |

#### Determining If Two Hosts Are on the Same Subnet

Apply the mask (bitwise AND) to both addresses and compare the network portions.

```
A: 10.0.5.20  /22   → network 10.0.4.0
B: 10.0.6.30  /22   → network 10.0.4.0     ← same subnet ✓

A: 10.0.5.20  /24   → network 10.0.5.0
B: 10.0.6.30  /24   → network 10.0.6.0     ← different subnets ✗ (need a router)
```

#### VLSM — Variable Length Subnet Masking

Real networks rarely need equal-sized subnets. **VLSM** lets you carve a parent block into subnets of **different** sizes, always starting from the **largest** requirement first.

**Example:** split `192.168.10.0/24` for these needs:

| Department  | Hosts Needed | CIDR  | Range                               |
| ----------- | ------------ | ----- | ----------------------------------- |
| Sales       | 100          | `/25` | `192.168.10.0` – `192.168.10.127`   |
| Engineering | 50           | `/26` | `192.168.10.128` – `192.168.10.191` |
| Ops         | 25           | `/27` | `192.168.10.192` – `192.168.10.223` |
| Mgmt        | 10           | `/28` | `192.168.10.224` – `192.168.10.239` |
| WAN link    | 2            | `/30` | `192.168.10.240` – `192.168.10.243` |

Always allocate the **biggest** block first — otherwise smaller subnets fragment the space and leave you unable to fit the larger ones.

#### Inspecting Subnets on Linux

```bash
# Show interfaces with their CIDR — the /24, /22 part is the mask
ip -4 a

# Which subnet does my host think 10.0.5.20 is on?
ip route get 10.0.5.20

# Quick subnet math from the shell (requires `ipcalc`)
ipcalc 192.168.1.0/26

# Same idea with `sipcalc` (more detailed output)
sipcalc 192.168.1.0/26

# One-liner: is 10.0.6.30 inside 10.0.4.0/22 ?
python3 -c "import ipaddress; print(ipaddress.ip_address('10.0.6.30') in ipaddress.ip_network('10.0.4.0/22'))"
```

**Notes:**

- The mask **must be contiguous** — `255.255.255.0` is valid, `255.0.255.0` is not.
- A `/31` is legal on point-to-point links (RFC 3021) — both addresses are usable, no broadcast.
- Don't confuse a **subnet mask** (`/24`) with a **wildcard mask** (`0.0.0.255`) — they are bit-inverses and used in different tools (ACLs in Cisco IOS use wildcards).
- **Classful ranges** (Class A `/8`, B `/16`, C `/24`) are historical — modern routing is classless (CIDR). They still show up in interview questions, so know them.
- When in doubt, write the mask in binary — the network/host split becomes obvious.
- Common interview question: _"How many usable hosts in a `/26`?"_ → `2^6 − 2 = 62`.

### NAT

**NAT** (Network Address Translation, RFC 3022) rewrites IP addresses (and often ports) as packets cross a boundary — typically between a private RFC 1918 network and the public internet. NAT is what lets thousands of home or office devices share a single public IPv4 address.

**Why NAT exists:** IPv4 has only ~4.3 billion addresses. NAT lets one public IP front many private hosts, postponing IPv4 exhaustion. IPv6 was designed to eliminate this need — see the next section.

**Types of NAT:**

| Type                          | Direction                    | What it rewrites                  | Use case                                                            |
| ----------------------------- | ---------------------------- | --------------------------------- | ------------------------------------------------------------------- |
| **SNAT** (Source NAT)         | Outbound                     | Source IP (sometimes port)        | Hide internal IPs behind a public one.                              |
| **DNAT** (Destination NAT)    | Inbound                      | Destination IP (sometimes port)   | Port forwarding — expose an internal server.                        |
| **PAT** / **NAPT**            | Outbound, many-to-one        | Source IP **and** port            | Home routers — many private hosts share one public IP.              |
| **Static NAT**                | Both                         | 1-to-1 IP mapping, no port change | Permanently map a public IP to one internal server.                 |
| **Hairpin NAT**               | Internal → public → internal | Both source and destination       | Reach your own server via its public IP from inside.                |
| **NAT64 / DNS64**             | IPv6 ↔ IPv4                  | Address family                    | Let IPv6-only clients reach IPv4-only services.                     |
| **CGNAT** (Carrier-grade NAT) | ISP-level                    | Multiple layers of NAT            | ISPs share one public IP across many subscribers (`100.64.0.0/10`). |

**NAT connection-tracking flow (PAT example):**

```
Internal client 10.0.0.5:51234  → router rewrites → 203.0.113.10:40001  → server 8.8.8.8:443
Server replies:                  203.0.113.10:40001 → router rewrites back → 10.0.0.5:51234
```

The router keeps a **connection-tracking table** mapping `(public-ip, public-port) ↔ (private-ip, private-port)`. When the flow ends or times out, the entry is freed.

**NAT on Linux — `nftables`:**

```bash
# Masquerade (SNAT with the dynamic interface IP) — classic home-router pattern
nft add table ip nat
nft add chain ip nat postrouting '{ type nat hook postrouting priority 100; }'
nft add rule ip nat postrouting oifname "eth0" masquerade

# DNAT — forward public :8080 to internal web server :80
nft add chain ip nat prerouting '{ type nat hook prerouting priority -100; }'
nft add rule ip nat prerouting iifname "eth0" tcp dport 8080 dnat to 10.0.0.20:80
```

**Equivalent with `iptables` (legacy but ubiquitous):**

```bash
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
iptables -t nat -A PREROUTING  -i eth0 -p tcp --dport 8080 -j DNAT --to 10.0.0.20:80
```

**NAT trade-offs:**

- Breaks end-to-end connectivity — peer-to-peer protocols (SIP, FTP, WebRTC, BitTorrent) need helpers like **STUN / TURN / ICE** or **ALGs**.
- Hides the real client IP from servers (mitigated by `X-Forwarded-For`, PROXY protocol).
- Stateful — the router must remember every flow; large NAT tables can become a bottleneck.
- Provides _incidental_ security (inbound unsolicited traffic has no mapping), but it's **not** a firewall — don't treat NAT as a security boundary.

**Inspect NAT state on Linux:**

```bash
# Live NAT / conntrack entries
sudo conntrack -L

# Just show the NAT rules currently loaded
sudo nft list table nat
sudo iptables -t nat -L -nv
```

### IPv6

**IPv6** (RFC 8200) replaces IPv4's 32-bit addresses with **128-bit** addresses — `2^128` ≈ `3.4 × 10^38` total, enough that NAT and address scarcity disappear as design constraints. Subnetting still uses CIDR notation but with very different conventions.

**Address format:**

- 128 bits, written as **eight 16-bit hex groups** separated by colons: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.
- **Compression rules:**
  - Drop leading zeros in each group: `2001:db8:85a3:0:0:8a2e:370:7334`.
  - Replace one run of all-zero groups with `::` (only once per address): `2001:db8:85a3::8a2e:370:7334`.

**Address types:**

| Type                     | Prefix                            | Meaning                                                                             |
| ------------------------ | --------------------------------- | ----------------------------------------------------------------------------------- |
| **Global Unicast (GUA)** | `2000::/3`                        | Routable on the public internet (analog of IPv4 public addresses).                  |
| **Unique Local (ULA)**   | `fc00::/7` (typically `fd00::/8`) | Private, non-routable on the internet (analog of RFC 1918).                         |
| **Link-Local (LLA)**     | `fe80::/10`                       | Auto-assigned per interface, valid only on that link. Every IPv6 interface has one. |
| **Multicast**            | `ff00::/8`                        | Replaces broadcast — `ff02::1` = all nodes, `ff02::2` = all routers on the link.    |
| **Loopback**             | `::1/128`                         | Equivalent of `127.0.0.1`.                                                          |
| **Unspecified**          | `::/128`                          | Equivalent of `0.0.0.0` — "no address yet".                                         |
| **IPv4-mapped**          | `::ffff:0:0/96`                   | Used in dual-stack sockets — `::ffff:192.0.2.1` represents an IPv4 inside IPv6.     |

**Subnetting conventions:**

- Standard **end-site allocation** is `/48` per organization, **`/64` per subnet**, leaving 16 bits of subnet ID — 65,536 subnets per site.
- **`/64` is the universal subnet size** — required for SLAAC (Stateless Address Autoconfiguration) to work. Don't make IPv6 subnets smaller than `/64` except on point-to-point links (`/127`) or loopbacks (`/128`).
- The 64-bit **interface ID** is auto-generated from the MAC (modified EUI-64) or random (privacy extensions, RFC 4941).

**Common prefix lengths:**

| Prefix | Typical use                                          |
| ------ | ---------------------------------------------------- |
| `/32`  | ISP allocation from an RIR.                          |
| `/48`  | Site / organization allocation.                      |
| `/56`  | Smaller end-site (what some ISPs hand out to homes). |
| `/64`  | A single subnet (standard).                          |
| `/127` | Point-to-point link (RFC 6164).                      |
| `/128` | Single host / loopback.                              |

**SLAAC vs DHCPv6:**

- **SLAAC** — host hears a Router Advertisement, builds its own address from the announced `/64` prefix + a 64-bit interface ID. No server needed.
- **DHCPv6** — stateful, server-assigned, used when you need to track or push extra config (DNS, NTP). Often combined with SLAAC (`M` / `O` flags in the RA).

**No NAT — by design:** every host can have a globally routable address, so NAT is unnecessary. Privacy comes from **temporary addresses** (random interface IDs that rotate). Firewalls still enforce inbound policy.

**Inspect IPv6 on Linux:**

```bash
# Show IPv6 addresses on all interfaces
ip -6 a

# Show the IPv6 routing table
ip -6 route

# Show the IPv6 neighbor cache (IPv6's equivalent of ARP)
ip -6 neigh

# Ping IPv6
ping -6 2606:4700:4700::1111      # Cloudflare public DNS
ping ::1                          # loopback

# Discover routers on the link
rdisc6 eth0
```

**IPv6 vs IPv4 quick contrasts:**

| Aspect             | IPv4                   | IPv6                                          |
| ------------------ | ---------------------- | --------------------------------------------- |
| Address size       | 32 bits                | 128 bits                                      |
| Notation           | Dotted-decimal         | Colon-hex with `::` compression               |
| Address resolution | ARP                    | NDP (Neighbor Discovery Protocol) over ICMPv6 |
| Broadcast          | Yes (`x.x.x.255`)      | None — replaced by multicast                  |
| Autoconfig         | DHCP only              | SLAAC, DHCPv6, or both                        |
| NAT                | Common (NAT44, PAT)    | Discouraged — designed for end-to-end         |
| Header             | Variable, with options | Fixed 40-byte, extension headers              |
| Fragmentation      | Routers + hosts        | Hosts only (PMTUD required)                   |

---

## Routing

**Routing** is how packets find their way from source to destination across multiple networks. Each router compares the destination IP of every incoming packet against its **routing table** and forwards the packet out the best-matching interface — hop by hop, until it reaches the target network.

### One Shot Revision

| Topic                                                   | Short Description                                                           |
| ------------------------------------------------------- | --------------------------------------------------------------------------- |
| [Routing Basics](#routing-basics)                       | How routers move packets between networks, hop-by-hop forwarding            |
| [Routing Table](#routing-table)                         | Entries, longest-prefix match, metrics, administrative distance             |
| [Path of a Packet](#path-of-a-packet)                   | End-to-end walk of a packet from source host through routers to destination |
| [Default Gateway](#default-gateway)                     | The `0.0.0.0/0` route used when nothing more specific matches               |
| [Static vs Dynamic Routing](#static-vs-dynamic-routing) | When to hand-code routes vs let a protocol discover them                    |
| [Routing Protocols](#routing-protocols)                 | RIP, OSPF, EIGRP, BGP — what each is for                                    |
| [Distance Vector Protocols](#distance-vector-protocols) | Bellman-Ford, routing by rumor, split horizon, RIP/EIGRP family             |
| [Link State Protocols](#link-state-protocols)           | Dijkstra SPF, LSAs, LSDB, OSPF areas and adjacency states                   |
| [Border Gateway Protocol](#border-gateway-protocol)     | Path-vector EGP of the internet; eBGP vs iBGP, best-path selection          |
| [IGP vs EGP](#igp-vs-egp)                               | Interior vs exterior gateway protocols and where they run                   |
| [Linux Routing](#linux-routing)                         | `ip route`, policy routing, multiple tables                                 |

### Routing Basics

A **router** is a Layer-3 device that forwards packets between different IP networks. Every router maintains a **routing table** — a list of known destination networks plus the next-hop or outgoing interface for each.

**How forwarding works (per packet):**

1. A packet arrives on an interface; the router reads its **destination IP**.
2. The router searches its table for the **longest matching prefix** (most specific entry).
3. The packet is rewritten with a new Layer-2 header and sent out the matching interface toward the **next hop**.
4. TTL is decremented; if it hits `0`, the packet is dropped and an ICMP Time Exceeded is returned.

**Key concepts:**

| Term                        | Meaning                                                                             |
| --------------------------- | ----------------------------------------------------------------------------------- |
| **Next hop**                | IP of the neighboring router that should receive the packet next.                   |
| **Outgoing interface**      | Local interface the router sends the packet out on.                                 |
| **Metric**                  | A number used to break ties between routes from the same protocol (lower = better). |
| **Administrative distance** | Trust level between sources — e.g., static beats OSPF beats RIP.                    |
| **Convergence**             | How long it takes for every router to agree on the topology after a change.         |

Routers only forward — they don't inspect payloads. End hosts also have a routing table; for a typical laptop it has just two entries: its own subnet and a default gateway.

### Routing Table

A routing table holds entries that say "to reach destination D, send the packet via next hop N out interface I." The router picks the **most specific** match — this is **longest-prefix match**.

**Sample table (Linux `ip route`):**

```
default via 192.168.1.1 dev eth0 proto dhcp metric 100
10.0.0.0/8 via 192.168.1.254 dev eth0
192.168.1.0/24 dev eth0 proto kernel scope link src 192.168.1.42
```

| Destination      | Next Hop        | Interface | Notes                          |
| ---------------- | --------------- | --------- | ------------------------------ |
| `0.0.0.0/0`      | `192.168.1.1`   | `eth0`    | Default route                  |
| `10.0.0.0/8`     | `192.168.1.254` | `eth0`    | Static route to internal block |
| `192.168.1.0/24` | —               | `eth0`    | Directly connected subnet      |

**Longest-prefix match — worked example.** A packet destined for `10.0.5.20` arrives. The table contains:

```
0.0.0.0/0     via 192.168.1.1
10.0.0.0/8    via 192.168.1.254
10.0.5.0/24   via 10.10.10.2
```

All three entries match, but `/24` is more specific than `/8`, which is more specific than `/0`. The router uses `10.0.5.0/24` and forwards to `10.10.10.2`.

**Administrative distance (Cisco defaults):**

| Source    | AD  |
| --------- | --- |
| Connected | 0   |
| Static    | 1   |
| eBGP      | 20  |
| OSPF      | 110 |
| RIP       | 120 |
| iBGP      | 200 |

When two protocols learn the **same** prefix, the router installs the one with the **lowest** AD.

### Default Gateway

The **default gateway** is the router a host uses when the destination isn't on any directly connected subnet — it's the route that matches every IP, written `0.0.0.0/0` (IPv4) or `::/0` (IPv6).

```bash
# Show the default gateway
ip route show default
# default via 192.168.1.1 dev eth0

# Set a default gateway manually
sudo ip route add default via 192.168.1.1 dev eth0

# Remove it
sudo ip route del default
```

Most laptops, phones, and servers learn their default gateway via **DHCP**; you only set it by hand on static-IP servers or routers.

### Static vs Dynamic Routing

Two ways to populate a routing table — they're not mutually exclusive; most real networks use both.

| Aspect            | Static Routing                              | Dynamic Routing                          |
| ----------------- | ------------------------------------------- | ---------------------------------------- |
| Configuration     | Hand-entered by admin                       | Learned via a routing protocol           |
| Reacts to outages | No — manual fix required                    | Yes — protocol reconverges automatically |
| Overhead          | Zero — no protocol traffic, no CPU          | CPU + bandwidth for hellos and updates   |
| Scalability       | Fine for small or stub networks             | Required for medium and large networks   |
| Predictability    | Fully deterministic                         | Depends on protocol convergence behavior |
| Common uses       | Default routes, point-to-point links, edges | Backbones, multi-path networks, ISPs     |

**Static route on Linux:**

```bash
# Send 10.20.0.0/16 traffic via 192.168.1.254
sudo ip route add 10.20.0.0/16 via 192.168.1.254 dev eth0

# Persist across reboots (Debian/Ubuntu netplan example)
# /etc/netplan/01-netcfg.yaml:
#   routes:
#     - to: 10.20.0.0/16
#       via: 192.168.1.254
```

**When to prefer static:** small networks, predictable topology, security-sensitive paths where you want zero protocol surface, or backup routes that should never auto-reconverge.

### Routing Protocols

Dynamic routing protocols let routers **discover** the topology and **react** to link changes without human intervention. Four show up everywhere.

| Protocol  | Type                 | Algorithm        | Metric                                | Typical Use                                 |
| --------- | -------------------- | ---------------- | ------------------------------------- | ------------------------------------------- |
| **RIP**   | IGP, distance-vector | Bellman-Ford     | Hop count (max 15)                    | Tiny legacy networks; rare today            |
| **OSPF**  | IGP, link-state      | Dijkstra (SPF)   | Cost (based on bandwidth)             | Most enterprise LANs and campuses           |
| **EIGRP** | IGP, hybrid          | DUAL             | Bandwidth + delay (configurable)      | Cisco-heavy networks                        |
| **BGP**   | EGP, path-vector     | Best-path policy | AS path, local pref, MED, communities | The protocol of the internet (between ASes) |

**Quick characterizations:**

- **RIP** — simple, periodic full-table updates every 30s; max 15 hops makes anything bigger unreachable. Mostly historical.
- **OSPF** — every router floods Link-State Advertisements (LSAs) describing its own links; each router independently runs Dijkstra to compute shortest paths. Fast convergence, organized into **areas** for scale.
- **EIGRP** — originally Cisco-proprietary (now open); converges fast using the DUAL algorithm and keeps a feasible successor (precomputed backup path).
- **BGP** — the protocol that holds the internet together. Each Autonomous System announces the prefixes it owns; BGP picks paths based on **policy**, not just shortest hop count.

### Distance Vector Protocols

Distance-vector protocols advertise **the distance and direction** to each destination — "I can reach network X in N hops, via me." Each router trusts its neighbors' summaries and never builds a full topology map. This is **routing by rumor**.

**How they work:**

1. Every router sends its **entire routing table** to directly connected neighbors on a timer.
2. A neighbor adds its own cost (e.g., `+1` hop) and installs the route if it's better than what it already has.
3. Repeat until the network converges — every router has consistent information.

**Core algorithm:** Bellman-Ford — shortest path is computed incrementally by comparing each neighbor's advertised cost plus the link cost.

| Protocol   | Metric                       | Update Style                         | Notes                                     |
| ---------- | ---------------------------- | ------------------------------------ | ----------------------------------------- |
| **RIPv1**  | Hop count (max 15)           | Full table, broadcast every 30s      | Classful; obsolete                        |
| **RIPv2**  | Hop count (max 15)           | Full table, multicast `224.0.0.9`    | Classless (supports VLSM/CIDR); rare use  |
| **RIPng**  | Hop count (max 15)           | IPv6 variant of RIPv2                | Rarely deployed                           |
| **IGRP**   | Bandwidth + delay            | Cisco-proprietary; deprecated        | Superseded by EIGRP                       |
| **EIGRP**  | Bandwidth + delay (DUAL)     | Triggered updates only               | Hybrid — has link-state-like properties   |

**Weaknesses & the loops they cause:**

- **Slow convergence** — updates propagate one hop per interval, so large networks take a long time to stabilize.
- **Count-to-infinity** — after a link fails, two routers can keep advertising the dead route back and forth with ever-increasing metrics.
- **Routing loops** — traffic can bounce between routers with stale views of the topology.

**Loop-prevention tricks:**

| Technique             | What It Does                                                                             |
| --------------------- | ---------------------------------------------------------------------------------------- |
| **Split horizon**     | Never advertise a route back out the interface you learned it from.                      |
| **Route poisoning**   | Advertise a failed route with an unreachable metric (e.g., 16 hops in RIP).              |
| **Poison reverse**    | Explicitly send the poisoned route back to the neighbor to break the loop faster.        |
| **Hold-down timer**   | Ignore updates about a flapping route for a fixed period after it goes down.             |
| **Triggered updates** | Send an update immediately on topology change instead of waiting for the periodic timer. |

**When to use:** small, stable, low-budget networks — or never, in a modern enterprise. Most environments have moved on to OSPF or EIGRP.

### Link State Protocols

Link-state protocols advertise **the state of each of a router's own links** — not summaries from neighbors. Every router in an area ends up with an identical **map of the topology** and independently computes the shortest paths from its own point of view.

**How they work:**

1. Every router discovers its **directly connected neighbors** via periodic **Hello** packets.
2. Each router originates **Link-State Advertisements (LSAs)** describing its links (neighbor, cost, state) and floods them reliably to all routers in the area.
3. Every router assembles the LSAs into a **Link-State Database (LSDB)** — an identical topology graph across the area.
4. Each router runs **Dijkstra's SPF algorithm** on the LSDB to compute the shortest path to every destination.

**Core algorithm:** Dijkstra's Shortest Path First (SPF) — builds a tree rooted at the calculating router with the least-cost path to every other node.

| Protocol  | Layer            | Metric                    | Notes                                                    |
| --------- | ---------------- | ------------------------- | -------------------------------------------------------- |
| **OSPF**  | IP (proto 89)    | Cost = ref-bw / link-bw   | Ubiquitous IGP; organized into **areas** for scalability |
| **IS-IS** | Directly on L2   | Configurable cost         | Common in large ISPs and service-provider backbones      |

**OSPF areas — why they exist:**

Big flat link-state networks are expensive: every router runs Dijkstra over every link. OSPF splits the AS into **areas** that summarize routes to one another; area **0 (backbone)** must connect all others.

| Area Type            | Description                                                                        |
| -------------------- | ---------------------------------------------------------------------------------- |
| **Backbone (0)**     | Central area; every other area must attach to it.                                  |
| **Standard**         | Normal area; carries intra- and inter-area routes.                                 |
| **Stub**             | Blocks external (Type-5) LSAs; replaces them with a default route.                 |
| **Totally Stubby**   | Blocks external **and** inter-area LSAs; only a default route leaves the area.     |
| **NSSA**             | "Not-So-Stubby" — like stub but allows limited external routes via Type-7 LSAs.    |

**Strengths:**

- **Fast convergence** — LSAs flood immediately on change; SPF runs in milliseconds.
- **No routing loops** — every router has the same map.
- **Scalable** — hierarchical areas keep LSDB size and SPF cost bounded.

**Costs:**

- More CPU and memory per router (holding the LSDB, running SPF).
- More complex to design and troubleshoot (areas, LSA types, adjacency states).

**OSPF adjacency states** (worth recognizing in logs): `Down → Init → 2-Way → ExStart → Exchange → Loading → Full`. `Full` means the neighbors have synchronized their LSDBs.

### Border Gateway Protocol

**BGP** is the routing protocol that runs the **public internet**. Every ISP, cloud, and large enterprise that owns an AS uses BGP to tell the world "these prefixes belong to me, and here is the AS-path to reach them." Unlike IGPs, BGP is **policy-driven** — the "best" path is whatever the local network's business rules say it is, not necessarily the shortest.

**Key characteristics:**

| Attribute       | Value                                                                          |
| --------------- | ------------------------------------------------------------------------------ |
| Type            | **Path-vector** protocol (advertises the full AS-path, not just a distance)    |
| Transport       | **TCP port 179** — sessions must be manually configured with each neighbor     |
| Scope           | **EGP** — runs between Autonomous Systems (also runs inside as **iBGP**)       |
| Convergence     | **Slow** by design — stability matters more than speed at internet scale       |
| Table size      | The full internet routing table is ~950k+ IPv4 prefixes (as of 2026)           |

**eBGP vs iBGP:**

| Variant   | Runs Between                        | TTL      | Purpose                                          |
| --------- | ----------------------------------- | -------- | ------------------------------------------------ |
| **eBGP**  | Routers in **different** ASes       | 1        | Exchange routes with peers and providers         |
| **iBGP**  | Routers in the **same** AS          | 255      | Distribute externally learned routes internally  |

iBGP requires a **full mesh** (every iBGP speaker peers with every other) or a scalability workaround like **route reflectors** or **confederations**.

**Best-path selection order** (simplified — real routers walk a longer list):

1. **Weight** (Cisco-local; higher wins)
2. **LOCAL_PREF** (higher wins; used to steer outbound traffic within an AS)
3. **Locally originated** routes beat learned ones
4. **AS_PATH length** (shorter wins — the closest thing BGP has to "hop count")
5. **Origin type** (IGP `<` EGP `<` Incomplete)
6. **MED** (Multi-Exit Discriminator; lower wins — hints to neighbors which entry point to prefer)
7. **eBGP > iBGP**
8. **Lowest IGP cost** to the next-hop
9. **Router-ID tie-break**

**Common BGP attributes:**

| Attribute       | Purpose                                                                                    |
| --------------- | ------------------------------------------------------------------------------------------ |
| **AS_PATH**     | Ordered list of ASes the prefix has traversed. Also prevents loops (reject if own ASN).    |
| **NEXT_HOP**    | IP of the router to forward packets to for this prefix.                                    |
| **LOCAL_PREF**  | Per-AS preference for outbound traffic (higher = more preferred).                          |
| **MED**         | Cross-AS hint to influence a neighbor's inbound decision (lower = more preferred).         |
| **COMMUNITIES** | Tags attached to routes (e.g., `65000:100`) used by policy filters at other ASes.          |

**Operational realities:**

- **Route hijacking** — anyone can announce anyone's prefix if their upstream doesn't filter. **RPKI** (Resource Public Key Infrastructure) cryptographically validates prefix ownership to mitigate this.
- **BGP flapping** — unstable sessions cause churn; **route dampening** penalizes prefixes that flap repeatedly.
- **Full table vs default** — small edge routers take only a default route from their ISP; transit routers take the **full internet table** (~950k+ IPv4 routes).
- **On Linux** — use **FRR** (Free Range Routing) or **BIRD** to speak BGP; commonly seen inside data-center fabrics ("BGP in the DC") and cloud VPN gateways.

### IGP vs EGP

Routing protocols are categorized by **where** they run.

| Category | Stands For                | Runs Where                        | Examples                   |
| -------- | ------------------------- | --------------------------------- | -------------------------- |
| **IGP**  | Interior Gateway Protocol | Inside a single Autonomous System | RIP, OSPF, EIGRP, IS-IS    |
| **EGP**  | Exterior Gateway Protocol | Between Autonomous Systems        | BGP (only one in real use) |

An **Autonomous System (AS)** is a network under a single administrative authority — an ISP, a large enterprise, a cloud provider — identified by a globally unique **AS number (ASN)**.

- Inside your AS, you use an IGP (commonly OSPF) to learn internal routes fast.
- To talk to other ASes (the rest of the internet), you peer with them over **BGP**.

### Linux Routing

The kernel keeps one or more routing tables; `ip route` is the modern interface.

```bash
# Show the main routing table
ip route
# default via 192.168.1.1 dev eth0
# 192.168.1.0/24 dev eth0 proto kernel scope link src 192.168.1.42

# Show how the kernel would route a specific destination
ip route get 8.8.8.8
# 8.8.8.8 via 192.168.1.1 dev eth0 src 192.168.1.42 uid 1000

# Add a static route
sudo ip route add 10.20.0.0/16 via 192.168.1.254 dev eth0

# Delete a route
sudo ip route del 10.20.0.0/16

# Enable IP forwarding (turn a Linux box into a router)
sudo sysctl -w net.ipv4.ip_forward=1
# Persist in /etc/sysctl.conf:  net.ipv4.ip_forward = 1
```

**Multiple routing tables (policy routing):**

Linux supports many named tables (`/etc/iproute2/rt_tables`) and rules that pick which table to consult per packet — useful for multi-homed hosts, VPNs, and source-based routing.

```bash
# List rules (which table to use for which packets)
ip rule show

# Show a non-default table
ip route show table 100

# Add a rule: traffic from 192.168.50.0/24 uses table 100
sudo ip rule add from 192.168.50.0/24 table 100

# Add a default route inside table 100
sudo ip route add default via 10.0.0.1 dev eth1 table 100
```

**Notes:**

- `ip route` changes are **runtime only** — to persist, use NetworkManager, netplan, systemd-networkd, or `/etc/network/interfaces` depending on distro.
- A Linux router with `ip_forward=1` and proper firewall/NAT rules can replace a small commercial router — and it's exactly what most home routers run under the hood.
- For BGP/OSPF on Linux use a routing daemon like **FRR** (Free Range Routing, the successor to Quagga) or **BIRD**.

---

## Network Configuration

Inspect and change interface settings, addresses, routes, and name resolution on a Linux host.

### One Shot Revision

| Command                                        | Short Description                                        |
| ---------------------------------------------- | -------------------------------------------------------- |
| [`ip`](#ip)                                    | The modern Swiss-army tool for interfaces, addrs, routes |
| [Network Interfaces](#network-interfaces)      | Physical & virtual NICs, naming, and state               |
| [`ifconfig`](#ifconfig)                        | Legacy interface tool (still common in older distros)    |
| [`route`](#route)                              | Legacy tool for viewing and editing the routing table    |
| [`hostname`](#hostname)                        | Show or set the system hostname                          |
| [`/etc/hosts`](#etchosts)                      | Static hostname → IP overrides, queried before DNS       |
| [`/etc/resolv.conf`](#etcresolvconf)           | Configured DNS resolvers and search domains              |
| [`nmcli`](#networkmanager-nmcli)               | NetworkManager CLI — manage connections and devices      |
| [`dhclient`](#dhclient)                        | Request, renew, or release a DHCP lease                  |
| [`arp`](#arp)                                  | Inspect and manage the ARP cache (IP ↔ MAC mappings)     |

### ip

_To be filled in._

### Network Interfaces

_To be filled in._

### ifconfig

_To be filled in._

### route

_To be filled in._

### hostname

_To be filled in._

### /etc/hosts

_To be filled in._

### /etc/resolv.conf

_To be filled in._

### NetworkManager (nmcli)

_To be filled in._

### dhclient

_To be filled in._

### arp

_To be filled in._

---

## Connectivity & Diagnostics

First-line tools for answering "can I reach that host, and if not, where does it break?"

### One Shot Revision

| Command                     | Short Description                                                |
| --------------------------- | ---------------------------------------------------------------- |
| [ICMP](#icmp)               | Internet Control Message Protocol — the signalling `ping` rides on |
| [`ping`](#ping)             | Send ICMP echoes to test reachability and round-trip time        |
| [`traceroute`](#traceroute) | Show the hops packets take to reach a destination                |
| [`netstat`](#netstat)       | Legacy socket/port lister (still common in old runbooks)         |
| [`mtr`](#mtr)               | Combined `ping` + `traceroute` with continuous per-hop stats     |
| [`telnet`](#telnet)         | Open a raw TCP connection to a host:port (handy for port checks) |
| [`nc`](#nc-netcat)          | Netcat — read/write TCP & UDP, simple servers, port scans        |

### ICMP

_To be filled in._

### ping

_To be filled in._

### traceroute

_To be filled in._

### netstat

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

| Command                             | Short Description                                             |
| ----------------------------------- | ------------------------------------------------------------- |
| [What is DNS](#what-is-dns)         | The phonebook of the internet — name → IP resolution          |
| [DNS Components](#dns-components)   | Resolvers, root/TLD/authoritative servers, zones, records     |
| [DNS Process](#dns-process)         | End-to-end lookup flow: recursive + iterative queries         |
| [`/etc/hosts`](#etchosts-1)         | Static local overrides — queried before hitting DNS           |
| [DNS Setup](#dns-setup)             | Configuring resolvers (`/etc/resolv.conf`, `systemd-resolved`) |
| [DNS Tools](#dns-tools-1)           | Overview of CLI tools used to query and debug DNS             |
| [`dig`](#dig)                       | The go-to DNS lookup tool — detailed, scriptable              |
| [`nslookup`](#nslookup)             | Interactive DNS lookup, still widely used                     |
| [`host`](#host)                     | Simple, quick name → address lookups                          |

### What is DNS

_To be filled in._

### DNS Components

_To be filled in._

### DNS Process

_To be filled in._

### /etc/hosts

_To be filled in._

### DNS Setup

_To be filled in._

### DNS Tools

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

| Command               | Short Description                                        |
| --------------------- | -------------------------------------------------------- |
| [`ss`](#ss)           | Modern replacement for `netstat` — fast and detailed     |
| [`lsof`](#lsof)       | List open files & sockets, mapped to processes           |

### ss

_To be filled in._

### lsof

_To be filled in._

---

## HTTP & Transfer Tools

Fetch URLs, inspect HTTP headers, and move files over the network.

### One Shot Revision

| Command         | Short Description                                        |
| --------------- | -------------------------------------------------------- |
| [`curl`](#curl) | Make HTTP(S) requests; inspect headers, status, timings  |
| [`wget`](#wget) | Download files recursively, resume interrupted downloads |

### curl

_To be filled in._

### wget

_To be filled in._

---

## Remote Access

Log in to remote hosts and move files between them — the daily bread of any DevOps role.

### One Shot Revision

| Command                                | Short Description                                   |
| -------------------------------------- | --------------------------------------------------- |
| [`ssh`](#ssh)                          | Encrypted remote shell over TCP/22                  |
| [`scp`](#scp)                          | Copy files over SSH                                 |
| [`rsync`](#rsync-1)                    | Efficient incremental file sync — local or over SSH |
| [SSH Keys & Config](#ssh-keys--config) | Key generation, `~/.ssh/config`, agent forwarding   |

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

| Command                   | Short Description                                          |
| ------------------------- | ---------------------------------------------------------- |
| [`iptables`](#iptables)   | Classic netfilter rule manager (still everywhere)          |
| [`nftables`](#nftables)   | Modern replacement for `iptables` — unified ruleset syntax |
| [`ufw`](#ufw)             | Uncomplicated Firewall — Ubuntu-friendly frontend          |
| [`firewalld`](#firewalld) | Zone-based firewall daemon (RHEL/CentOS/Fedora)            |

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

| Command                                    | Short Description                                        |
| ------------------------------------------ | -------------------------------------------------------- |
| [`tcpdump`](#tcpdump)                      | CLI packet capture — filter, dump, save as `.pcap`       |
| [`wireshark / tshark`](#wireshark--tshark) | GUI / CLI deep-dive packet analysis with full dissection |
| [`nmap`](#nmap)                            | Port scanner & host/service discovery tool               |

### tcpdump

_To be filled in._

### wireshark / tshark

_To be filled in._

### nmap

_To be filled in._

---

## Common Interview Questions

**50 commonly asked Networking interview questions** — every answer written from a **DevOps / Cloud Engineer interview perspective**: production scenarios, Kubernetes/cloud context, the follow-ups interviewers drill into, and the mistakes candidates make. Grouped as **10 Easy** (junior), **20 Medium** (mid-level), **20 Hard** (senior/SRE).

---

### Easy (Junior Level)

**1. What is the OSI model? Name all seven layers.**

The **OSI (Open Systems Interconnection)** model is a conceptual framework for how network communication works, split into 7 layers:

| # | Layer | Examples |
|---|-------|---------|
| 7 | Application | HTTP, DNS, SMTP, SSH, FTP |
| 6 | Presentation | TLS/SSL, JPEG, gzip encoding |
| 5 | Session | NetBIOS, RPC session management |
| 4 | Transport | TCP, UDP — port numbers, reliability |
| 3 | Network | IP, ICMP, routing |
| 2 | Data Link | Ethernet, MAC addresses, ARP, switches |
| 1 | Physical | Cables, Wi-Fi signals, fiber, NICs |

**Why DevOps interviewers care:** Troubleshooting uses layer-by-layer thinking. "Can you ping it?" = Layer 3. "Can you curl it?" = Layer 7. When you say "it's a Layer 4 issue" you're telling the interviewer you know TCP is failing, not DNS or the app. Common follow-up: *"Where does a load balancer sit?"* — Layer 4 (TCP/UDP) or Layer 7 (HTTP) depending on type.

**2. What is the difference between TCP and UDP?**

| Aspect | TCP | UDP |
|--------|-----|-----|
| Connection | 3-way handshake | Connectionless |
| Reliability | Guaranteed delivery, ordering, retransmit | Best-effort, no guarantee |
| Speed | Slower (overhead) | Faster |
| Use cases | HTTP/S, SSH, databases | DNS, video streaming, VoIP, game state |

**DevOps angle:** DNS queries use UDP (fast, small). DNS zone transfers use TCP (reliable, large). Kubernetes `kube-dns`/CoreDNS uses both. `etcd` uses TCP for Raft consensus — data must not be lost. Monitoring metrics (StatsD) use UDP intentionally — a dropped metric is better than blocking the app.

**3. What is an IP address? What is the difference between IPv4 and IPv6?**

An IP address is a unique identifier for a host on a network.

- **IPv4:** 32-bit, dotted-decimal (`192.168.1.10`). ~4.3 billion addresses — exhausted. Requires NAT at scale.
- **IPv6:** 128-bit, colon-hex (`2001:0db8::1`). 340 undecillion addresses. Built-in IPsec, no NAT needed.

**DevOps angle:** AWS, GCP, and Azure all dual-stack their infrastructure. EKS pods get IPv6 addresses natively in dual-stack clusters. `curl` on a dual-stack host prefers IPv6 by default (`-4` forces IPv4). Always test your app against both. `::1` is IPv6 loopback (same as `127.0.0.1`).

**4. What is DNS and how does it work?**

DNS (Domain Name System) translates human-readable names (`app.example.com`) into IP addresses.

Resolution flow: **Browser cache → OS cache → `/etc/hosts` → Recursive resolver (e.g. 8.8.8.8) → Root nameserver → TLD nameserver → Authoritative nameserver → Answer**.

**DevOps angle:** DNS is the first thing to check when a service is unreachable. `dig app.example.com` or `nslookup app.example.com` from inside the cluster tells you whether CoreDNS resolves it. In Kubernetes, service DNS is `<svc>.<namespace>.svc.cluster.local`. A missing record or wrong TTL causes cascading failures at deploy time.

**5. What is a subnet mask? What does `/24` mean?**

A subnet mask defines which part of an IP address is the network and which part is the host.

- `/24` = `255.255.255.0` — first 24 bits are network, last 8 bits are host. Gives **254 usable hosts** (256 − network − broadcast).
- `/16` = `255.255.0.0` — 65,534 usable hosts.
- `/32` = single host (used in security group rules, route table entries).

**DevOps angle:** AWS VPC subnets are CIDR blocks. A `/24` subnet gives you 251 usable IPs in AWS (5 reserved by AWS). EKS nodes in a `/24` subnet cap your pod count — a common mistake that requires a VPC re-architecture to fix.

**6. What is the default gateway?**

The default gateway is the router a host sends packets to when the destination IP is outside its local subnet. Every packet leaving a host's network goes to the gateway first.

```bash
ip route show          # Linux — look for 'default via x.x.x.x'
route -n               # legacy
```

**DevOps angle:** On a Kubernetes node, the default gateway is the VPC router. If a pod can reach the internet but not a specific VPC endpoint, the issue is routing (missing route or security group), not the gateway itself. Missing default gateway = no external connectivity.

**7. What is DHCP and what does it assign?**

DHCP (Dynamic Host Configuration Protocol) automatically assigns: **IP address, subnet mask, default gateway, DNS server IPs, and lease time** to clients on a network.

DORA process: **Discover → Offer → Request → Acknowledge** (UDP broadcast, ports 67/68).

**DevOps angle:** EC2 instances get IPs via DHCP from AWS's DHCP servers. EKS nodes get their primary IP via DHCP; pods get IPs from the VPC CNI plugin (secondary ENI IPs). DHCP lease expiry during a long-running instance can cause IP changes — always reference instances by hostname or Elastic IP, not raw IP.

**8. What is NAT and why is it used?**

NAT (Network Address Translation) maps private IPs to a public IP when traffic leaves a private network, and reverses it on the way back.

- **SNAT (Source NAT):** Private host → internet (outbound). NAT gateway in AWS.
- **DNAT (Destination NAT):** Inbound — maps public IP:port to a private host (port forwarding, load balancers).

**DevOps angle:** Private subnets in AWS have no direct internet access. A NAT Gateway in a public subnet allows outbound traffic (pulling Docker images, hitting APIs). Cost-conscious teams use NAT instances or VPC endpoints to avoid NAT Gateway data charges.

**9. What is the difference between a hub, switch, and router?**

| Device | Layer | How it works |
|--------|-------|-------------|
| Hub | L1 | Broadcasts to all ports — dumb repeater, creates collisions |
| Switch | L2 | Learns MAC addresses, forwards frames only to the correct port |
| Router | L3 | Routes packets between different networks using IP addresses |

**DevOps angle:** You almost never deal with hubs today. Switches are in your data center racks. Routers (or VPC route tables) are what you configure in cloud. A Kubernetes Service of type `NodePort` works at L4; a LoadBalancer creates a cloud L4/L7 load balancer in front of it.

**10. What ports do common protocols use?**

| Protocol | Port |
|----------|------|
| HTTP | 80 |
| HTTPS | 443 |
| SSH | 22 |
| DNS | 53 (UDP/TCP) |
| SMTP | 25 / 587 (TLS) |
| MySQL | 3306 |
| PostgreSQL | 5432 |
| Redis | 6379 |
| etcd | 2379 (client), 2380 (peer) |
| Kubernetes API | 6443 |
| kubelet | 10250 |

**DevOps angle:** Security groups and firewall rules live and die by port numbers. Misconfiguring a port (e.g., blocking 10250 between control plane and nodes) breaks kubelet communication and causes `NotReady` nodes. Always document and automate your port rules in Terraform/Pulumi — manual security group changes are the #1 source of "works in dev, broken in prod."

---

### Medium (Mid-Level)

**11. Explain the TCP three-way handshake.**

1. **SYN** — client sends segment with SYN flag, random sequence number.
2. **SYN-ACK** — server acknowledges client's SYN and sends its own SYN.
3. **ACK** — client acknowledges server's SYN. Connection established.

Teardown: **FIN → FIN-ACK → ACK** (4-way). TIME_WAIT state holds the connection for 2×MSL (typically 60s) after close.

**DevOps angle:** High TIME_WAIT counts (`ss -s | grep TIME-WAIT`) on a load balancer or app server mean connections aren't being reused. Fix: enable **HTTP keep-alive**, tune `net.ipv4.tcp_tw_reuse = 1`, or use a connection pool. SYN flood attacks exploit the handshake — SYN cookies (`net.ipv4.tcp_syncookies = 1`) mitigate them without dropping legitimate traffic.

**12. What is the difference between HTTP/1.1, HTTP/2, and HTTP/3?**

| Version | Transport | Key improvement |
|---------|-----------|----------------|
| HTTP/1.1 | TCP | Keep-alive, pipelining (HOL blocking) |
| HTTP/2 | TCP + TLS | Multiplexing (multiple streams over one connection), header compression, server push |
| HTTP/3 | QUIC (UDP) | No TCP HOL blocking, faster handshake, built-in TLS 1.3, connection migration |

**DevOps angle:** nginx, Envoy, and AWS ALB all support HTTP/2. GRPC runs over HTTP/2. HTTP/3 is supported by Cloudflare and is gaining adoption in service meshes. When debugging gRPC performance issues, check if the proxy supports HTTP/2 end-to-end — a proxy that downgrades to HTTP/1.1 breaks streaming RPCs.

**13. What is HTTPS and how does TLS work?**

HTTPS = HTTP over TLS. TLS provides **authentication** (certificate), **encryption** (symmetric after handshake), and **integrity** (MAC).

TLS 1.3 handshake (simplified):
1. Client Hello (supported ciphers, key share)
2. Server Hello + Certificate + Finished
3. Client Finished
4. Application data (1-RTT, or 0-RTT for resumption)

**DevOps angle:** `curl -v https://app.example.com` shows the TLS handshake. Certificate errors (`x509: certificate has expired`) are the #1 cause of TLS-related incidents. cert-manager in Kubernetes auto-renews Let's Encrypt certs. Always monitor cert expiry (`openssl s_client -connect host:443 | openssl x509 -noout -dates`). Misconfigured cipher suites block older clients — use Mozilla's SSL Config Generator.

**14. What is a load balancer? What are the types?**

A load balancer distributes incoming traffic across multiple backends to improve availability and scalability.

| Type | Layer | Example |
|------|-------|---------|
| L4 (Network) | TCP/UDP | AWS NLB, HAProxy TCP mode |
| L7 (Application) | HTTP/S | AWS ALB, nginx, Envoy, Traefik |

**Algorithms:** Round-robin, least connections, IP hash (session affinity), weighted.

**DevOps angle:** ALB (L7) can route by path (`/api/*` → API service, `/` → frontend), by header, or by host — essential for microservices. NLB (L4) preserves client IP and handles millions of req/s with lower latency. In Kubernetes, `Service type=LoadBalancer` provisions a cloud LB. Ingress controllers (nginx-ingress, AWS ALB Ingress) provide L7 routing inside the cluster.

**15. What is BGP and why does it matter for cloud networking?**

BGP (Border Gateway Protocol) is the routing protocol that exchanges routes between autonomous systems (AS) on the internet. It's the "glue of the internet" — decides which path packets take across ISPs.

**DevOps angle:** AWS Direct Connect and VPN attachments to Transit Gateway use BGP to advertise VPC CIDR ranges to your on-prem network. Kubernetes networking (Calico in BGP mode) uses BGP to advertise pod CIDRs to physical routers — enabling direct pod-to-pod routing without overlay networks. A misconfigured BGP AS path or route filter causes route leaks and outages.

**16. What is a VLAN and what problem does it solve?**

A VLAN (Virtual LAN) logically segments a physical network into multiple isolated broadcast domains using IEEE 802.1Q tagging. Devices in different VLANs can't communicate without a router (or L3 switch).

**DevOps angle:** Data center racks use VLANs to isolate management, storage, and application traffic on the same physical switches. In cloud, **VPCs and subnets** replace VLANs. In Kubernetes bare-metal deployments (on-prem), VLAN-aware CNI plugins (Multus + MACVLAN) attach pods directly to VLANs — needed for latency-sensitive workloads or legacy network integration.

**17. Explain DNS record types.**

| Record | Purpose | Example |
|--------|---------|---------|
| A | IPv4 address | `app.example.com → 1.2.3.4` |
| AAAA | IPv6 address | `app.example.com → 2001::1` |
| CNAME | Alias to another name | `www → app.example.com` |
| MX | Mail server | Priority + hostname |
| TXT | Arbitrary text (SPF, DKIM, domain verification) | `v=spf1 include:...` |
| NS | Authoritative nameservers for a zone | |
| PTR | Reverse DNS (IP → name) | Used by spam filters, SSH logging |
| SRV | Service discovery (host + port + priority) | Used by etcd, gRPC, Kubernetes |

**DevOps angle:** CNAME cannot point to a bare domain (apex/root) — use ALIAS/ANAME records (Route 53 Alias) instead. A misconfigured CNAME chain causes resolution failures. TXT records are needed for Let's Encrypt DNS-01 challenges and AWS SES domain verification.

**18. What is the difference between `curl` and `wget`?**

| Tool | Primary use | Output | Key strength |
|------|------------|--------|-------------|
| `curl` | Transfer data, API testing | stdout | Full protocol control, headers, auth, methods |
| `wget` | Download files | file | Recursive download, resume (`-c`), offline mirroring |

```bash
curl -sv -o /dev/null https://app.example.com    # full headers, discard body
curl -X POST -H "Content-Type: application/json" -d '{"k":"v"}' https://api/endpoint
wget -q -O - https://checkip.amazonaws.com       # get public IP silently
```

**DevOps angle:** Use `curl` for API calls in scripts, health checks, and webhook testing. `curl -w "%{http_code} %{time_total}s\n" -o /dev/null -s URL` gives status code + latency — great for smoke tests in CI pipelines. `wget` is preferred when downloading large binaries with retry support.

**19. How does `traceroute` work? What information does it give you?**

`traceroute` sends packets with increasing TTL (starting at 1). Each router that drops the packet (TTL=0) returns an ICMP Time Exceeded message, revealing its IP and round-trip time.

```bash
traceroute -n api.example.com      # -n skips reverse DNS (faster)
mtr --report -n api.example.com    # continuous traceroute + stats
```

**DevOps angle:** Use `traceroute` / `mtr` when latency spikes or packets drop between two points. In cloud: if traceroute stops at a specific hop (AWS Transit Gateway, a firewall) — that's where packets are being dropped. Asymmetric routes (different path in/out) are normal in cloud and explain why latency looks different from each side. `mtr --report` shows per-hop packet loss — a middle hop showing 100% loss may be normal (ICMP rate-limiting by routers) if the final destination responds.

**20. What is `iptables` and how does it filter traffic?**

`iptables` is the Linux firewall framework operating in the kernel's netfilter hooks. Rules are organized into **tables** (filter, nat, mangle, raw) and **chains** (INPUT, OUTPUT, FORWARD, PREROUTING, POSTROUTING).

```bash
sudo iptables -L -n -v --line-numbers   # list rules
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -j DROP          # default deny
sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
```

**DevOps angle:** Kubernetes kube-proxy uses iptables (or IPVS) to implement Service ClusterIPs — every `kubectl get svc` entry is backed by iptables DNAT rules. `iptables-save | grep <ClusterIP>` shows them. Too many services = too many iptables rules = slow connection setup. IPVS mode (`kube-proxy --proxy-mode=ipvs`) scales better for large clusters (1000+ services).

**21. What is `ss` and how is it different from `netstat`?**

Both show socket statistics, but `ss` reads `/proc/net/tcp` directly — faster, more detail, still maintained. `netstat` is deprecated (part of `net-tools`).

```bash
ss -lntp                          # listening TCP with PIDs
ss -tnp state established         # active connections
ss -s                             # summary
ss -tnp 'dport = :5432'           # connections TO postgres
ss -tnp 'sport = :8080'           # connections FROM 8080
```

**DevOps angle:** On minimal container images (Alpine, distroless), neither tool is installed. Options: exec a debug sidecar, or read `/proc/net/tcp` directly (decode hex port/IP). In Kubernetes: `kubectl exec -it <pod> -- ss -lntp` to inspect what a pod is actually listening on — often different from what `containerPort` says.

**22. Explain how Kubernetes networking works (pod-to-pod, pod-to-service).**

**Pod-to-pod:** Every pod gets a unique IP from the cluster CIDR. The CNI plugin (Calico, Flannel, Cilium, AWS VPC CNI) ensures all pods can reach each other without NAT. Flannel uses VXLAN overlays; Calico uses BGP or VXLAN; AWS VPC CNI assigns real VPC IPs to pods.

**Pod-to-service:** A Service gets a virtual ClusterIP. kube-proxy (iptables/IPVS) programs DNAT rules: traffic to ClusterIP:port is load-balanced to healthy pod endpoints. Endpoint updates happen via the Endpoints/EndpointSlice API.

**DNS:** CoreDNS resolves `<svc>.<ns>.svc.cluster.local → ClusterIP`. Pods use CoreDNS as their resolver (`/etc/resolv.conf` injected by kubelet).

**Gotcha:** A pod that can't reach a service — check: Does the service selector match pod labels? (`kubectl get endpoints <svc>`). Is the target port correct? Is the pod in `Ready` state? Is there a NetworkPolicy blocking it?

**23. What is a VPN? What types are used in DevOps?**

A VPN (Virtual Private Network) creates an encrypted tunnel over a public network, making remote hosts appear on the same private network.

| Type | Use case |
|------|---------|
| Site-to-site VPN | On-prem DC ↔ AWS VPC via IPsec (AWS VPN Gateway) |
| Client VPN | Engineers → VPC resources (AWS Client VPN, WireGuard, OpenVPN) |
| WireGuard | Modern, fast, kernel-native, simple config — replacing OpenVPN |

**DevOps angle:** Bastion hosts are being replaced by VPNs + SSM Session Manager. WireGuard's minimal attack surface (`~4,000 lines of code` vs OpenVPN's `~600,000`) makes it the modern default for internal access. AWS Direct Connect + BGP gives dedicated, non-internet connectivity — preferred for latency-sensitive or compliance workloads.

**24. What is a CDN and how does it reduce latency?**

A CDN (Content Delivery Network) caches content at edge PoPs (Points of Presence) geographically close to users. Requests are served from the nearest edge, reducing round-trip time and origin load.

**How it works:** DNS resolves the CDN domain to the nearest edge IP → edge checks cache → cache hit: serve immediately; cache miss: fetch from origin, cache, serve.

**DevOps angle:** Cloudflare, AWS CloudFront, Fastly. Cache headers (`Cache-Control`, `ETag`, `Last-Modified`) control what gets cached and for how long. A deploy that doesn't invalidate CloudFront cache serves stale JS/CSS for the TTL duration. Use versioned asset filenames (`app.abc123.js`) to bust caches automatically. Use CDN for static assets, not API responses (unless you're sure they're cacheable).

**25. Explain the difference between symmetric and asymmetric encryption.**

| Type | Keys | Speed | Use |
|------|------|-------|-----|
| Symmetric | Same key to encrypt/decrypt | Fast | Bulk data encryption (AES-256-GCM) |
| Asymmetric | Public key encrypts, private key decrypts | Slow | Key exchange, signatures, auth (RSA, ECDSA, Ed25519) |

**TLS combines both:** Asymmetric crypto during the handshake (to securely exchange a session key), then symmetric (AES) for the actual data — best of both worlds.

**DevOps angle:** SSH uses Ed25519 (asymmetric) for auth; the session data is AES-encrypted symmetrically. GPG signing of container images (cosign/Sigstore) uses asymmetric keys. AWS KMS stores asymmetric keys for envelope encryption: KMS key encrypts a data key, data key encrypts the data — only KMS can decrypt the data key.

**26. What is a reverse proxy? How is it different from a forward proxy?**

| Type | Who configures it | What it hides | Example |
|------|------------------|--------------|---------|
| Forward proxy | Client | Client IP from internet | Squid, company web filter |
| Reverse proxy | Server operator | Server IPs from clients | nginx, HAProxy, Envoy, AWS ALB |

**DevOps angle:** nginx as a reverse proxy in front of a Go/Python app: terminates TLS, handles compression, rate-limits, adds security headers, load-balances across app instances. Kubernetes Ingress controllers are reverse proxies. `X-Forwarded-For` header carries the original client IP — your app must trust it only from known proxy IPs, or it's spoofable.

**27. What is CIDR? How do you calculate host ranges?**

CIDR (Classless Inter-Domain Routing) notation: `IP/prefix-length`. The prefix length defines how many bits are the network portion.

```
10.0.1.0/24:
  Network:    10.0.1.0
  Broadcast:  10.0.1.255
  Usable:     10.0.1.1 – 10.0.1.254  (254 hosts)

10.0.0.0/16:
  Usable hosts: 2^(32-16) - 2 = 65,534
```

**Formula:** Usable hosts = `2^(32 - prefix) - 2` (subtract network and broadcast).

**DevOps angle:** AWS reserves 5 IPs per subnet (network, VPC router, DNS, future, broadcast) — a `/24` gives 251 usable. Kubernetes clusters need enough pod CIDR space — plan `--cluster-cidr=10.244.0.0/16` for up to 256 nodes × 256 pods. Overlapping CIDRs between VPCs, on-prem, and pod networks are a classic VPC peering issue.

**28. What is SSH tunneling / port forwarding?**

SSH can forward ports through an encrypted tunnel, bypassing firewalls or accessing services on remote networks.

```bash
# Local forward: access remote DB locally
ssh -L 5432:db-host:5432 bastion-host
# Now: psql -h localhost -p 5432

# Remote forward: expose local service to remote host
ssh -R 8080:localhost:3000 remote-server

# Dynamic forward (SOCKS proxy): route all traffic
ssh -D 1080 bastion-host
# Then: curl --socks5 localhost:1080 http://internal-service

# Kubernetes: kubectl port-forward (same concept, no SSH needed)
kubectl port-forward svc/postgres 5432:5432
```

**DevOps angle:** SSH tunneling is the safe way to access production databases without opening public ports. Modern alternative: AWS SSM Session Manager port forwarding (`aws ssm start-session --target i-xxx --document-name AWS-StartPortForwardingSession`) — no open port 22 at all.

**29. What is the purpose of `/etc/hosts`?**

`/etc/hosts` is a static lookup table: hostname → IP, checked before DNS (by default via `/etc/nsswitch.conf`).

```bash
cat /etc/hosts
# 127.0.0.1   localhost
# 10.0.0.50   db.internal db
# 192.168.1.5 staging-api.local
```

**DevOps angle:** In Kubernetes, each pod's `/etc/hosts` is injected by kubelet with the pod's own IP and hostname, plus any `hostAliases` from the pod spec. Useful for: overriding DNS in tests, adding entries for hosts that aren't in DNS, canary testing by pointing a name at a new IP on one machine. Warning: it's a local-only override — doesn't propagate to other pods/hosts.

**30. What is `nmap` and what do you use it for?**

`nmap` is a network scanner for host discovery, port scanning, service/OS detection, and vulnerability scripting.

```bash
nmap -sV -p 22,80,443,8080 10.0.1.0/24    # service version on specific ports
nmap -sn 10.0.0.0/24                       # ping sweep (host discovery, no port scan)
nmap -sT -p- --open host                   # all open TCP ports (full connect)
nmap --script=http-title -p 80 10.0.1.0/24 # grab HTTP titles
```

**DevOps angle:** Use `nmap` to audit what ports are exposed after a security group change. A common interview scenario: *"You deployed a new security group rule — verify only expected ports are open."* → `nmap -sV target`. On AWS, also cross-check with `aws ec2 describe-security-groups` — the firewall is in the VPC, not the host, so local `ss` doesn't show blocked ports.

---

### Hard (Senior / SRE Level)

**31. Explain how a packet travels from a browser to a web server (full stack walkthrough).**

1. **DNS:** Browser checks cache → OS cache → `/etc/hosts` → recursive resolver → authoritative NS → returns A record (IP).
2. **TCP:** Browser opens socket, 3-way handshake with server IP:443.
3. **TLS:** TLS 1.3 handshake — server cert validated, session key derived.
4. **HTTP/2:** Browser sends request over encrypted stream.
5. **Network path:** Packet leaves NIC → through host iptables → OS routing table → default gateway → ISP → BGP routing across internet → CDN edge or origin LB → backend server.
6. **Server:** Accept → process → response → TCP ACK → browser renders.

**DevOps angle:** This end-to-end view is the mental model for debugging. Narrow down: DNS? TCP reachability? TLS cert? App-level 5xx? Tools: `dig`, `curl -v`, `traceroute`, `tcpdump`. In Kubernetes: add pod → Ingress → Service → Endpoint → container networking to the path.

**32. How does Kubernetes Service networking work internally? Explain ClusterIP and kube-proxy.**

A ClusterIP Service gets a virtual IP from `--service-cluster-ip-range`. No process listens on this IP — it only exists in iptables/IPVS rules programmed by kube-proxy on every node.

**iptables mode:** kube-proxy writes `DNAT` rules: packets to `ClusterIP:port` are redirected to a random healthy pod endpoint. Rules are re-evaluated per-connection. Problem: O(n) rule chain traversal as services scale.

**IPVS mode:** Uses kernel's IPVS (LVS) hash tables — O(1) lookup. Supports more algorithms (rr, lc, sh, dh). Required for clusters with 1000+ services.

**Cilium (eBPF mode):** Replaces kube-proxy entirely — eBPF maps in kernel do the load balancing without iptables. Latency-optimal, observability built-in.

**Debugging:**
```bash
iptables -t nat -L KUBE-SERVICES -n          # ClusterIP DNAT rules
ipvsadm -Ln                                  # IPVS virtual servers
kubectl get endpoints <svc>                  # pod IPs behind the service
```

**33. Explain BGP route propagation, AS paths, and how route leaks happen.**

BGP routers exchange **Network Layer Reachability Information (NLRI)** — prefix + attributes. The **AS_PATH** attribute lists autonomous systems the route traversed — used for loop prevention and path selection.

**Selection order (simplified):** Highest LOCAL_PREF → shortest AS_PATH → lowest MED → eBGP > iBGP → lowest router ID.

**Route leak:** An AS accidentally re-advertises routes it received from one peer to another — e.g., a customer AS re-advertises a provider's full table to another provider, attracting all internet traffic through their network. Famous examples: Pakistan Telecom hijacking YouTube (2008), Cloudflare Verizon incident (2019).

**DevOps angle:** AWS Transit Gateway BGP: each VPN/Direct Connect attachment has a BGP session. A misconfigured `advertise_prefixes` in a VPN customer gateway can leak VPC CIDRs or even accept unexpected routes, causing traffic to bypass firewalls. Always use BGP communities and route filters.

**34. How does VXLAN work and why does Kubernetes use it?**

VXLAN (Virtual Extensible LAN) encapsulates L2 Ethernet frames inside UDP packets (port 4789). It creates a virtual L2 overlay over an L3 network.

```
Original Ethernet frame
→ VXLAN header (24-byte, includes 24-bit VNI)
→ UDP header (src/dst port 4789)
→ IP header (VTEP-to-VTEP)
→ Ethernet (underlay)
```

VTEPs (VXLAN Tunnel Endpoints) are usually the host NICs or virtual switches. Each VXLAN Network Identifier (VNI) defines a L2 segment — supports 16 million segments vs VLAN's 4096.

**Kubernetes (Flannel/Calico VXLAN):** Each node is a VTEP. Pod traffic to another node is encapsulated in VXLAN, sent over the node network. Encapsulation overhead: ~50 bytes per packet, ~10% throughput reduction. Calico in native routing mode (BGP) avoids this — no encapsulation, but requires L2 adjacency or a BGP-capable underlay.

**35. What is eBPF and how is it changing Kubernetes networking?**

eBPF (extended Berkeley Packet Filter) allows running sandboxed programs in the kernel without modifying kernel source or loading kernel modules. Programs are JIT-compiled and verified for safety.

**What eBPF can do in networking:**
- Attach to XDP (eXpress Data Path) hooks — process packets before they hit the networking stack (line-rate DDoS mitigation)
- Implement socket-level load balancing (Cilium's kube-proxy replacement)
- Track all network flows with zero overhead vs iptables
- Enforce NetworkPolicy at the kernel level without iptables rules

**Cilium with eBPF:**
- No iptables — all service proxy and policy enforcement in BPF maps
- `cilium monitor` — real-time packet-level visibility
- Hubble — eBPF-based observability layer, Prometheus metrics + flow logs
- 90%+ latency reduction vs iptables mode at scale

**Interview follow-up:** *"Why is iptables slow at scale?"* → O(n) linear rule traversal for each new connection. 10,000 services = 250,000+ iptables rules. eBPF hash maps = O(1) regardless of rule count.

**36. Explain TCP congestion control mechanisms.**

TCP congestion control prevents a sender from overwhelming the network. Linux default: **CUBIC** (optimized for high-bandwidth, high-latency links). Google's **BBR** (Bottleneck Bandwidth and Round-trip propagation time) is widely used on cloud servers.

Phases:
1. **Slow start:** Exponentially increase `cwnd` (congestion window) from 1 MSS until threshold or loss.
2. **Congestion Avoidance:** Linear increase per RTT.
3. **Fast Retransmit:** 3 duplicate ACKs → retransmit without waiting for timeout.
4. **Fast Recovery (CUBIC/BBR):** Don't drop to 1 MSS — reduce window by factor, continue.

```bash
sysctl net.ipv4.tcp_congestion_control     # current algorithm
sysctl net.ipv4.tcp_available_congestion_control
sysctl -w net.ipv4.tcp_congestion_control=bbr
```

**DevOps angle:** BBR significantly improves throughput on lossy or high-latency links (satellite, cross-region). Google enabled BBR on all their servers and measured 4% median throughput increase globally. AWS instances default to CUBIC — switching to BBR can help cross-region replication and streaming workloads.

**37. How does DNS at scale work? Explain TTL, negative caching, and split-horizon DNS.**

**TTL (Time To Live):** How long resolvers cache a DNS answer. Low TTL (30–60s) enables fast failover but increases resolver load and latency. High TTL (300–3600s) reduces load but slows down IP changes during incidents.

**Negative caching (RFC 2308):** NXDOMAIN answers are cached for the SOA record's minimum TTL. A deleted record that your app tries to resolve gets a cached NXDOMAIN — app sees "DNS failure" even after the record is restored, until the cache expires.

**Split-horizon DNS:** Different DNS answers for the same name depending on the querier's location/network.
- Internal resolvers see `db.internal → 10.0.1.5` (private IP).
- External resolvers see `db.example.com → ` (no answer — not exposed).
- Used heavily in AWS: Route 53 private hosted zones resolve differently inside VPCs vs public internet.

**Debugging:**
```bash
dig +nocmd +noall +answer +ttl example.com   # show TTL remaining
dig @8.8.8.8 vs @169.254.169.253             # public vs AWS internal resolver
```

**38. What is a network namespace and how does Docker/Kubernetes use it?**

A Linux network namespace gives a process its own isolated network stack: interfaces, routes, iptables rules, sockets, and `/proc/net/*`. Processes in different namespaces are invisible to each other at the network level.

```bash
ip netns list                         # list network namespaces
ip netns exec <ns> ip a               # run command in a namespace
ip netns exec <ns> ss -lntp           # inspect sockets in that ns
```

**Docker:** Each container gets its own netns. `docker run` creates a veth pair: one end in the container netns (eth0), one end in the host netns (attached to docker0 bridge). Traffic flows: container eth0 → veth → docker0 bridge → host routing → NAT → internet.

**Kubernetes:** Each pod shares one netns among all its containers (that's why containers in a pod communicate via `localhost`). The CNI plugin sets up veth pairs from the pod netns to the node. `crictl inspect <container-id>` shows the netns path.

**Debugging:** `ls -la /proc/<pid>/ns/net` — if two containers share the same netns symlink target, they share a network stack.

**39. Explain how AWS VPC networking works (subnets, route tables, security groups, NACLs).**

**VPC:** An isolated virtual network with a defined CIDR block (e.g., `10.0.0.0/16`).

**Subnets:** Partitions of the VPC CIDR, tied to one AZ. Public = has route `0.0.0.0/0 → IGW`. Private = has route `0.0.0.0/0 → NAT GW` (or no default route).

**Route tables:** Each subnet has one. Routes: `local` (VPC CIDR, always present), IGW, NAT GW, Transit GW, VPC peering. The most specific route wins.

**Security groups:** Stateful L4 firewall on ENIs. Inbound + outbound rules. Return traffic is automatically allowed. Applied at the instance/ENI level.

**NACLs (Network ACLs):** Stateless L4 firewall at the subnet boundary. Rules processed in order (lowest rule # first). BOTH inbound and outbound rules must allow traffic (stateless = return traffic needs explicit allow). Used for broad subnet-level controls (e.g., block a CIDR range).

**Debugging order:** SG → NACL → route table → IGW/NAT → OS firewall (iptables). A common mistake: SG allows traffic but NACL blocks return packets (stateless — easy to forget).

**40. How would you diagnose and fix a network performance problem in production?**

**Systematic approach:**

```bash
# 1. Is it DNS?
time dig app.example.com          # should be <10ms internally
dig +short @169.254.169.253 app   # AWS VPC resolver

# 2. Is it latency (RTT)?
ping -c 20 target                 # baseline RTT, packet loss
mtr --report -n target            # per-hop latency + loss

# 3. Is it bandwidth?
iperf3 -c target -t 10            # throughput between two nodes
ethtool eth0 | grep Speed         # interface negotiated speed

# 4. Is it TCP?
ss -s                             # connection state summary
ss -tnp | awk '{print $1}' | sort | uniq -c  # states distribution
sysctl net.ipv4.tcp_retrans_collapse          # retransmit rate

# 5. Is it the application?
curl -w "@curl-format.txt" -s -o /dev/null https://app  # timing breakdown
# curl-format: time_namelookup, time_connect, time_appconnect, time_starttransfer, time_total

# 6. Packet-level capture
sudo tcpdump -i eth0 -nn host target -w capture.pcap
# Analyze in Wireshark: look for retransmits, out-of-order, zero-window
```

**Common root causes and fixes:**

| Symptom | Likely cause | Fix |
|---------|-------------|-----|
| High DNS latency | Resolver overloaded, misconfigured | Use VPC resolver, cache at app level |
| Packet loss between nodes | MTU mismatch (jumbo frames + VXLAN) | `ip link show` → set MTU; check encapsulation overhead |
| High TIME_WAIT | Short-lived connections not reused | Enable keep-alive, connection pooling |
| Throughput low cross-AZ | Not using placement groups for HPC | Use cluster placement groups, enhanced networking |
| Intermittent drops | NIC queue overflow | `ethtool -S eth0 | grep drop`; tune RX/TX ring buffers |

**41. What is an anycast IP and how does it work?**

Anycast assigns the same IP address to multiple servers in different locations. BGP advertises the same prefix from multiple ASes — routers send traffic to the topologically nearest instance.

**How it works:** Each PoP announces `203.0.113.0/24` via BGP. A user in Tokyo hits the Tokyo PoP; a user in London hits the London PoP — same destination IP, different physical server.

**DevOps angle:** Cloudflare's entire network (1.1.1.1 DNS, DDoS mitigation) runs on anycast. AWS Global Accelerator uses anycast to route users to the nearest AWS edge, then routes over the AWS backbone instead of the public internet — reducing latency and jitter for latency-sensitive applications. Key: anycast gives geographic load balancing at the routing layer without DNS.

**42. How does packet fragmentation work and why does it cause problems?**

When a packet exceeds the **MTU (Maximum Transmission Unit)** of a link, it's fragmented: split into smaller packets, each with a fragment offset. Reassembled at the destination (not at routers, in IP).

**IPv4:** Routers can fragment. `DF` (Don't Fragment) bit prevents fragmentation — if set and packet exceeds MTU, router drops and sends ICMP Type 3 Code 4 (Fragmentation Needed). Path MTU Discovery uses this to find the smallest MTU along the path.

**IPv6:** Routers cannot fragment — only the source can. PMTUD is mandatory.

**DevOps angle:** VXLAN adds ~50 bytes overhead. If the underlay MTU is 1500 and overlay is also 1500, VXLAN packets exceed MTU. Fix: set pod/container MTU to 1450 (1500 − 50 VXLAN header). Kubernetes CNI plugins (Flannel, Calico) must account for this. PMTUD black holes occur when ICMP is blocked by firewalls — packets never arrive, connection hangs silently. Fix: `iptables -A FORWARD -p tcp --tcp-flags SYN,RST SYN -j TCPMSS --clamp-mss-to-pmtu` (TCP MSS clamping).

**43. What is OSPF and how does it compare to BGP for internal routing?**

**OSPF (Open Shortest Path First):** Link-state IGP. Each router floods its link states to all routers in the area. Every router builds a complete topology map and runs Dijkstra's algorithm to compute shortest paths. Fast convergence (seconds), suitable for large enterprise networks.

| Aspect | OSPF | BGP |
|--------|------|-----|
| Type | IGP (interior) | EGP (exterior, also used internally as iBGP) |
| Algorithm | Dijkstra (link-state) | Path vector |
| Convergence | Fast (seconds) | Slower (minutes possible) |
| Scale | Up to ~500 routers per area | Entire internet |
| Policy control | Limited | Rich (communities, AS path, MED) |
| Use case | Campus/data center | Internet, multi-AS, cloud peering |

**DevOps angle:** On-prem data centers run OSPF/IS-IS internally. AWS uses its own proprietary IGP internally. When you set up Direct Connect, the edge is BGP — your on-prem router speaks BGP to AWS. Calico in BGP mode acts like a simple BGP router, advertising pod CIDRs — simpler for data center integration than OSPF because most ToR switches already support BGP.

**44. Explain TIME_WAIT in TCP and how to handle it at scale.**

After a TCP connection closes, the side that sends the last FIN enters **TIME_WAIT** for **2×MSL** (Maximum Segment Lifetime, typically 60 seconds on Linux). Purpose: ensure the remote side received the final ACK, and prevent stale packets from a previous connection being misinterpreted by a new connection with the same 4-tuple.

**At scale:** A high-throughput server or load balancer can accumulate hundreds of thousands of TIME_WAIT connections, exhausting ephemeral ports (`net.ipv4.ip_local_port_range`).

**Mitigations:**
```bash
# Kernel tunables:
net.ipv4.tcp_tw_reuse = 1         # reuse TIME_WAIT sockets for new outbound connections
net.ipv4.ip_local_port_range = 1024 65535   # maximize ephemeral port range
net.ipv4.tcp_fin_timeout = 30     # reduce FIN_WAIT_2 timeout

# Application-level:
# Use HTTP keep-alive — reuse connections instead of opening new ones
# Use connection pooling (pgBouncer for Postgres, etc.)
# Load balancer: enable connection draining, use persistent connections upstream
```

**Note:** `tcp_tw_reuse` only helps outbound (client-side). `tcp_tw_recycle` was removed in Linux 4.12 — never use it. The real fix at scale is **connection reuse**.

**45. How does Envoy proxy work? Why is it used in service meshes?**

Envoy is a high-performance L4/L7 proxy written in C++, designed for cloud-native environments. It is the data plane of Istio, AWS App Mesh, and many other service meshes.

**Architecture:**
- **Listeners:** Bind to ports, accept connections.
- **Filters:** Process traffic (HTTP connection manager, TCP proxy, gRPC transcoding, rate limiting, compression).
- **Clusters:** Upstream endpoints (with load balancing, health checking, circuit breaking).
- **Routes:** Match traffic and forward to clusters.

**Key features for service meshes:**
- **Dynamic configuration via xDS API (ADS/CDS/EDS/LDS/RDS):** Istio's Istiod pushes config changes to all Envoy sidecars in real time — no restarts.
- **Observability:** Emits Prometheus metrics, distributed traces (Jaeger/Zipkin via B3 headers), access logs.
- **Resilience:** Circuit breaker, outlier detection (auto-eject unhealthy hosts), retries, timeouts — configured declaratively.
- **mTLS:** Built-in TLS termination and origination.

**Interview follow-up:** *"What is the xDS API?"* → Discovery Service API — Envoy subscribes to Listener/Cluster/Endpoint/Route Discovery Services. Istio's control plane (Istiod) implements xDS and pushes changes to Envoy sidecars dynamically, without config file changes or process restarts.

**46. What is ECMP (Equal-Cost Multi-Path) routing?**

ECMP distributes traffic across multiple equal-cost next-hops (routes with the same metric to a destination). The router hashes packet fields (src IP, dst IP, src/dst port, protocol) to select a consistent path per flow.

```bash
ip route show                  # multiple 'nexthop' entries = ECMP
```

**DevOps angle:** AWS uses ECMP within its backbone. VPC Transit Gateway ECMP: if you have multiple VPN tunnels or Direct Connect circuits to the same TGW, ECMP spreads traffic across them — providing both bandwidth aggregation AND redundancy. Kubernetes with Cilium uses ECMP for external load balancing (no cloud LB needed for bare-metal). **Stateful ECMP problem:** NAT/firewalls with stateful tracking can break if a flow switches paths mid-connection. Solution: consistent hashing (same flow always hits same path).

**47. How do you secure a Kubernetes cluster's network?**

**Defense-in-depth approach:**

**1. Network Policies (L3/L4 isolation):**
```yaml
# Default deny all, then allow explicitly
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata: {name: default-deny, namespace: prod}
spec:
  podSelector: {}
  policyTypes: [Ingress, Egress]
```

**2. CNI enforcement:** NetworkPolicy requires a CNI that enforces it (Calico, Cilium, Weave). Flannel does NOT enforce NetworkPolicy alone.

**3. Encrypt pod-to-pod traffic:** Cilium transparent encryption (WireGuard or IPsec), Istio mTLS.

**4. API server access:** Private cluster (no public API endpoint), IP allowlisting, RBAC, audit logging.

**5. Egress control:** Dedicated egress gateway (Istio), `EgressNetworkPolicy` (OpenShift), or DNS-based egress filtering (Cilium DNS policy).

**6. Runtime security:** Falco for syscall-level anomaly detection. Seccomp/AppArmor profiles per pod. `allowPrivilegeEscalation: false`, `readOnlyRootFilesystem: true` in `securityContext`.

**Interview probe:** *"A pod is exfiltrating data to an external IP — how do you detect and stop it?"* → Cilium Hubble shows all flows. NetworkPolicy `Egress` deny rule + allowlist for known services. Falco rule triggers on unexpected network connections. Add `EgressNetworkPolicy` scoped to the namespace.

**48. What is DNS-based service discovery and how does it work in microservices?**

Service discovery via DNS: services register their name and IP with a DNS server; clients resolve the name to get current IPs. In dynamic environments, IPs change frequently — DNS TTL and health-check-based record updates make DNS the discovery mechanism.

**Kubernetes:** CoreDNS is the cluster DNS. Services automatically get a DNS entry: `<svc>.<ns>.svc.cluster.local`. Headless services (`clusterIP: None`) return all pod IPs as A records — enabling client-side load balancing (gRPC, Cassandra). StatefulSet pods get individual DNS entries: `<pod-name>.<svc>.<ns>.svc.cluster.local` — essential for stateful apps (Kafka, Cassandra, etcd) that need to address specific replicas.

**External service discovery:** Consul (DNS + health checks), AWS Cloud Map (integrates with Route 53 and App Mesh), etcd (used by Kubernetes itself for its control plane data).

**Gotcha:** DNS caching in the JVM (default: cache forever), Go standard library (respects TTL), and nginx (caches at startup by default) can cause stale IP issues after pod restarts. Fix in nginx: use a resolver with `valid=` timeout and dynamic upstream variables.

**49. How does a CDN handle cache invalidation and what are the risks?**

**Cache invalidation methods:**
- **TTL expiry:** Cached object expires after `Cache-Control: max-age=X`. Simple but imprecise.
- **Purge by URL:** `curl -X PURGE https://cdn.example.com/path` — instant but must enumerate all edge PoPs.
- **Surrogate keys / Cache tags:** Tag responses with logical keys (e.g., `product-123`); purge all responses tagged with that key in one API call. Supported by Fastly, Cloudflare.
- **Versioned URLs:** `app.abc123.js` — change the hash at deploy, old URL remains cached, new URL is a cache miss. No invalidation needed.

**Risks:**
- **Stale content served during invalidation propagation delay** (seconds to minutes across PoPs).
- **Cache stampede (thundering herd):** TTL expires simultaneously for a popular object → all requests hit origin at once. Mitigation: staggered TTLs, request coalescing (edge holds first request, queues rest until response arrives).
- **Purging too aggressively** flushes cache unnecessarily → origin overload spike.
- **Sensitive data cached:** `Vary: Cookie` / `Cache-Control: private` must be set correctly or private responses leak to other users.

**DevOps angle:** A deploy that serves stale HTML pointing to the new `app.hash.js` but the CSS still has the old hash creates a mixed-content/visual regression. Use versioned assets + immutable caching for static assets, short TTLs for HTML.

**50. How does mTLS work and how do service meshes implement it?**

**mTLS (Mutual TLS):** Both client AND server present certificates for authentication — bidirectional identity verification, unlike regular TLS where only the server authenticates.

```
Client → [Client Cert + Server Cert Verification] → Server
Server → [Server Cert + Client Cert Verification] → Client
```

**Service mesh implementation (Istio/Linkerd):**
1. A **sidecar proxy** (Envoy/linkerd-proxy) is injected into every pod.
2. The control plane issues short-lived X.509 certificates to each workload via SPIFFE/SPIRE.
3. The sidecar intercepts all pod traffic using iptables rules (init container adds `REDIRECT` rules).
4. Sidecar-to-sidecar communication is automatically mTLS — the app itself is unaware.
5. Istio's `PeerAuthentication` policy enforces `STRICT` mTLS (plaintext rejected) per namespace/workload.

**Benefits:** Zero-trust networking inside the cluster — even if a pod is compromised, it can only reach services its certificate is authorized for (combined with `AuthorizationPolicy`).

**Debugging:**
```bash
istioctl proxy-config listener <pod>    # verify mTLS config
istioctl authn tls-check <pod> <svc>   # check mTLS handshake status
kubectl exec -it <pod> -c istio-proxy -- curl -v https://other-svc  # test within mesh
```

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
