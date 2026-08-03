<h1 align="center">Kubernetes Learning Notes</h1>

<p align="center">
  A personal collection of Kubernetes commands, concepts,<br>
  and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes">
  <img src="https://img.shields.io/badge/kubectl-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="kubectl">
  <img src="https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white" alt="Helm">
  <img src="https://img.shields.io/badge/DevOps-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="DevOps">
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
  <a href="../Git-Github/README.md"><b>Git &amp; GitHub Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Linux/README.md"><b>Linux Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Networking/README.md"><b>Networking Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Cloud-Engineering/README.md"><b>Cloud Engineering Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Docker/README.md"><b>Docker Notes</b></a>
</p>

---

## Table of Contents

- [Introduction](#introduction)
- [Kubernetes Commands](#kubernetes-commands)
- [Kubernetes Fundamentals](#kubernetes-fundamentals)
  - [One Shot Revision](#one-shot-revision)
  - [What is Kubernetes?](#what-is-kubernetes)
  - [Kubernetes vs Docker](#kubernetes-vs-docker)
  - [Kubernetes Architecture](#kubernetes-architecture)
  - [Control Plane Components](#control-plane-components)
  - [Worker Node Components](#worker-node-components)
- [Kubernetes Basics](#kubernetes-basics)
  - [One Shot Revision](#one-shot-revision-1)
  - [Create a Cluster](#create-a-cluster)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction

Brief notes about Kubernetes — the open-source container orchestration platform that automates deployment, scaling, and management of containerized applications.

- **Focus:** Deploying, scaling, and managing containerized workloads with Kubernetes.
- **Scope:** Pods → Deployments → Services → Namespaces → ConfigMaps → Secrets → Volumes → Helm.
- **Goal:** Build strong Kubernetes fundamentals for DevOps interview prep and day-to-day workflows.

**Learn from the official source:**

→ [Kubernetes Documentation](https://kubernetes.io/docs/home/)

---

## Kubernetes Commands

Kubernetes' primary CLI is `kubectl` — it lets you create, inspect, update, and delete Kubernetes resources. Every command follows the pattern `kubectl <verb> <resource> [options]`. Common verbs: `get`, `describe`, `apply`, `delete`, `logs`, `exec`, `scale`, `rollout`.

For the full list of commands and flags, see the **[kubectl Reference →](https://kubernetes.io/docs/reference/kubectl/)**

---

## Kubernetes Fundamentals

Before touching any command, it helps to build a clear mental picture of what Kubernetes is, why it exists, and how its pieces fit together. This section is the "story" behind every command in the rest of the notes.

### One Shot Revision

| Topic                                                             | Short Description                                                                 |
| ----------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| [What is Kubernetes?](#what-is-kubernetes)                        | Container orchestration platform that automates deployment, scaling, and healing  |
| [Kubernetes vs Docker](#kubernetes-vs-docker)                     | Docker runs containers; Kubernetes orchestrates many containers across many hosts |
| [Kubernetes Architecture](#kubernetes-architecture)               | Control plane manages state; worker nodes run workloads                           |
| [Control Plane Components](#control-plane-components)             | API Server, etcd, Scheduler, Controller Manager — the cluster brain               |
| [Worker Node Components](#worker-node-components)                 | kubelet, kube-proxy, container runtime — execute and expose workloads             |

### What is Kubernetes?

**In one sentence:** Kubernetes (K8s) is an open-source platform that automates deploying, scaling, and operating containerized applications across a cluster of machines.

Without an orchestrator, running containers in production means manual restarts on failure, no automatic scaling under load, and hand-stitched networking between services. Kubernetes solves this by declaring the **desired state** (e.g., "run 3 replicas of my API") and continuously reconciling the cluster to match it.

**Why it matters for DevOps:**

- **Self-healing** — crashed containers restart automatically; unhealthy nodes are replaced.
- **Horizontal scaling** — scale workloads up or down with a single command or automatically via HPA.
- **Declarative configuration** — describe infrastructure in YAML; apply it anywhere.
- **Service discovery & load balancing** — built-in DNS and load balancing between pods.
- **Rolling updates & rollbacks** — zero-downtime deployments with one-command rollback.

**Name origin:** "Kubernetes" is Greek for *helmsman* — the person who steers the ship. The abbreviation **K8s** counts the 8 letters between "K" and "s".

---

### Kubernetes vs Docker

Docker and Kubernetes are complementary, not competing, tools.

| Aspect              | Docker                                              | Kubernetes                                               |
| ------------------- | --------------------------------------------------- | -------------------------------------------------------- |
| **What it does**    | Builds and runs containers on a single host         | Orchestrates containers across a cluster of many hosts   |
| **Scope**           | One machine                                         | Many machines (nodes)                                    |
| **Scheduling**      | Manual — you choose which host                      | Automatic — scheduler picks the best node                |
| **Self-healing**    | No — you restart failed containers yourself         | Yes — controllers restart, reschedule, and replace pods  |
| **Scaling**         | Manual — run more `docker run` commands             | Automatic — `kubectl scale` or HPA adjusts replicas      |
| **Networking**      | Bridge/overlay per host                             | Flat pod network across all nodes; built-in DNS          |
| **Config mgmt**     | `--env`, `--env-file`, bind mounts                  | ConfigMaps, Secrets, mounted as env vars or volumes      |
| **Compose equiv.**  | `docker compose up`                                 | `kubectl apply -f` (YAML manifests)                      |

**Mental model:** Docker is the engine under the hood; Kubernetes is the autopilot that decides when and where to run each container, keeps the right number running, and routes traffic to healthy instances.

---

### Kubernetes Architecture

A Kubernetes **cluster** is made up of two logical layers:

1. **Control Plane** — the brain of the cluster. Stores cluster state, makes scheduling decisions, and reconciles desired vs actual state.
2. **Worker Nodes** — the muscles. Each node runs a container runtime (usually containerd), a `kubelet` agent, and a `kube-proxy`. This is where your application pods actually live.

```
┌─────────────────────────────────────────────────────────────┐
│                        Control Plane                        │
│  ┌──────────────┐  ┌──────┐  ┌────────────┐  ┌──────────┐  │
│  │  API Server  │  │ etcd │  │ Scheduler  │  │Controller│  │
│  │  (kube-      │  │      │  │ (kube-     │  │ Manager  │  │
│  │  apiserver)  │  │      │  │ scheduler) │  │          │  │
│  └──────┬───────┘  └──────┘  └────────────┘  └──────────┘  │
└─────────┼───────────────────────────────────────────────────┘
          │  (HTTPS / watch)
┌─────────┼──────────────────────────────────────────────────┐
│         │            Worker Node 1                          │
│  ┌──────▼───────┐  ┌─────────────┐  ┌──────────────────┐  │
│  │   kubelet    │  │  kube-proxy │  │ container runtime │  │
│  └──────────────┘  └─────────────┘  └──────────────────┘  │
│  ┌──────────────────────────────────────────────────────┐  │
│  │  Pod  [container A]  [container B]  (shared network) │  │
│  └──────────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────┘
          (same pattern repeats for Node 2, Node 3, …)
```

**Flow of a deployment:**

1. You run `kubectl apply -f deployment.yaml`.
2. `kubectl` sends the manifest to the **API Server** over HTTPS.
3. The API Server validates and persists it in **etcd**.
4. The **Scheduler** watches for unscheduled pods and assigns each to a node.
5. The **kubelet** on that node pulls the image and starts the container via the container runtime.
6. **Controllers** continuously compare desired state (etcd) with actual state and fix any drift.

---

### Control Plane Components

| Component              | Role                                                                                                    |
| ---------------------- | ------------------------------------------------------------------------------------------------------- |
| **kube-apiserver**     | The single front door for all cluster operations. Every `kubectl` call hits this REST API.              |
| **etcd**               | Distributed key-value store — the source of truth for all cluster state. Back it up.                   |
| **kube-scheduler**     | Watches for unscheduled pods and assigns them to nodes based on resource requests, affinity, taints.   |
| **kube-controller-manager** | Runs built-in controllers: Node, Replication, Endpoints, ServiceAccount controllers, and more.   |
| **cloud-controller-manager** | Optional; talks to cloud APIs to provision load balancers, persistent disks, and node objects.  |

**Key insight:** Every component (except etcd) communicates only through the API Server — nothing talks to etcd directly. This makes the API Server the single point of consistency for the entire cluster.

---

### Worker Node Components

| Component             | Role                                                                                                      |
| --------------------- | --------------------------------------------------------------------------------------------------------- |
| **kubelet**           | Agent running on every node. Receives PodSpecs from the API Server and ensures the described containers are running and healthy. |
| **kube-proxy**        | Maintains network rules (iptables/ipvs) on each node to implement Kubernetes Services — routing traffic to the right pods. |
| **Container runtime** | The software that actually runs containers — usually **containerd** (or CRI-O). Docker Engine can also be used via a shim. |

---

## Kubernetes Basics

Hands-on foundation — from spinning up a cluster to running your first workload. Every concept from the Fundamentals section becomes concrete here.

### One Shot Revision

| Topic | Short Description |
| ----- | ----------------- |
| [Create a Cluster](#create-a-cluster) | Bootstrap a real cluster with kubeadm or a local dev cluster with kind |

### Create a Cluster

Two tools dominate cluster creation depending on your context:

| Tool | Best For | What It Creates |
| ---- | -------- | --------------- |
| **kind** | Local development / CI | Cluster running inside Docker containers |
| **kubeadm** | Production / bare-metal / VMs | Real multi-node cluster on Linux hosts |

---

#### Using kind

`kind` (**K**ubernetes **IN** **D**ocker) runs a full Kubernetes cluster inside Docker containers. Ideal for local development, CI pipelines, and quick experimentation — no VMs needed.

**Prerequisites:**
- Docker installed and running
- `kubectl` installed

**Install kind**

```bash
# macOS
brew install kind

# Linux
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.23.0/kind-linux-amd64
chmod +x ./kind && sudo mv ./kind /usr/local/bin/kind
```

**Create a single-node cluster (quickstart)**

```bash
kind create cluster
```

kind automatically sets the current `kubectl` context to point at the new cluster.

```bash
kubectl cluster-info --context kind-kind
kubectl get nodes
```

**Create a named multi-node cluster**

Write a config file and pass it to `kind create`:

```yaml
# cluster-config.yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
  - role: control-plane
  - role: worker
  - role: worker
```

```bash
kind create cluster --name dev-cluster --config cluster-config.yaml
kubectl get nodes --context kind-dev-cluster
```

**Load a local Docker image into kind**

kind nodes don't share your local Docker registry — images must be loaded explicitly:

```bash
docker build -t my-app:latest .
kind load docker-image my-app:latest --name dev-cluster
```

**Delete a cluster**

```bash
kind delete cluster --name dev-cluster
```

**List all kind clusters**

```bash
kind get clusters
```

---

#### Using kubeadm

`kubeadm` is the official Kubernetes bootstrap tool. It sets up the control plane and joins worker nodes onto the cluster.

**Prerequisites (all nodes):**
- Ubuntu 22.04 / CentOS 9 (or equivalent Linux)
- 2 GB RAM, 2 CPUs minimum per node
- Unique hostname, MAC address, and `product_uuid` on every node
- Swap disabled
- `containerd` installed as the container runtime
- Required ports open per the [Kubernetes networking docs](https://kubernetes.io/docs/reference/networking/ports-and-protocols/)

**Step 1 — Disable swap (all nodes)**

```bash
sudo swapoff -a
sudo sed -i '/ swap / s/^/#/' /etc/fstab
```

**Step 2 — Install containerd (all nodes)**

```bash
sudo apt-get update
sudo apt-get install -y containerd
sudo mkdir -p /etc/containerd
containerd config default | sudo tee /etc/containerd/config.toml
sudo systemctl restart containerd && sudo systemctl enable containerd
```

**Step 3 — Install kubeadm, kubelet, kubectl (all nodes)**

```bash
sudo apt-get install -y apt-transport-https ca-certificates curl

curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | \
  sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg

echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] \
  https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /' | \
  sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

`apt-mark hold` prevents these packages from being auto-upgraded and breaking the cluster.

**Step 4 — Initialize the control plane (master node only)**

```bash
sudo kubeadm init --pod-network-cidr=192.168.0.0/16
```

After the command succeeds, copy the `kubeadm join` command printed at the bottom — you will need it in Step 7 to add worker nodes.

**Step 5 — Configure kubectl (master node)**

```bash
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

**Step 6 — Install a pod network (CNI) add-on (master node)**

Without a CNI plugin, pods on different nodes cannot communicate. Calico is a common choice:

```bash
kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
```

**Step 7 — Join worker nodes**

Run the `kubeadm join` command (from Step 4 output) on each worker node:

```bash
sudo kubeadm join <control-plane-ip>:6443 \
  --token <token> \
  --discovery-token-ca-cert-hash sha256:<hash>
```

**Verify the cluster**

```bash
kubectl get nodes        # all nodes should show Ready
kubectl get pods -A      # all system pods should be Running or Completed
```

---

> **Quick pick guide:**
> - Local dev / CI → use **kind** (fast, zero infrastructure cost)
> - Real VMs / bare-metal / on-prem production → use **kubeadm**
> - Managed cloud cluster → use your cloud provider's tool (EKS, GKE, AKS)

---

## Conclusion

Kubernetes is the industry-standard platform for running containerized workloads at scale. This section covers the mental model needed before writing a single YAML manifest.

**Key takeaways so far:**

- Kubernetes declares **desired state** and continuously reconciles the cluster to match it.
- The **control plane** stores state and makes decisions; **worker nodes** run workloads.
- The **API Server** is the single entry point — all components speak through it.
- Docker builds and runs containers; Kubernetes **orchestrates** them at scale.
- Use **kind** for local development and **kubeadm** for production cluster bootstrapping.

More sections (Pods, Deployments, Services, Namespaces, ConfigMaps, Secrets, Volumes, Helm) will be added here as they are completed.

---

## References

- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [The Kubernetes Book — Nigel Poulton](https://nigelpoulton.com/books/)
- [BongoDev](https://www.bongodev.com/)
- [BongoDev on GitHub](https://github.com/bongodev)
- [k8sStarter](https://github.com/TahshinSharon/k8sStarter)

---

<p align="center">
  <sub>Part of the <a href="../README.md"><b>DevOps Preparation</b></a> repository — maintained by <b>Tahshin Sharon</b></sub>
</p>

<p align="center">
  <a href="https://tahshinsharon.github.io/"><b>Visit My Portfolio</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/TahshinSharon"><b>GitHub</b></a>
</p>
