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
  <img src="https://img.shields.io/badge/Sections-9-blue?style=flat-square" alt="Sections">
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
- [Networking Fundamentals](#networking-fundamentals)
  - [One Shot Revision](#one-shot-revision)
  - [OSI Model](#osi-model)
  - [TCP/IP Model](#tcpip-model)
  - [IP Addressing](#ip-addressing)
  - [Subnetting & CIDR](#subnetting--cidr)
  - [Ports & Protocols](#ports--protocols)
  - [MAC Addresses & ARP](#mac-addresses--arp)
- [Network Configuration](#network-configuration)
  - [One Shot Revision](#one-shot-revision-1)
  - [ip](#ip)
  - [ifconfig](#ifconfig)
  - [hostname](#hostname)
  - [/etc/hosts](#etchosts)
  - [/etc/resolv.conf](#etcresolvconf)
  - [NetworkManager (nmcli)](#networkmanager-nmcli)
- [Connectivity & Diagnostics](#connectivity--diagnostics)
  - [One Shot Revision](#one-shot-revision-2)
  - [ping](#ping)
  - [traceroute](#traceroute)
  - [mtr](#mtr)
  - [telnet](#telnet)
  - [nc (netcat)](#nc-netcat)
- [DNS Tools](#dns-tools)
  - [One Shot Revision](#one-shot-revision-3)
  - [DNS Concepts](#dns-concepts)
  - [dig](#dig)
  - [nslookup](#nslookup)
  - [host](#host)
- [Sockets & Ports](#sockets--ports)
  - [One Shot Revision](#one-shot-revision-4)
  - [ss](#ss)
  - [netstat](#netstat)
  - [lsof](#lsof)
- [HTTP & Transfer Tools](#http--transfer-tools)
  - [One Shot Revision](#one-shot-revision-5)
  - [curl](#curl)
  - [wget](#wget)
- [Remote Access](#remote-access)
  - [One Shot Revision](#one-shot-revision-6)
  - [ssh](#ssh)
  - [scp](#scp)
  - [rsync](#rsync)
  - [SSH Keys & Config](#ssh-keys--config)
- [Firewall & Security](#firewall--security)
  - [One Shot Revision](#one-shot-revision-7)
  - [iptables](#iptables)
  - [nftables](#nftables)
  - [ufw](#ufw)
  - [firewalld](#firewalld)
- [Packet Analysis](#packet-analysis)
  - [One Shot Revision](#one-shot-revision-8)
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
| [`rsync`](#rsync)                       | Efficient incremental file sync — local or over SSH        |
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
