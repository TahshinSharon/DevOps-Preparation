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
  <img src="https://img.shields.io/badge/Topics-6-blue?style=flat-square" alt="Topics">
  <img src="https://img.shields.io/badge/Made%20For-DevOps%20Prep-orange?style=flat-square" alt="Made For">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="./Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Networking/README.md"><b>Networking Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Cloud-Engineering/README.md"><b>Cloud Engineering Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Docker/README.md"><b>Docker Notes</b></a>
  &nbsp;·&nbsp;
  <a href="./Kubernetes/README.md"><b>Kubernetes Notes</b></a>
</p>

---

## Table of Contents

- [About This Repository](#about-this-repository)
- [Repository Structure](#repository-structure)
- [How to Read This Repo](#how-to-read-this-repo)
- [Sections](#sections)
  - [Git & GitHub](#git--github)
  - [Linux](#linux)
  - [Networking](#networking)
  - [Cloud Engineering](#cloud-engineering)
  - [Docker](#docker)
  - [Kubernetes](#kubernetes)
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
├── README.md                   ← you are here
├── 1. Git-Github/
│   └── README.md               ← Git workflows, branching, GitHub & gh CLI, Actions, ...
├── 2. Linux/
│   └── README.md               ← Linux commands, text formating, user management, ...
├── 3. Networking/
│   └── README.md               ← OSI/TCP-IP, ip/ss/dig/curl/ssh, firewalls, packet capture, ...
├── 4. Cloud-Engineering/
│   └── README.md               ← AWS EC2 and other cloud services, concepts, and notes
├── 5. Docker/
│   └── README.md               ← Containers, images, Dockerfile, volumes, networks, Compose, ...
└── 6. Kubernetes/
    └── README.md               ← Pods, Deployments, Services, Namespaces, kubectl, Helm, ...
```

> **Note:** the numbers above indicate the recommended reading order; the actual folders on disk are named without the `N. ` prefix (`Git-Github/`, `Linux/`, `Networking/`, `Cloud-Engineering/`, `Docker/`, `Kubernetes/`).

Every topic folder holds a single `README.md` that acts as the full reference for that subject. New topics (Kubernetes, CI/CD, Terraform, etc.) will be added the same way — one folder, one self-contained `README.md`.

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

### Git & GitHub

Distributed version control plus the collaboration layer on top.

- **Git Basics** — `init`, `clone`, `config`, `status`.
- **Working with Changes** — `add`, `commit`, `diff`, `log`, `.gitignore`.
- **Branching & Merging** — `branch`, `switch`, `merge`, `rebase`, `cherry-pick`.
- **Remote Repositories** — `remote`, `fetch`, `pull`, `push`, SSH vs HTTPS.
- **Undoing Changes** — `restore`, `reset`, `revert`, `clean`, `reflog`.
- **Stashing & Tagging** — `stash`, `tag`.
- **Advanced Git** — `bisect`, `blame`, `submodule`, `worktree`, hooks.
- **GitHub & Collaboration** — SSH keys, PR workflow, `gh` CLI, GitHub Actions, CI/CD concepts.

→ [Open the Git & GitHub notes](./Git-Github/README.md)

### Linux

Foundational shell skills — the bread and butter of any DevOps role.

- **Basic Commands** — `pwd`, `cd`, `ls`, `cp`, `mv`, `rm`, `find`, `man`, ...
- **Text-Formating** — pipes, redirection, `cut`, `sort`, `uniq`, `grep`, `wc`, ...
- **Advanced Text-Formating** — regular expressions and the `vim` editor.
- **User Management** — `/etc/passwd`, `/etc/shadow`, `useradd`, `usermod`, `sudo`, root.
- **Permissions** — file permission bits (`rwx`), user/group/other classes, symbolic vs octal notation.
- **Packages** — software distribution formats (`.rpm`, `.deb`, Snap, Flatpak), repositories, `tar`/`gzip`, dependency management, `rpm`/`dpkg`, `yum`/`apt`, compiling from source (`./configure && make && make install`), and building NGINX from source (deps, `--with-*` module flags, systemd unit, hot upgrade, dynamic modules).

→ [Open the Linux notes](./Linux/README.md)

### Networking

The Linux networking stack and the tools used to inspect, configure, and troubleshoot it.

- **Network Sharing** — file sharing overview, `rsync`, simple HTTP server, NFS, Samba.
- **Networking Fundamentals** — network basics (components, LAN/WAN/WLAN, hosts & packets), OSI/TCP-IP models, per-layer deep-dives (application, transport, network, link), IP addressing, DHCP, ports, ARP.
- **Subnetting** — subnets & broadcast domains, subnet math, mental-math cheats, CIDR & supernetting, IPv4 with VLSM, NAT (SNAT/DNAT/PAT/CGNAT), IPv6 (`/64`, SLAAC, NDP).
- **Routing** — routing tables & longest-prefix match, path of a packet end-to-end, default gateway, static vs dynamic routing, routing protocols (RIP/OSPF/EIGRP/BGP), distance-vector (Bellman-Ford, split horizon), link-state (Dijkstra SPF, OSPF areas), BGP (path-vector, eBGP/iBGP, best-path selection), IGP vs EGP, Linux `ip route` & policy routing.
- **Network Configuration** — `ip`, `ifconfig`, `hostname`, `/etc/hosts`, `nmcli`.
- **Connectivity & Diagnostics** — `ping`, `traceroute`, `netstat`, `mtr`, `telnet`, `nc`.
- **DNS Tools** — what DNS is, DNS components (resolvers, root/TLD/authoritative servers, records), DNS process (recursive + iterative), `/etc/hosts`, DNS setup, and lookup tools (`dig`, `nslookup`, `host`).
- **Sockets & Ports** — `ss`, `lsof`.
- **HTTP & Transfer Tools** — `curl`, `wget`.
- **Remote Access** — `ssh`, `scp`, `rsync`, SSH keys & config.
- **Firewall & Security** — `iptables`, `nftables`, `ufw`, `firewalld`.
- **Packet Analysis** — `tcpdump`, `wireshark`/`tshark`, `nmap`.

→ [Open the Networking notes](./Networking/README.md)

### Cloud Engineering

Cloud-native services on AWS (and equivalents on other providers) used to build, deploy, and scale infrastructure.

- **Cloud Computing Models** — service models (IaaS, PaaS, SaaS, FaaS), deployment models (Public, Private, Hybrid, Multi-Cloud), and the AWS Shared Responsibility Model.
- **AWS Global Infrastructure** — the physical and logical backbone of AWS — Regions, Availability Zones, Edge Locations, Local Zones, Wavelength Zones, Outposts, and how to choose the right Region.
- **AWS Free Tier** — three offer types (Always Free, 12 Months Free, Trials), key service allowances, billing alerts, and a cleanup checklist to avoid unexpected charges.
- **AWS Pricing Models** — On-Demand, Reserved Instances, Savings Plans, Spot Instances, Dedicated Hosts, and the cost tools used to estimate, monitor, and optimise spend.
- **AWS Access Methods** — Management Console (browser GUI), AWS CLI v2 (install, configure, profiles, common commands), AWS SDKs (boto3 and others), CloudShell (browser-based pre-authenticated shell), raw REST APIs (SigV4 signing), and Infrastructure as Code (CloudFormation, CDK, Terraform).
- **IAM (Identity and Access Management)** — the global identity plane for AWS — users, groups, roles, policies, trust relationships, and policy evaluation logic.
- **Amazon S3** — object storage — buckets, objects, keys, storage classes (Standard, IA, Glacier, Intelligent-Tiering), security (bucket policies, encryption, Block Public Access), and lifecycle policies.
- **Elastic Compute Cloud (EC2)** — resizable virtual servers in AWS — instances, AMIs, instance types, security groups, EBS volumes, key pairs, and SSH access.
- **AWS Lambda** — serverless compute — functions, handlers, invocation types (synchronous, asynchronous, poll-based), runtimes, cold starts, concurrency (unreserved, reserved, provisioned), versions & aliases, async destinations & DLQ, Function URLs, VPC configuration, CloudWatch metrics, X-Ray tracing, and Lambda Insights.
- **AWS CLI** — the command-line tool for AWS — installation and configuration, named profiles and credentials, output formats and JMESPath querying, common service commands (S3, EC2, IAM, Lambda), pagination, waiters, batch operations, scripting best practices, and credential security.
- **CloudWatch** — AWS's native observability service — logs (log groups, streams, retention, filtering), metrics (built-in and custom), alarms (thresholds, actions, anomaly detection), dashboards (custom visualizations), and Log Insights (query language for log analysis).

→ [Open the Cloud Engineering notes](./Cloud-Engineering/README.md)

### Docker

The container platform for packaging applications with their dependencies into portable, isolated runtimes.

- **Docker Fundamentals** — what Docker is, containers vs virtual machines, Docker architecture (client / daemon / registry), images, containers, and registries.
- **Container Basics** — `docker run`, port publishing (`-p`), detached mode (`-d`), listing containers (`docker ps`/`docker ps -a`), naming and renaming (`--name`, `docker rename`), stopping and killing (`docker stop`/`docker kill`), restarting (`docker restart`), staging without running (`docker create`), removing dangling containers (`docker rm`, `docker container prune`), interactive mode (`-it`), executing commands (`docker exec`), and working with executable images (`ENTRYPOINT`).
- **Image Basics** — end-to-end image creation workflow: write a Dockerfile, build (`docker build`), verify locally (`docker image ls`), tag for a registry (`docker image tag`), push (`docker push`), pull on another machine (`docker pull`), and clean up (`docker image rm`/`prune`); tag anatomy, semantic versioning patterns, multi-registry tagging (Docker Hub, GHCR, ECR), mutable vs immutable tag references; listing images with filters and format templates, inspecting metadata and layer history, removing single/multiple images, and bulk cleanup with `docker image prune`; understanding image layers — read-only layer stack, copy-on-write container layer, `docker image history`, layer caching and instruction ordering for fast builds.
- **How to Containerize a JavaScript Application** — writing a development Dockerfile with a non-root user; enabling hot reload with bind mounts; protecting `node_modules` with anonymous volumes; shipping a lean production image using multi-stage builds (`node` builder → `nginx` runtime); and excluding unnecessary files with `.dockerignore`.
- **Docker Networking** — network drivers (`bridge`, `host`, `none`, `overlay`), `docker network` commands, and container-to-container DNS.
- **How to Containerize a Multi-Container JavaScript Application** — running a PostgreSQL database container with a named volume; checking logs; creating a user-defined network; writing a multi-stage Dockerfile for a Node.js API; running migrations with `docker exec`; and automating the full lifecycle with shell scripts.
- **How to Compose Projects Using Docker-Compose** — `compose.yaml` structure and per-service keys; starting (`docker compose up`), listing (`docker compose ps`), exec-ing into (`docker compose exec`), and logging (`docker compose logs`) services; `stop` vs `down` vs `down --volumes`; composing the hello-dock full-stack app for development with bind mounts and anonymous volumes.

→ [Open the Docker notes](./Docker/README.md)

### Kubernetes

The container orchestration platform for deploying, scaling, and managing containerized applications across a cluster.

- **Kubernetes Fundamentals** — what Kubernetes is, K8s vs Docker, cluster architecture, control plane (API Server, etcd, Scheduler, Controller Manager), worker node components (kubelet, kube-proxy, container runtime).
- **Kubernetes Basics** — creating a cluster with **kubeadm** (production / VMs) and **kind** (local development / CI), deploying and managing apps with kubectl, viewing pods and nodes for inspection and debugging, exposing apps via Services (ClusterIP, NodePort, LoadBalancer) and Ingress.

→ [Open the Kubernetes notes](./Kubernetes/README.md)

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
