<h1 align="center">Ansible Learning Notes</h1>

<p align="center">
  A personal collection of Ansible commands, concepts,<br>
  and notes gathered while learning Configuration Management and Automation.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white" alt="Ansible">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/DevOps-EE0000?style=for-the-badge&logo=ansible&logoColor=white" alt="DevOps">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-2-blue?style=flat-square" alt="Sections">
  <img src="https://img.shields.io/badge/Level-Beginner→Intermediate-orange?style=flat-square" alt="Level">
  <img src="https://img.shields.io/badge/Status-Actively%20Updated-brightgreen?style=flat-square" alt="Status">
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="../README.md"><b>Back to DevOps Prep</b></a>
  &nbsp;·&nbsp;
  <a href="../1. Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../2. Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../3. Networking/README.md"><b>Networking Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../4. Cloud-Engineering/README.md"><b>Cloud Engineering Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../5. Docker/README.md"><b>Docker Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../6. Kubernetes/README.md"><b>Kubernetes Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../7. Terraform/README.md"><b>Terraform Notes</b></a>
</p>

---

## Table of Contents

- [Introduction](#introduction)
- [Ansible Commands](#ansible-commands)
- [Ansible Fundamentals](#ansible-fundamentals)
  - [One Shot Revision](#one-shot-revision)
  - [What is Ansible?](#what-is-ansible)
  - [Ansible vs Other Config Management Tools](#ansible-vs-other-config-management-tools)
  - [How Ansible Works](#how-ansible-works)
  - [YAML Basics](#yaml-basics)
- [Ansible Basics](#ansible-basics)
  - [One Shot Revision](#one-shot-revision-1)
  - [Install Ansible](#install-ansible)
  - [Inventory](#inventory)
  - [Ad-hoc Commands](#ad-hoc-commands)
  - [Playbooks](#playbooks)
  - [Variables and Facts](#variables-and-facts)
  - [Handlers](#handlers)
  - [Roles](#roles)
  - [Ansible Vault](#ansible-vault)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction

Brief notes about Ansible — the open-source automation tool by Red Hat that lets you configure systems, deploy applications, and orchestrate multi-step workflows without installing agents on managed nodes.

- **Focus:** Writing inventories, ad-hoc commands, and playbooks to automate infrastructure tasks.
- **Scope:** Inventory → Ad-hoc Commands → Playbooks → Variables → Handlers → Roles → Vault.
- **Goal:** Build strong Ansible fundamentals for DevOps interview prep and day-to-day configuration management workflows.

**Learn from the official source:**

→ [Ansible Documentation](https://docs.ansible.com/)

---

## Ansible Commands

Ansible ships several CLI tools — each serves a specific purpose in the automation workflow.

| Command | Purpose |
| ------- | ------- |
| `ansible` | Run ad-hoc commands against managed hosts |
| `ansible-playbook` | Execute a playbook |
| `ansible-inventory` | Display or graph the inventory |
| `ansible-vault` | Encrypt and decrypt sensitive data |
| `ansible-galaxy` | Download and install roles/collections from Galaxy |
| `ansible-doc` | Show module documentation in the terminal |
| `ansible-config` | View and validate Ansible configuration |
| `ansible-lint` | Lint playbooks for best-practice violations |

For the full list of commands and options, see the **[Ansible CLI Reference →](https://docs.ansible.com/ansible/latest/command_guide/index.html)**

---

## Ansible Fundamentals

Before writing a single playbook, it helps to build a clear mental picture of what Ansible is, why it exists, and how its agentless architecture differs from every other config-management tool. This section is the "story" behind every command in the rest of the notes.

### One Shot Revision

| Topic | Short Description |
| ----- | ----------------- |
| [What is Ansible?](#what-is-ansible) | Open-source automation tool for config mgmt, app deployment, and orchestration |
| [Ansible vs Other Tools](#ansible-vs-other-config-management-tools) | Ansible is agentless and push-based; Puppet/Chef require agents |
| [How Ansible Works](#how-ansible-works) | Control node → SSH → managed nodes; no daemon, no agent |
| [YAML Basics](#yaml-basics) | Playbooks are YAML — key-value pairs, lists, dicts, and indentation rules |

### What is Ansible?

**In one sentence:** Ansible is an open-source IT automation tool that uses SSH and YAML playbooks to configure systems, deploy applications, and orchestrate complex workflows — without installing any agent on the managed machines.

Without a config management tool, managing dozens (or hundreds) of servers means logging into each one individually, running commands by hand, and hoping nothing drifts over time. Ansible solves this by describing the **desired state** of your systems in human-readable YAML playbooks and pushing those changes over SSH.

**Problem → Solution Flow:**

```
Without Ansible:
  50 servers → SSH to each one → run commands manually → configuration drift
  New server → repeat all setup steps → easy to miss steps → inconsistent state
  Secret rotation → update each server by hand → forgotten servers → security risk

With Ansible:
  50 servers → one playbook → ansible-playbook site.yml → identical state everywhere
         ↓
  New server → add to inventory → run playbook → fully configured in minutes
         ↓
  Secret rotation → update vault → run playbook → all servers updated atomically
         ↓
  Audit trail → playbook in Git → every change reviewed, versioned, repeatable
```

**Why it matters for DevOps:**

- **Agentless** — managed nodes only need Python and SSH. No daemons, no ports to open, no agent upgrades to manage.
- **Declarative & procedural** — playbooks read top-to-bottom but modules are idempotent: running a playbook twice leaves the system in the same state.
- **Human-readable** — YAML playbooks serve as living documentation of your infrastructure state.
- **Push-based** — the control node initiates all connections; managed nodes never call home.
- **Huge module library** — 3,000+ built-in modules covering packages, files, services, cloud APIs, databases, network devices, and more.
- **Low barrier to entry** — no DSL to learn; if you know YAML and basic Linux, you can write playbooks on day one.

**Name origin:** "Ansible" is a science-fiction device that allows faster-than-light communication — fitting for a tool that lets one machine instantly configure thousands of others.

---

### Ansible vs Other Config Management Tools

Ansible is not the only config management tool. Understanding where it fits helps you pick the right tool and answer interview questions confidently.

**Tool Comparison:**

```
┌──────────────────────────────────────────────────────────────────────┐
│               Config Management Tool Landscape                       │
├──────────────┬──────────────┬──────────────┬────────────────────────┤
│   Ansible    │    Puppet    │     Chef     │      SaltStack         │
│  (Red Hat)   │  (Perforce)  │  (Progress)  │     (VMware)           │
├──────────────┼──────────────┼──────────────┼────────────────────────┤
│ Agentless    │ Agent-based  │ Agent-based  │ Agent-based (or SSH)   │
│ Push-based   │ Pull-based   │ Pull-based   │ Push & Pull            │
│ YAML         │ Puppet DSL   │ Ruby (DSL)   │ YAML / Python          │
│ SSH transport│ HTTPS/PuppetDB│ HTTPS/Chef  │ ZeroMQ / SSH           │
│ Procedural   │ Declarative  │ Declarative  │ Declarative            │
│ No master    │ Puppet master│ Chef server  │ Salt master (optional) │
└──────────────┴──────────────┴──────────────┴────────────────────────┘
```

| Aspect | Ansible | Puppet | Chef | SaltStack |
| ------ | ------- | ------ | ---- | --------- |
| **Agent** | None (agentless) | Required on all nodes | Required on all nodes | Optional (SSH mode) |
| **Communication** | Push over SSH | Pull from Puppet master | Pull from Chef server | Push/Pull via ZeroMQ |
| **Language** | YAML playbooks | Puppet DSL | Ruby cookbooks | YAML states / Python |
| **Learning curve** | Low | High | High | Medium |
| **Idempotency** | Module-level | Built-in | Built-in | Built-in |
| **Best for** | App deployment, orchestration, ad-hoc tasks | Large-scale continuous config enforcement | Large-scale continuous config enforcement | Large-scale, event-driven automation |

**Mental model:**

```
Use Terraform   → to provision the cloud resources (VPC, EC2, RDS)
Use Ansible     → to configure the software on those resources (install Nginx, deploy app)
Use Kubernetes  → to orchestrate containerized workloads on top

They are complementary, not competing.
```

---

### How Ansible Works

Ansible's architecture is intentionally simple: one control node, SSH, Python, and no persistent state on managed nodes.

**Ansible Architecture:**

```
┌──────────────────────────────────────────────────────────────────┐
│                        Ansible Architecture                      │
│                                                                  │
│   Control Node (your laptop, CI server, AWX)                     │
│   ┌─────────────────────────────────────────┐                   │
│   │  ansible-playbook site.yml              │                   │
│   │  ├─ Reads inventory (hosts & groups)    │                   │
│   │  ├─ Reads playbook (tasks to run)       │                   │
│   │  └─ Resolves variables and templates    │                   │
│   └────────────────┬────────────────────────┘                   │
│                    │  SSH (port 22)                              │
│          ┌─────────┼─────────┐                                  │
│          ▼         ▼         ▼                                  │
│   ┌──────────┐ ┌──────────┐ ┌──────────┐                        │
│   │ web-01   │ │ web-02   │ │ db-01    │  ← Managed Nodes       │
│   │ (Python) │ │ (Python) │ │ (Python) │    (only need SSH      │
│   └──────────┘ └──────────┘ └──────────┘     + Python)          │
│                                                                  │
│   No agents. No daemons. No open inbound ports.                  │
└──────────────────────────────────────────────────────────────────┘
```

**What happens when you run a playbook:**

```
ansible-playbook site.yml
        │
        ├─ 1. Parse inventory → build list of target hosts
        │
        ├─ 2. Parse playbook → build ordered list of tasks
        │
        ├─ 3. For each host (in parallel, up to `forks` limit):
        │      ├─ Open SSH connection
        │      ├─ Copy module code to /tmp on managed node
        │      ├─ Execute module with task arguments
        │      ├─ Collect JSON result (changed / ok / failed)
        │      └─ Clean up /tmp
        │
        ├─ 4. Evaluate results:
        │      ├─ ok      → task ran, no change needed (idempotent)
        │      ├─ changed → task ran and made a change
        │      ├─ failed  → task errored, playbook stops (by default)
        │      └─ skipped → when condition was false
        │
        └─ 5. Print PLAY RECAP with counts per host
```

**Key Ansible concepts:**

| Concept | What it is |
| ------- | ---------- |
| **Control node** | The machine running Ansible (your laptop, CI server) |
| **Managed node** | The target machine being configured (server, VM, container) |
| **Inventory** | List of managed nodes, organized into groups |
| **Module** | A unit of work Ansible executes on a managed node (e.g., `apt`, `copy`, `service`) |
| **Task** | One call to a module with specific arguments |
| **Play** | A mapping of hosts to a list of tasks |
| **Playbook** | A YAML file containing one or more plays |
| **Role** | A reusable, structured collection of tasks, variables, templates, and handlers |
| **Handler** | A task triggered only when notified by another task (e.g., restart Nginx after config change) |
| **Fact** | Auto-discovered information about a managed node (OS, IP, CPU, memory, etc.) |

---

### YAML Basics

Ansible playbooks are written in YAML (**Y**et **A**nother **M**arkup **L**anguage). YAML uses indentation and simple syntax to represent structured data.

**The Golden Rules of YAML:**

```
1. Indentation uses SPACES, never tabs.
2. Indentation level defines structure.
3. Strings don't need quotes unless they contain special characters.
4. Comments start with #.
5. A YAML file (or document) starts with --- (optional but conventional).
```

**YAML data types used in Ansible:**

```yaml
---
# Key-value pair (string)
name: web-server
environment: production

# Number
port: 8080
timeout: 30

# Boolean
enabled: true
debug: false

# List (sequence)
packages:
  - nginx
  - git
  - python3

# Inline list
packages: [nginx, git, python3]

# Dictionary (mapping)
database:
  host: db.example.com
  port: 5432
  name: myapp

# Inline dictionary
database: {host: db.example.com, port: 5432}

# List of dictionaries (the most common pattern in playbooks)
users:
  - name: alice
    shell: /bin/bash
  - name: bob
    shell: /bin/zsh

# Multi-line string (literal block — preserves newlines)
script: |
  #!/bin/bash
  echo "hello"
  exit 0

# Multi-line string (folded block — folds newlines into spaces)
description: >
  This is a long description
  that wraps across multiple lines.
```

**Minimal playbook anatomy:**

```yaml
---
- name: Configure web servers        # play name (human-readable)
  hosts: webservers                  # which inventory group to target
  become: true                       # run tasks as root (sudo)

  tasks:
    - name: Install nginx            # task name
      ansible.builtin.apt:           # module (fully-qualified)
        name: nginx
        state: present               # ensure nginx is installed

    - name: Start and enable nginx
      ansible.builtin.service:
        name: nginx
        state: started
        enabled: true
```

```
Playbook
└── Play (hosts: webservers)
    ├── Task 1: Install nginx
    └── Task 2: Start nginx

Each task calls one module with specific arguments.
```

---

## Ansible Basics

Hands-on foundation — from installing Ansible to writing your first role. Every concept from the Fundamentals section becomes concrete here.

### One Shot Revision

| Topic | Short Description |
| ----- | ----------------- |
| [Install Ansible](#install-ansible) | Install the Ansible CLI on the control node |
| [Inventory](#inventory) | Define which hosts Ansible manages and how to group them |
| [Ad-hoc Commands](#ad-hoc-commands) | Run one-off tasks without a playbook: `ansible all -m ping` |
| [Playbooks](#playbooks) | YAML files that define ordered plays and tasks to execute |
| [Variables and Facts](#variables-and-facts) | Pass data into plays; use auto-gathered facts about each host |
| [Handlers](#handlers) | Tasks that only fire when notified — perfect for service restarts |
| [Roles](#roles) | Reusable, structured collections of tasks, vars, templates, and handlers |
| [Ansible Vault](#ansible-vault) | Encrypt secrets in files or strings so they are safe to commit |

### Install Ansible

Ansible only needs to be installed on the **control node**. Managed nodes need only SSH access and Python 3.

**Install Ansible CLI:**

```
┌─────────────────────────────────────┐
│  Choose Your Platform               │
├─────────────────────────────────────┤
│                                     │
├─ macOS (Homebrew)                   │
│  └─ brew install ansible            │
│                                     │
├─ Ubuntu / Debian (apt)              │
│  └─ apt-get install ansible         │
│                                     │
├─ RHEL / CentOS / Fedora (dnf)       │
│  └─ dnf install ansible             │
│                                     │
├─ Any OS (pip — recommended)         │
│  └─ pip install ansible             │
│                                     │
└─────────────────────────────────────┘
```

**macOS:**

```bash
brew install ansible
```

**Ubuntu/Debian:**

```bash
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

**Any OS via pip (recommended — always gets the latest version):**

```bash
pip install ansible
```

**Verify installation:**

```bash
ansible --version
# ansible [core 2.x.x]
#   config file = /etc/ansible/ansible.cfg
#   python version = 3.x.x
```

**Ansible configuration file (`ansible.cfg`):**

Ansible looks for configuration in this order (first match wins):

```
1. ANSIBLE_CONFIG environment variable
2. ./ansible.cfg (current directory)
3. ~/.ansible.cfg (home directory)
4. /etc/ansible/ansible.cfg (global default)
```

Minimal `ansible.cfg` for a project:

```ini
[defaults]
inventory      = ./inventory         # path to your inventory file
remote_user    = ubuntu              # SSH user on managed nodes
private_key_file = ~/.ssh/id_rsa     # SSH key
host_key_checking = False            # disable strict host key checking (dev only)
forks          = 10                  # run tasks on 10 hosts in parallel
```

---

### Inventory

The inventory tells Ansible **which hosts exist** and how to group them. It is the starting point for every command and playbook.

**Static inventory (INI format — simplest):**

```ini
# inventory/hosts

# Ungrouped hosts
192.168.1.10
192.168.1.11

# Group: webservers
[webservers]
web-01.example.com
web-02.example.com
192.168.1.20

# Group: databases
[databases]
db-01.example.com ansible_port=2222 ansible_user=admin

# Group of groups
[production:children]
webservers
databases

# Group variables
[webservers:vars]
http_port=80
max_clients=200
```

**Static inventory (YAML format — preferred for complex setups):**

```yaml
# inventory/hosts.yml

all:
  children:
    webservers:
      hosts:
        web-01.example.com:
          ansible_user: ubuntu
        web-02.example.com:
          ansible_user: ubuntu
    databases:
      hosts:
        db-01.example.com:
          ansible_user: admin
          ansible_port: 2222
    production:
      children:
        webservers:
        databases:
```

**Host variables (per-host connection settings):**

| Variable | Purpose |
| -------- | ------- |
| `ansible_host` | IP or hostname to connect to (overrides the inventory name) |
| `ansible_port` | SSH port (default: 22) |
| `ansible_user` | SSH user on the managed node |
| `ansible_ssh_private_key_file` | Path to the SSH private key |
| `ansible_become` | Whether to use privilege escalation |
| `ansible_become_method` | Escalation method: `sudo`, `su`, `doas` |
| `ansible_python_interpreter` | Python path on managed node (e.g., `/usr/bin/python3`) |

**Inspect your inventory:**

```bash
ansible-inventory -i inventory/hosts.yml --list       # JSON dump of all hosts and vars
ansible-inventory -i inventory/hosts.yml --graph      # tree view of groups
ansible-inventory -i inventory/hosts.yml --host web-01.example.com  # vars for one host
```

**Test connectivity:**

```bash
ansible all -i inventory/hosts -m ping                # ping all hosts
ansible webservers -i inventory/hosts -m ping         # ping only the webservers group
```

**Directory layout for inventory variables:**

```
inventory/
├── hosts.yml          ← host/group definitions
├── group_vars/
│   ├── all.yml        ← variables applied to every host
│   ├── webservers.yml ← variables applied to the webservers group
│   └── databases.yml  ← variables applied to the databases group
└── host_vars/
    ├── web-01.example.com.yml   ← variables for this specific host only
    └── db-01.example.com.yml
```

---

### Ad-hoc Commands

Ad-hoc commands run a single module against hosts without a playbook — perfect for quick checks, one-off tasks, and exploring modules.

**Syntax:**

```bash
ansible <host-pattern> -i <inventory> -m <module> -a "<arguments>" [options]
```

**Common options:**

| Option | Short | Purpose |
| ------ | ----- | ------- |
| `--inventory` | `-i` | Path to inventory file |
| `--module-name` | `-m` | Module to use (default: `command`) |
| `--args` | `-a` | Module arguments |
| `--become` | `-b` | Run with sudo |
| `--become-user` | | User to become (default: root) |
| `--user` | `-u` | SSH user |
| `--forks` | `-f` | Parallel tasks (default: 5) |
| `--limit` | `-l` | Limit to specific hosts or groups |
| `--check` | | Dry run — show what would change |
| `--verbose` | `-v` | Verbose output (`-vvv` for max verbosity) |

**Examples:**

```bash
# Ping all hosts (test connectivity)
ansible all -m ping

# Run a shell command on all webservers
ansible webservers -m shell -a "df -h"

# Gather facts about a host
ansible web-01.example.com -m setup

# Gather only specific facts
ansible all -m setup -a "filter=ansible_os_family"

# Install a package (with sudo)
ansible webservers -b -m apt -a "name=nginx state=present"

# Remove a package
ansible webservers -b -m apt -a "name=nginx state=absent"

# Copy a file to all hosts
ansible all -m copy -a "src=/local/file.conf dest=/etc/file.conf"

# Create a directory
ansible all -b -m file -a "path=/opt/myapp state=directory mode=0755"

# Restart a service
ansible webservers -b -m service -a "name=nginx state=restarted"

# Run a raw command (no Python needed on managed node — useful for bootstrapping)
ansible all -m raw -a "apt-get install -y python3"

# Check mode (dry run — does not make changes)
ansible webservers -b -m apt -a "name=nginx state=present" --check
```

**Module output statuses:**

```
SUCCESS: ok=1   → module ran, system already in desired state (no change)
SUCCESS: changed=1 → module ran and made a change
FAILED:  failed=1  → module encountered an error
```

---

### Playbooks

Playbooks are the heart of Ansible — ordered YAML files that define what to do and where to do it.

**Playbook structure:**

```yaml
---
# A playbook can contain multiple plays
- name: Configure web servers        # PLAY 1
  hosts: webservers
  become: true
  vars:
    http_port: 80

  tasks:
    - name: Install nginx
      ansible.builtin.apt:
        name: nginx
        state: present
        update_cache: true

    - name: Deploy nginx config
      ansible.builtin.template:
        src: templates/nginx.conf.j2
        dest: /etc/nginx/nginx.conf
      notify: Restart nginx           # triggers handler

    - name: Ensure nginx is running
      ansible.builtin.service:
        name: nginx
        state: started
        enabled: true

  handlers:
    - name: Restart nginx
      ansible.builtin.service:
        name: nginx
        state: restarted

- name: Configure database servers   # PLAY 2
  hosts: databases
  become: true

  tasks:
    - name: Install PostgreSQL
      ansible.builtin.apt:
        name: postgresql
        state: present
```

**Running a playbook:**

```bash
ansible-playbook site.yml                            # run against default inventory
ansible-playbook -i inventory/hosts site.yml         # specify inventory
ansible-playbook site.yml --limit webservers         # only run against webservers group
ansible-playbook site.yml --tags install             # only run tasks with tag "install"
ansible-playbook site.yml --skip-tags deploy         # skip tasks tagged "deploy"
ansible-playbook site.yml --check                    # dry run
ansible-playbook site.yml --diff                     # show file diffs when templates change
ansible-playbook site.yml -v                         # verbose output
ansible-playbook site.yml -vvv                       # max verbosity (connection debugging)
```

**Task control:**

```yaml
tasks:
  # Run only on RHEL/CentOS
  - name: Install EPEL (RHEL/CentOS only)
    ansible.builtin.dnf:
      name: epel-release
      state: present
    when: ansible_os_family == "RedHat"

  # Loop over a list
  - name: Install required packages
    ansible.builtin.apt:
      name: "{{ item }}"
      state: present
    loop:
      - nginx
      - git
      - curl

  # Ignore errors and continue
  - name: Check if service exists
    ansible.builtin.command: systemctl status myapp
    ignore_errors: true
    register: service_status            # capture output

  # Use the registered variable
  - name: Show service status
    ansible.builtin.debug:
      msg: "Service status: {{ service_status.rc }}"

  # Tags for selective execution
  - name: Deploy application
    ansible.builtin.copy:
      src: app/
      dest: /opt/myapp/
    tags:
      - deploy
      - app
```

**Essential modules:**

| Module | Purpose | Example |
| ------ | ------- | ------- |
| `ansible.builtin.apt` | Manage apt packages (Debian/Ubuntu) | `name: nginx state: present` |
| `ansible.builtin.dnf` | Manage dnf packages (RHEL/Fedora) | `name: nginx state: present` |
| `ansible.builtin.yum` | Manage yum packages (older RHEL) | `name: nginx state: present` |
| `ansible.builtin.service` | Manage system services | `name: nginx state: started` |
| `ansible.builtin.copy` | Copy files to managed nodes | `src: file.conf dest: /etc/` |
| `ansible.builtin.template` | Render Jinja2 templates and copy | `src: nginx.conf.j2 dest: /etc/nginx/nginx.conf` |
| `ansible.builtin.file` | Manage files, dirs, symlinks, permissions | `path: /opt/app state: directory` |
| `ansible.builtin.command` | Run a command (no shell features) | `cmd: /usr/bin/myapp --init` |
| `ansible.builtin.shell` | Run a shell command (pipes, redirects) | `cmd: cat /etc/hosts \| grep db` |
| `ansible.builtin.user` | Manage OS users | `name: deploy shell: /bin/bash` |
| `ansible.builtin.group` | Manage OS groups | `name: www-data state: present` |
| `ansible.builtin.git` | Clone/update a Git repository | `repo: https://... dest: /opt/app` |
| `ansible.builtin.lineinfile` | Ensure a line is (or is not) in a file | `path: /etc/ssh/sshd_config line: PermitRootLogin no` |
| `ansible.builtin.debug` | Print a message or variable | `msg: "IP is {{ ansible_default_ipv4.address }}"` |
| `ansible.builtin.ping` | Test connectivity | _(no args)_ |
| `ansible.builtin.setup` | Gather facts from managed nodes | _(no args)_ |
| `ansible.builtin.stat` | Get file/path status | `path: /etc/nginx/nginx.conf` |
| `ansible.builtin.uri` | Interact with HTTP/HTTPS endpoints | `url: http://localhost method: GET` |
| `ansible.builtin.cron` | Manage cron jobs | `name: backup minute: "0" hour: "2" job: /usr/bin/backup.sh` |

---

### Variables and Facts

Variables let you parameterize playbooks; facts are auto-discovered variables about each managed node.

**Defining variables — precedence (lowest to highest):**

```
role defaults          (roles/myrole/defaults/main.yml)
inventory group_vars   (inventory/group_vars/all.yml)
inventory host_vars    (inventory/host_vars/web-01.yml)
playbook vars          (vars: section in playbook)
vars_files             (vars_files: section in playbook)
vars_prompt            (interactive prompt)
set_fact / registered  (tasks during play)
extra_vars             (ansible-playbook -e "key=value")  ← highest
```

**Defining variables in a playbook:**

```yaml
---
- name: Deploy application
  hosts: webservers
  vars:
    app_port: 8080
    app_user: deploy
    app_dir: /opt/myapp

  vars_files:
    - vars/common.yml
    - vars/production.yml

  tasks:
    - name: Create app directory
      ansible.builtin.file:
        path: "{{ app_dir }}"
        state: directory
        owner: "{{ app_user }}"
        mode: "0755"
```

**Group and host variable files:**

```yaml
# inventory/group_vars/webservers.yml
http_port: 80
max_clients: 200
nginx_worker_processes: auto

# inventory/host_vars/web-01.example.com.yml
nginx_worker_connections: 1024
```

**Passing variables at the command line:**

```bash
ansible-playbook site.yml -e "app_port=9090"
ansible-playbook site.yml -e "@vars/override.yml"   # load from a YAML file
```

**Registering task output:**

```yaml
- name: Check disk space
  ansible.builtin.command: df -h /
  register: disk_output

- name: Print disk usage
  ansible.builtin.debug:
    msg: "{{ disk_output.stdout }}"

- name: Fail if disk is almost full
  ansible.builtin.fail:
    msg: "Low disk space!"
  when: disk_output.rc != 0
```

**Facts — auto-gathered information:**

When Ansible connects to a managed node, it runs the `setup` module and collects **facts** — system information available as variables in your playbook.

```bash
# See all facts for a host
ansible web-01.example.com -m setup

# Filter facts
ansible web-01.example.com -m setup -a "filter=ansible_distribution*"
```

**Commonly used facts:**

| Fact | Example Value | What it contains |
| ---- | ------------- | ---------------- |
| `ansible_hostname` | `web-01` | Short hostname |
| `ansible_fqdn` | `web-01.example.com` | Fully qualified domain name |
| `ansible_os_family` | `Debian`, `RedHat` | OS family (for conditional tasks) |
| `ansible_distribution` | `Ubuntu`, `CentOS` | Exact OS name |
| `ansible_distribution_version` | `22.04` | OS version |
| `ansible_architecture` | `x86_64` | CPU architecture |
| `ansible_default_ipv4.address` | `192.168.1.10` | Primary IPv4 address |
| `ansible_memtotal_mb` | `8192` | Total RAM in MB |
| `ansible_processor_vcpus` | `4` | Number of vCPUs |

**Using facts in tasks:**

```yaml
- name: Install correct package for OS family
  ansible.builtin.apt:
    name: nginx
    state: present
  when: ansible_os_family == "Debian"

- name: Print hostname and IP
  ansible.builtin.debug:
    msg: "Host {{ ansible_hostname }} has IP {{ ansible_default_ipv4.address }}"
```

**Custom facts (disable fact gathering for speed):**

```yaml
---
- name: Fast play (no facts needed)
  hosts: webservers
  gather_facts: false            # skip the setup module — faster execution

  tasks:
    - name: Ping
      ansible.builtin.ping:
```

---

### Handlers

Handlers are special tasks that run **only when notified** by another task. They run once at the end of a play (regardless of how many tasks notify them) — perfect for service restarts after config changes.

**How handlers work:**

```
Task: Deploy nginx config  →  notify: "Restart nginx"
                                      │
                           (config changed?)
                                      │
                               YES → Handler runs at end of play
                                NO  → Handler does NOT run
```

**Defining and using handlers:**

```yaml
---
- name: Configure nginx
  hosts: webservers
  become: true

  tasks:
    - name: Install nginx
      ansible.builtin.apt:
        name: nginx
        state: present

    - name: Deploy nginx.conf
      ansible.builtin.template:
        src: templates/nginx.conf.j2
        dest: /etc/nginx/nginx.conf
        mode: "0644"
      notify:
        - Validate nginx config
        - Restart nginx

    - name: Deploy SSL certificate
      ansible.builtin.copy:
        src: files/server.crt
        dest: /etc/ssl/certs/server.crt
      notify: Reload nginx

  handlers:
    - name: Validate nginx config
      ansible.builtin.command: nginx -t
      changed_when: false

    - name: Restart nginx
      ansible.builtin.service:
        name: nginx
        state: restarted

    - name: Reload nginx
      ansible.builtin.service:
        name: nginx
        state: reloaded
```

**Key handler rules:**

- Handlers run **once** at the end of the play, even if notified by multiple tasks.
- Handlers run **in the order they are defined**, not the order they are notified.
- If a task fails mid-play, handlers that were notified earlier in the play will **not run** (unless you use `--force-handlers`).
- Use `listen` to have multiple handlers respond to one notification:

```yaml
handlers:
  - name: Restart web stack
    listen: "restart services"
    ansible.builtin.service:
      name: nginx
      state: restarted

  - name: Restart app
    listen: "restart services"
    ansible.builtin.service:
      name: myapp
      state: restarted

tasks:
  - name: Update config
    ansible.builtin.template:
      src: config.j2
      dest: /etc/myapp/config.yml
    notify: "restart services"      # fires both handlers
```

---

### Roles

Roles are Ansible's way of organizing reusable automation. A role bundles tasks, variables, templates, files, and handlers into a standard directory layout that can be shared and re-used across playbooks.

**Role directory structure:**

```
roles/
└── nginx/                          ← role name
    ├── tasks/
    │   └── main.yml                ← entry point for tasks
    ├── handlers/
    │   └── main.yml                ← handlers for this role
    ├── templates/
    │   └── nginx.conf.j2           ← Jinja2 templates
    ├── files/
    │   └── index.html              ← static files to copy
    ├── vars/
    │   └── main.yml                ← variables (high precedence)
    ├── defaults/
    │   └── main.yml                ← default variables (low precedence — override-able)
    ├── meta/
    │   └── main.yml                ← role metadata and dependencies
    └── README.md                   ← role documentation
```

**Create a role scaffold:**

```bash
ansible-galaxy role init nginx      # creates the standard directory structure
```

**Example role: `roles/nginx/tasks/main.yml`**

```yaml
---
- name: Install nginx
  ansible.builtin.apt:
    name: nginx
    state: present
    update_cache: true

- name: Deploy nginx configuration
  ansible.builtin.template:
    src: nginx.conf.j2
    dest: /etc/nginx/nginx.conf
    mode: "0644"
  notify: Restart nginx

- name: Ensure nginx is started and enabled
  ansible.builtin.service:
    name: nginx
    state: started
    enabled: true
```

**Example role defaults: `roles/nginx/defaults/main.yml`**

```yaml
---
nginx_port: 80
nginx_user: www-data
nginx_worker_processes: auto
nginx_worker_connections: 1024
```

**Using a role in a playbook:**

```yaml
---
- name: Configure web servers
  hosts: webservers
  become: true

  roles:
    - nginx                         # simple reference

  # Or with role-specific variables:
  roles:
    - role: nginx
      vars:
        nginx_port: 443
```

**Ansible Galaxy — community roles:**

```bash
# Install a role from Ansible Galaxy
ansible-galaxy install geerlingguy.nginx

# Install from a requirements file
ansible-galaxy install -r requirements.yml

# List installed roles
ansible-galaxy list
```

**`requirements.yml`:**

```yaml
---
roles:
  - name: geerlingguy.nginx
    version: "3.2.0"
  - name: geerlingguy.postgresql
    version: "3.5.0"

collections:
  - name: community.general
    version: "7.0.0"
  - name: amazon.aws
    version: "6.0.0"
```

---

### Ansible Vault

Ansible Vault encrypts sensitive data (passwords, API keys, certificates) so they can be safely committed to version control. Vault uses AES-256 encryption.

**Vault workflow:**

```
Developer                  Git Repo                  CI/CD
    │                          │                        │
    ├─ ansible-vault encrypt →  ├─ encrypted file ──────►├─ ansible-playbook
    │   vars/secrets.yml        │   (safe to commit)     │   --vault-password-file
    │                          │                        │   /run/secrets/vault_pass
    └─ ansible-vault decrypt ← ─┘                        └─ runs decrypted in memory
```

**Encrypting and decrypting files:**

```bash
# Encrypt a file (prompts for password)
ansible-vault encrypt vars/secrets.yml

# Decrypt a file (restores plain text)
ansible-vault decrypt vars/secrets.yml

# View an encrypted file without decrypting it to disk
ansible-vault view vars/secrets.yml

# Edit an encrypted file in-place
ansible-vault edit vars/secrets.yml

# Encrypt a single string (embed in a YAML file)
ansible-vault encrypt_string 'mysecretpassword' --name 'db_password'
# Output:
# db_password: !vault |
#   $ANSIBLE_VAULT;1.1;AES256
#   ...

# Re-key (change the vault password)
ansible-vault rekey vars/secrets.yml
```

**Using vault-encrypted variables in a playbook:**

```yaml
# vars/secrets.yml (encrypted)
---
db_password: !vault |
  $ANSIBLE_VAULT;1.1;AES256
  6238633962326664343031313731353831...

# playbook.yml
---
- name: Configure database
  hosts: databases
  become: true

  vars_files:
    - vars/secrets.yml              # Ansible decrypts at runtime

  tasks:
    - name: Set database password
      ansible.builtin.command:
        cmd: "psql -c \"ALTER USER app WITH PASSWORD '{{ db_password }}';\""
```

**Running a playbook with vault:**

```bash
# Prompt for password
ansible-playbook site.yml --ask-vault-pass

# Use a password file (for CI/CD)
ansible-playbook site.yml --vault-password-file ~/.vault_pass

# Use an environment variable (for CI/CD)
export ANSIBLE_VAULT_PASSWORD_FILE=~/.vault_pass
ansible-playbook site.yml
```

**Multiple vault passwords (Vault IDs):**

```bash
# Encrypt with a specific vault ID
ansible-vault encrypt --vault-id prod@prompt vars/prod_secrets.yml
ansible-vault encrypt --vault-id dev@~/.dev_vault_pass vars/dev_secrets.yml

# Run playbook with multiple vault IDs
ansible-playbook site.yml \
  --vault-id prod@prompt \
  --vault-id dev@~/.dev_vault_pass
```

**Best practices for Vault:**

- **Never commit plain-text secrets** — always encrypt before committing.
- **Use a vault password file in CI/CD** — inject the password via a secret manager (AWS Secrets Manager, HashiCorp Vault, GitHub Actions secrets).
- **Separate vault files by environment** — `vars/dev_secrets.yml`, `vars/prod_secrets.yml`.
- **Use `.gitignore` for the vault password file** — add `*.vault_pass` to `.gitignore`.
- **Rotate vault passwords periodically** — use `ansible-vault rekey`.

---

## Conclusion

Ansible is the go-to tool for configuration management, application deployment, and multi-tier orchestration in a DevOps workflow. Its agentless, SSH-based architecture means you can start automating existing infrastructure in minutes with no changes to managed nodes.

**The Complete Ansible Story:**

```
┌──────────────────────────────────────────────────────────────────┐
│  DevOps Engineer                                                 │
│  ansible-playbook site.yml                                       │
└─────────────────┬────────────────────────────────────────────────┘
                  │
                  ▼
        ┌─────────────────────┐
        │  Ansible Control    │
        │  Node               │
        ├─────────────────────┤
        │  Reads inventory    │
        │  Parses playbook    │
        │  Resolves variables │
        │  Renders templates  │
        └──────────┬──────────┘
                   │  SSH (parallel, up to forks limit)
        ┌──────────┼──────────────────┐
        │          │                  │
        ▼          ▼                  ▼
┌──────────┐ ┌──────────┐     ┌──────────┐
│ web-01   │ │ web-02   │ ... │ db-01    │
│ Tasks    │ │ Tasks    │     │ Tasks    │
│ executed │ │ executed │     │ executed │
│ in order │ │ in order │     │ in order │
└──────────┘ └──────────┘     └──────────┘
        │          │                  │
        └──────────┴──────────────────┘
                   │
                   ▼
          PLAY RECAP
          ok=5  changed=2  failed=0
```

**Key takeaways so far:**

- Ansible is **agentless** — only SSH and Python required on managed nodes.
- The **inventory** is the source of truth for which machines Ansible manages.
- **Ad-hoc commands** are for quick, one-off tasks; **playbooks** are for repeatable automation.
- **Variables and facts** make playbooks reusable across environments and hosts.
- **Handlers** fire once at the end of a play — the right pattern for service restarts.
- **Roles** bundle tasks, variables, and templates into shareable, testable units.
- **Ansible Vault** keeps secrets encrypted in version control — never commit plain-text passwords.

More sections (Templates/Jinja2, Dynamic Inventory, Ansible Tower/AWX, Testing with Molecule, Ansible with Docker/Kubernetes, Performance Tuning) will be added here as they are completed.

---

## References

- [Ansible Documentation](https://docs.ansible.com/)
- [Ansible Module Index](https://docs.ansible.com/ansible/latest/collections/index_module.html)
- [Ansible Galaxy](https://galaxy.ansible.com/)
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
