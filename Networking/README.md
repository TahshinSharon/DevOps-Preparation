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
  - [Default Gateway](#default-gateway)
  - [Static vs Dynamic Routing](#static-vs-dynamic-routing)
  - [Routing Protocols](#routing-protocols)
  - [IGP vs EGP](#igp-vs-egp)
  - [Linux Routing](#linux-routing)
- [Network Configuration](#network-configuration)
  - [One Shot Revision](#one-shot-revision-4)
  - [ip](#ip)
  - [ifconfig](#ifconfig)
  - [hostname](#hostname)
  - [/etc/hosts](#etchosts)
  - [/etc/resolv.conf](#etcresolvconf)
  - [NetworkManager (nmcli)](#networkmanager-nmcli)
- [Connectivity & Diagnostics](#connectivity--diagnostics)
  - [One Shot Revision](#one-shot-revision-5)
  - [ping](#ping)
  - [traceroute](#traceroute)
  - [mtr](#mtr)
  - [telnet](#telnet)
  - [nc (netcat)](#nc-netcat)
- [DNS Tools](#dns-tools)
  - [One Shot Revision](#one-shot-revision-6)
  - [DNS Concepts](#dns-concepts)
  - [dig](#dig)
  - [nslookup](#nslookup)
  - [host](#host)
- [Sockets & Ports](#sockets--ports)
  - [One Shot Revision](#one-shot-revision-7)
  - [ss](#ss)
  - [netstat](#netstat)
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
| [Network Basics](#network-basics)           | Core components, network types (LAN/WAN/WLAN), hosts and packets        |
| [OSI Model](#osi-model)                     | 7-layer reference model: Physical → Data Link → … → Application         |
| [TCP/IP Model](#tcpip-model)                | The 4-layer model that the real internet actually runs on               |
| [Network Addressing](#network-addressing)   | IPv4 vs IPv6, public vs private, static vs DHCP, special addresses      |
| [Application Layer](#application-layer)     | Layer-7 protocols apps actually speak: HTTP, DNS, SSH, SMTP, …          |
| [Transport Layer](#transport-layer)         | TCP vs UDP, ports, sockets, the three-way handshake                     |
| [Network Layer](#network-layer)             | IP routing, default gateway, ICMP, MTU & fragmentation                  |
| [Link Layer](#link-layer)                   | Frames, MAC addresses, switches, Ethernet/Wi-Fi                         |
| [DHCP Overview](#dhcp-overview)             | How hosts get IP, gateway, and DNS automatically via the DORA handshake |
| [Ports & Protocols](#ports--protocols)      | TCP vs UDP, well-known ports, ephemeral ports                           |
| [MAC Addresses & ARP](#mac-addresses--arp)  | Layer-2 identity and how IP maps to MAC on a LAN                        |

### Network Basics

Before diving into models and protocols, it helps to know **what's actually on a network** and **how data moves between the pieces**.

#### Core Network Components

The building blocks every network — from a home Wi-Fi to a data center — is made of:

| Component                    | Role                                                                                     |
| ---------------------------- | ---------------------------------------------------------------------------------------- |
| **Host**                     | Any device with an IP address — laptop, server, phone, IoT sensor.                       |
| **NIC** (Network Interface Card) | Hardware that connects a host to the network (wired Ethernet or wireless radio).     |
| **Switch**                   | Forwards frames between devices on the **same LAN** using MAC addresses (Layer 2).       |
| **Router**                   | Forwards packets between **different networks** using IP addresses (Layer 3).            |
| **Access Point (AP)**        | Bridges wireless clients onto a wired LAN — what most "Wi-Fi routers" actually do.       |
| **Modem**                    | Translates the ISP's signal (DSL / cable / fiber) into Ethernet your router can use.     |
| **Firewall**                 | Filters traffic by rule — can be host-based (`iptables`, `ufw`) or a dedicated appliance.|
| **Cabling / Media**          | The physical medium — copper (Cat5e/6), fiber, or air (Wi-Fi, 4G/5G).                    |
| **Protocols**                | The agreed rules for how data is formatted and exchanged (TCP/IP, HTTP, DNS, …).         |

**Rule of thumb:** if it has an IP, it's a **host**; if it moves traffic between hosts, it's **infrastructure** (switch / router / AP / firewall).

#### Understanding Network Types: WAN, LAN, and WLAN

Networks are usually classified by **how far they reach**.

| Type      | Full Name                      | Typical Scope                  | Example                                |
| --------- | ------------------------------ | ------------------------------ | -------------------------------------- |
| **LAN**   | Local Area Network             | One building / floor / home    | Office network, home Ethernet          |
| **WLAN**  | Wireless LAN                   | Same scope as LAN — but wireless | Home/office Wi-Fi (802.11)           |
| **WAN**   | Wide Area Network              | City → country → worldwide     | The Internet itself, an SD-WAN link    |
| **MAN**   | Metropolitan Area Network      | A city                         | A citywide ISP backbone                |
| **PAN**   | Personal Area Network          | A few meters around one user   | Bluetooth phone ↔ headphones           |

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

| #   | Layer            | Responsibility                                  | Examples                       |
| --- | ---------------- | ----------------------------------------------- | ------------------------------ |
| 7   | **Application**  | Protocols users / apps interact with directly   | HTTP, FTP, SMTP, DNS, SSH      |
| 6   | **Presentation** | Data format, encoding, encryption, compression  | TLS, JPEG, ASCII, UTF-8        |
| 5   | **Session**      | Open, manage, and close conversations           | NetBIOS, RPC                   |
| 4   | **Transport**    | End-to-end delivery and reliability             | TCP, UDP                       |
| 3   | **Network**      | Logical addressing & routing between networks   | IP, ICMP                       |
| 2   | **Data Link**    | Frame delivery on the local segment             | Ethernet, ARP, MAC, Wi-Fi      |
| 1   | **Physical**     | Raw bits on the medium                          | Copper, fiber, radio waves     |

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

| #   | Layer                       | OSI Equivalent              | Responsibility                                    | Protocols                                |
| --- | --------------------------- | --------------------------- | ------------------------------------------------- | ---------------------------------------- |
| 4   | **Application**             | Session + Presentation + App | App-level data and APIs                           | HTTP, HTTPS, DNS, SSH, FTP, SMTP         |
| 3   | **Transport**               | Transport                   | Process-to-process delivery using **ports**       | TCP, UDP                                 |
| 2   | **Internet**                | Network                     | Logical addressing & routing across networks      | IP, ICMP, ARP\*                          |
| 1   | **Network Access** (Link)   | Data Link + Physical        | Frames on the local medium                        | Ethernet, Wi-Fi (802.11), PPP            |

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

| Aspect            | IPv4                                | IPv6                                          |
| ----------------- | ----------------------------------- | --------------------------------------------- |
| **Size**          | 32 bits (~4.3 billion addresses)    | 128 bits (~3.4 × 10³⁸ addresses)              |
| **Notation**      | Dotted decimal — `192.168.1.10`     | Colon hex — `2001:db8::1`                     |
| **Header**        | Variable length, has checksum       | Fixed 40-byte header, no checksum             |
| **Configuration** | Manual or DHCP                      | Manual, DHCPv6, or **SLAAC** (autoconfig)     |
| **Broadcast**     | Yes (`255.255.255.255`)             | No — replaced by **multicast**                |
| **NAT needed?**   | Usually (address exhaustion)        | No — every host can have a public address     |

**Example IPv4 packet flow:** `192.168.1.10` → `8.8.8.8` over the public internet (NAT'd at the home router).

**Example IPv6 address parts:** `2001:0db8:0000:0000:0000:0000:0000:0001` shortens to `2001:db8::1` (consecutive zero groups collapse to `::`, exactly once per address).

#### Public vs Private Addresses

Private ranges are reserved by **RFC 1918** for use inside organizations — they are **not routable on the public internet** and need NAT to reach the outside world.

| Range                | CIDR              | Typical Use                                  |
| -------------------- | ----------------- | -------------------------------------------- |
| `10.0.0.0 – 10.255.255.255`        | `10.0.0.0/8`      | Large corporate networks, cloud VPCs         |
| `172.16.0.0 – 172.31.255.255`      | `172.16.0.0/12`   | Mid-size networks, Docker default bridges    |
| `192.168.0.0 – 192.168.255.255`    | `192.168.0.0/16`  | Home and small-office LANs                   |

Everything else is **public** — assigned by IANA/RIRs and globally reachable.

#### Static vs Dynamic Assignment

| Method     | How Address Is Assigned                                       | When to Use                                          |
| ---------- | ------------------------------------------------------------- | ---------------------------------------------------- |
| **Static** | Manually configured on the host (`/etc/network/...`, `nmcli`) | Servers, routers, printers — anything you connect to |
| **DHCP**   | A DHCP server hands out a lease when the host boots           | Laptops, phones, ephemeral VMs                       |
| **SLAAC**  | IPv6 host self-generates an address from a router advertisement | Default on IPv6 LANs                              |

A DHCP lease comes with more than just an IP — it usually also delivers the **subnet mask**, **default gateway**, and **DNS servers**.

#### Special-Purpose Addresses

| Address / Range                | Meaning                                                            |
| ------------------------------ | ------------------------------------------------------------------ |
| `127.0.0.1` / `::1`            | **Loopback** — refers to the host itself                           |
| `0.0.0.0`                      | "Any address" — bind to all interfaces; also a default route       |
| `255.255.255.255`              | IPv4 **limited broadcast** (current network only)                  |
| `169.254.0.0/16`               | **APIPA / link-local** — assigned when DHCP fails                  |
| `fe80::/10`                    | IPv6 link-local — every IPv6 interface always has one              |
| `224.0.0.0/4`                  | IPv4 **multicast** group addresses                                 |
| `ff00::/8`                     | IPv6 multicast                                                     |

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

| Protocol         | Default Port  | Transport | Purpose                                                          |
| ---------------- | ------------- | --------- | ---------------------------------------------------------------- |
| **HTTP**         | 80            | TCP       | The web — request/response for HTML, APIs, static assets         |
| **HTTPS**        | 443           | TCP (+TLS)| HTTP wrapped in TLS for confidentiality and integrity            |
| **DNS**          | 53            | UDP / TCP | Resolve names (`example.com`) to IP addresses                    |
| **SSH**          | 22            | TCP       | Encrypted remote shell and file transfer                         |
| **FTP**          | 21 (ctrl)     | TCP       | Legacy file transfer (cleartext — use SFTP/FTPS instead)         |
| **SFTP**         | 22            | TCP       | File transfer **over SSH** — same port as ssh                    |
| **SMTP**         | 25 / 587      | TCP       | Send/relay email between mail servers                            |
| **IMAP / POP3**  | 143 / 110     | TCP       | Read email from a mail server (IMAP keeps state, POP3 downloads) |
| **NTP**          | 123           | UDP       | Synchronize system clocks across hosts                           |
| **SNMP**         | 161 / 162     | UDP       | Poll devices for monitoring data and receive traps               |
| **DHCP**         | 67 / 68       | UDP       | Hand out IP leases, gateway, and DNS info to hosts at boot       |
| **LDAP**         | 389 / 636     | TCP       | Directory lookups (users, groups) — often behind auth systems    |

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

| Service                | Provided By                                                              |
| ---------------------- | ------------------------------------------------------------------------ |
| **Multiplexing**       | Ports let many app conversations share one IP address                    |
| **Reliability**        | TCP retransmits lost bytes; UDP does not                                 |
| **Ordering**           | TCP delivers bytes in the order they were sent                           |
| **Flow control**       | TCP receiver tells sender how much it can accept (window)                |
| **Congestion control** | TCP backs off when the network is overloaded                             |
| **Error detection**    | Checksum over header + payload (both TCP and UDP)                        |

The Network Layer (IP) only promises **"best effort"** delivery between hosts — anything above that, including knowing *which app* on the host should receive the data, is the Transport Layer's job.

#### TCP vs UDP

| Aspect                | **TCP**                                              | **UDP**                                              |
| --------------------- | ---------------------------------------------------- | ---------------------------------------------------- |
| **Connection**        | Connection-oriented (handshake before data)          | Connectionless (just send)                           |
| **Reliability**       | Guaranteed delivery + ordering + retransmission      | No guarantees — packets may be lost or reordered     |
| **Header size**       | 20+ bytes                                            | 8 bytes                                              |
| **Speed**             | Slower — more bookkeeping                            | Faster — minimal overhead                            |
| **Flow / Congestion** | Yes                                                  | No                                                   |
| **Best for**          | HTTP, SSH, SMTP, databases, file transfer            | DNS queries, NTP, VoIP, video, gaming, DHCP          |

**Rule of thumb:** *"If losing a packet would corrupt the data, use TCP. If losing one is OK because a newer one will come in a moment, use UDP."*

#### Ports & Sockets

- A **port** is a 16-bit number (0–65535) identifying a specific service/process on a host.
- A **socket** is the full endpoint: `IP:port` — e.g. `192.168.1.10:443`.
- A TCP connection is uniquely identified by a **4-tuple**: `src-IP : src-port  ↔  dst-IP : dst-port`.

| Range            | Name              | Typical Use                                        |
| ---------------- | ----------------- | -------------------------------------------------- |
| `0 – 1023`       | **Well-known**    | Standard services (HTTP 80, HTTPS 443, SSH 22)     |
| `1024 – 49151`   | **Registered**    | Apps that registered with IANA (Postgres 5432, …) |
| `49152 – 65535`  | **Ephemeral**     | Temporary ports for client-side connections        |

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

| State           | Meaning                                                            |
| --------------- | ------------------------------------------------------------------ |
| `LISTEN`        | Server is waiting for incoming connections on a port               |
| `SYN-SENT`      | Client sent SYN, waiting for SYN-ACK                               |
| `SYN-RECV`      | Server received SYN, sent SYN-ACK, waiting for final ACK           |
| `ESTABLISHED`   | Connection is open — data can flow                                 |
| `FIN-WAIT-1/2`  | One side has started closing the connection                        |
| `TIME-WAIT`     | Local side closed, holding the socket briefly to absorb stragglers |
| `CLOSE-WAIT`    | Remote side closed; local app hasn't called `close()` yet          |

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
- **QUIC / HTTP/3** moves transport responsibilities (reliability, ordering, congestion control) into user space on top of **UDP** — same Layer-4 *role*, different implementation.
- A common interview question: *"What happens when you type `example.com` in a browser?"* — the answer walks through DNS (App), the TCP handshake (Transport), IP routing (Network), and back up.

### Network Layer

The **Network Layer** is Layer 3 in OSI and the **Internet** layer in TCP/IP. Its job is to get a packet from any host on any network to any other host on any other network — across switches, routers, ISPs, and continents — using **logical addresses** (IP) rather than the physical MAC addresses used by the link below.

#### What This Layer Does

| Service                    | Provided By                                                       |
| -------------------------- | ----------------------------------------------------------------- |
| **Logical addressing**     | IPv4 / IPv6 addresses identify hosts independent of hardware      |
| **Routing**                | Pick the next hop toward the destination, hop by hop              |
| **Forwarding**             | Move a packet from an input interface to the right output one     |
| **Fragmentation**          | Split a packet that's larger than the link's MTU (mostly IPv4)    |
| **Error / control signals**| ICMP messages — "host unreachable", "TTL exceeded", echo reply    |

It is **connectionless and best-effort** — no handshake, no guaranteed delivery, no ordering. Reliability (if needed) is added by TCP above.

#### Key Protocols at This Layer

| Protocol     | Purpose                                                                |
| ------------ | ---------------------------------------------------------------------- |
| **IPv4 / IPv6** | The actual packet format and addressing                             |
| **ICMP / ICMPv6** | Diagnostic and error messages — what `ping` and `traceroute` ride on |
| **ARP**\*    | Maps IPv4 → MAC on the local segment (sits between L2 and L3)          |
| **NDP**      | IPv6 equivalent of ARP — neighbor discovery, router advertisements     |
| **IGMP**     | Manage IPv4 multicast group membership                                 |

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

| ICMP Type                  | When You See It                                                  |
| -------------------------- | ---------------------------------------------------------------- |
| **Echo Request / Reply**   | `ping` — "are you alive?"                                        |
| **Destination Unreachable** | No route, port closed (for UDP), or admin filter                |
| **Time Exceeded**          | TTL hit 0 — fuel for `traceroute`                                |
| **Redirect**               | Router telling you "use this other gateway instead" (often filtered) |
| **Fragmentation Needed**   | Packet too big, "Don't Fragment" bit was set                     |

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

| PDU         | Layer       | Header Adds                                          |
| ----------- | ----------- | ---------------------------------------------------- |
| **Frame**   | Data Link   | Source/destination **MAC**, EtherType, FCS           |
| **Packet**  | Network     | Source/destination **IP**, TTL, protocol             |
| **Segment** | Transport   | Source/destination **port**, sequence/ack numbers    |

On the wire it looks like nested envelopes: `Frame[ IP[ TCP[ HTTP-bytes ] ] ]`.

#### Common Link-Layer Technologies

| Technology               | Where You See It                | Notes                                                |
| ------------------------ | ------------------------------- | ---------------------------------------------------- |
| **Ethernet (802.3)**     | Wired LANs, data centers        | MAC + EtherType frame; 1G / 10G / 25G / 100G+        |
| **Wi-Fi (802.11)**       | Wireless LANs                   | Same MAC scheme; uses CSMA/CA and retransmits        |
| **PPP**                  | DSL, dial-up, some WAN links    | Point-to-point, often with built-in authentication   |
| **VLAN (802.1Q)**        | Enterprise switching            | Tags frames so one switch hosts many isolated LANs   |
| **MPLS**                 | ISP backbones                   | Label-switched forwarding — sits between L2 and L3   |

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

| Field                       | Purpose                                                  |
| --------------------------- | -------------------------------------------------------- |
| **IP address**              | The address the host may use, for a limited time         |
| **Subnet mask**             | Defines the local network (e.g. `/24`)                   |
| **Default gateway**         | Router IP for off-LAN traffic                            |
| **DNS servers**             | Where to send name lookups                               |
| **Lease time**              | How long the assignment is valid (hours to days)         |
| **Domain name / NTP / WPAD**| Optional extras delivered as numbered "DHCP options"     |

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

| Topic                                   | Short Description                                                              |
| --------------------------------------- | ------------------------------------------------------------------------------ |
| [Subnets](#subnets)                     | What a subnet is, why we subnet, broadcast domains, key terminology            |
| [Subnet Math](#subnet-math)             | Powers of two, formulas, host counts, bit-borrowing intuition                  |
| [Subnetting Cheats](#subnetting-cheats) | Magic number, block size shortcut, fast mental math                            |
| [CIDR](#cidr)                           | Classless notation, supernetting, route aggregation, reserved blocks           |
| [IPv4](#ipv4)                           | 32-bit addressing, masks, network/broadcast/host math, VLSM, worked examples   |
| [NAT](#nat)                             | SNAT, DNAT, PAT, CGNAT, NAT64, Linux `iptables` / `nftables` examples          |
| [IPv6](#ipv6)                           | 128-bit addressing, address types, `/64` subnets, SLAAC vs DHCPv6, NDP         |

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

| `2^n` | Value | Used for                                |
| ----- | ----- | --------------------------------------- |
| `2^1` | 2     | `/31` block / 2-host point-to-point     |
| `2^2` | 4     | `/30` block / 2 usable hosts            |
| `2^3` | 8     | `/29` block / 6 usable hosts            |
| `2^4` | 16    | `/28` block / 14 usable hosts           |
| `2^5` | 32    | `/27` block / 30 usable hosts           |
| `2^6` | 64    | `/26` block / 62 usable hosts           |
| `2^7` | 128   | `/25` block / 126 usable hosts          |
| `2^8` | 256   | `/24` block (full octet, 254 usable)    |

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

| Prefix | Mask Last Octet | Block | Hosts | Mnemonic                       |
| ------ | --------------- | ----- | ----- | ------------------------------ |
| `/25`  | `128`           | 128   | 126   | "Half a /24"                   |
| `/26`  | `192`           | 64    | 62    | "Quarter a /24"                |
| `/27`  | `224`           | 32    | 30    | "Eighth a /24"                 |
| `/28`  | `240`           | 16    | 14    | "Sixteenth a /24"              |
| `/29`  | `248`           | 8     | 6     | "Storage networks / small links" |
| `/30`  | `252`           | 4     | 2     | "Classic point-to-point link"  |

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

| Class | Old Range                       | Implicit Mask    | Why retired                                       |
| ----- | ------------------------------- | ---------------- | ------------------------------------------------- |
| A     | `1.0.0.0` – `126.255.255.255`   | `/8` (16M hosts) | Wasted huge blocks on small organizations.        |
| B     | `128.0.0.0` – `191.255.255.255` | `/16` (65K hosts)| Same problem — coarse boundaries.                 |
| C     | `192.0.0.0` – `223.255.255.255` | `/24` (254 hosts)| Routing tables exploded as the internet grew.     |

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

| CIDR              | Meaning                                                                  |
| ----------------- | ------------------------------------------------------------------------ |
| `0.0.0.0/0`       | Default route — "everything not matched elsewhere".                      |
| `10.0.0.0/8`      | RFC 1918 private.                                                        |
| `172.16.0.0/12`   | RFC 1918 private (covers `172.16.0.0` – `172.31.255.255`).               |
| `192.168.0.0/16`  | RFC 1918 private.                                                        |
| `127.0.0.0/8`     | Loopback.                                                                |
| `169.254.0.0/16`  | Link-local (APIPA — host couldn't reach DHCP).                           |
| `100.64.0.0/10`   | Carrier-grade NAT (RFC 6598).                                            |
| `224.0.0.0/4`     | Multicast.                                                               |

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

| CIDR  | Subnet Mask         | Network Bits | Host Bits | Usable Hosts |
| ----- | ------------------- | ------------ | --------- | ------------ |
| `/8`  | `255.0.0.0`         | 8            | 24        | 16,777,214   |
| `/16` | `255.255.0.0`       | 16           | 16        | 65,534       |
| `/24` | `255.255.255.0`     | 24           | 8         | 254          |
| `/25` | `255.255.255.128`   | 25           | 7         | 126          |
| `/26` | `255.255.255.192`   | 26           | 6         | 62           |
| `/27` | `255.255.255.224`   | 27           | 5         | 30           |
| `/28` | `255.255.255.240`   | 28           | 4         | 14           |
| `/29` | `255.255.255.248`   | 29           | 3         | 6            |
| `/30` | `255.255.255.252`   | 30           | 2         | 2            |
| `/31` | `255.255.255.254`   | 31           | 1         | 2 (point-to-point, RFC 3021) |
| `/32` | `255.255.255.255`   | 32           | 0         | 1 (single host route)        |

**Formulas:**

- Total addresses in a subnet = `2^(host bits)`
- Usable host addresses = `2^(host bits) − 2` (subtract the network + broadcast addresses)
- Number of subnets when borrowing `n` bits = `2^n`

#### Network, Broadcast, and Host Addresses

Every IPv4 subnet has three special address types:

| Address               | How to Find It                                          | Usable for Hosts? |
| --------------------- | ------------------------------------------------------- | ----------------- |
| **Network address**   | All host bits set to `0` — the first address in the block | No              |
| **Broadcast address** | All host bits set to `1` — the last address in the block | No              |
| **Host addresses**    | Everything in between                                   | Yes               |

**Example:** for `192.168.1.0/24`:

- Network address  → `192.168.1.0`
- Broadcast address → `192.168.1.255`
- Usable host range → `192.168.1.1` – `192.168.1.254` (254 hosts)

#### Worked Example — Splitting `192.168.1.0/24` into Four Subnets

Borrow **2 bits** from the host portion (`/24` → `/26`) to create `2² = 4` subnets, each with `2⁶ − 2 = 62` usable hosts.

| Subnet | CIDR                  | Network        | First Host    | Last Host     | Broadcast      |
| ------ | --------------------- | -------------- | ------------- | ------------- | -------------- |
| 1      | `192.168.1.0/26`      | `192.168.1.0`  | `192.168.1.1` | `192.168.1.62`| `192.168.1.63` |
| 2      | `192.168.1.64/26`     | `192.168.1.64` | `192.168.1.65`| `192.168.1.126`| `192.168.1.127`|
| 3      | `192.168.1.128/26`    | `192.168.1.128`| `192.168.1.129`| `192.168.1.190`| `192.168.1.191`|
| 4      | `192.168.1.192/26`    | `192.168.1.192`| `192.168.1.193`| `192.168.1.254`| `192.168.1.255`|

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

| Department | Hosts Needed | CIDR  | Range                                   |
| ---------- | ------------ | ----- | --------------------------------------- |
| Sales      | 100          | `/25` | `192.168.10.0`   – `192.168.10.127`     |
| Engineering| 50           | `/26` | `192.168.10.128` – `192.168.10.191`     |
| Ops        | 25           | `/27` | `192.168.10.192` – `192.168.10.223`     |
| Mgmt       | 10           | `/28` | `192.168.10.224` – `192.168.10.239`     |
| WAN link   | 2            | `/30` | `192.168.10.240` – `192.168.10.243`     |

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
- Common interview question: *"How many usable hosts in a `/26`?"* → `2^6 − 2 = 62`.

### NAT

**NAT** (Network Address Translation, RFC 3022) rewrites IP addresses (and often ports) as packets cross a boundary — typically between a private RFC 1918 network and the public internet. NAT is what lets thousands of home or office devices share a single public IPv4 address.

**Why NAT exists:** IPv4 has only ~4.3 billion addresses. NAT lets one public IP front many private hosts, postponing IPv4 exhaustion. IPv6 was designed to eliminate this need — see the next section.

**Types of NAT:**

| Type                                    | Direction               | What it rewrites                | Use case                                                  |
| --------------------------------------- | ----------------------- | ------------------------------- | --------------------------------------------------------- |
| **SNAT** (Source NAT)                   | Outbound                | Source IP (sometimes port)      | Hide internal IPs behind a public one.                    |
| **DNAT** (Destination NAT)              | Inbound                 | Destination IP (sometimes port) | Port forwarding — expose an internal server.              |
| **PAT** / **NAPT**                      | Outbound, many-to-one   | Source IP **and** port          | Home routers — many private hosts share one public IP.    |
| **Static NAT**                          | Both                    | 1-to-1 IP mapping, no port change | Permanently map a public IP to one internal server.     |
| **Hairpin NAT**                         | Internal → public → internal | Both source and destination | Reach your own server via its public IP from inside.      |
| **NAT64 / DNS64**                       | IPv6 ↔ IPv4             | Address family                  | Let IPv6-only clients reach IPv4-only services.           |
| **CGNAT** (Carrier-grade NAT)           | ISP-level               | Multiple layers of NAT          | ISPs share one public IP across many subscribers (`100.64.0.0/10`). |

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
- Provides *incidental* security (inbound unsolicited traffic has no mapping), but it's **not** a firewall — don't treat NAT as a security boundary.

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

| Type                    | Prefix             | Meaning                                                                       |
| ----------------------- | ------------------ | ----------------------------------------------------------------------------- |
| **Global Unicast (GUA)**| `2000::/3`         | Routable on the public internet (analog of IPv4 public addresses).            |
| **Unique Local (ULA)**  | `fc00::/7` (typically `fd00::/8`) | Private, non-routable on the internet (analog of RFC 1918).    |
| **Link-Local (LLA)**    | `fe80::/10`        | Auto-assigned per interface, valid only on that link. Every IPv6 interface has one. |
| **Multicast**           | `ff00::/8`         | Replaces broadcast — `ff02::1` = all nodes, `ff02::2` = all routers on the link. |
| **Loopback**            | `::1/128`          | Equivalent of `127.0.0.1`.                                                    |
| **Unspecified**         | `::/128`           | Equivalent of `0.0.0.0` — "no address yet".                                   |
| **IPv4-mapped**         | `::ffff:0:0/96`    | Used in dual-stack sockets — `::ffff:192.0.2.1` represents an IPv4 inside IPv6. |

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

| Aspect              | IPv4                       | IPv6                                            |
| ------------------- | -------------------------- | ----------------------------------------------- |
| Address size        | 32 bits                    | 128 bits                                        |
| Notation            | Dotted-decimal             | Colon-hex with `::` compression                 |
| Address resolution  | ARP                        | NDP (Neighbor Discovery Protocol) over ICMPv6   |
| Broadcast           | Yes (`x.x.x.255`)          | None — replaced by multicast                    |
| Autoconfig          | DHCP only                  | SLAAC, DHCPv6, or both                          |
| NAT                 | Common (NAT44, PAT)        | Discouraged — designed for end-to-end           |
| Header              | Variable, with options     | Fixed 40-byte, extension headers                |
| Fragmentation       | Routers + hosts            | Hosts only (PMTUD required)                     |

---

## Routing

**Routing** is how packets find their way from source to destination across multiple networks. Each router compares the destination IP of every incoming packet against its **routing table** and forwards the packet out the best-matching interface — hop by hop, until it reaches the target network.

### One Shot Revision

| Topic                                                   | Short Description                                                        |
| ------------------------------------------------------- | ------------------------------------------------------------------------ |
| [Routing Basics](#routing-basics)                       | How routers move packets between networks, hop-by-hop forwarding         |
| [Routing Table](#routing-table)                         | Entries, longest-prefix match, metrics, administrative distance          |
| [Default Gateway](#default-gateway)                     | The `0.0.0.0/0` route used when nothing more specific matches            |
| [Static vs Dynamic Routing](#static-vs-dynamic-routing) | When to hand-code routes vs let a protocol discover them                 |
| [Routing Protocols](#routing-protocols)                 | RIP, OSPF, EIGRP, BGP — what each is for                                 |
| [IGP vs EGP](#igp-vs-egp)                               | Interior vs exterior gateway protocols and where they run                |
| [Linux Routing](#linux-routing)                         | `ip route`, policy routing, multiple tables                              |

### Routing Basics

A **router** is a Layer-3 device that forwards packets between different IP networks. Every router maintains a **routing table** — a list of known destination networks plus the next-hop or outgoing interface for each.

**How forwarding works (per packet):**

1. A packet arrives on an interface; the router reads its **destination IP**.
2. The router searches its table for the **longest matching prefix** (most specific entry).
3. The packet is rewritten with a new Layer-2 header and sent out the matching interface toward the **next hop**.
4. TTL is decremented; if it hits `0`, the packet is dropped and an ICMP Time Exceeded is returned.

**Key concepts:**

| Term                        | Meaning                                                                              |
| --------------------------- | ------------------------------------------------------------------------------------ |
| **Next hop**                | IP of the neighboring router that should receive the packet next.                    |
| **Outgoing interface**      | Local interface the router sends the packet out on.                                  |
| **Metric**                  | A number used to break ties between routes from the same protocol (lower = better).  |
| **Administrative distance** | Trust level between sources — e.g., static beats OSPF beats RIP.                     |
| **Convergence**             | How long it takes for every router to agree on the topology after a change.          |

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

| Source     | AD  |
| ---------- | --- |
| Connected  | 0   |
| Static     | 1   |
| eBGP       | 20  |
| OSPF       | 110 |
| RIP        | 120 |
| iBGP       | 200 |

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

| Aspect            | Static Routing                              | Dynamic Routing                            |
| ----------------- | ------------------------------------------- | ------------------------------------------ |
| Configuration     | Hand-entered by admin                       | Learned via a routing protocol             |
| Reacts to outages | No — manual fix required                    | Yes — protocol reconverges automatically   |
| Overhead          | Zero — no protocol traffic, no CPU          | CPU + bandwidth for hellos and updates     |
| Scalability       | Fine for small or stub networks             | Required for medium and large networks     |
| Predictability    | Fully deterministic                         | Depends on protocol convergence behavior   |
| Common uses       | Default routes, point-to-point links, edges | Backbones, multi-path networks, ISPs       |

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

| Protocol  | Type                 | Algorithm        | Metric                                | Typical Use                                  |
| --------- | -------------------- | ---------------- | ------------------------------------- | -------------------------------------------- |
| **RIP**   | IGP, distance-vector | Bellman-Ford     | Hop count (max 15)                    | Tiny legacy networks; rare today             |
| **OSPF**  | IGP, link-state      | Dijkstra (SPF)   | Cost (based on bandwidth)             | Most enterprise LANs and campuses            |
| **EIGRP** | IGP, hybrid          | DUAL             | Bandwidth + delay (configurable)      | Cisco-heavy networks                         |
| **BGP**   | EGP, path-vector     | Best-path policy | AS path, local pref, MED, communities | The protocol of the internet (between ASes)  |

**Quick characterizations:**

- **RIP** — simple, periodic full-table updates every 30s; max 15 hops makes anything bigger unreachable. Mostly historical.
- **OSPF** — every router floods Link-State Advertisements (LSAs) describing its own links; each router independently runs Dijkstra to compute shortest paths. Fast convergence, organized into **areas** for scale.
- **EIGRP** — originally Cisco-proprietary (now open); converges fast using the DUAL algorithm and keeps a feasible successor (precomputed backup path).
- **BGP** — the protocol that holds the internet together. Each Autonomous System announces the prefixes it owns; BGP picks paths based on **policy**, not just shortest hop count.

### IGP vs EGP

Routing protocols are categorized by **where** they run.

| Category | Stands For                | Runs Where                        | Examples                  |
| -------- | ------------------------- | --------------------------------- | ------------------------- |
| **IGP**  | Interior Gateway Protocol | Inside a single Autonomous System | RIP, OSPF, EIGRP, IS-IS   |
| **EGP**  | Exterior Gateway Protocol | Between Autonomous Systems        | BGP (only one in real use)|

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
