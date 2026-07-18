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
  <img src="https://img.shields.io/badge/Sections-7-blue?style=flat-square" alt="Sections">
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
- [Command Note Template](#command-note-template)
- [Docker Fundamentals](#docker-fundamentals)
  - [One Shot Revision](#one-shot-revision)
  - [What is Docker?](#what-is-docker)
  - [Containers vs Virtual Machines](#containers-vs-virtual-machines)
  - [Docker Architecture](#docker-architecture)
  - [Images, Containers & Registries](#images-containers--registries)
- [Container Basics](#container-basics)
  - [One Shot Revision](#one-shot-revision-1)
  - [`docker run`](#docker-run)
  - [`docker ps`](#docker-ps)
  - [`docker stop` / `docker kill`](#docker-stop--docker-kill)
  - [`docker start` / `docker restart`](#docker-start--docker-restart)
  - [`docker exec`](#docker-exec)
  - [`docker rm` / `docker prune`](#docker-rm--docker-prune)
- [Image Basics](#image-basics)
  - [One Shot Revision](#one-shot-revision-2)
  - [`docker pull`](#docker-pull)
  - [`docker image ls`](#docker-image-ls)
  - [`docker image build`](#docker-image-build)
  - [`docker image tag`](#docker-image-tag)
  - [`docker push`](#docker-push)
  - [`docker image rm` / `docker image prune`](#docker-image-rm--docker-image-prune)
- [Dockerfile Instructions](#dockerfile-instructions)
  - [One Shot Revision](#one-shot-revision-3)
  - [Instruction Reference](#instruction-reference)
  - [Example Dockerfiles](#example-dockerfiles)
  - [Image Layers & Caching](#image-layers--caching)
  - [Multi-Stage Builds](#multi-stage-builds)
- [Volumes & Bind Mounts](#volumes--bind-mounts)
  - [Bind Mounts](#bind-mounts)
  - [Named Volumes](#named-volumes)
  - [Anonymous Volumes](#anonymous-volumes)
- [Docker Networking](#docker-networking)
  - [Network Types](#network-types)
  - [`docker network` Commands](#docker-network-commands)
  - [Container-to-Container Communication](#container-to-container-communication)
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

## Command Note Template

Use this format whenever a new command or concept is added.

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

## Docker Fundamentals

Before touching any command, it helps to build a clear mental picture of what Docker is, why it exists, and how its pieces fit together. This section is the "story" behind every command in the rest of the notes.

### One Shot Revision

| Topic                                                     | Short Description                                                  |
| --------------------------------------------------------- | ------------------------------------------------------------------ |
| [What is Docker?](#what-is-docker)                        | Containerization platform that packages apps with their dependencies |
| [Containers vs VMs](#containers-vs-virtual-machines)      | Containers share the host kernel; VMs ship a full guest OS         |
| [Docker Architecture](#docker-architecture)               | CLI → daemon → containerd → runc; daemon also talks to registries  |
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

| Aspect         | Container                            | Virtual Machine                    |
| -------------- | ------------------------------------ | ---------------------------------- |
| What's virtualized | Just the OS (shares host kernel) | The whole machine (CPU, RAM, disk) |
| Guest OS       | None — uses the host kernel          | A full OS (Ubuntu, Windows, etc.)  |
| Size           | Tens of MB                           | Several GB                         |
| Startup        | Milliseconds                         | Minutes                            |
| Density        | Hundreds per host                    | A handful per host                 |
| Isolation      | Process-level (namespaces, cgroups)  | Hardware-level (hypervisor)        |

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

| Command                                              | Short Description                              |
| ---------------------------------------------------- | ---------------------------------------------- |
| [`docker run`](#docker-run)                          | Create + start a container from an image       |
| [`docker ps`](#docker-ps)                            | List running (or all) containers               |
| [`docker stop` / `docker kill`](#docker-stop--docker-kill) | Graceful stop vs immediate kill          |
| [`docker start` / `docker restart`](#docker-start--docker-restart) | Restart existing containers          |
| [`docker exec`](#docker-exec)                        | Run a command inside a **running** container   |
| [`docker rm` / `docker prune`](#docker-rm--docker-prune) | Remove stopped containers                  |

### `docker run`

**Description:** Creates a new container from an image and starts it in one step. This is the single most-used Docker command.

**Syntax:**

```bash
docker run [options] <image> [command]
```

**Common Options:**

| Option              | Description                                                          |
| ------------------- | -------------------------------------------------------------------- |
| `-p, --publish`     | Map a host port to a container port: `-p 8080:80`                    |
| `-d, --detach`      | Run in the background; return the container ID                       |
| `-it`               | `-i` (interactive) + `-t` (tty) — for shells and REPLs               |
| `--name`            | Give the container a friendly, memorable name                        |
| `--rm`              | Auto-remove the container when it exits (great for one-off commands) |
| `-e, --env`         | Set an environment variable: `-e NODE_ENV=production`                |
| `-v, --volume`      | Attach a volume or bind mount: `-v $(pwd):/app`                      |
| `--network`         | Attach the container to a specific network                           |

**Examples:**

```bash
# Run nginx and publish port 80 in the container as 8080 on the host
docker run -d -p 8080:80 --name web nginx

# Open an interactive Ubuntu shell that cleans itself up on exit
docker run --rm -it ubuntu bash

# Run a one-off command with an env var
docker run --rm -e GREETING=hello alpine sh -c 'echo $GREETING world'

# Mount the current folder into /app for live development
docker run --rm -it -v $(pwd):/app -w /app node:20-alpine sh
```

**Notes:**

- `docker run` = `docker create` + `docker start`. Use `docker create` when you want to configure a container without starting it yet.
- Without `-p`, the container is unreachable from the host — publishing ports is opt-in.
- `-it` combines two flags: `-i` keeps STDIN open, `-t` allocates a TTY so prompts render nicely.

### `docker ps`

**Description:** Lists containers. By default it shows only running ones.

**Syntax:**

```bash
docker ps [options]
```

**Common Options:**

| Option           | Description                                       |
| ---------------- | ------------------------------------------------- |
| `-a, --all`      | Show all containers (running + stopped)           |
| `-q, --quiet`    | Show only container IDs (great for scripting)     |
| `--filter`       | Filter output: `--filter status=exited`           |
| `--format`       | Custom output using Go templates                  |

**Examples:**

```bash
# What's currently running?
docker ps

# Show everything, including stopped containers
docker ps -a

# Just the IDs — handy for piping into other commands
docker ps -aq

# Remove every stopped container in one line
docker rm $(docker ps -aq --filter status=exited)
```

**Notes:**

- `docker container ls` is the newer, longer form of `docker ps` — they do the same thing.

### `docker stop` / `docker kill`

**Description:** Two ways to shut a container down — one polite, one abrupt.

**Syntax:**

```bash
docker stop <container>   # Sends SIGTERM, waits ~10s, then SIGKILL
docker kill <container>   # Sends SIGKILL immediately
```

**Examples:**

```bash
# Graceful stop (default; lets the app clean up)
docker stop web

# Force-kill when the container is unresponsive
docker kill web

# Stop everything running at once
docker stop $(docker ps -q)
```

**Notes:**

- Prefer `stop` for production apps so databases and services can flush state cleanly.
- `kill` is fine for stuck containers or when you don't care about clean shutdown.

### `docker start` / `docker restart`

**Description:** Bring a **previously created** container back to life.

**Syntax:**

```bash
docker start <container>     # Start a stopped container
docker restart <container>   # Stop then start again
```

**Examples:**

```bash
# Resume a container you stopped earlier — keeps its name, ports, volumes
docker start web

# Bounce it (useful after config changes)
docker restart web
```

**Notes:**

- `start` reuses the original `docker run` options — you don't need to repeat `-p`, `-e`, etc.
- If a container was created with `--rm`, it's already gone once it stops. There's nothing to `start`.

### `docker exec`

**Description:** Runs a new command inside an **already-running** container. Perfect for debugging.

**Syntax:**

```bash
docker exec [options] <container> <command>
```

**Common Options:**

| Option | Description                             |
| ------ | --------------------------------------- |
| `-it`  | Interactive terminal (for shells)       |
| `-e`   | Add an env var just for this command    |
| `-u`   | Run as a specific user: `-u root`       |
| `-w`   | Change working directory for the command|

**Examples:**

```bash
# Open a shell inside a running container
docker exec -it web bash        # or `sh` for tiny images like alpine

# Peek at the process list
docker exec web ps aux

# Run a psql query inside a postgres container
docker exec -it db psql -U postgres -c '\l'
```

**Notes:**

- `exec` is not the same as `run`: `run` starts a **new** container from an image; `exec` reaches **into an existing** one.
- If a container has no `bash`, try `sh` — Alpine and other minimal images don't ship bash.

### `docker rm` / `docker prune`

**Description:** Remove stopped containers to free disk space.

**Syntax:**

```bash
docker rm <container> [<container>...]
docker container prune
```

**Examples:**

```bash
# Remove one specific container
docker rm web

# Force-remove a running container (stop + remove in one shot)
docker rm -f web

# Sweep away every stopped container
docker container prune
```

**Notes:**

- A running container can't be removed without `-f`.
- `prune` will prompt for confirmation unless you add `-f`.
- Use `--rm` on `docker run` to skip the cleanup step altogether.

---

## Image Basics

Everything you do with the images themselves — pulling from a registry, listing them locally, building your own, and pushing them back.

### One Shot Revision

| Command                                              | Short Description                                    |
| ---------------------------------------------------- | ---------------------------------------------------- |
| [`docker pull`](#docker-pull)                        | Download an image from a registry                    |
| [`docker image ls`](#docker-image-ls)                | List local images                                    |
| [`docker image build`](#docker-image-build)          | Build an image from a Dockerfile                     |
| [`docker image tag`](#docker-image-tag)              | Give an image an additional name/tag                 |
| [`docker push`](#docker-push)                        | Upload an image to a registry                        |
| [`docker image rm` / `prune`](#docker-image-rm--docker-image-prune) | Delete images                          |

### `docker pull`

**Description:** Downloads an image from a registry (Docker Hub by default) so it's available locally.

**Syntax:**

```bash
docker pull <image>[:<tag>]
```

**Examples:**

```bash
# Pull the "latest" tag of nginx
docker pull nginx

# Pull a specific version — always safer for reproducibility
docker pull nginx:1.27-alpine

# Pull from GitHub Container Registry
docker pull ghcr.io/tahshinsharon/my-app:v1.0
```

**Notes:**

- If you skip the tag, Docker assumes `:latest` — which is a moving target. Pin versions in production.
- `docker run` will automatically pull the image if it's not already local.

### `docker image ls`

**Description:** Lists images that live on your machine.

**Syntax:**

```bash
docker image ls [options]
```

**Examples:**

```bash
# All local images
docker image ls

# Just image IDs (great for scripting cleanups)
docker image ls -q

# Show dangling (untagged) images
docker image ls --filter dangling=true
```

**Notes:**

- `docker images` is the shorter alias — same thing.
- Dangling images are old layers that no longer have a tag. Clean them with `docker image prune`.

### `docker image build`

**Description:** Reads a `Dockerfile` and produces a new image.

**Syntax:**

```bash
docker image build [-t <name>:<tag>] <build-context>
# Modern shorthand:
docker build -t <name>:<tag> .
```

**Common Options:**

| Option        | Description                                                     |
| ------------- | --------------------------------------------------------------- |
| `-t, --tag`   | Name the resulting image: `-t my-app:1.0`                       |
| `-f, --file`  | Use a Dockerfile with a non-standard name/location              |
| `--no-cache`  | Ignore the build cache and rebuild from scratch                 |
| `--build-arg` | Pass an `ARG` value: `--build-arg VERSION=1.2.3`                |

**Examples:**

```bash
# Build from the Dockerfile in the current folder, tag it as my-app:1.0
docker build -t my-app:1.0 .

# Build using a differently named Dockerfile
docker build -f Dockerfile.prod -t my-app:prod .

# Force a fresh build, no cache
docker build --no-cache -t my-app:1.0 .
```

**Notes:**

- The **build context** is the directory Docker sends to the daemon. Keep it small — add a `.dockerignore` to skip `node_modules`, `.git`, etc.
- Every instruction in the Dockerfile creates a **layer** that gets cached. Order instructions so the ones that change least come first.

### `docker image tag`

**Description:** Adds an extra name (or version) to an existing image. It doesn't copy the image — it just labels it.

**Syntax:**

```bash
docker image tag <source>:<tag> <target>:<tag>
```

**Examples:**

```bash
# Tag a local image for pushing to Docker Hub
docker image tag my-app:1.0 tahshinsharon/my-app:1.0

# Add a "latest" alias
docker image tag my-app:1.0 my-app:latest
```

**Notes:**

- The full form is `<registry>/<repository>:<tag>` — e.g. `ghcr.io/tahshinsharon/my-app:v1`.
- No registry prefix ⇒ Docker Hub is assumed on push.

### `docker push`

**Description:** Uploads a local image to a registry so others (or your servers) can pull it.

**Syntax:**

```bash
docker push <registry>/<repository>:<tag>
```

**Examples:**

```bash
# 1) Log in first (interactive prompt)
docker login

# 2) Push a Docker Hub image
docker push tahshinsharon/my-app:1.0

# Push to GHCR
docker push ghcr.io/tahshinsharon/my-app:1.0
```

**Notes:**

- You must `docker login` first — pushes to a registry require auth.
- The image name **must** include the target registry/user, or Docker will reject the push.

### `docker image rm` / `docker image prune`

**Description:** Delete images you no longer need.

**Syntax:**

```bash
docker image rm <image>[:<tag>]
docker image prune           # remove dangling images
docker image prune -a        # remove ALL unused images
```

**Examples:**

```bash
# Remove a specific image
docker image rm my-app:1.0

# Clean up dangling layers
docker image prune

# Nuke every image not used by a container
docker image prune -a
```

**Notes:**

- If an image is referenced by a container (even a stopped one), remove the container first or add `-f`.
- Freeing space? `docker system prune -a --volumes` cleans images, containers, networks, and volumes in one shot.

---

## Dockerfile Instructions

A **Dockerfile** is a plain-text recipe that tells Docker how to build an image, step by step. Each line is an instruction; each instruction becomes a layer.

### One Shot Revision

| Instruction  | Purpose                                             |
| ------------ | --------------------------------------------------- |
| `FROM`       | Set the base image (must be the first instruction)  |
| `WORKDIR`    | Set the working directory for the rest of the build |
| `COPY`       | Copy local files/folders into the image             |
| `ADD`        | Like `COPY`, but also handles URLs and tar extraction |
| `RUN`        | Execute a command at **build time**                 |
| `ENV`        | Set an environment variable (build + run time)      |
| `ARG`        | Set a build-time-only variable                      |
| `EXPOSE`     | Document the port the app listens on                |
| `CMD`        | Default command executed when a container starts    |
| `ENTRYPOINT` | Fixed executable of the container                   |
| `VOLUME`     | Declare a mount point for external volumes          |
| `USER`       | Set the user for subsequent instructions            |
| `LABEL`      | Attach metadata (maintainer, version, description)  |

### Instruction Reference

**`FROM`** — the starting layer.

```dockerfile
FROM node:20-alpine    # small, secure, production-friendly
```

**`WORKDIR`** — like `cd` for the build; also becomes the container's default directory.

```dockerfile
WORKDIR /app
```

**`COPY`** vs **`ADD`** — both copy files, but `ADD` also unpacks tarballs and can download URLs. Prefer `COPY`; use `ADD` only when you actually need those extras.

```dockerfile
COPY package*.json ./         # copy only manifests first (cache-friendly)
COPY . .                      # copy the rest of the app
ADD https://example.com/x.tar.gz /opt/    # ADD-specific: download + extract
```

**`RUN`** — executes at build time. Chain related commands with `&&` to keep layers small.

```dockerfile
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl && \
    apt-get clean && rm -rf /var/lib/apt/lists/*
```

**`ENV`** vs **`ARG`** — `ENV` sticks around at runtime; `ARG` only exists during the build.

```dockerfile
ARG APP_VERSION=1.0.0            # only visible while building
ENV NODE_ENV=production PORT=3000 # visible to the running container
```

**`EXPOSE`** — documentation only. It does **not** publish the port; you still need `-p` at runtime.

```dockerfile
EXPOSE 3000
```

**`CMD`** vs **`ENTRYPOINT`** — both define what runs when the container starts.

- `CMD` sets a **default** that can be overridden by arguments to `docker run`.
- `ENTRYPOINT` sets a **fixed** command; anything after the image name becomes arguments to it.
- Combine them for the "app with default args" pattern.

```dockerfile
ENTRYPOINT ["node"]
CMD ["server.js"]
# `docker run my-app`             → node server.js
# `docker run my-app worker.js`   → node worker.js
```

**`VOLUME`** — declares that a path should be a mount point.

```dockerfile
VOLUME /var/lib/postgresql/data
```

**`USER`** — drop privileges after installing things as root.

```dockerfile
RUN adduser -D appuser
USER appuser
```

**`LABEL`** — freeform metadata.

```dockerfile
LABEL maintainer="tahshinsharon@example.com" \
      version="1.0" \
      description="Sample Node.js app"
```

### Example Dockerfiles

**A minimal NGINX image:**

```dockerfile
FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y nginx && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

Build and run it:

```bash
docker build -t custom-nginx:1.0 .
docker run -d -p 8080:80 --name web custom-nginx:1.0
```

**A Node.js app:**

```dockerfile
FROM node:20-alpine

WORKDIR /app

# Copy manifests first so `npm install` is cached
COPY package*.json ./
RUN npm ci --omit=dev

# Copy the rest
COPY . .

EXPOSE 3000
CMD ["node", "server.js"]
```

Add a `.dockerignore` next to it:

```
node_modules
npm-debug.log
.git
.env
.vscode
Dockerfile
```

### Image Layers & Caching

- Every Dockerfile instruction produces a **read-only layer**. Containers add one thin writable layer on top.
- If an earlier layer changes, all layers after it are **invalidated** and rebuilt.
- **Put stable instructions first, volatile ones last.** Copy `package.json` and run `npm install` **before** copying the rest of your source.
- Peek at the layers of any image:

```bash
docker image history my-app:1.0
```

### Multi-Stage Builds

Multi-stage builds let you use a big, tool-heavy image for the build, then copy only the final artifacts into a tiny runtime image. Result: much smaller and safer production images.

```dockerfile
# ── Stage 1: build ─────────────────────────────
FROM node:20 AS builder
WORKDIR /build
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# ── Stage 2: runtime ───────────────────────────
FROM node:20-alpine
WORKDIR /app
COPY --from=builder /build/dist ./dist
COPY --from=builder /build/node_modules ./node_modules
EXPOSE 3000
CMD ["node", "dist/index.js"]
```

**Why it matters:** compilers, dev dependencies, and build tools never touch the shipped image.

---

## Volumes & Bind Mounts

By default, everything you write inside a container disappears the moment the container is removed. **Volumes** and **bind mounts** are how you persist and share data.

### Bind Mounts

Map a folder on your **host** to a folder inside the container. Two-way sync; great for development.

```bash
# Live-reload development: your local /src is visible inside the container
docker run --rm -it -v $(pwd):/app -w /app node:20-alpine sh
```

**Syntax:** `-v <host-path>:<container-path>[:ro]` — add `:ro` for read-only.

### Named Volumes

Docker manages the storage location. Best for databases and anything you want to persist across container rebuilds.

```bash
# Create the volume once
docker volume create db-data

# Mount it into a Postgres container
docker run -d --name db \
  -v db-data:/var/lib/postgresql/data \
  -e POSTGRES_PASSWORD=secret \
  postgres:16-alpine

# Inspect / list / clean up
docker volume ls
docker volume inspect db-data
docker volume rm db-data
docker volume prune
```

### Anonymous Volumes

No name given — Docker assigns a random ID. Useful for "carve out this path so the host's bind mount doesn't overwrite it."

```bash
# Bind the source, but keep node_modules isolated inside the container
docker run --rm -it \
  -v $(pwd):/app \
  -v /app/node_modules \
  -w /app node:20-alpine sh
```

---

## Docker Networking

Containers talk to each other over Docker-managed networks. Docker creates a default network for you, but user-defined networks are usually a better choice.

### Network Types

| Driver    | When to use                                                        |
| --------- | ------------------------------------------------------------------ |
| `bridge`  | Default. Best for single-host apps with multiple containers.       |
| `host`    | Share the host's network stack directly. No isolation, max speed.  |
| `none`    | No network at all. Total isolation.                                |
| `overlay` | Multi-host networking for Docker Swarm / clusters.                 |
| `macvlan` | Give a container its own MAC address on the physical LAN.          |

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

---

## Docker Compose

Docker Compose lets you describe a multi-container app in a single YAML file and start the whole stack with one command. Instead of long `docker run` commands, you commit `compose.yaml` to your repo.

### `compose.yaml` Structure

```yaml
services:
  web:
    build: .                         # build the current folder's Dockerfile
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
