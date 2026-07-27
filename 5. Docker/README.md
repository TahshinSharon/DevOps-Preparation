<h1 align="center">Docker Learning Notes</h1>

<p align="center">
  A personal collection of Docker commands, concepts,<br>
  and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">
  <img src="https://img.shields.io/badge/Containers-0DB7ED?style=for-the-badge&logo=docker&logoColor=white" alt="Containers">
  <img src="https://img.shields.io/badge/Compose-384D54?style=for-the-badge&logo=docker&logoColor=white" alt="Compose">
  <img src="https://img.shields.io/badge/DevOps-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="DevOps">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-8-blue?style=flat-square" alt="Sections">
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
  <a href="../Networking/README.md"><b>Networking Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Cloud-Engineering/README.md"><b>Cloud Engineering Notes</b></a>
</p>

---

## Table of Contents

- [Introduction](#introduction)
- [Docker Commands](#docker-commands)
- [Docker Fundamentals](#docker-fundamentals)
  - [One Shot Revision](#one-shot-revision)
  - [What is Docker?](#what-is-docker)
  - [Containers vs Virtual Machines](#containers-vs-virtual-machines)
  - [Docker Architecture](#docker-architecture)
  - [Images, Containers & Registries](#images-containers--registries)
- [Container Basics](#container-basics)
  - [One Shot Revision](#one-shot-revision-1)
  - [How to Run a Container](#how-to-run-a-container)
  - [How to Publish a Port](#how-to-publish-a-port)
  - [How to Use Detached Mode](#how-to-use-detached-mode)
  - [How to List Containers](#how-to-list-containers)
  - [How to Name or Rename a Container](#how-to-name-or-rename-a-container)
  - [How to Stop or Kill a Running Container](#how-to-stop-or-kill-a-running-container)
  - [How to Restart a Container](#how-to-restart-a-container)
  - [How to Create a Container Without Running](#how-to-create-a-container-without-running)
  - [How to Remove Dangling Containers](#how-to-remove-dangling-containers)
  - [How to Run a Container in Interactive Mode](#how-to-run-a-container-in-interactive-mode)
  - [How to Execute Commands Inside a Container](#how-to-execute-commands-inside-a-container)
  - [How to Work With Executable Images](#how-to-work-with-executable-images)
- [Image Basics](#image-basics)
  - [One Shot Revision](#one-shot-revision-2)
  - [How to Create a Docker Image](#how-to-create-a-docker-image)
  - [How to Tag Docker Images](#how-to-tag-docker-images)
  - [How to List and Remove Docker Images](#how-to-list-and-remove-docker-images)
  - [How to Understand the Many Layers of a Docker Image](#how-to-understand-the-many-layers-of-a-docker-image)
  - [How to Build NGINX from Source](#how-to-build-nginx-from-source)
  - [How to Optimize Docker Images](#how-to-optimize-docker-images)
  - [Embracing Alpine Linux](#embracing-alpine-linux)
  - [How to Create Executable Docker Images](#how-to-create-executable-docker-images)
  - [How to Share Your Docker Images Online](#how-to-share-your-docker-images-online)
- [How to Containerize a JavaScript Application](#how-to-containerize-a-javascript-application)
  - [One Shot Revision](#one-shot-revision-3)
  - [How to Write the Development Dockerfile](#how-to-write-the-development-dockerfile)
  - [How to Work With Bind Mounts in Docker](#how-to-work-with-bind-mounts-in-docker)
  - [How to Work With Anonymous Volumes in Docker](#how-to-work-with-anonymous-volumes-in-docker)
  - [How to Perform Multi-Staged Builds in Docker](#how-to-perform-multi-staged-builds-in-docker)
  - [How to Ignore Unnecessary Files](#how-to-ignore-unnecessary-files)
- [How to Containerize a Multi-Container JavaScript Application](#how-to-containerize-a-multi-container-javascript-application)
  - [One Shot Revision](#one-shot-revision-4)
  - [How to Run the Database Server](#how-to-run-the-database-server)
  - [How to Work with Named Volumes in Docker](#how-to-work-with-named-volumes-in-docker)
  - [How to Access Logs from a Container in Docker](#how-to-access-logs-from-a-container-in-docker)
  - [How to Create a Network and Attaching the Database Server in Docker](#how-to-create-a-network-and-attaching-the-database-server-in-docker)
  - [How to Write the Dockerfile](#how-to-write-the-dockerfile)
- [Docker Networking](#docker-networking)
  - [One Shot Revision](#one-shot-revision-4)
  - [Docker Network Basics](#docker-network-basics)
  - [Network Types](#network-types)
  - [`docker network` Commands](#docker-network-commands)
  - [Container-to-Container Communication](#container-to-container-communication)
  - [How to Create a User-Defined Bridge in Docker](#how-to-create-a-user-defined-bridge-in-docker)
  - [How to Attach a Container to a Network in Docker](#how-to-attach-a-container-to-a-network-in-docker)
  - [How to Detach Containers from a Network in Docker](#how-to-detach-containers-from-a-network-in-docker)
  - [How to Get Rid of Networks in Docker](#how-to-get-rid-of-networks-in-docker)
- [How to Containerize a Multi-Container JavaScript Application](#how-to-containerize-a-multi-container-javascript-application)
  - [One Shot Revision](#one-shot-revision-5)
  - [How to Run the Database Server](#how-to-run-the-database-server)
  - [How to Work with Named Volumes in Docker](#how-to-work-with-named-volumes-in-docker)
  - [How to Access Logs from a Container in Docker](#how-to-access-logs-from-a-container-in-docker)
  - [How to Create a Network and Attaching the Database Server in Docker](#how-to-create-a-network-and-attaching-the-database-server-in-docker)
  - [How to Write the Dockerfile](#how-to-write-the-dockerfile)
  - [How to Execute Commands in a Running Container](#how-to-execute-commands-in-a-running-container)
  - [How to Write Management Scripts in Docker](#how-to-write-management-scripts-in-docker)
  - [How to Execute Commands in a Running Container](#how-to-execute-commands-in-a-running-container)
- [Docker Compose](#docker-compose)
  - [`compose.yaml` Structure](#composeyaml-structure)
  - [Core Compose Commands](#core-compose-commands)
- [Useful Tips & Tricks](#useful-tips--tricks)
- [References](#references)

---

## Introduction

Brief notes about Docker — the container platform that packages an application together with its dependencies into a portable, isolated runtime.

- **Focus:** Building, running, and shipping containerized applications with Docker.
- **Scope:** Images → containers → volumes → networks → Dockerfile → Compose → registries.
- **Goal:** Build strong container fundamentals for DevOps interview prep and day-to-day workflows.

**Learn from the official source:**

→ [The Docker Handbook — freeCodeCamp (Farhan Hasin Chowdhury)](https://www.freecodecamp.org/news/the-docker-handbook/)

---

## Docker Commands

Docker's CLI is the primary way you interact with Docker — building images, running containers, managing networks, and more. Every command follows the pattern `docker <command> [options] [arguments]`. Most commands have both a legacy short form (e.g. `docker ps`) and a modern management form (e.g. `docker container ls`) — they do the same thing. Commands are grouped by object: `container`, `image`, `network`, `volume`, and `compose`.

For the full list of commands and flags, see the **[Docker CLI Reference →](https://docs.docker.com/reference/cli/docker/)**

---

## Docker Fundamentals

Before touching any command, it helps to build a clear mental picture of what Docker is, why it exists, and how its pieces fit together. This section is the "story" behind every command in the rest of the notes.

### One Shot Revision

| Topic                                                             | Short Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------- |
| [What is Docker?](#what-is-docker)                                | Containerization platform that packages apps with their dependencies    |
| [Containers vs VMs](#containers-vs-virtual-machines)              | Containers share the host kernel; VMs ship a full guest OS              |
| [Docker Architecture](#docker-architecture)                       | CLI → daemon → containerd → runc; daemon also talks to registries       |
| [Images, Containers & Registries](#images-containers--registries) | Image = blueprint, container = running instance, registry = image store |

### What is Docker?

**In one sentence:** Docker packages an application together with everything it needs to run — code, runtime, libraries, environment variables, and settings — into a portable box called a **container**.

**Why it exists:**

- Fixes the classic **"it works on my machine"** problem — the container carries its own environment, so it behaves the same on your laptop, a colleague's laptop, a CI runner, and a production server.
- Removes painful setup steps like "install Python 3.10, then install Node 18, then install these five system libraries, then set these three env vars."
- Starts in **milliseconds**, uses far less RAM/disk than a virtual machine, and can be shipped as a single file (an image).

**How it works under the hood:** Docker is built on two Linux kernel features:

- **Namespaces** — give each container its own private view of the system (processes, network, mounts, hostname, users).
- **Control groups (cgroups)** — limit and account for how much CPU, memory, and I/O each container can use.

Together they create the illusion of a separate machine without ever leaving the host kernel.

**Docker Engine vs Docker Desktop:**

- **Docker Engine** runs natively on Linux (containers use the host kernel directly).
- **Docker Desktop** (macOS/Windows) ships a lightweight Linux VM under the hood, because containers need a Linux kernel — you're actually running containers inside that VM.

**Real-world mental model:** Think of a container like a shipping container. The dock (your OS) doesn't care what's inside — as long as the container follows the standard shape, any crane (Docker Engine) on any port (host OS) can lift and run it.

### Containers vs Virtual Machines

Both give you isolation, but they achieve it very differently.

| Aspect             | Container                           | Virtual Machine                    |
| ------------------ | ----------------------------------- | ---------------------------------- |
| What's virtualized | Just the OS (shares host kernel)    | The whole machine (CPU, RAM, disk) |
| Guest OS           | None — uses the host kernel         | A full OS (Ubuntu, Windows, etc.)  |
| Size               | Tens of MB                          | Several GB                         |
| Startup            | Milliseconds                        | Minutes                            |
| Density            | Hundreds per host                   | A handful per host                 |
| Isolation          | Process-level (namespaces, cgroups) | Hardware-level (hypervisor)        |

**Easy way to remember:** A **VM is a whole house** with its own foundation, plumbing, and roof. A **container is an apartment** in a shared building — it has its own locked door and furniture, but the walls, wiring, and heating are shared with everyone else.

**Stack diagram — same host, very different layers:**

```
       Virtual Machines                        Containers
   ┌──────┐ ┌──────┐ ┌──────┐            ┌──────┐ ┌──────┐ ┌──────┐
   │ App  │ │ App  │ │ App  │            │ App  │ │ App  │ │ App  │
   │ +Deps│ │ +Deps│ │ +Deps│            │ +Deps│ │ +Deps│ │ +Deps│
   ├──────┤ ├──────┤ ├──────┤            └──────┘ └──────┘ └──────┘
   │Guest │ │Guest │ │Guest │            ┌────────────────────────┐
   │  OS  │ │  OS  │ │  OS  │            │     Docker Engine      │
   ├──────┴─┴──────┴─┴──────┤            ├────────────────────────┤
   │      Hypervisor        │            │        Host OS         │
   ├────────────────────────┤            ├────────────────────────┤
   │        Host OS         │            │       Hardware         │
   ├────────────────────────┤            └────────────────────────┘
   │       Hardware         │
   └────────────────────────┘
```

Each VM drags its own guest OS along. Containers skip that entire layer and share the host kernel — that's why one is measured in gigabytes and the other in megabytes.

**Proof containers share the kernel:**

```bash
# Runs "uname -a" inside a tiny Alpine container — you'll see YOUR host's kernel
docker run --rm alpine uname -a
```

### Docker Architecture

Docker uses a **client-server model**. When you type `docker ...` on the terminal, the CLI talks to a daemon, which delegates the actual container work to two lower-level runtimes:

```
┌─────────────┐  REST API   ┌───────────────┐   gRPC   ┌───────────┐   exec    ┌──────┐
│ docker CLI  │ ──────────► │ Docker daemon │ ───────► │ containerd│ ────────► │ runc │──► container
│  (client)   │             │   (dockerd)   │          │           │           │      │    process
└─────────────┘             └───────┬───────┘          └───────────┘           └──────┘
                                    │
                                    ▼
                             ┌──────────────┐
                             │   Registry   │  (Docker Hub, GHCR, ECR, ...)
                             └──────────────┘
```

- **Docker client (`docker`)** — the CLI you type commands into. It doesn't do the heavy lifting itself.
- **Docker daemon (`dockerd`)** — a long-running background service that exposes the REST API, builds images (via **BuildKit**), and manages higher-level objects like networks, volumes, and image storage.
- **containerd** — the container runtime the daemon delegates to. It handles the container lifecycle: pulling images, unpacking them, and running containers.
- **runc** — the low-level OCI runtime that actually creates the container process using Linux namespaces and cgroups. This is where a container becomes real.
- **REST API** — the bridge the client uses to talk to the daemon (locally over a Unix socket at `/var/run/docker.sock`, or remotely over TCP).
- **Registry** — a remote image store. **Docker Hub** is the default public registry; others include GitHub Container Registry (GHCR), Amazon ECR, Google Artifact Registry, and self-hosted options like Harbor.

**Why the split matters:** Because container work lives in `containerd` + `runc` (both OCI-standard), Kubernetes and other tools can run containers **without** Docker — they just talk to `containerd` (or another OCI runtime) directly. Docker is the friendly all-in-one wrapper on top.

### Images, Containers & Registries

The three nouns you'll see over and over:

- **Image** — a read-only, layered **blueprint** for a container. It bundles the file system, dependencies, and a default command. Images are immutable and portable.
- **Container** — a **running instance** of an image, with a thin writable layer on top. You can have many containers from the same image.
- **Registry** — a **library of images**. You `pull` images from it and `push` your own to share.

**Analogy:**

- Image = a class (or a recipe, or a class blueprint).
- Container = an object created from that class (or the cooked meal made from the recipe).
- Registry = the cookbook everyone shares.

**How image layers work (and why images stay small):**

Every instruction in a `Dockerfile` produces a **read-only layer**. When a container starts, Docker stacks a thin **writable layer** on top using a **union filesystem** (OverlayFS on modern Linux). Writes go to that top layer via **copy-on-write** — unchanged files are never duplicated.

```
   ┌────────────────────────────┐  ← writable layer  (per container)
   ├────────────────────────────┤
   │      CMD ["node", ...]     │  ← image layers    (shared, read-only)
   │      COPY . .              │
   │      RUN npm ci            │
   │      COPY package*.json    │
   │      FROM node:20-alpine   │
   └────────────────────────────┘
```

**Practical payoff:** ten containers from the same image share one set of layers on disk. Only their tiny writable layers differ.

---

## Container Basics

The commands you use every single day to run, inspect, and clean up containers.

### One Shot Revision

| Topic                                                                                     | Short Description                                      |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| [How to Run a Container](#how-to-run-a-container)                                         | Create + start a container from an image               |
| [How to Publish a Port](#how-to-publish-a-port)                                           | Map host ports to container ports                      |
| [How to Use Detached Mode](#how-to-use-detached-mode)                                     | Run containers in the background with `-d`             |
| [How to List Containers](#how-to-list-containers)                                         | Inspect running and stopped containers                 |
| [How to Name or Rename a Container](#how-to-name-or-rename-a-container)                   | Set a name at creation or rename with `docker rename`  |
| [How to Stop or Kill a Running Container](#how-to-stop-or-kill-a-running-container)       | Graceful stop vs immediate kill                        |
| [How to Restart a Container](#how-to-restart-a-container)                                 | Bounce a container with `docker restart`               |
| [How to Create a Container Without Running](#how-to-create-a-container-without-running)   | Stage a container with `docker create`                 |
| [How to Remove Dangling Containers](#how-to-remove-dangling-containers)                   | Clean up stopped and leftover containers               |
| [How to Run a Container in Interactive Mode](#how-to-run-a-container-in-interactive-mode) | Open a shell inside a new container with `-it`         |
| [How to Execute Commands Inside a Container](#how-to-execute-commands-inside-a-container) | Run commands in a running container with `docker exec` |
| [How to Work With Executable Images](#how-to-work-with-executable-images)                 | Use `ENTRYPOINT` images as CLI tools                   |

### How to Run a Container

**Description:** `docker run` creates a new container from an image and starts it in one step. This is the single most-used Docker command — under the hood it combines `docker create` and `docker start`.

**Syntax:**

```bash
docker run [options] <image> [command]
```

**Common Options:**

| Option          | Description                                           |
| --------------- | ----------------------------------------------------- |
| `-p, --publish` | Map a host port to a container port: `-p 8080:80`     |
| `-d, --detach`  | Run in the background; return the container ID        |
| `-it`           | Interactive + TTY — for shells and REPLs              |
| `--name`        | Give the container a friendly name                    |
| `--rm`          | Auto-remove the container when it exits               |
| `-e, --env`     | Set an environment variable: `-e NODE_ENV=production` |
| `-v, --volume`  | Attach a volume or bind mount: `-v $(pwd):/app`       |
| `--network`     | Attach the container to a specific network            |

**Examples:**

```bash
# Run nginx in the background and expose it on port 8080
docker run -d -p 8080:80 --name web nginx

# Open an interactive shell that cleans itself up on exit
docker run --rm -it ubuntu bash

# Run a one-off command with an env var
docker run --rm -e GREETING=hello alpine sh -c 'echo $GREETING world'

# Mount the current folder for live development
docker run --rm -it -v $(pwd):/app -w /app node:20-alpine sh
```

**Notes:**

- Without `-p`, the container is unreachable from the host — port publishing is opt-in.
- `-it` combines two flags: `-i` keeps STDIN open, `-t` allocates a TTY so prompts render correctly.
- If a container was created with `--rm`, it's gone once stopped — there's nothing to `docker start` later.

### How to Publish a Port

**Description:** By default a container's ports are not reachable from the host. The `-p` flag maps a port on the host to a port inside the container, making the service accessible.

**Syntax:**

```bash
docker run -p <host-port>:<container-port> <image>
```

**Port Mapping Formats:**

| Format                 | Description                                        |
| ---------------------- | -------------------------------------------------- |
| `-p 8080:80`           | Map host port 8080 → container port 80             |
| `-p 127.0.0.1:8080:80` | Bind only on loopback — not exposed to the network |
| `-p 80`                | Docker picks a random host port                    |
| `-p 8080:80/udp`       | Map a UDP port instead of TCP                      |

**Examples:**

```bash
# Serve nginx on host port 8080
docker run -d -p 8080:80 --name web nginx

# Bind to localhost only — not reachable from other machines
docker run -d -p 127.0.0.1:5432:5432 postgres:16-alpine

# Map multiple ports at once
docker run -d -p 80:80 -p 443:443 --name proxy nginx

# See which host port was assigned to a running container
docker port web
```

**Notes:**

- Port mapping is always `<host>:<container>` — left side is your machine, right side is the container.
- `-P` (uppercase) publishes every port declared with `EXPOSE` in the Dockerfile to random host ports.
- `docker port <container>` lists all active port mappings for a running container.

### How to Use Detached Mode

**Description:** By default `docker run` attaches your terminal to the container's output — when you close the terminal, the container stops. The `-d` (or `--detach`) flag runs the container in the background and immediately returns the container ID, leaving your terminal free.

**Syntax:**

```bash
docker run -d [options] <image>
```

**Examples:**

```bash
# Run nginx in the background
docker run -d -p 8080:80 --name web nginx

# Run a database in the background with a named volume
docker run -d \
  --name db \
  -e POSTGRES_PASSWORD=secret \
  -v db-data:/var/lib/postgresql/data \
  postgres:16-alpine

# Confirm it's running
docker ps

# Follow the logs of a detached container
docker logs -f web

# Attach back to a detached container's output stream
docker attach web

# Stop a detached container
docker stop web
```

**Managing Detached Containers:**

| Command                 | What it does                                       |
| ----------------------- | -------------------------------------------------- |
| `docker ps`             | List all running containers                        |
| `docker ps -a`          | List all containers, including stopped ones        |
| `docker logs <name>`    | Print the container's stdout/stderr                |
| `docker logs -f <name>` | Follow (tail) live log output                      |
| `docker stop <name>`    | Gracefully stop the container (sends SIGTERM)      |
| `docker start <name>`   | Restart a stopped container in detached mode       |
| `docker attach <name>`  | Re-attach your terminal to the container's output  |
| `docker stats`          | Live CPU / memory usage for all running containers |

**Notes:**

- A detached container keeps running until it exits on its own or you explicitly `docker stop` it — closing the terminal has no effect.
- `docker attach` connects you to the main process's stdin/stdout; press `Ctrl-P Ctrl-Q` to detach again without stopping the container.
- Combine `-d` with `--rm` for ephemeral background jobs: the container is deleted automatically once it finishes.
- Always give long-running detached containers a `--name` so you don't have to look up the container ID later.

### How to List Containers

**Description:** `docker ps` shows you what containers exist on the host — by default only running ones, but with `-a` you see everything including stopped containers. It's the first command to reach for when something isn't behaving as expected.

**Syntax:**

```bash
docker ps [options]
# Modern alias:
docker container ls [options]
```

**Common Options:**

| Option        | Description                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| `-a, --all`   | Show all containers — running **and** stopped                               |
| `-q, --quiet` | Print only container IDs (useful for scripting)                             |
| `--filter`    | Filter by field: `--filter status=exited`, `--filter name=web`              |
| `--format`    | Custom output with Go templates: `--format "table {{.Names}}\t{{.Status}}"` |
| `-n <count>`  | Show the last N containers created                                          |
| `-s, --size`  | Display the container's disk usage                                          |

**Examples:**

```bash
# What's currently running?
docker ps

# Show everything, including stopped containers
docker ps -a

# Just IDs — useful for piping into other commands
docker ps -aq

# Show only exited containers
docker ps -a --filter status=exited

# Show only containers matching a name
docker ps --filter name=web

# Custom table: name, image, and status columns
docker ps --format "table {{.Names}}\t{{.Image}}\t{{.Status}}"

# Remove every stopped container in one shot
docker rm $(docker ps -aq --filter status=exited)
```

**Output Columns:**

| Column         | What it shows                                     |
| -------------- | ------------------------------------------------- |
| `CONTAINER ID` | Short ID of the container                         |
| `IMAGE`        | The image the container was created from          |
| `COMMAND`      | The command running inside the container          |
| `CREATED`      | How long ago the container was created            |
| `STATUS`       | `Up X minutes`, `Exited (0) X minutes ago`, etc.  |
| `PORTS`        | Port mappings (e.g. `0.0.0.0:8080->80/tcp`)       |
| `NAMES`        | The container's name (auto-generated or `--name`) |

**Notes:**

- `docker container ls` is the modern form — identical to `docker ps`.
- `docker ps -aq` is one of the most useful combos: quiet + all gives you a plain list of every container ID on the host, perfect for bulk operations like `docker rm $(docker ps -aq)`.
- The `STATUS` field is your first debugging clue — `Exited (1)` means the process crashed; `Exited (0)` means it finished cleanly.
- `docker inspect <container>` gives the full JSON config when `ps` doesn't show enough detail.

### How to Name or Rename a Container

**Description:** Every container gets a name — either one you choose with `--name` at creation, or a random two-word name Docker generates (e.g. `pensive_euler`). A meaningful name lets you reference the container by name in every subsequent command instead of hunting for its ID. If you forgot to set a name, `docker rename` fixes that without stopping the container.

**Syntax:**

```bash
# Set a name at creation
docker run --name <name> [options] <image>

# Rename an existing container (running or stopped)
docker rename <old-name> <new-name>
```

**Examples:**

```bash
# Give the container a clear name up front
docker run -d -p 8080:80 --name web nginx

# Rename a container that was created without --name
docker rename pensive_euler web

# Rename a running container — no restart needed
docker run -d --name temp-db postgres:16-alpine
docker rename temp-db primary-db

# Confirm the new name
docker ps --filter name=primary-db
```

**Naming Rules:**

| Rule               | Detail                                                  |
| ------------------ | ------------------------------------------------------- |
| Characters allowed | Letters, digits, underscores `_`, hyphens `-`, dots `.` |
| Case sensitive     | `Web` and `web` are different names                     |
| Must be unique     | Two containers on the same host cannot share a name     |
| No spaces          | Use `-` or `_` as word separators                       |

**Notes:**

- Names must be unique per Docker host — trying to reuse a name raises an error. Remove or rename the old container first.
- `docker rename` works on running containers; the process inside is not interrupted.
- If you omit `--name`, Docker picks a random adjective-noun pair. These are memorable but meaningless — always name containers you plan to reference again.
- You can reference a container by its full ID, short ID (first 12 chars), or name interchangeably in any Docker command.

### How to Stop or Kill a Running Container

**Description:** Docker gives you two ways to shut a container down. `docker stop` is the polite option — it sends **SIGTERM** to the main process, waits up to 10 seconds for it to exit cleanly, then sends **SIGKILL** if it hasn't stopped. `docker kill` skips the waiting and sends **SIGKILL** (or any signal you choose) immediately. Use `stop` by default; reach for `kill` only when a container is unresponsive.

**Syntax:**

```bash
docker stop [options] <container> [<container>...]
docker kill [options] <container> [<container>...]
```

**Common Options:**

| Option           | Command       | Description                                          |
| ---------------- | ------------- | ---------------------------------------------------- |
| `-t, --time <n>` | `docker stop` | Seconds to wait before sending SIGKILL (default: 10) |
| `-s, --signal`   | `docker kill` | Signal to send instead of SIGKILL (e.g. `-s SIGINT`) |

**Examples:**

```bash
# Graceful stop — gives the app time to flush state and close connections
docker stop web

# Shorten the grace period to 3 seconds
docker stop -t 3 web

# Stop multiple containers at once
docker stop web db cache

# Stop every running container on the host
docker stop $(docker ps -q)

# Immediately kill an unresponsive container
docker kill web

# Send a specific signal instead of SIGKILL
docker kill -s SIGINT web

# Verify the container is stopped
docker ps -a --filter name=web
```

**`stop` vs `kill` — when to use which:**

| Scenario                                     | Use              |
| -------------------------------------------- | ---------------- |
| Normal shutdown — app should clean up        | `docker stop`    |
| Container is frozen / not responding to stop | `docker kill`    |
| Database or message broker (needs flush)     | `docker stop`    |
| Quick teardown in a dev/test script          | `docker kill`    |
| Sending a custom signal (e.g. SIGHUP)        | `docker kill -s` |

**Notes:**

- A stopped container still exists on disk — its filesystem and config are preserved. Use `docker start` to bring it back, or `docker rm` to delete it.
- `docker stop` waits **10 seconds** by default. If your app needs more time (e.g. a database with a large write buffer), increase the timeout: `docker stop -t 30 db`.
- `docker kill` does **not** guarantee data integrity — avoid it for databases or any process that writes to disk.
- Stopping a container created with `--rm` automatically removes it — there's nothing left to inspect or restart.

### How to Restart a Container

**Description:** `docker restart` stops a container and starts it again in a single command — equivalent to `docker stop` followed by `docker start`. It's useful for picking up config changes, recovering from a stuck process, or bouncing a service after updating an env var. The container keeps its name, port bindings, volumes, and all original `docker run` options.

**Syntax:**

```bash
docker restart [options] <container> [<container>...]
```

**Common Options:**

| Option           | Description                                                    |
| ---------------- | -------------------------------------------------------------- |
| `-t, --time <n>` | Seconds to wait for graceful stop before forcing (default: 10) |

**Examples:**

```bash
# Restart a single container
docker restart web

# Restart with a shorter grace period
docker restart -t 5 web

# Restart multiple containers at once
docker restart web db cache

# Restart every running container on the host
docker restart $(docker ps -q)

# Start a stopped container (first time after docker stop)
docker start web

# Confirm the container came back up
docker ps --filter name=web
```

**`docker restart` vs `docker start`:**

| Command          | Use when                                               |
| ---------------- | ------------------------------------------------------ |
| `docker restart` | Container is **running** and you want to bounce it     |
| `docker start`   | Container is **stopped** and you want to bring it back |

**Notes:**

- `docker restart` re-reads nothing from the image — it restarts the same container with the same config. To pick up image changes, you need `docker run` (or `docker compose up --build`).
- The `-t` timeout controls the stop phase only; start is always immediate.
- Restart policies (`--restart always`, `--restart unless-stopped`, etc.) set on `docker run` control **automatic** restarts — `docker restart` is the manual equivalent.
- After a restart the container gets a new start time but keeps the same ID, name, and volumes.

### How to Create a Container Without Running

**Description:** `docker create` builds a container from an image and configures it — allocating a writable layer, setting up networking and volumes — but does **not** start the process. The container sits in `Created` state until you explicitly call `docker start`. This is useful when you want to stage a container, pre-pull its image, or inspect it before it ever runs.

**Syntax:**

```bash
docker create [options] <image> [command]
```

`docker create` accepts the same options as `docker run` (except `-d`, since the container doesn't start).

**Examples:**

```bash
# Create a container without starting it
docker create --name web -p 8080:80 nginx

# Verify it exists in "Created" state
docker ps -a --filter name=web

# Start it when you're ready
docker start web

# Create and immediately inspect before starting
docker create --name db \
  -e POSTGRES_PASSWORD=secret \
  -v db-data:/var/lib/postgresql/data \
  postgres:16-alpine
docker inspect db

# Start the database
docker start db

# Stream its logs once it's running
docker logs -f db
```

**`docker create` vs `docker run`:**

| Aspect          | `docker create`                        | `docker run`                            |
| --------------- | -------------------------------------- | --------------------------------------- |
| Starts process? | No — stays in `Created` state          | Yes — container starts immediately      |
| Start manually? | Yes — `docker start <name>`            | Not needed                              |
| Use case        | Stage, inspect, or pre-pull before run | Default for all everyday container work |

**Notes:**

- `docker create` is effectively the first half of `docker run` — under the hood `docker run` calls `docker create` then `docker start`.
- The container ID returned by `docker create` is the same ID you'll see in `docker ps -a` and use with `docker start`.
- All volume mounts and port bindings are configured at create time; you cannot change them without removing and recreating the container.
- Rarely needed in day-to-day work — `docker run -d` covers most use cases. It shines in scripted pipelines where you want to set up a container ahead of time.

### How to Remove Dangling Containers

**Description:** Every time you run or create a container without `--rm`, it lingers on disk after it stops — occupying space and cluttering `docker ps -a`. These leftover stopped containers are sometimes called **dangling containers**. `docker rm` removes one or more by name or ID; `docker container prune` sweeps away all stopped containers at once.

**Syntax:**

```bash
# Remove one or more specific containers
docker rm <container> [<container>...]

# Remove all stopped containers
docker container prune
```

**Common Options:**

| Option          | Command                  | Description                                             |
| --------------- | ------------------------ | ------------------------------------------------------- |
| `-f, --force`   | `docker rm`              | Force-remove a **running** container (stop + remove)    |
| `-v, --volumes` | `docker rm`              | Also remove anonymous volumes attached to the container |
| `-f, --force`   | `docker container prune` | Skip the confirmation prompt                            |
| `--filter`      | `docker container prune` | Prune only containers matching a condition              |

**Examples:**

```bash
# Remove a single stopped container
docker rm web

# Remove multiple containers at once
docker rm web db cache

# Force-remove a running container without stopping it first
docker rm -f web

# Remove a container and its anonymous volumes
docker rm -v web

# Remove every stopped container (interactive confirmation)
docker container prune

# Prune without confirmation — safe for scripts
docker container prune -f

# Prune only containers that exited more than 24 hours ago
docker container prune --filter "until=24h"

# One-liner: remove all exited containers using docker ps
docker rm $(docker ps -aq --filter status=exited)

# Nuclear option: remove everything not currently running
docker container prune -f && docker volume prune -f
```

**`docker rm` vs `docker container prune`:**

| Command                                   | Removes                                | Requires name/ID? |
| ----------------------------------------- | -------------------------------------- | ----------------- |
| `docker rm <name>`                        | The specific container(s) you name     | Yes               |
| `docker rm $(docker ps -aq --filter ...)` | Containers matching a filter           | No (scripted)     |
| `docker container prune`                  | **All** stopped containers on the host | No                |

**Notes:**

- A running container cannot be removed without `-f`. Stop it first with `docker stop`, or use `docker rm -f` for a combined stop-and-remove.
- `docker rm -v` removes only **anonymous** volumes — named volumes (`-v my-vol:/data`) are always kept unless you explicitly run `docker volume rm my-vol`.
- `--rm` on `docker run` is the cleanest approach: the container deletes itself the moment it exits, so there's nothing to clean up later.
- `docker system prune` is the broadest cleanup — it removes stopped containers, dangling images, unused networks, and (with `-a --volumes`) everything unused in one command.

### How to Run a Container in Interactive Mode

**Description:** By default a container runs non-interactively — its stdin is closed and there is no terminal. The `-it` flag pair opens an interactive session: `-i` keeps stdin open so you can type, and `-t` allocates a pseudo-TTY so prompts, colours, and cursor movement render correctly. Together they let you open a shell or REPL directly inside a fresh container.

**Syntax:**

```bash
docker run -it [options] <image> [shell]
```

**Flags explained:**

| Flag  | Full name       | What it does                                         |
| ----- | --------------- | ---------------------------------------------------- |
| `-i`  | `--interactive` | Keep stdin open even when not attached               |
| `-t`  | `--tty`         | Allocate a pseudo-TTY (terminal emulator)            |
| `-it` | Both together   | The standard combo for any interactive shell session |

**Examples:**

```bash
# Open a bash shell inside Ubuntu — feel free to explore
docker run -it ubuntu bash

# Alpine ships sh, not bash
docker run -it alpine sh

# Start interactive, auto-remove on exit
docker run --rm -it node:20-alpine sh

# Interactive with a working directory set
docker run --rm -it -w /app node:20-alpine sh

# Interactive with an env var passed in
docker run --rm -it -e APP_ENV=dev python:3.12-slim bash

# Mount the current folder and open a shell for live dev work
docker run --rm -it -v $(pwd):/app -w /app node:20-alpine sh
```

**Notes:**

- Always pair `-i` and `-t` together — `-i` alone gives you input but no formatted output; `-t` alone gives you a TTY but stdin is closed so you can't type.
- To exit the shell without stopping the container, use `Ctrl-P Ctrl-Q` (detach). Typing `exit` or pressing `Ctrl-D` terminates the shell process and stops the container.
- On minimal images like `alpine`, `busybox`, or `distroless`, `bash` may not be installed — use `sh` instead.
- `-it` is incompatible with `-d` (detached mode) — you can't have an interactive foreground session and run in the background at the same time.

### How to Execute Commands Inside a Container

**Description:** `docker exec` runs a new command inside an **already-running** container. Unlike `docker run` (which creates a new container), `exec` reaches into an existing one without disturbing the main process. It's the go-to tool for debugging, inspecting state, and running one-off admin tasks inside a live container.

**Syntax:**

```bash
docker exec [options] <container> <command> [args...]
```

**Common Options:**

| Option          | Description                                            |
| --------------- | ------------------------------------------------------ |
| `-it`           | Interactive + TTY — required for opening a shell       |
| `-d, --detach`  | Run the command in the background inside the container |
| `-e, --env`     | Set an env var for this command only: `-e DEBUG=true`  |
| `-u, --user`    | Run as a specific user: `-u root` or `-u 1000`         |
| `-w, --workdir` | Set the working directory for the command              |

**Examples:**

```bash
# Open an interactive shell inside a running container
docker exec -it web bash

# Alpine/minimal images — use sh instead of bash
docker exec -it web sh

# Run a one-off command without opening a shell
docker exec web ls /etc/nginx/conf.d

# Check running processes inside the container
docker exec web ps aux

# Run a psql query inside a Postgres container
docker exec -it db psql -U postgres -c '\l'

# Run a command as root even if the container uses a non-root user
docker exec -u root -it web bash

# Set an env var just for this exec session
docker exec -e DEBUG=true -it web node debug.js

# Check an env variable inside the container
docker exec web env | grep NODE_ENV
```

**`docker exec` vs `docker run`:**

| Aspect           | `docker exec`                            | `docker run`                                  |
| ---------------- | ---------------------------------------- | --------------------------------------------- |
| Target           | An **existing, running** container       | Creates a **brand-new** container             |
| Main process     | Untouched — runs alongside it            | The command you pass becomes the main process |
| Stops container? | No — exec exits, container keeps running | Container stops when the command exits        |
| Use case         | Debug, inspect, admin tasks              | Start a fresh container from an image         |

**Notes:**

- If the container has no `bash`, try `sh` — Alpine and other minimal images skip bash to save space.
- `docker exec` only works on **running** containers. If the container is stopped, start it first with `docker start`.
- Exit the exec shell with `exit` or `Ctrl-D` — this closes the exec session only; the main container process keeps running.
- Avoid using `docker exec` to make permanent changes inside a container — those changes live only in the writable layer and are lost when the container is removed. Put changes in the Dockerfile instead.

### How to Work With Executable Images

**Description:** Some images are designed to behave like a standalone CLI tool rather than a long-running service. They achieve this by setting `ENTRYPOINT` to the binary in their Dockerfile — so the image name effectively becomes the command, and anything you pass after `docker run <image>` becomes arguments to that binary. Common examples include `alpine`, `busybox`, `curl`, compiler images, and custom tooling images.

**Syntax:**

```bash
# Arguments after the image name are passed to the ENTRYPOINT
docker run [options] <image> [arguments]

# Override the entrypoint entirely
docker run --entrypoint <binary> <image> [arguments]
```

**Examples:**

```bash
# Run a one-off curl request using the curlimages/curl image
docker run --rm curlimages/curl curl https://example.com

# Use alpine as a throwaway shell environment
docker run --rm -it alpine sh

# Run a Python script without installing Python locally
docker run --rm -v $(pwd):/app -w /app python:3.12-slim python script.py

# Compile a Go binary using the official Go image
docker run --rm -v $(pwd):/src -w /src golang:1.22-alpine go build -o app .

# Use Node as a REPL without a local installation
docker run --rm -it node:20-alpine node

# Pass arguments directly to the entrypoint (e.g. ping image)
docker run --rm alpine ping -c 3 google.com

# Override the entrypoint to get a shell instead of the default command
docker run --rm --entrypoint sh alpine

# Check what entrypoint an image defines
docker inspect --format '{{.Config.Entrypoint}}' nginx
```

**How `ENTRYPOINT` and `CMD` combine:**

| Dockerfile                                | `docker run` invocation        | Command that runs        |
| ----------------------------------------- | ------------------------------ | ------------------------ |
| `ENTRYPOINT ["curl"]`                     | `docker run img https://x.com` | `curl https://x.com`     |
| `ENTRYPOINT ["node"]` `CMD ["server.js"]` | `docker run img`               | `node server.js`         |
| `ENTRYPOINT ["node"]` `CMD ["server.js"]` | `docker run img worker.js`     | `node worker.js`         |
| `CMD ["nginx", "-g", "daemon off;"]`      | `docker run img`               | `nginx -g "daemon off;"` |

**Notes:**

- `CMD` sets default arguments that can be replaced by anything you type after the image name. `ENTRYPOINT` sets the fixed binary; only `--entrypoint` can override it.
- Always add `--rm` for one-shot tool containers — there's no reason to keep them around after the command finishes.
- Executable images pair naturally with shell aliases. For example, `alias curl='docker run --rm curlimages/curl curl'` gives you a containerised `curl` that works like the system one.
- `docker inspect --format '{{.Config.Entrypoint}}' <image>` reveals what the image runs by default before you commit to a `docker run` invocation.

---

## Image Basics

Everything you do with the images themselves — pulling from a registry, listing them locally, building your own, and pushing them back.

### One Shot Revision

| Command                                                                           | Short Description                                                   |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `docker pull`                                                                     | Download an image from a registry                                   |
| [`docker image ls`](#how-to-list-and-remove-docker-images)                        | List local images                                                   |
| `docker image build`                                                              | Build an image from a Dockerfile                                    |
| [`docker image tag`](#how-to-tag-docker-images)                                   | Give an image an additional name/tag                                |
| `docker push`                                                                     | Upload an image to a registry                                       |
| [`docker image rm` / `prune`](#how-to-list-and-remove-docker-images)              | Delete images                                                       |
| [`docker image history`](#how-to-understand-the-many-layers-of-a-docker-image)    | Show layer history of an image                                      |
| [Build NGINX from Source](#how-to-build-nginx-from-source)                        | Compile NGINX from source inside a Dockerfile                       |
| [Optimize Docker Images](#how-to-optimize-docker-images)                          | Techniques to shrink image size and speed up builds                 |
| [Embracing Alpine Linux](#embracing-alpine-linux)                                 | Why Alpine is the default small base and how to use it              |
| [How to Create Executable Docker Images](#how-to-create-executable-docker-images) | Build images that behave like standalone CLI tools via `ENTRYPOINT` |
| [How to Share Your Docker Images Online](#how-to-share-your-docker-images-online) | Push images to Docker Hub and other registries for sharing          |

### How to Create a Docker Image

Creating and publishing a Docker image follows a four-step workflow: **write a Dockerfile → build → tag → push**. Pulling and cleanup are covered at the end.

#### Step 1 — Write a Dockerfile

A `Dockerfile` is the plain-text recipe Docker reads to assemble the image. At minimum it needs a base image, your app files, and a start command.

```dockerfile
FROM node:20-alpine

WORKDIR /app

# Copy manifests first — keeps npm install cached between builds
COPY package*.json ./
RUN npm ci --omit=dev

COPY . .

EXPOSE 3000
CMD ["node", "server.js"]
```

See [Dockerfile Instructions](#dockerfile-instructions) for the full instruction reference.

#### Step 2 — Build the image

```bash
docker build -t my-app:1.0 .
```

| Option                | What it does                                                       |
| --------------------- | ------------------------------------------------------------------ |
| `-t my-app:1.0`       | Name and tag the resulting image                                   |
| `.`                   | Build context — the folder Docker packages and sends to the daemon |
| `-f Dockerfile.prod`  | Use a differently named Dockerfile                                 |
| `--no-cache`          | Ignore all cached layers and rebuild from scratch                  |
| `--build-arg KEY=val` | Pass a value for an `ARG` declared in the Dockerfile               |

Verify the image appeared locally:

```bash
docker image ls
# docker images          ← shorter alias, same output

docker image ls -q                          # just IDs, useful for scripting
docker image ls --filter dangling=true      # show untagged (dangling) layers
```

> Add a `.dockerignore` beside your Dockerfile to exclude `node_modules`, `.git`, `.env`, etc. from the build context — it keeps builds fast and avoids leaking secrets.

#### Step 3 — Tag for a registry

A tag is just a label; it never copies data. Before pushing, the image name must match the registry path:

- **Docker Hub:** `<username>/<repo>:<tag>`
- **GHCR:** `ghcr.io/<owner>/<repo>:<tag>`

```bash
# Prepare for Docker Hub
docker image tag my-app:1.0 tahshinsharon/my-app:1.0

# Prepare for GitHub Container Registry
docker image tag my-app:1.0 ghcr.io/tahshinsharon/my-app:1.0

# Add a floating "latest" alias
docker image tag my-app:1.0 my-app:latest
```

#### Step 4 — Push to the registry

```bash
docker login                                  # one-time interactive login
docker push tahshinsharon/my-app:1.0
```

Anyone (or any server) can now pull it:

```bash
docker pull tahshinsharon/my-app:1.0

# Pull from GHCR
docker pull ghcr.io/tahshinsharon/my-app:1.0

# If you omit the tag, Docker assumes :latest — pin versions in production
docker pull nginx:1.27-alpine
```

> `docker run` auto-pulls if the image isn't local, so an explicit `docker pull` is only needed when you want to pre-fetch or update.

#### Clean up

```bash
# Remove a specific image (container must be stopped/removed first)
docker image rm my-app:1.0

# Remove dangling (untagged) layers
docker image prune

# Remove every image not referenced by any container
docker image prune -a

# Nuclear option — images + stopped containers + unused networks + volumes
docker system prune -a --volumes
```

### How to Tag Docker Images

A **tag** is just a pointer — a human-readable label attached to an image ID. The same image can carry multiple tags simultaneously, and tagging never copies image data.

#### Tag anatomy

```
[registry/][username/]repository:tag
```

| Part         | Example                                                | Default if omitted |
| ------------ | ------------------------------------------------------ | ------------------ |
| `registry`   | `ghcr.io`, `123456789.dkr.ecr.us-east-1.amazonaws.com` | Docker Hub         |
| `username`   | `tahshinsharon`                                        | —                  |
| `repository` | `my-app`                                               | —                  |
| `tag`        | `1.0`, `stable`, `latest`                              | `latest`           |

#### Syntax

```bash
docker image tag <source-image>[:<tag>] <target-image>[:<tag>]
```

If the source tag is omitted, Docker assumes `:latest`.

#### Common patterns

**Semantic versioning** — tag the same build at multiple levels of precision so consumers can pin as tightly or loosely as they like:

```bash
docker image tag my-app:1.2.3 my-app:1.2
docker image tag my-app:1.2.3 my-app:1
docker image tag my-app:1.2.3 my-app:latest
```

**Prepare for Docker Hub:**

```bash
docker image tag my-app:1.0 tahshinsharon/my-app:1.0
docker image tag my-app:1.0 tahshinsharon/my-app:latest
```

**Prepare for GitHub Container Registry (GHCR):**

```bash
docker image tag my-app:1.0 ghcr.io/tahshinsharon/my-app:1.0
```

**Prepare for AWS ECR:**

```bash
docker image tag my-app:1.0 123456789.dkr.ecr.us-east-1.amazonaws.com/my-app:1.0
```

#### Remove a tag

`docker image rm` on a specific `name:tag` removes only that label. The underlying layers are deleted only when the last tag pointing to them is removed.

```bash
docker image rm my-app:1.2      # removes tag; layers survive if other tags remain
docker image rm my-app:1.2.3    # removes tag; layers deleted if this was the last reference
```

#### Notes

- `:latest` is a convention, not a guarantee of freshness — always pin exact versions in production Dockerfiles and `docker run` commands.
- Tags are mutable: pushing a new image under the same tag silently replaces it in the registry. Use immutable digest references (`image@sha256:…`) when you need a hard guarantee.

### How to List and Remove Docker Images

#### Listing images

```bash
docker image ls
```

This is the primary command for inspecting what images exist on your machine. It shows repository name, tag, image ID, creation date, and size.

```bash
# Show all images (default view)
docker image ls

# Shorter alias — identical output
docker images

# Only image IDs — useful for scripting bulk operations
docker image ls -q

# Filter to a specific repository
docker image ls my-app

# Show dangling images (untagged layers left over from rebuilds)
docker image ls --filter dangling=true

# Show images created before / since a reference image
docker image ls --filter before=my-app:1.0
docker image ls --filter since=my-app:1.0

# Custom output columns
docker image ls --format "table {{.Repository}}\t{{.Tag}}\t{{.Size}}"
```

**What dangling images are:** when you rebuild an image with the same tag, the old layers lose their tag but remain on disk. They show up as `<none>:<none>` in `docker image ls`. They waste disk space and can be safely removed.

#### Inspecting an image

```bash
# Full metadata (OS, architecture, layers, env vars, entrypoint …)
docker image inspect my-app:1.0

# Flatten to a single field with Go templates
docker image inspect my-app:1.0 --format "{{.Os}}/{{.Architecture}}"

# See the layer history and sizes
docker image history my-app:1.0
```

#### Removing images

```bash
# Remove one image by name:tag
docker image rm my-app:1.0

# Remove using the image ID (first few chars are enough)
docker image rm a1b2c3d4

# Remove multiple images in one command
docker image rm my-app:1.0 my-app:2.0 nginx:alpine

# Force-remove even if a stopped container still references it
docker image rm -f my-app:1.0
```

> If a **running** container uses the image, removal will always fail — stop and remove the container first.

#### Bulk cleanup

| Command                                      | What it removes                                         |
| -------------------------------------------- | ------------------------------------------------------- |
| `docker image prune`                         | Dangling images only (`<none>:<none>`)                  |
| `docker image prune -a`                      | Every image not used by at least one container          |
| `docker image prune -a --filter "until=24h"` | Unused images older than 24 hours                       |
| `docker system prune -a --volumes`           | Images + stopped containers + unused networks + volumes |

```bash
# Dry-run style: see what prune would delete before committing
docker image ls --filter dangling=true

# Then prune dangling only
docker image prune

# Or nuke all unused images
docker image prune -a
```

### How to Understand the Many Layers of a Docker Image

A Docker image is not a single flat file — it is a **stack of read-only layers**, each produced by one instruction in the Dockerfile. Understanding layers explains why builds are fast, why images share disk space, and what actually changes when a container runs.

#### What a layer is

Every `RUN`, `COPY`, and `ADD` instruction in a Dockerfile produces a new layer. Instructions that only set metadata (`ENV`, `EXPOSE`, `CMD`, `LABEL`, etc.) add zero-byte metadata layers that do not contribute to the image size in a meaningful way.

```
Image: my-app:1.0
│
├── Layer 4 — COPY . .                     (your source files)
├── Layer 3 — RUN npm ci --omit=dev        (installed node_modules)
├── Layer 2 — COPY package*.json ./        (package manifests)
├── Layer 1 — WORKDIR /app                 (directory creation)
└── Layer 0 — FROM node:20-alpine          (the base image, itself many layers)
```

Each layer stores only the **diff** — files that were added, changed, or deleted relative to the layer below. The final image is the union of all layers read from bottom to top.

#### The writable container layer

When Docker starts a container from an image, it adds a thin **writable layer** on top of the read-only image stack using a copy-on-write (CoW) strategy.

| Layer type      | Read/Write | Persists after container stops? |
| --------------- | ---------- | ------------------------------- |
| Image layers    | Read-only  | Yes — unchanged, shared         |
| Container layer | Read-write | No — deleted with the container |

- Reading a file: served directly from whichever image layer owns it — zero copying.
- Writing or modifying a file: Docker copies it up to the writable container layer first, then applies the modification. The image layer is untouched.
- Deleting a file: a _whiteout_ entry is written to the container layer, masking the file from lower layers.

This is why a large image does not make each container large — many containers can share the same read-only image layers simultaneously.

#### Inspecting layers

**View layer history and sizes:**

```bash
docker image history my-app:1.0
```

```
IMAGE          CREATED        CREATED BY                                      SIZE
a1b2c3d4e5f6   2 hours ago    COPY . . # buildkit                             8.5MB
<missing>      2 hours ago    RUN npm ci --omit=dev                           42MB
<missing>      2 hours ago    COPY package*.json ./                            12kB
<missing>      2 hours ago    WORKDIR /app                                     0B
<missing>      3 weeks ago    /bin/sh -c #(nop)  CMD ["node"]                 0B
```

- `SIZE` shows how much each layer contributes on top of the ones below it.
- `<missing>` in IMAGE ID is normal for intermediate layers — they are identified by digest internally.

**View layer digests:**

```bash
docker image inspect my-app:1.0 --format '{{json .RootFS.Layers}}'
```

Each digest (`sha256:…`) uniquely identifies a layer. Two images that share the same digest for a layer share exactly the same bytes on disk.

**See layers being fetched during a pull:**

```bash
docker pull node:20-alpine
```

```
20-alpine: Pulling from library/node
1a1b4b8f3c2d: Pull complete      # base OS layer
7f8e2d6a9c1b: Pull complete      # Node.js runtime
Digest: sha256:...
Status: Downloaded newer image for node:20-alpine
```

Each line corresponds to one layer. Layers already present locally are skipped (`Already exists`), which is why pulling a second Node-based image is almost instant.

#### Layer caching in builds

Docker caches each layer. On a subsequent `docker build`, every layer whose instruction **and its inputs** are unchanged is reused from cache — that instruction is skipped entirely.

**Cache is invalidated from the changed layer downward.** This is why the order of instructions matters:

```dockerfile
# Good — dependencies cached separately from source code
COPY package*.json ./
RUN npm ci --omit=dev      # ← cached unless package.json changed
COPY . .                   # ← only this layer and below rebuild on code change
```

```dockerfile
# Bad — any code change busts the npm install cache
COPY . .
RUN npm ci --omit=dev      # ← always reruns, even for a one-line README change
```

**Force a full rebuild (bypass cache):**

```bash
docker build --no-cache -t my-app:1.0 .
```

#### Practical implications

| Goal              | What to do                                                                                    |
| ----------------- | --------------------------------------------------------------------------------------------- |
| Smaller images    | Chain related `RUN` commands with `&&` — one layer instead of many                            |
| Faster builds     | Put rarely-changing instructions (install deps) before frequently-changing ones (copy source) |
| Smaller images    | Use a `.dockerignore` file to exclude large or secret files from the build context            |
| Production safety | Avoid writing secrets in `RUN` layers — they persist in the layer even if deleted later       |

### How to Build NGINX from Source

**Description:** Compiling NGINX from source inside a Dockerfile is a hands-on exercise that ties together everything in Image Basics — writing a Dockerfile, managing layers, installing build dependencies, and producing a working custom binary. It is also a real production pattern: building from source lets you enable non-default modules, apply custom patches, or pin an exact upstream commit.

#### The Dockerfile

```dockerfile
FROM ubuntu:22.04

# Install build dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        libpcre3 \
        libpcre3-dev \
        zlib1g \
        zlib1g-dev \
        libssl-dev \
        wget && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Download, compile, and install NGINX — all in one layer
ARG NGINX_VERSION=1.26.1
RUN wget http://nginx.org/download/nginx-${NGINX_VERSION}.tar.gz && \
    tar -xzf nginx-${NGINX_VERSION}.tar.gz && \
    cd nginx-${NGINX_VERSION} && \
    ./configure \
        --sbin-path=/usr/bin/nginx \
        --conf-path=/etc/nginx/nginx.conf \
        --error-log-path=/var/log/nginx/error.log \
        --http-log-path=/var/log/nginx/access.log \
        --pid-path=/var/run/nginx.pid \
        --with-http_ssl_module && \
    make && make install && \
    cd .. && rm -rf nginx-${NGINX_VERSION} nginx-${NGINX_VERSION}.tar.gz

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

**What `./configure` flags do:**

| Flag                                   | Purpose                                         |
| -------------------------------------- | ----------------------------------------------- |
| `--sbin-path`                          | Where the compiled `nginx` binary lands         |
| `--conf-path`                          | Path to the main configuration file             |
| `--error-log-path` / `--http-log-path` | Log file locations                              |
| `--pid-path`                           | Where NGINX writes its process ID               |
| `--with-http_ssl_module`               | Enable TLS support (not compiled in by default) |

#### Build and run

```bash
# Build with the default version baked into ARG
docker build -t nginx-from-source:1.0 .

# Override the NGINX version at build time — no Dockerfile edit needed
docker build --build-arg NGINX_VERSION=1.27.0 -t nginx-from-source:1.27 .

# Run and verify
docker run -d -p 8080:80 --name web nginx-from-source:1.0
curl http://localhost:8080

# Check the compiled version
docker exec web nginx -v
```

**Notes:**

- Chaining the download, compile, and cleanup into **one `RUN` instruction** is critical. Splitting them across multiple `RUN` commands would leave the tarball and extracted source tree baked into separate layers, permanently inflating the image size.
- `apt-get clean && rm -rf /var/lib/apt/lists/*` must run in the **same** `RUN` as the `apt-get install` — deleting files in a later layer only adds a whiteout entry; the bytes from the install layer are never reclaimed.
- `ARG NGINX_VERSION=1.26.1` provides a build-time variable with a sensible default. Pass a different version at build time with `--build-arg NGINX_VERSION=1.27.0` without touching the Dockerfile.
- For production, pair this with a **multi-stage build**: compile in a builder stage with all the dev libraries, then `COPY` only the compiled binary into a minimal runtime image — compilers and headers never ship to production.

### How to Optimize Docker Images

**Description:** A bloated image is slower to pull, uses more disk, and has a larger attack surface. Optimization is not a single technique — it is a set of habits applied at every layer of the Dockerfile. Most gains come from five areas: choosing the right base image, ordering instructions wisely, keeping layers clean, excluding junk from the build context, and using multi-stage builds.

#### 1. Choose a smaller base image

The base image is the floor — everything else stacks on top. Switching from a general-purpose OS to a purpose-built variant can cut hundreds of megabytes instantly.

| Base image             | Approximate size | When to use                                         |
| ---------------------- | ---------------- | --------------------------------------------------- |
| `ubuntu:22.04`         | ~80 MB           | Familiarity, apt packages                           |
| `debian:bookworm-slim` | ~75 MB           | Debian ecosystem, smaller than ubuntu               |
| `node:20-alpine`       | ~50 MB           | Alpine-based runtimes — most common choice          |
| `node:20-slim`         | ~80 MB           | Debian-slim, if Alpine causes compat issues         |
| `distroless/nodejs20`  | ~50 MB           | No shell, no package manager — production hardening |
| `scratch`              | 0 MB             | Statically compiled binaries only (Go, Rust)        |

```dockerfile
# Before — full Ubuntu base
FROM ubuntu:22.04

# After — Alpine-based Node, 5× smaller
FROM node:20-alpine
```

#### 2. Use multi-stage builds

Build tools (compilers, `make`, `gcc`, dev headers) belong in the build stage, not the runtime image. Multi-stage builds copy only the finished artifact.

```dockerfile
# Stage 1 — build
FROM node:20 AS builder
WORKDIR /build
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# Stage 2 — runtime (no dev dependencies, no source, no npm)
FROM node:20-alpine
WORKDIR /app
COPY --from=builder /build/dist ./dist
COPY --from=builder /build/node_modules ./node_modules
EXPOSE 3000
CMD ["node", "dist/index.js"]
```

The final image contains only the compiled output and production `node_modules` — the builder stage is discarded entirely.

#### 3. Chain `RUN` commands to minimize layers

Each `RUN` instruction creates a layer. Files deleted in a later layer still occupy space in the earlier layer. Chain related steps with `&&` so cleanup happens in the same layer as creation.

```dockerfile
# Bad — three layers; the apt cache bloat survives in layer 1
RUN apt-get update
RUN apt-get install -y curl
RUN rm -rf /var/lib/apt/lists/*

# Good — one layer; the cache never persists
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl && \
    apt-get clean && rm -rf /var/lib/apt/lists/*
```

Use `--no-install-recommends` with `apt-get` to skip optional packages you don't need.

#### 4. Order instructions by change frequency

Docker's build cache is invalidated **from the changed layer downward**. Instructions that rarely change belong at the top; instructions that change on every build belong at the bottom.

```dockerfile
# Good — dependency install is cached unless package.json changes
FROM node:20-alpine
WORKDIR /app
COPY package*.json ./        # changes rarely
RUN npm ci --omit=dev        # cached after first build
COPY . .                     # changes on every code edit
CMD ["node", "server.js"]

# Bad — any code change forces a fresh npm install
FROM node:20-alpine
WORKDIR /app
COPY . .                     # changes on every edit → cache busted here
RUN npm ci --omit=dev        # always reruns, even for a typo fix
CMD ["node", "server.js"]
```

#### 5. Use a `.dockerignore` file

The build context is everything Docker sends to the daemon before the build starts. Large or secret files in the context bloat the transfer and can leak into the image via `COPY . .`.

```
# .dockerignore
node_modules
.git
.env
*.log
dist
coverage
.vscode
Dockerfile
.dockerignore
```

Every file matched here is excluded from the context — it can never be `COPY`'d into the image, even accidentally.

#### Quick-reference optimization checklist

| Technique                                      | Impact                                           |
| ---------------------------------------------- | ------------------------------------------------ |
| Switch to Alpine or slim base                  | Large size reduction                             |
| Multi-stage build                              | Eliminates build tools and dev deps              |
| Chain `RUN` with `&&` + cleanup in same layer  | Removes layer bloat from installs                |
| `--no-install-recommends` on `apt-get install` | Skips optional packages                          |
| Order: stable deps → volatile source           | Keeps cache warm on rebuilds                     |
| `.dockerignore`                                | Shrinks build context; prevents accidental leaks |
| Pin exact image tags                           | Reproducible builds                              |

```bash
# See where the size is coming from
docker image history my-app:1.0

# Compare before and after optimization
docker image ls my-app
```

**Notes:**

- Run `docker image history <image>` to identify which layer is the biggest offender before optimizing — don't guess.
- `distroless` and `scratch` images have no shell, which means `docker exec -it ... sh` won't work. Plan for debugging with `docker cp` or a debug sidecar instead.
- Pinning tags (`node:20.14.0-alpine3.20` instead of `node:20-alpine`) locks the exact layer digest, making builds fully reproducible and immune to upstream surprises.
- `docker system df` shows total disk usage by images, containers, and volumes — run it before and after to confirm your optimizations actually reduced footprint.

### Embracing Alpine Linux

**Description:** Alpine Linux is a security-oriented, minimal Linux distribution built on **musl libc** and **BusyBox**. It is the most popular Docker base image for a reason — a bare `alpine` image is around **7 MB**, compared to ~80 MB for Ubuntu. Most official images ship an `-alpine` variant (`node:20-alpine`, `python:3.12-alpine`, `golang:1.22-alpine`), making Alpine the default choice whenever image size matters.

#### What makes Alpine different

| Aspect             | Alpine             | Debian / Ubuntu    |
| ------------------ | ------------------ | ------------------ |
| C library          | musl libc          | glibc              |
| Shell              | `sh` (BusyBox ash) | `bash`             |
| Package manager    | `apk`              | `apt-get`          |
| Base image size    | ~7 MB              | ~75–80 MB          |
| Default user tools | Minimal (BusyBox)  | Full GNU coreutils |

#### Using Alpine as a base

```dockerfile
FROM alpine:3.20

# Install packages with apk
RUN apk add --no-cache curl bash

CMD ["sh"]
```

The `--no-cache` flag tells `apk` not to store the index locally — you get the same effect as `apt-get clean && rm -rf /var/lib/apt/lists/*` in a single flag, with no extra cleanup step.

#### Common `apk` commands

| Command                                           | What it does                                     |
| ------------------------------------------------- | ------------------------------------------------ |
| `apk add --no-cache <pkg>`                        | Install a package without caching the index      |
| `apk add --no-cache --virtual .build-deps <pkgs>` | Install packages under a named group             |
| `apk del .build-deps`                             | Remove every package in that named group at once |
| `apk update && apk upgrade`                       | Refresh index and upgrade installed packages     |
| `apk search <term>`                               | Search the package index                         |
| `apk info <pkg>`                                  | Show details about an installed package          |

#### The virtual package pattern

Alpine's virtual packages are the idiomatic way to install build-time dependencies and remove them in the same layer:

```dockerfile
FROM alpine:3.20

# Install build tools under a named group, compile, then delete the group
RUN apk add --no-cache --virtual .build-deps \
        gcc musl-dev make && \
    # ... compile something ... && \
    apk del .build-deps
```

A single `apk del .build-deps` removes every package in the group without listing them individually. The compiled output stays; the compilers do not.

#### Alpine-tagged official images

```bash
# Pull the Alpine variant of popular images
docker pull node:20-alpine
docker pull python:3.12-alpine
docker pull golang:1.22-alpine
docker pull nginx:1.27-alpine
docker pull postgres:16-alpine

# Verify the size difference
docker image ls | grep alpine
```

#### Practical Dockerfile using Alpine

```dockerfile
FROM node:20-alpine

WORKDIR /app

COPY package*.json ./
RUN npm ci --omit=dev

COPY . .

EXPOSE 3000
CMD ["node", "server.js"]
```

This is the standard production Node.js pattern — Alpine base, dependency layer cached separately, source copied last.

**Notes:**

- **No `bash` by default.** Alpine ships `sh` (BusyBox ash). If your scripts require `bash`, either add `apk add --no-cache bash` or rewrite them for POSIX `sh`.
- **musl vs glibc.** A small number of native Node addons and Python C extensions are compiled against glibc and will fail on Alpine. If you hit this, switch to the `-slim` (Debian) variant instead.
- **`docker exec` into Alpine containers** uses `sh`, not `bash`: `docker exec -it <container> sh`.
- **`--no-cache` vs `apk update`:** running `apk update` without `--no-cache` leaves the package index on disk. Always use `--no-cache` (or delete `/var/cache/apk/*` in the same layer) to keep the image lean.
- Alpine versions are stable; pin the minor version (`alpine:3.20`) rather than `alpine:latest` to avoid silent OS upgrades breaking your build.

### How to Create Executable Docker Images

**Description:** An executable image behaves like a standalone CLI tool — the image name acts as the command, and anything you pass after `docker run <image>` becomes arguments to it. This is achieved by setting `ENTRYPOINT` to the binary in the Dockerfile. The pattern is common for custom tooling, script wrappers, and one-shot task runners where you want a repeatable, dependency-free execution environment.

#### How `ENTRYPOINT` makes an image executable

Without `ENTRYPOINT`, everything you pass to `docker run <image> <args>` replaces `CMD` entirely. With `ENTRYPOINT` set, the fixed binary always runs — your args are appended to it instead.

```
┌───────────────────────────────────────────────────────────────────┐
│  docker run my-tool --flag value                                  │
│                                                                   │
│  ENTRYPOINT ["my-tool"]   ← fixed; cannot be replaced by args    │
│  CMD        ["--default"] ← default args; replaced if you pass any│
│                                                                   │
│  Result: my-tool --flag value                                     │
└───────────────────────────────────────────────────────────────────┘
```

#### Building a simple executable image

Here is a custom `greet` tool as a worked example:

**`greet.sh`** — the script the image will run:

```bash
#!/bin/sh
NAME="${1:-World}"
echo "Hello, ${NAME}!"
```

**`Dockerfile`:**

```dockerfile
FROM alpine:3.20

COPY greet.sh /usr/local/bin/greet
RUN chmod +x /usr/local/bin/greet

ENTRYPOINT ["greet"]
CMD ["World"]
```

**Build and use it:**

```bash
docker build -t greet:1.0 .

# Uses the CMD default
docker run --rm greet:1.0
# → Hello, World!

# Replaces CMD with your own argument
docker run --rm greet:1.0 Alice
# → Hello, Alice!

# Override the ENTRYPOINT entirely
docker run --rm --entrypoint sh greet:1.0
```

#### Real-world executable image patterns

**Wrap a CLI tool (e.g. `curl`):**

```dockerfile
FROM alpine:3.20
RUN apk add --no-cache curl
ENTRYPOINT ["curl"]
CMD ["--help"]
```

```bash
docker build -t my-curl .
docker run --rm my-curl https://example.com
# equivalent to: curl https://example.com
```

**Shell alias shortcut — use any containerised tool as if it were installed locally:**

```bash
alias curl='docker run --rm my-curl'
curl https://example.com
```

**Wrap a Python script:**

```dockerfile
FROM python:3.12-alpine

WORKDIR /app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
COPY report.py ./

ENTRYPOINT ["python", "report.py"]
CMD ["--help"]
```

```bash
docker build -t report-tool:1.0 .

# Run with default --help
docker run --rm report-tool:1.0

# Pass real arguments
docker run --rm -v $(pwd)/data:/app/data report-tool:1.0 --input data/sales.csv
```

#### `ENTRYPOINT` forms — exec vs shell

Always prefer the **exec form** (`["binary", "arg"]`) for `ENTRYPOINT`. The shell form wraps the command in `sh -c`, which means signals like `SIGTERM` never reach your process — the shell absorbs them and the container hangs on `docker stop`.

| Form             | Syntax                         | Signal handling                                 |
| ---------------- | ------------------------------ | ----------------------------------------------- |
| Exec (preferred) | `ENTRYPOINT ["binary", "arg"]` | PID 1 = your binary, signals delivered directly |
| Shell (avoid)    | `ENTRYPOINT binary arg`        | PID 1 = `sh`, signals swallowed                 |

#### Discover what an image's entrypoint is

```bash
# Show the entrypoint and default command of any image
docker inspect --format '{{.Config.Entrypoint}}' nginx
docker inspect --format '{{.Config.Cmd}}' nginx

# Or pull both in one shot
docker inspect --format 'ENTRYPOINT={{.Config.Entrypoint}} CMD={{.Config.Cmd}}' nginx
```

**Notes:**

- `CMD` sets the default arguments. If the user passes anything after the image name, `CMD` is **completely replaced** — `ENTRYPOINT` is not.
- Use `--entrypoint` to bypass the fixed binary when you need to debug: `docker run --rm --entrypoint sh my-tool`.
- Executable images pair naturally with `--rm` — they run once and exit, leaving nothing behind.
- Mount volumes with `-v` to pass files in and get results out without baking data into the image: `docker run --rm -v $(pwd):/data my-tool /data/input.txt`.
- When the tool needs network access, omit `--network none` (the default `bridge` network is fine for outbound requests).

### How to Share Your Docker Images Online

**Description:** Once an image is built locally, sharing it means pushing it to a **container registry** — a hosted store where images live, versioned by tag. Docker Hub is the default public registry; others (GHCR, AWS ECR, Google Artifact Registry) are common in production. The workflow is always the same: **login → tag → push → pull**.

#### Registries at a glance

| Registry                         | Host prefix                                | Free tier                        |
| -------------------------------- | ------------------------------------------ | -------------------------------- |
| Docker Hub                       | _(none — default)_                         | 1 private repo, unlimited public |
| GitHub Container Registry (GHCR) | `ghcr.io`                                  | Free for public repos            |
| Amazon ECR                       | `<account>.dkr.ecr.<region>.amazonaws.com` | 500 MB free tier                 |
| Google Artifact Registry         | `<region>-docker.pkg.dev/<project>/<repo>` | 0.5 GB free                      |
| Self-hosted (Harbor, Gitea)      | your own domain                            | Unlimited                        |

#### Step 1 — Log in

```bash
# Docker Hub (prompts for username + password / access token)
docker login

# Docker Hub with explicit credentials
docker login -u tahshinsharon

# GitHub Container Registry
docker login ghcr.io -u tahshinsharon

# AWS ECR (uses AWS CLI to generate a temporary token)
aws ecr get-login-password --region us-east-1 \
  | docker login --username AWS --password-stdin \
    123456789.dkr.ecr.us-east-1.amazonaws.com
```

Use a **personal access token** instead of your account password — tokens can be scoped and revoked individually.

#### Step 2 — Tag the image for the registry

The image name must match the registry path before it can be pushed. Tagging never copies data — it only adds a new label to the existing image ID.

```bash
# Docker Hub — format: <username>/<repo>:<tag>
docker image tag my-app:1.0 tahshinsharon/my-app:1.0
docker image tag my-app:1.0 tahshinsharon/my-app:latest

# GitHub Container Registry — format: ghcr.io/<owner>/<repo>:<tag>
docker image tag my-app:1.0 ghcr.io/tahshinsharon/my-app:1.0

# AWS ECR — format: <account>.dkr.ecr.<region>.amazonaws.com/<repo>:<tag>
docker image tag my-app:1.0 123456789.dkr.ecr.us-east-1.amazonaws.com/my-app:1.0
```

#### Step 3 — Push

```bash
# Push to Docker Hub
docker push tahshinsharon/my-app:1.0
docker push tahshinsharon/my-app:latest

# Push to GHCR
docker push ghcr.io/tahshinsharon/my-app:1.0

# Push all tags for a repository at once
docker push --all-tags tahshinsharon/my-app
```

Docker uploads only the layers that don't already exist in the registry — layers shared with other images are skipped.

#### Step 4 — Pull from anywhere

```bash
# Pull from Docker Hub (short form — username/repo resolves to hub.docker.com)
docker pull tahshinsharon/my-app:1.0

# Pull from GHCR
docker pull ghcr.io/tahshinsharon/my-app:1.0

# Pull by digest instead of tag (immutable — never silently updated)
docker pull tahshinsharon/my-app@sha256:a1b2c3d4...

# docker run auto-pulls if the image isn't cached locally
docker run -d -p 3000:3000 tahshinsharon/my-app:1.0
```

#### Full end-to-end example

```bash
# 1. Build
docker build -t my-app:1.0 .

# 2. Tag for Docker Hub
docker image tag my-app:1.0 tahshinsharon/my-app:1.0

# 3. Login and push
docker login
docker push tahshinsharon/my-app:1.0

# 4. On any other machine — pull and run
docker run -d -p 3000:3000 tahshinsharon/my-app:1.0
```

#### Logging out

```bash
docker logout            # Docker Hub
docker logout ghcr.io    # GHCR
```

**Notes:**

- **Never push an image that contains secrets.** If a secret was written in a `RUN` layer it is baked in permanently — even if deleted in a later layer. Audit with `docker image history <image>` and rebuild cleanly.
- **`:latest` is mutable.** Pushing a new image under the same tag silently overwrites it in the registry. Pin exact versions (`1.0`, `1.2.3`) in production; use `:latest` only as a convenience alias.
- **Public images are public.** Any image pushed to a public Docker Hub repository is downloadable by anyone. Use private repositories or GHCR with package visibility set to private for proprietary code.
- **Digest-based pulls are immutable:** `docker pull image@sha256:…` always fetches the exact same bytes, regardless of what tag currently points to. Use them in production Kubernetes manifests for reproducibility.
- Log in with a **read-only access token** in CI pipelines — it limits blast radius if the token is ever leaked.

---

## How to Containerize a JavaScript Application

Containerizing a JavaScript application means packaging it — along with its Node.js runtime, dependencies, and configuration — into a Docker image so it runs identically on any host. The sections below cover the full workflow: from writing a development Dockerfile, through enabling hot reload with bind mounts, to shipping a lean production image with multi-stage builds.

### One Shot Revision

| Step | Action                                          | Key detail                                                                               |
| ---- | ----------------------------------------------- | ---------------------------------------------------------------------------------------- |
| 1    | Use `Dockerfile.dev` (not `Dockerfile`)         | Pass `--file Dockerfile.dev` to `docker build`                                           |
| 2    | Run as non-root                                 | `USER node` — the official `node` image ships a built-in non-root user                   |
| 3    | Copy `package.json` first                       | Keeps `npm install` layer cached until deps change                                       |
| 4    | Start the dev server                            | `CMD ["npm", "run", "dev"]`                                                              |
| 5    | Enable hot reload with a bind mount             | `--volume $(pwd):/home/node/app` syncs local source into the container                   |
| 6    | Protect `node_modules` with an anonymous volume | `--volume /home/node/app/node_modules` prevents the bind mount from overwriting it       |
| 7    | Build for production with multi-stage builds    | Stage 1: `node` builds the app; Stage 2: `nginx` serves the static output                |
| 8    | Exclude unnecessary files                       | `.dockerignore` prevents `.git`, `node_modules`, secrets from entering the build context |

### How to Write the Development Dockerfile

When containerizing a JavaScript application for development you need a Dockerfile that starts a hot-reload dev server rather than serving static production files. The example below is based on a [Vite](https://vitejs.dev/) project, but the pattern applies to any Node.js app that runs a dev server.

**Plan before you write:**

1. Pick a Node.js base image.
2. Set a non-root user for security.
3. Establish a working directory.
4. Copy `package.json` and install dependencies.
5. Copy the rest of the source.
6. Start the dev server with `npm run dev`.

**`Dockerfile.dev`:**

```dockerfile
FROM node:lts-alpine

EXPOSE 3000

USER node

RUN mkdir -p /home/node/app

WORKDIR /home/node/app

COPY ./package.json .
RUN npm install

COPY . .

CMD [ "npm", "run", "dev" ]
```

**Why each instruction is here:**

| Instruction                   | Reason                                                           |
| ----------------------------- | ---------------------------------------------------------------- |
| `FROM node:lts-alpine`        | Smallest official Node.js image with long-term support           |
| `USER node`                   | Runs as non-root — the `node` image ships a built-in `node` user |
| `RUN mkdir -p /home/node/app` | Creates the app directory under the node user's home             |
| `WORKDIR /home/node/app`      | All subsequent `COPY`, `RUN`, and `CMD` resolve relative to here |
| `COPY ./package.json .`       | Copied alone so `npm install` is cached until deps change        |
| `RUN npm install`             | Installs dependencies at build time                              |
| `COPY . .`                    | Copies the rest of the source after the cached layer             |
| `CMD ["npm", "run", "dev"]`   | Starts the dev server when the container launches                |
| `EXPOSE 3000`                 | Documents that the dev server listens on port 3000               |

Because the filename is `Dockerfile.dev` (not the default `Dockerfile`), pass it explicitly with `--file`:

```bash
docker image build --file Dockerfile.dev --tag hello-dock:dev .
```

Run the container and publish the port:

```bash
docker container run \
    --rm \
    --detach \
    --publish 3000:3000 \
    --name hello-dock-dev \
    hello-dock:dev
```

Visit `http://127.0.0.1:3000` to see the app.

**Enabling hot reload with bind mounts:**

The container runs a copy of your code baked into the image, so editing local files won't trigger the dev server to reload. Fix this by mounting your project root as a volume:

```bash
docker container run \
    --rm \
    --detach \
    --publish 3000:3000 \
    --name hello-dock-dev \
    --volume $(pwd):/home/node/app \
    --volume /home/node/app/node_modules \
    hello-dock:dev
```

The second `--volume` flag mounts an **anonymous volume** at `/home/node/app/node_modules`. Without it the bind mount would overwrite the `node_modules` installed during the build, breaking the dev server. Docker keeps the anonymous volume's content separate, so installed packages survive the bind mount.

### How to Work With Bind Mounts in Docker

A **bind mount** links a directory on your host machine directly into the container filesystem. Any edit you make locally is immediately visible inside the container — enabling the hot reload feature of your dev server.

**The problem without a bind mount:** the container runs a snapshot of your code baked in at build time. Local edits don't reach it, so the dev server never reloads.

**Syntax:**

```
--volume <host-absolute-path>:<container-absolute-path>[:<access>]
```

Add `:ro` at the end to make the mount read-only.

**Start the container with a bind mount:**

```bash
docker container run \
    --rm \
    --publish 3000:3000 \
    --name hello-dock-dev \
    --volume $(pwd):/home/node/app \
    hello-dock:dev
```

With this flag, every file save on your host is instantly reflected inside `/home/node/app`, triggering the Vite dev server's hot reload. Changes made inside the container also write back to your local filesystem.

> **Note:** Running this command as-is will fail — see [How to Work With Anonymous Volumes in Docker](#how-to-work-with-anonymous-volumes-in-docker) for why and how to fix it.

### How to Work With Anonymous Volumes in Docker

When you bind-mount the project root, Docker replaces the container's entire `/home/node/app` directory — including the `node_modules` folder that was installed during the build. The dev server can't find `vite` and crashes:

```
sh: 1: vite: not found
npm ERR! Failed at the hello-dock@0.0.0 dev script.
npm WARN Local package.json exists, but node_modules missing, did you mean to install?
```

An **anonymous volume** solves this. It tells Docker to "carve out" a specific path inside the container and manage its contents separately, so the bind mount can't overwrite it.

**Syntax:**

```
--volume <container-absolute-path>[:<access>]
```

No source path — Docker assigns a random ID and manages the directory on the host.

**Start the container with both volumes:**

```bash
docker container run \
    --rm \
    --detach \
    --publish 3000:3000 \
    --name hello-dock-dev \
    --volume $(pwd):/home/node/app \
    --volume /home/node/app/node_modules \
    hello-dock:dev
```

Docker takes the `node_modules` content built into the image, stores it in a daemon-managed location, then mounts it back at `/home/node/app/node_modules`. The bind mount covers everything else in `/home/node/app`, but `node_modules` is shadowed by the anonymous volume — so your installed packages are untouched and hot reload works correctly.

### How to Perform Multi-Staged Builds in Docker

In development the `npm run dev` command starts a Node.js server. In production, `npm run build` compiles the app into static HTML, CSS, and JavaScript files — and Node is no longer needed to serve them. A lightweight web server like **nginx** is enough, and it produces a much smaller image.

**Multi-stage builds** let you use a heavy build image in the first stage and copy only the output into a minimal runtime image in the second stage. The build tools never reach the shipped image.

**`Dockerfile` (production):**

```dockerfile
# ── Stage 1: build ──────────────────────────────
FROM node:lts-alpine as builder

WORKDIR /app

COPY ./package.json ./
RUN npm install

COPY . .
RUN npm run build

# ── Stage 2: runtime ────────────────────────────
FROM nginx:stable-alpine

EXPOSE 80

COPY --from=builder /app/dist /usr/share/nginx/html
```

**How it works:**

| Line                              | What it does                                                |
| --------------------------------- | ----------------------------------------------------------- |
| `FROM node:lts-alpine as builder` | Names the first stage `builder` so Stage 2 can reference it |
| `RUN npm run build`               | Compiles the app; output lands in `/app/dist`               |
| `FROM nginx:stable-alpine`        | Starts a fresh, tiny nginx image — no Node runtime included |
| `COPY --from=builder /app/dist …` | Pulls only the compiled files from the `builder` stage      |
| `EXPOSE 80`                       | nginx listens on port 80 by default                         |

**Build and run:**

```bash
docker image build --tag hello-dock:prod .

docker container run \
    --rm \
    --detach \
    --name hello-dock-prod \
    --publish 8080:80 \
    hello-dock:prod
```

Visit `http://127.0.0.1:8080` to see the production build served by nginx.

**Why it matters:** compilers, dev dependencies, and build tooling never touch the shipped image — the result is a smaller, faster, and more secure production container.

### How to Ignore Unnecessary Files

Just like `.gitignore` tells Git which files to exclude from a repository, a **`.dockerignore`** file tells Docker which files and directories to exclude from the **build context** — the set of files sent to the daemon when you run `docker build`.

Place the `.dockerignore` file in the same directory as your `Dockerfile`. A typical example for a JavaScript project:

```
.git
*Dockerfile*
*docker-compose*
node_modules
```

**What each entry does:**

| Entry              | Why exclude it                                                          |
| ------------------ | ----------------------------------------------------------------------- |
| `.git`             | Git history is irrelevant inside the image and adds significant size    |
| `*Dockerfile*`     | The build recipe itself doesn't belong in the image                     |
| `*docker-compose*` | Compose files are orchestration config, not app code                    |
| `node_modules`     | Dependencies are installed fresh during the build via `RUN npm install` |

**Two important rules:**

1. The `.dockerignore` file must be in the **build context directory** — Docker reads it before sending files to the daemon, so it can't be placed elsewhere.
2. `.dockerignore` only affects `COPY` and `ADD` instructions. It has **no effect on bind mounts** — files excluded here are still visible to a running container if you mount the host directory with `--volume`.

---

## Docker Networking

Containers talk to each other over Docker-managed networks. Docker creates a default network for you, but user-defined networks are usually a better choice.

### One Shot Revision

| Concept / Command                             | What it does                                                                          |
| --------------------------------------------- | ------------------------------------------------------------------------------------- |
| Default `bridge` network                      | Every container joins this automatically; containers reach each other by IP only      |
| User-defined bridge network                   | Containers on the same network reach each other by **container name** (automatic DNS) |
| `docker network create <name>`                | Create a user-defined bridge network                                                  |
| `docker network ls`                           | List all networks on the host                                                         |
| `docker network inspect <name>`               | Show connected containers and network config                                          |
| `docker network connect <net> <container>`    | Attach a running container to a network                                               |
| `docker network disconnect <net> <container>` | Detach a running container from a network                                             |
| `docker network rm <name>`                    | Remove a network                                                                      |
| `docker network prune`                        | Remove all unused networks                                                            |
| `-p host:container`                           | Publish a container port to the host (port mapping)                                   |

### Docker Network Basics

Every container gets its own isolated **network namespace** — its own network interfaces, routing table, and DNS. Containers can't reach each other by default unless they share a network.

**How the default bridge network works:**

When you start a container without specifying a network, Docker attaches it to a built-in network called `bridge`. Containers on this network can communicate with each other, but only by **IP address** — hostnames don't resolve. That makes the default bridge fragile; if a container restarts, its IP can change.

```bash
# Both containers are on the default bridge, but can only reach each other by IP
docker run -d --name db postgres:16-alpine
docker run -d --name web my-app:1.0
```

**Why user-defined networks are better:**

When you create your own network with `docker network create`, Docker sets up **automatic DNS** for every container on that network. Containers can reach each other by container name — no IP tracking needed.

```bash
docker network create app-net

docker run -d --name db --network app-net postgres:16-alpine
docker run -d --name web --network app-net my-app:1.0

# Inside "web", "db" resolves to the database container's IP automatically
```

**Port publishing:**

By default, a container's ports are not reachable from outside. Use `-p` to map a host port to a container port:

```bash
docker run -d -p 8080:3000 my-app:1.0
# host:8080 → container:3000
```

**Key rules to remember:**

- Containers on the **same user-defined network** talk to each other freely by name.
- Containers on **different networks** are isolated from each other.
- Use `-p` to expose a container port to the host (and therefore the outside world).
- The default `bridge` network is for quick testing only — always use user-defined networks in real projects.

### Network Types

| Driver    | When to use                                                       |
| --------- | ----------------------------------------------------------------- |
| `bridge`  | Default. Best for single-host apps with multiple containers.      |
| `host`    | Share the host's network stack directly. No isolation, max speed. |
| `none`    | No network at all. Total isolation.                               |
| `overlay` | Multi-host networking for Docker Swarm / clusters.                |
| `macvlan` | Give a container its own MAC address on the physical LAN.         |

### `docker network` Commands

```bash
# Create a user-defined bridge network
docker network create app-net

# Attach a container at run time
docker run -d --name db --network app-net postgres:16-alpine

# Attach / detach an already-running container
docker network connect app-net web
docker network disconnect app-net web

# Inspect what's on a network
docker network inspect app-net

# List and clean up
docker network ls
docker network rm app-net
docker network prune
```

### Container-to-Container Communication

The best reason to use a **user-defined bridge network**: containers on the same user-defined network can reach each other by **container name** via automatic DNS.

```bash
docker network create app-net

docker run -d --name db --network app-net -e POSTGRES_PASSWORD=secret postgres:16-alpine
docker run -d --name web --network app-net -p 3000:3000 my-app:1.0

# Inside "web", the database is reachable at hostname "db" on port 5432
# Connection string: postgres://postgres:secret@db:5432/postgres
```

On the **default** bridge network, containers can only reach each other by IP — which is fragile and painful.

### How to Create a User-Defined Bridge in Docker

The default `bridge` network lets containers communicate only by IP address. If a container restarts its IP can change, making references fragile. A **user-defined bridge** solves this with automatic DNS — containers reach each other by name.

**Advantages of a user-defined bridge over the default bridge:**

| Feature                  | Default bridge               | User-defined bridge                    |
| ------------------------ | ---------------------------- | -------------------------------------- |
| Container name DNS       | No — IP only                 | Yes — automatic                        |
| Isolation                | All containers share it      | Only containers you attach             |
| Attach/detach on the fly | No — must recreate container | Yes — `network connect` / `disconnect` |

**Step 1 — Create the network:**

```bash
docker network create skynet

# 7bd5f351aa892ac6ec15fed8619fc3bbb95a7dcdd58980c28304627c8f7eb070

docker network ls
# NETWORK ID     NAME     DRIVER    SCOPE
# be0cab667c4b   bridge   bridge    local
# 124dccee067f   host     host      local
# 506e3822bf1f   none     null      local
# 7bd5f351aa89   skynet   bridge    local
```

**Step 2 — Attach containers at run time using `--network`:**

```bash
docker container run --network skynet --rm --name hello-dock --detach --publish 8080:80 fhsinchy/hello-dock
```

**Step 3 — Attach an already-running container using `network connect`:**

```bash
# Generic syntax
docker network connect <network> <container>

# Example
docker network connect skynet hello-dock
```

A container can be on multiple networks at the same time. `network inspect` shows which containers are attached:

```bash
docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' skynet
#  hello-dock
```

**Step 4 — Verify automatic DNS:**

Spin up a second container on the same network and ping the first by name:

```bash
docker container run --network skynet --rm --name alpine-box -it alpine sh

/ # ping hello-dock
# PING hello-dock (172.18.0.2): 56 data bytes
# 64 bytes from 172.18.0.2: seq=0 ttl=64 time=0.191 ms
# 64 bytes from 172.18.0.2: seq=1 ttl=64 time=0.103 ms
```

Containers on the same user-defined bridge resolve each other by container name automatically. This only works when you give containers explicit names with `--name` — randomly generated names don't participate in DNS.

**Step 5 — Detach a container from the network:**

```bash
# Generic syntax
docker network disconnect <network> <container>

# Example
docker network disconnect skynet hello-dock
```

**Step 6 — Remove the network:**

```bash
docker network rm skynet

# Remove all unused networks at once
docker network prune
```

### How to Attach a Container to a Network in Docker

There are two ways to attach a container to a network.

**Method 1 — `--network` flag at run time:**

Pass `--network <network>` to `docker container run` or `docker container create`. The container joins the network from the moment it starts.

```bash
docker container run \
    --network skynet \
    --rm \
    --detach \
    --name hello-dock \
    --publish 8080:80 \
    fhsinchy/hello-dock
```

**Method 2 — `docker network connect` for a running container:**

Use this when a container is already running and you want to add it to another network without restarting it.

```bash
# Generic syntax
docker network connect <network> <container>

# Example
docker network connect skynet hello-dock
```

A container can belong to multiple networks simultaneously. Verify by inspecting each network:

```bash
docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' skynet
#  hello-dock

docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' bridge
#  hello-dock
```

Both commands show `hello-dock`, confirming it is attached to both networks at the same time.

**Verifying automatic DNS:**

Once two containers share a user-defined network, they can reach each other by container name:

```bash
docker container run --network skynet --rm --name alpine-box -it alpine sh

/ # ping hello-dock
# PING hello-dock (172.18.0.2): 56 data bytes
# 64 bytes from 172.18.0.2: seq=0 ttl=64 time=0.191 ms
# 64 bytes from 172.18.0.2: seq=1 ttl=64 time=0.103 ms
```

> Automatic DNS only works with explicitly named containers. The `--name` flag is required — randomly generated names are not resolvable.

### How to Detach Containers from a Network in Docker

Use `docker network disconnect` to remove a container from a network without stopping or restarting it.

```bash
# Generic syntax
docker network disconnect <network> <container>

# Example
docker network disconnect skynet hello-dock
```

The command produces no output on success. The container continues running but can no longer communicate with other containers on `skynet` by name.

To confirm the container is gone from the network:

```bash
docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' skynet
# (empty — hello-dock has been detached)
```

### How to Get Rid of Networks in Docker

**Remove a specific network:**

```bash
# Generic syntax
docker network rm <network>

# Example
docker network rm skynet
```

The network must have no active endpoints (connected containers) before it can be removed. Stop or disconnect all containers first.

**Remove all unused networks at once:**

```bash
docker network prune
```

Docker will prompt for confirmation. Pass `-f` or `--force` to skip the prompt:

```bash
docker network prune -f
```

A network is considered unused if no running container is currently connected to it.

---

## How to Containerize a Multi-Container JavaScript Application

A real-world application almost always needs more than one service — an API, a database, a cache. This section walks through containerizing `notes-api`, a Node.js REST API backed by a PostgreSQL database, using only `docker run`, named volumes, and user-defined networks. Doing it manually first makes clear exactly what Docker Compose automates in the next section.

**The stack:**

- **notes-db** — a PostgreSQL 12 container that stores the data.
- **notes-api** — a Node.js/Express API that reads and writes to the database.

### One Shot Revision

| Step | What you do                                | Key command / concept                                                                       |
| ---- | ------------------------------------------ | ------------------------------------------------------------------------------------------- |
| 1    | Run the database server                    | `docker container run --detach --name notes-db postgres:12`                                 |
| 2    | Persist data with a named volume           | `docker volume create notes-db-data` then `--volume notes-db-data:/var/lib/postgresql/data` |
| 3    | Check the database started correctly       | `docker container logs notes-db`                                                            |
| 4    | Create a network and attach the database   | `docker network create notes-api-network`                                                   |
| 5    | Write a multi-stage Dockerfile for the API | Stage 1: build deps; Stage 2: minimal runtime image                                         |
| 6    | Write management scripts                   | Shell scripts that automate the full start/stop lifecycle                                   |

### How to Run the Database Server

The API needs a PostgreSQL database. Rather than installing PostgreSQL on the host, run it as a Docker container using the official `postgres` image. The image accepts environment variables to configure the database name and credentials on first startup.

**Run the database container:**

```bash
docker container run \
    --detach \
    --name=notes-db \
    --env POSTGRES_DB=notesdb \
    --env POSTGRES_PASSWORD=secret \
    postgres:12
```

**What each flag does:**

| Flag                             | Purpose                                           |
| -------------------------------- | ------------------------------------------------- |
| `--detach`                       | Run in the background                             |
| `--name=notes-db`                | Give it a stable name so the API can reference it |
| `--env POSTGRES_DB=notesdb`      | Create a database called `notesdb` on startup     |
| `--env POSTGRES_PASSWORD=secret` | Set the password for the `postgres` superuser     |
| `postgres:12`                    | Use the official PostgreSQL 12 image              |

**Verify it's running:**

```bash
docker container ls
# CONTAINER ID   IMAGE         COMMAND                  CREATED          STATUS          NAMES
# f5b01a8c22c2   postgres:12   "docker-entrypoint.s…"   10 seconds ago   Up 9 seconds    notes-db
```

**Problem — data is lost on restart:**

Right now, PostgreSQL writes its data to `/var/lib/postgresql/data` inside the container. When the container is removed, that data vanishes. The fix is a named volume (see next section).

### How to Work with Named Volumes in Docker

A **named volume** is Docker-managed storage that persists beyond the lifecycle of any single container. Unlike an anonymous volume, you choose the name — which makes it easy to reuse across containers and inspect with `docker volume` commands.

**Volume commands:**

```bash
# Create a named volume
docker volume create notes-db-data

# List all volumes
docker volume ls

# Inspect a volume (shows the host path Docker manages internally)
docker volume inspect notes-db-data

# Remove a volume (all data is permanently deleted)
docker volume rm notes-db-data

# Remove all unused volumes
docker volume prune
```

**Named vs anonymous volumes:**

| Aspect      | Named volume                | Anonymous volume                                |
| ----------- | --------------------------- | ----------------------------------------------- |
| Name        | You choose it               | Docker assigns a random hash                    |
| Reuse       | Easy — reference by name    | Hard — must look up the hash                    |
| Persistence | Survives `docker rm`        | Removed when container is removed (with `--rm`) |
| Use case    | Databases, persistent state | Protecting a path from a bind mount             |

**Start the database with a named volume:**

Stop and remove the old container first, then re-run with `--volume`:

```bash
docker container rm --force notes-db

docker container run \
    --detach \
    --name=notes-db \
    --env POSTGRES_DB=notesdb \
    --env POSTGRES_PASSWORD=secret \
    --volume notes-db-data:/var/lib/postgresql/data \
    postgres:12
```

The flag `--volume notes-db-data:/var/lib/postgresql/data` mounts the named volume at the path PostgreSQL uses for its data files. Now you can stop, remove, and recreate the container — the data lives in the named volume and is automatically reattached on the next run.

### How to Access Logs from a Container in Docker

`docker container logs` prints the stdout and stderr output of a container's main process — the same output you'd see if you ran it without `--detach`.

**Syntax:**

```bash
docker container logs [options] <container>
```

**Common options:**

| Option                | Description                                                                |
| --------------------- | -------------------------------------------------------------------------- |
| `--follow` / `-f`     | Stream live output (Ctrl-C to stop)                                        |
| `--tail <n>`          | Show only the last n lines                                                 |
| `--timestamps` / `-t` | Prefix each line with a timestamp                                          |
| `--since <time>`      | Show logs since a timestamp or relative duration (e.g. `1h`, `2023-01-01`) |

**Examples:**

```bash
# Print all logs since the container started
docker container logs notes-db

# Stream live output
docker container logs --follow notes-db

# Show only the last 20 lines
docker container logs --tail 20 notes-db

# Show logs with timestamps
docker container logs --timestamps notes-db

# Logs from the last hour only
docker container logs --since 1h notes-db
```

**What to look for in the PostgreSQL logs:**

```
LOG:  database system is ready to accept connections
```

That line confirms the database server started successfully and is listening for connections. If you see errors instead, check that the `POSTGRES_PASSWORD` environment variable is set correctly.

### How to Create a Network and Attaching the Database Server in Docker

The API container needs to reach the database container by name. For this to work, both containers must share the same **user-defined bridge network** — automatic DNS resolution only works on user-defined networks, not the default `bridge`.

**Step 1 — Create the network:**

```bash
docker network create notes-api-network
```

**Step 2 — Remove the old database container and re-run it on the network:**

The `--network` flag must be set at run time. You either specify it at `docker run`, or attach a running container afterward with `docker network connect`.

```bash
docker container rm --force notes-db

docker container run \
    --detach \
    --name=notes-db \
    --env POSTGRES_DB=notesdb \
    --env POSTGRES_PASSWORD=secret \
    --network=notes-api-network \
    --volume notes-db-data:/var/lib/postgresql/data \
    postgres:12
```

**Verify the container is on the network:**

```bash
docker network inspect notes-api-network
# ...
# "Containers": {
#     "f5b01a8c22c2": {
#         "Name": "notes-db",
#         ...
#     }
# }
```

Once the API container joins the same network, it can reach the database at hostname `notes-db` (the container's `--name`) on port `5432` — no IP address needed.

### How to Write the Dockerfile

The `notes-api` image uses a **multi-stage build** — the first stage installs build dependencies, the second stage copies only the compiled production modules into a minimal runtime image.

**Why multi-stage?** Native Node add-ons (like `bcrypt` or `pg`) require `python`, `make`, and `g++` to compile. Those tools are heavy and should never ship in the production image. Stage 1 does the compilation; Stage 2 takes only the output.

**`Dockerfile`:**

```dockerfile
# ── Stage 1: build ──────────────────────────────────────────────────────────
FROM node:lts-alpine as builder

# python, make, and g++ are needed to compile native Node add-ons
RUN apk add --no-cache python make g++

WORKDIR /app

COPY ./package.json .
RUN npm install --only=prod

# ── Stage 2: runtime ────────────────────────────────────────────────────────
FROM node:lts-alpine

EXPOSE 3000
ENV NODE_ENV=production

USER node
RUN mkdir -p /home/node/app
WORKDIR /home/node/app

COPY --chown=node:node --from=builder /app/node_modules /home/node/app/node_modules
COPY --chown=node:node . .

CMD [ "node", "bin/www" ]
```

**What each instruction does:**

| Instruction                                             | Reason                                                                     |
| ------------------------------------------------------- | -------------------------------------------------------------------------- |
| `FROM node:lts-alpine as builder`                       | Names the first stage so Stage 2 can reference it                          |
| `RUN apk add --no-cache python make g++`                | Adds native-module build tools (Alpine uses `apk`)                         |
| `COPY ./package.json .` + `RUN npm install --only=prod` | Installs only production dependencies, cached until `package.json` changes |
| `FROM node:lts-alpine` (Stage 2)                        | Starts a clean, minimal image — no build tools included                    |
| `ENV NODE_ENV=production`                               | Tells Express and most Node libraries to use production mode               |
| `USER node`                                             | Drops root privileges; the `node` image ships a built-in `node` user       |
| `COPY --from=builder /app/node_modules …`               | Pulls only the compiled `node_modules` from Stage 1                        |
| `COPY --chown=node:node . .`                            | Copies the rest of the source with ownership set to `node`                 |
| `CMD ["node", "bin/www"]`                               | Starts the API server                                                      |

**Build and run the API container:**

```bash
# Build the image (run from the project root where Dockerfile lives)
docker image build --tag notes-api .

# Run the API and attach it to the same network as the database
docker container run \
    --detach \
    --name=notes-api \
    --env DB_HOST=notes-db \
    --env DB_DATABASE=notesdb \
    --env DB_PASSWORD=secret \
    --publish=3000:3000 \
    --network=notes-api-network \
    notes-api
```

The `DB_HOST=notes-db` environment variable points the API at the database container by name. Because both containers are on `notes-api-network`, Docker resolves `notes-db` to the correct IP automatically.

### How to Write Management Scripts in Docker

As the number of `docker run` flags grows, commands become hard to remember and error-prone to type. Shell scripts wrap the full workflow into a single repeatable command.

**Project layout:**

```
notes-api/
├── Dockerfile
├── .dockerignore
├── package.json
├── bin/
│   └── www
└── shell/
    ├── boot.sh       ← creates network/volume/containers from scratch
    ├── stop.sh       ← stops containers without destroying them
    └── nuke.sh       ← tears down and cleans up everything
```

**`shell/boot.sh` — start the full stack:**

```bash
#!/bin/bash

set -e

# Create the network (ignore error if it already exists)
docker network create notes-api-network 2>/dev/null || true

# Create the named volume (ignore error if it already exists)
docker volume create notes-db-data 2>/dev/null || true

# Run the database container
docker container run \
    --detach \
    --name=notes-db \
    --env POSTGRES_DB=notesdb \
    --env POSTGRES_PASSWORD=secret \
    --network=notes-api-network \
    --volume notes-db-data:/var/lib/postgresql/data \
    postgres:12

# Build the API image
docker image build --tag notes-api .

# Run the API container
docker container run \
    --detach \
    --name=notes-api \
    --env DB_HOST=notes-db \
    --env DB_DATABASE=notesdb \
    --env DB_PASSWORD=secret \
    --publish=3000:3000 \
    --network=notes-api-network \
    notes-api

# Run migrations after the API is up
docker container exec notes-api npm run db:migrate

echo "Stack is up → http://localhost:3000"
```

**`shell/stop.sh` — pause the stack:**

```bash
#!/bin/bash

docker container stop notes-api notes-db
```

**`shell/nuke.sh` — tear everything down:**

```bash
#!/bin/bash

# Force-remove containers
docker container rm --force notes-api notes-db

# Remove the named volume (all data is lost)
docker volume rm notes-db-data

# Remove the network
docker network rm notes-api-network

echo "Stack torn down."
```

**Make the scripts executable and run:**

```bash
chmod +x shell/boot.sh shell/stop.sh shell/nuke.sh

# Start the stack
./shell/boot.sh

# Stop the stack (containers preserved)
./shell/stop.sh

# Tear it all down
./shell/nuke.sh
```

**Why write scripts instead of jumping straight to Docker Compose?**

Writing the shell scripts manually first teaches you exactly what Compose does for you — networks, volumes, container ordering, env vars. Once you've done it by hand, the `compose.yaml` format makes intuitive sense.

---

## Docker Networking

Containers talk to each other over Docker-managed networks. Docker creates a default network for you, but user-defined networks are usually a better choice.

### One Shot Revision

| Concept / Command                             | What it does                                                                          |
| --------------------------------------------- | ------------------------------------------------------------------------------------- |
| Default `bridge` network                      | Every container joins this automatically; containers reach each other by IP only      |
| User-defined bridge network                   | Containers on the same network reach each other by **container name** (automatic DNS) |
| `docker network create <name>`                | Create a user-defined bridge network                                                  |
| `docker network ls`                           | List all networks on the host                                                         |
| `docker network inspect <name>`               | Show connected containers and network config                                          |
| `docker network connect <net> <container>`    | Attach a running container to a network                                               |
| `docker network disconnect <net> <container>` | Detach a running container from a network                                             |
| `docker network rm <name>`                    | Remove a network                                                                      |
| `docker network prune`                        | Remove all unused networks                                                            |
| `-p host:container`                           | Publish a container port to the host (port mapping)                                   |
| `docker container exec <container> <cmd>`     | Run a command inside a running container                                              |
| `docker container exec -it <container> sh`    | Open an interactive shell in a running container                                      |

### Docker Network Basics

Every container gets its own isolated **network namespace** — its own network interfaces, routing table, and DNS. Containers can't reach each other by default unless they share a network.

**How the default bridge network works:**

When you start a container without specifying a network, Docker attaches it to a built-in network called `bridge`. Containers on this network can communicate with each other, but only by **IP address** — hostnames don't resolve. That makes the default bridge fragile; if a container restarts, its IP can change.

```bash
# Both containers are on the default bridge, but can only reach each other by IP
docker run -d --name db postgres:16-alpine
docker run -d --name web my-app:1.0
```

**Why user-defined networks are better:**

When you create your own network with `docker network create`, Docker sets up **automatic DNS** for every container on that network. Containers can reach each other by container name — no IP tracking needed.

```bash
docker network create app-net

docker run -d --name db --network app-net postgres:16-alpine
docker run -d --name web --network app-net my-app:1.0

# Inside "web", "db" resolves to the database container's IP automatically
```

**Port publishing:**

By default, a container's ports are not reachable from outside. Use `-p` to map a host port to a container port:

```bash
docker run -d -p 8080:3000 my-app:1.0
# host:8080 → container:3000
```

**Key rules to remember:**

- Containers on the **same user-defined network** talk to each other freely by name.
- Containers on **different networks** are isolated from each other.
- Use `-p` to expose a container port to the host (and therefore the outside world).
- The default `bridge` network is for quick testing only — always use user-defined networks in real projects.

### Network Types

| Driver    | When to use                                                       |
| --------- | ----------------------------------------------------------------- |
| `bridge`  | Default. Best for single-host apps with multiple containers.      |
| `host`    | Share the host's network stack directly. No isolation, max speed. |
| `none`    | No network at all. Total isolation.                               |
| `overlay` | Multi-host networking for Docker Swarm / clusters.                |
| `macvlan` | Give a container its own MAC address on the physical LAN.         |

### `docker network` Commands

```bash
# Create a user-defined bridge network
docker network create app-net

# Attach a container at run time
docker run -d --name db --network app-net postgres:16-alpine

# Attach / detach an already-running container
docker network connect app-net web
docker network disconnect app-net web

# Inspect what's on a network
docker network inspect app-net

# List and clean up
docker network ls
docker network rm app-net
docker network prune
```

### Container-to-Container Communication

The best reason to use a **user-defined bridge network**: containers on the same user-defined network can reach each other by **container name** via automatic DNS.

```bash
docker network create app-net

docker run -d --name db --network app-net -e POSTGRES_PASSWORD=secret postgres:16-alpine
docker run -d --name web --network app-net -p 3000:3000 my-app:1.0

# Inside "web", the database is reachable at hostname "db" on port 5432
# Connection string: postgres://postgres:secret@db:5432/postgres
```

On the **default** bridge network, containers can only reach each other by IP — which is fragile and painful.

### How to Create a User-Defined Bridge in Docker

The default `bridge` network lets containers communicate only by IP address. If a container restarts its IP can change, making references fragile. A **user-defined bridge** solves this with automatic DNS — containers reach each other by name.

**Advantages of a user-defined bridge over the default bridge:**

| Feature                  | Default bridge               | User-defined bridge                    |
| ------------------------ | ---------------------------- | -------------------------------------- |
| Container name DNS       | No — IP only                 | Yes — automatic                        |
| Isolation                | All containers share it      | Only containers you attach             |
| Attach/detach on the fly | No — must recreate container | Yes — `network connect` / `disconnect` |

**Step 1 — Create the network:**

```bash
docker network create skynet

# 7bd5f351aa892ac6ec15fed8619fc3bbb95a7dcdd58980c28304627c8f7eb070

docker network ls
# NETWORK ID     NAME     DRIVER    SCOPE
# be0cab667c4b   bridge   bridge    local
# 124dccee067f   host     host      local
# 506e3822bf1f   none     null      local
# 7bd5f351aa89   skynet   bridge    local
```

**Step 2 — Attach containers at run time using `--network`:**

```bash
docker container run --network skynet --rm --name hello-dock --detach --publish 8080:80 fhsinchy/hello-dock
```

**Step 3 — Attach an already-running container using `network connect`:**

```bash
# Generic syntax
docker network connect <network> <container>

# Example
docker network connect skynet hello-dock
```

A container can be on multiple networks at the same time. `network inspect` shows which containers are attached:

```bash
docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' skynet
#  hello-dock
```

**Step 4 — Verify automatic DNS:**

Spin up a second container on the same network and ping the first by name:

```bash
docker container run --network skynet --rm --name alpine-box -it alpine sh

/ # ping hello-dock
# PING hello-dock (172.18.0.2): 56 data bytes
# 64 bytes from 172.18.0.2: seq=0 ttl=64 time=0.191 ms
# 64 bytes from 172.18.0.2: seq=1 ttl=64 time=0.103 ms
```

Containers on the same user-defined bridge resolve each other by container name automatically. This only works when you give containers explicit names with `--name` — randomly generated names don't participate in DNS.

**Step 5 — Detach a container from the network:**

```bash
# Generic syntax
docker network disconnect <network> <container>

# Example
docker network disconnect skynet hello-dock
```

**Step 6 — Remove the network:**

```bash
docker network rm skynet

# Remove all unused networks at once
docker network prune
```

### How to Attach a Container to a Network in Docker

There are two ways to attach a container to a network.

**Method 1 — `--network` flag at run time:**

Pass `--network <network>` to `docker container run` or `docker container create`. The container joins the network from the moment it starts.

```bash
docker container run \
    --network skynet \
    --rm \
    --detach \
    --name hello-dock \
    --publish 8080:80 \
    fhsinchy/hello-dock
```

**Method 2 — `docker network connect` for a running container:**

Use this when a container is already running and you want to add it to another network without restarting it.

```bash
# Generic syntax
docker network connect <network> <container>

# Example
docker network connect skynet hello-dock
```

A container can belong to multiple networks simultaneously. Verify by inspecting each network:

```bash
docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' skynet
#  hello-dock

docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' bridge
#  hello-dock
```

Both commands show `hello-dock`, confirming it is attached to both networks at the same time.

**Verifying automatic DNS:**

Once two containers share a user-defined network, they can reach each other by container name:

```bash
docker container run --network skynet --rm --name alpine-box -it alpine sh

/ # ping hello-dock
# PING hello-dock (172.18.0.2): 56 data bytes
# 64 bytes from 172.18.0.2: seq=0 ttl=64 time=0.191 ms
# 64 bytes from 172.18.0.2: seq=1 ttl=64 time=0.103 ms
```

> Automatic DNS only works with explicitly named containers. The `--name` flag is required — randomly generated names are not resolvable.

### How to Detach Containers from a Network in Docker

Use `docker network disconnect` to remove a container from a network without stopping or restarting it.

```bash
# Generic syntax
docker network disconnect <network> <container>

# Example
docker network disconnect skynet hello-dock
```

The command produces no output on success. The container continues running but can no longer communicate with other containers on `skynet` by name.

To confirm the container is gone from the network:

```bash
docker network inspect --format='{{range .Containers}} {{.Name}} {{end}}' skynet
# (empty — hello-dock has been detached)
```

### How to Get Rid of Networks in Docker

**Remove a specific network:**

```bash
# Generic syntax
docker network rm <network>

# Example
docker network rm skynet
```

The network must have no active endpoints (connected containers) before it can be removed. Stop or disconnect all containers first.

**Remove all unused networks at once:**

```bash
docker network prune
```

Docker will prompt for confirmation. Pass `-f` or `--force` to skip the prompt:

```bash
docker network prune -f
```

A network is considered unused if no running container is currently connected to it.

### How to Execute Commands in a Running Container

`docker container exec` runs an arbitrary command inside a running container without interrupting the main process.

**Syntax:**

```bash
docker container exec [options] <container> <command> [args]
```

**Common options:**

| Option         | Description                                              |
| -------------- | -------------------------------------------------------- |
| `-it`          | Interactive + TTY — opens a shell session                |
| `-e KEY=VALUE` | Pass an extra environment variable for this command only |
| `-u <user>`    | Run as a specific user                                   |
| `-w <dir>`     | Set the working directory                                |

**Run database migrations:**

```bash
docker container exec notes-api npm run db:migrate

# Expected output:
# > notes-api@ db:migrate /home/node/app
# > knex migrate:latest
#
# Using environment: production
# Batch 1 run: 4 migrations
```

**Open an interactive shell:**

```bash
docker container exec -it notes-api sh

# Once inside, you can inspect the filesystem, run commands, or debug:
/home/node/app $ ls
/home/node/app $ cat .env
/home/node/app $ exit
```

**Seed the database:**

```bash
docker container exec notes-api npm run db:seed
```

**Key difference from `docker container run`:**

|                        | `docker container run`      | `docker container exec`               |
| ---------------------- | --------------------------- | ------------------------------------- |
| Target                 | Creates a **new** container | Runs inside an **existing** container |
| Effect on main process | None (separate container)   | None (main process keeps running)     |
| Use case               | One-off jobs, debug shells  | Migrations, seeds, admin tasks        |

---

## Docker Compose

Docker Compose lets you describe a multi-container app in a single YAML file and start the whole stack with one command. Instead of long `docker run` commands, you commit `compose.yaml` to your repo.

### `compose.yaml` Structure

```yaml
services:
  web:
    build: . # build the current folder's Dockerfile
    image: my-app:1.0
    ports:
      - "3000:3000"
    environment:
      DATABASE_URL: postgres://postgres:secret@db:5432/postgres
    depends_on:
      - db
    networks:
      - app-net

  db:
    image: postgres:16-alpine
    environment:
      POSTGRES_PASSWORD: secret
    volumes:
      - db-data:/var/lib/postgresql/data
    networks:
      - app-net

volumes:
  db-data:

networks:
  app-net:
    driver: bridge
```

**What Compose gives you for free:**

- A shared network — services can call each other by service name (`web` reaches the DB at `db`).
- Named volumes so data survives container rebuilds.
- Consistent, reviewable configuration in version control.

### Core Compose Commands

```bash
# Start everything (foreground, streaming logs)
docker compose up

# Start in the background
docker compose up -d

# Rebuild images before starting
docker compose up -d --build

# See what's running
docker compose ps

# Follow logs from one service
docker compose logs -f web

# Run a one-off command inside a service
docker compose exec db psql -U postgres

# Stop the stack but keep containers/volumes
docker compose stop

# Stop and remove containers + default network (keeps named volumes)
docker compose down

# Full clean including volumes
docker compose down -v
```

**Notes:**

- Modern Docker uses `docker compose` (space, plugin). The older standalone tool is `docker-compose` (hyphen) — same idea, different binary.
- File name can be `compose.yaml`, `compose.yml`, `docker-compose.yaml`, or `docker-compose.yml`.

---

## Useful Tips & Tricks

- **Pin your tags.** `nginx:1.27-alpine` today is the same nginx forever; `nginx:latest` is a moving target.
- **Use Alpine-based images** (`node:20-alpine`, `python:3.12-alpine`) when size matters — often 5–10× smaller.
- **Always add a `.dockerignore`.** Copying `node_modules` or `.git` into an image bloats it and slows the build.
- **Order Dockerfile instructions from most stable to most volatile** to keep the build cache warm.
- **One process per container.** Databases, web servers, and workers should each live in their own container.
- **Never bake secrets into an image.** Pass them at runtime via `-e`, `--env-file`, or a secrets manager.
- **Free up disk fast:** `docker system df` shows what's using space; `docker system prune -a --volumes` reclaims it.
- **Debug a broken container** by overriding its command: `docker run --rm -it --entrypoint sh my-app:1.0`.
- **Reproducible builds:** commit both your `Dockerfile` and the `docker-compose.yaml` — the container is only as portable as the recipe that built it.

---

## References

- [The Docker Handbook — freeCodeCamp](https://www.freecodecamp.org/news/the-docker-handbook/)
- [Docker Documentation](https://docs.docker.com/)
- [Docker Get Started Guide](https://docs.docker.com/get-started/)
- [Dockerfile Reference](https://docs.docker.com/engine/reference/builder/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [Docker Hub](https://hub.docker.com/)
- [Play with Docker (browser sandbox)](https://labs.play-with-docker.com/)
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
