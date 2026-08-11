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
  - [Deploy an App Using Kubectl](#deploy-an-app-using-kubectl)
  - [Viewing Pods and Nodes](#viewing-pods-and-nodes)
  - [Expose Your App Publicly](#expose-your-app-publicly)
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

**Problem → Solution Flow:**

```
Without Kubernetes:
  App Crashes → Manual Restart Needed → Downtime
  Traffic Spike → Manual Scaling → Delay in Response
  Service Update → Manual Coordination → Risk of Failure

With Kubernetes:
  App Crashes → Auto-restart via controller
         ↓
  Traffic Spike → Auto-scale via HPA
         ↓
  Service Update → Declarative YAML → Rolling update (zero downtime)
         ↓
  Continuous Reconciliation: Desired State ↔ Actual State
```

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

**Architecture Comparison:**

```
Docker (Single Host):              Kubernetes (Multi-Host Cluster):
┌──────────────────────┐           ┌────────────────────────────────┐
│  Docker Host / VM    │           │   Control Plane                │
│                      │           │  ┌──────────────────────────┐  │
│  ┌────┐ ┌────┐       │           │  │ Orchestration, Scheduling│  │
│  │C-1 │ │C-2 │       │    vs.    │  │ State Management         │  │
│  └────┘ └────┘       │           │  └──────────────────────────┘  │
│  (Manual restart)    │           │                                 │
│  (Manual scale)      │           │  Worker Nodes (Many):           │
└──────────────────────┘           │  ┌──────────┐ ┌──────────┐     │
                                   │  │  Node 1  │ │  Node 2  │     │
                                   │  │┌──┐┌──┐ │ │┌──┐┌──┐  │     │
                                   │  │└──┘└──┘ │ │└──┘└──┘  │     │
                                   │  └──────────┘ └──────────┘     │
                                   │  (Auto restart, Auto scale)   │
                                   └────────────────────────────────┘
```

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

**Request Flow through Control Plane:**

```
User / CI/CD
     │
     │ kubectl apply -f deployment.yaml
     ▼
┌──────────────────────────────────────────────────────────┐
│              API Server (Gatekeeper)                     │
│  ├─ Validates request                                    │
│  ├─ Stores in etcd (Source of Truth)                     │
│  └─ Notifies watchers                                    │
└─────────────┬──────────────────────────────────────────────┘
              │
        ┌─────▼─────┐
        │   etcd     │
        │ (Database) │
        └─────┬──────┘
              │
      ┌───────┴────────┐
      │                │
      ▼                ▼
 Scheduler      Controller Manager
 (Watches for   (Watches for state
  unscheduled   drift, fixes it)
  pods)
      │                │
      └────────┬───────┘
               │
        ┌──────▼──────┐
        │ kubelet on  │
        │ Nodes       │
        │ (Execute)   │
        └─────────────┘
```

**Key insight:** Every component (except etcd) communicates only through the API Server — nothing talks to etcd directly. This makes the API Server the single point of consistency for the entire cluster.

---

### Worker Node Components

**Pod Execution Flow on Worker Node:**

```
API Server sends PodSpec to kubelet
              │
              ▼
         kubelet (Agent)
         ├─ Receives spec
         ├─ Validates
         ├─ Requests container runtime
         │
         ▼
    Container Runtime
    (containerd / CRI-O)
    ├─ Pulls image
    ├─ Creates container
    └─ Starts container
         │
         ▼
      Pod (Container(s) + Network namespace)
         │
         ├─ Container A
         ├─ Container B
         └─ Shared networking
              │
              ▼
         kube-proxy
         (Routes traffic to pod
          via iptables/ipvs rules)
```

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
| [Deploy an App Using Kubectl](#deploy-an-app-using-kubectl) | Run, expose, scale, and inspect a workload with kubectl imperatively |
| [Viewing Pods and Nodes](#viewing-pods-and-nodes) | Inspect cluster state — list, describe, and debug pods and nodes with kubectl |
| [Expose Your App Publicly](#expose-your-app-publicly) | Make your application accessible externally using Services, port-forward, and Ingress |

### Create a Cluster

Two tools dominate cluster creation depending on your context:

**Cluster Creation Workflows:**

```
┌─────────────────────────────────────┐
│  Choose Your Path                   │
├─────────────────────────────────────┤
│                                     │
├─ kind (Kubernetes IN Docker)       │
│  └─ Install kind                   │
│     └─ kind create cluster         │
│        └─ Cluster ready (secs)     │
│                                     │
├─ kubeadm (Production Setup)        │
│  ├─ Setup nodes (Ubuntu/CentOS)    │
│  ├─ Install containerd             │
│  ├─ Install kubeadm/kubelet/kubectl│
│  ├─ kubeadm init (control plane)   │
│  ├─ Install CNI (Calico)           │
│  ├─ kubeadm join (worker nodes)    │
│  └─ Cluster ready (mins)           │
│                                     │
└─────────────────────────────────────┘
```

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

### Deploy an App Using Kubectl

Once the cluster is running, the fastest way to get a workload up is with `kubectl` imperative commands — no YAML required for a first run.

**Deployment Lifecycle Flow:**

```
Step 1: Create Deployment
        kubectl create deployment hello-app --image=nginx:latest
              │
              ▼
        Deployment Created (desired replicas: 1)
              │
              ▼
Step 2: Verify & Inspect
        kubectl get deployments / pods
              │
              ▼
        Pods are Running
              │
              ▼
Step 3: Expose as Service
        kubectl expose deployment hello-app --type=NodePort --port=80
              │
              ▼
        Service Created (assigned a NodePort: 30XXX)
              │
              ▼
Step 4: Scale (Optional)
        kubectl scale deployment hello-app --replicas=3
              │
              ▼
        3 Pods Running (auto-scheduled across nodes)
              │
              ▼
Step 5: Monitor & Debug
        kubectl logs <pod-name>
        kubectl describe pod <pod-name>
              │
              ▼
Step 6: Clean Up
        kubectl delete service hello-app
        kubectl delete deployment hello-app
              │
              ▼
        Application Removed
```

**1 — Create a Deployment**

A Deployment manages a set of identical Pods and keeps the desired replica count healthy.

```bash
kubectl create deployment hello-app --image=nginx:latest
```

**2 — Verify the Deployment and Pod**

```bash
kubectl get deployments          # shows desired / ready / up-to-date counts
kubectl get pods                 # shows the pod(s) spawned by the deployment
kubectl describe pod <pod-name>  # full event log — useful when a pod is pending/crashing
```

**3 — Expose the Deployment as a Service**

A Service gives the Deployment a stable network endpoint. `NodePort` makes it reachable on a port of each node's IP:

```bash
kubectl expose deployment hello-app --type=NodePort --port=80
kubectl get services             # note the NodePort assigned (30000–32767 range)
```

For a local kind cluster, forward the port directly to your machine:

```bash
kubectl port-forward deployment/hello-app 8080:80
# Now open http://localhost:8080 in your browser
```

**4 — Scale the Deployment**

```bash
kubectl scale deployment hello-app --replicas=3
kubectl get pods                 # three pods should now be Running
```

**5 — Check logs**

```bash
kubectl logs <pod-name>          # stdout/stderr of the container
kubectl logs -f <pod-name>       # follow (stream) logs live
```

**6 — Clean up**

```bash
kubectl delete service hello-app
kubectl delete deployment hello-app
```

---

### Viewing Pods and Nodes

Once applications are running, inspecting cluster state is critical for debugging, monitoring, and understanding what's happening. This section covers the kubectl commands used to view pods and nodes.

**Inspection Workflow Flow:**

```
Cluster Running with Pods/Nodes
         │
    ┌────┴────┐
    │          │
    ▼          ▼
Get Overview  Describe Details
    │          │
    ├─┐      ├─┐
    │ ├─ Nodes    │ ├─ Node details (capacity, taints, conditions)
    │ ├─ Pods     │ ├─ Pod details (image, IP, events)
    │ ├─ Services │ ├─ Service endpoints
    │ └─ All (-A) │ └─ Resource status & history
    │            │
    ▼            ▼
Quick Snapshot  Troubleshooting
(List command)  (Describe command)
    │            │
    └─────┬──────┘
          │
    Debug & Resolve
```

**1 — Get Nodes**

Display all nodes in the cluster with their status and resource info.

```bash
kubectl get nodes                           # list all nodes
kubectl get nodes -o wide                   # show additional columns (Internal/External IP, OS Image)
kubectl get nodes -o json                   # get raw JSON output
kubectl describe node <node-name>           # detailed node info (capacity, allocated, taints, conditions)
```

**Example output:**

```
NAME             STATUS   ROLES           AGE     VERSION
kind-control-plane   Ready    control-plane   5m2s    v1.30.0
kind-worker          Ready    <none>          4m58s   v1.30.0
kind-worker2         Ready    <none>          4m56s   v1.30.0
```

**2 — Get Pods**

Display pods in the current namespace (default).

```bash
kubectl get pods                            # list pods in default namespace
kubectl get pods -n <namespace>             # list pods in a specific namespace
kubectl get pods -A                         # list pods in all namespaces
kubectl get pods -o wide                    # show pod IPs, node assignments, and restart count
kubectl get pods --selector=<label-key>=<label-value>    # filter by label
kubectl get pods --field-selector=status.phase=Running   # filter by field
```

**Example output:**

```
NAME                        READY   STATUS    RESTARTS   AGE
hello-app-8f8f8f8f8-abc12   1/1     Running   0          2m15s
hello-app-8f8f8f8f8-def45   1/1     Running   0          2m12s
hello-app-8f8f8f8f8-ghi78   1/1     Running   1          1m50s
```

**3 — Describe Pods**

Get detailed information about a specific pod (useful for debugging).

```bash
kubectl describe pod <pod-name>             # detailed pod info (events, conditions, containers)
kubectl describe pod <pod-name> -n <namespace>  # describe pod in specific namespace
```

**Helpful information from describe:**

- **Status** — Current state (Pending, Running, Succeeded, Failed, Unknown)
- **Conditions** — Ready, Initialized, etc., with timestamps
- **Events** — Chronological log of what happened to the pod (pulls, starts, errors)
- **Containers** — Image, port, resources requested/limited, environment

**4 — Get Services**

Display services and their cluster endpoints.

```bash
kubectl get services                        # list services in default namespace
kubectl get services -A                     # list services in all namespaces
kubectl get services -o wide                # show endpoint IPs and port mapping
kubectl describe service <service-name>     # detailed service info (selector, endpoints, type)
```

**5 — Get All Resources**

Display all resource types at once.

```bash
kubectl get all                             # pods, services, deployments, replicasets, statefulsets
kubectl get all -A                          # all resources in all namespaces
kubectl get all --field-selector=status.phase=Failed  # find failed resources
```

**6 — Pod Logs and Events**

Stream logs and examine events for troubleshooting.

```bash
kubectl logs <pod-name>                     # show pod's stdout/stderr
kubectl logs <pod-name> -f                  # follow logs live (like tail -f)
kubectl logs <pod-name> -p                  # logs from previous container (useful if pod crashed)
kubectl logs <pod-name> -c <container-name>    # logs from specific container in multi-container pod
kubectl logs <deployment-name> -l app=<app-label>  # logs from all pods matching a label

kubectl events                              # show cluster events (pod failures, node status changes)
kubectl get events -A                       # events in all namespaces
```

**7 — Pod Status Phases**

Understanding pod status phases helps you diagnose issues:

| Phase      | Meaning |
| ---------- | ------- |
| **Pending** | Pod created but not yet scheduled; waiting for node resources or image pull |
| **Running** | Pod scheduled and containers are running |
| **Succeeded** | Pod completed successfully (usually batch/job pods) |
| **Failed** | Pod crashed or one or more containers exited with non-zero code |
| **Unknown** | Pod state cannot be determined (usually communication issue with kubelet) |

**8 — Quick Debugging Commands**

```bash
kubectl describe pod <pod-name>             # check Events section for errors
kubectl logs <pod-name> --tail=20           # last 20 lines of logs
kubectl logs <pod-name> --timestamps=true   # add timestamps to log lines
kubectl top nodes                           # show CPU/memory usage of nodes
kubectl top pods                            # show CPU/memory usage of pods
kubectl exec -it <pod-name> -- /bin/sh      # open shell in pod for interactive debugging
```

**Common Troubleshooting Scenarios:**

| Issue | Investigation |
| ----- | -------------- |
| Pod stuck in **Pending** | `kubectl describe pod` → check Events for scheduling errors, node resource constraints |
| Pod in **CrashLoopBackOff** | `kubectl logs <pod-name>` → check previous logs with `-p` flag |
| Pod not receiving traffic | `kubectl get services` → verify endpoints are assigned; `kubectl describe service` → check selector matches pods |
| Node **NotReady** | `kubectl describe node` → check conditions and events; SSH to node and check kubelet status |

---

### Expose Your App Publicly

Running an app inside Kubernetes is only half the battle — you need to expose it so users (or other services) can access it. Kubernetes offers multiple ways to expose applications depending on your network topology and use case.

**Exposure Methods Comparison:**

```
Your Application Running in Pods (ClusterIP default)
         │
    ┌────┴──────────────────────────────────────┐
    │                                            │
    ▼                                            ▼
Internal Only                        External Access Needed
(ClusterIP Service)                         │
    │                        ┌───────────────┼───────────────┐
    │                        │               │               │
    ▼                        ▼               ▼               ▼
Pod-to-Pod DNS          kubectl           NodePort        LoadBalancer
Within cluster only     port-forward      High-numbered   Cloud LB assigns
                        Local dev         port (30k-32k)  external IP
                        only              Any node works
                                          
                        ┌─────────────────────────────────────┐
                        │   HTTP/HTTPS Routing Needed?        │
                        │   (Domain names, paths, TLS)        │
                        └────────────┬────────────────────────┘
                                     │
                                     ▼
                                 Ingress
                         (requires ingress controller)
```

**1 — Understanding Service Types**

A Kubernetes Service is an abstraction that defines how to expose pods. The type determines accessibility:

| Service Type | Use Case | Accessible From |
| ------------ | -------- | --------------- |
| **ClusterIP** (default) | Internal communication only | Only within cluster |
| **NodePort** | Development, testing, small deployments | Any client that can reach any node's IP:port |
| **LoadBalancer** | Production external access on cloud | Anyone on the internet (cloud assigns external IP) |
| **ExternalName** | Route to external service | DNS CNAME alias for external services |

**2 — ClusterIP Service (Internal Only)**

Exposed internally within the cluster — pods can reach each other via DNS.

```bash
# Create ClusterIP Service (default if type not specified)
kubectl expose deployment hello-app --type=ClusterIP --port=80
kubectl get services
```

**Inside a pod, you can now reach the service:**

```bash
# From within any pod in the cluster:
curl hello-app                          # use short name (same namespace)
curl hello-app.default.svc.cluster.local   # use FQDN (any namespace)
```

**Key points:**

- No external IP assigned (shows `<none>`)
- Only accessible from within the cluster
- Perfect for internal microservice communication
- DNS name is `<service-name>.<namespace>.svc.cluster.local`

**3 — NodePort Service (Accessible on Node IPs)**

Exposes a high-numbered port (30000–32767) on every node. Traffic to that port is forwarded to the pods.

```bash
# Create NodePort Service
kubectl expose deployment hello-app --type=NodePort --port=80
kubectl get services
```

**Example output:**

```
NAME        TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
hello-app   NodePort   10.96.123.45    <none>        80:30123/TCP   2m
```

The port `30123` is the NodePort — traffic sent to `<node-ip>:30123` reaches the app.

**Access the app from outside the cluster:**

```bash
# Get any node's IP
kubectl get nodes -o wide

# Access on any node (e.g., 192.168.1.100:30123)
curl 192.168.1.100:30123
curl 192.168.1.101:30123   # works on any node
curl 192.168.1.102:30123   # works on any node too

# For kind clusters, use localhost with port-forward
kubectl port-forward service/hello-app 8080:80
# Now curl http://localhost:8080
```

**NodePort drawbacks:**

- High-numbered ports are not user-friendly (port 30123 instead of 80)
- Must expose a port on every node
- Not recommended for production HTTP(S) traffic

**4 — LoadBalancer Service (Cloud-Native External Access)**

Requests Kubernetes to provision an external load balancer (available on cloud providers like AWS, GCP, Azure). The cloud assigns an external IP.

```bash
# Create LoadBalancer Service
kubectl expose deployment hello-app --type=LoadBalancer --port=80 --target-port=80
kubectl get services
```

**Example output (on AWS/GCP/Azure):**

```
NAME        TYPE           CLUSTER-IP      EXTERNAL-IP           PORT(S)        AGE
hello-app   LoadBalancer   10.96.123.45    a1b2c3d4.example.com   80:30456/TCP   1m
```

The `EXTERNAL-IP` is now a real external address — users can access it directly.

**Access from anywhere:**

```bash
curl a1b2c3d4.example.com
```

**LoadBalancer considerations:**

- Cloud provider must support it (works on EKS, GKE, AKS; not on bare-metal/on-prem)
- Each LoadBalancer Service gets its own external IP (costs money)
- One service per load balancer — not efficient for many services
- Great for non-HTTP protocols (TCP/UDP)

**5 — Port-Forward for Local Development**

Don't expose publicly — instead, forward a local port to a pod for testing.

```bash
# Forward local port 8080 to pod port 80
kubectl port-forward pod/<pod-name> 8080:80

# Forward to a service instead
kubectl port-forward service/hello-app 8080:80

# Forward from a deployment
kubectl port-forward deployment/hello-app 8080:80

# Bind to all interfaces (allow remote connections)
kubectl port-forward service/hello-app 8080:80 --address 0.0.0.0
```

**Use cases:**

- Debug an app locally without exposing it publicly
- Quick testing of a single pod/service
- No firewall rules or DNS changes needed

**6 — Ingress (HTTP(S) Routing at Layer 7)**

For HTTP(S) traffic, Ingress is the standard way to route traffic based on hostnames, paths, and TLS. A single external IP can route to many services.

**Why Ingress over LoadBalancer:**

- One external IP routes to many services (save costs)
- Path-based routing (`/api`, `/web`)
- Hostname-based routing (`api.example.com`, `web.example.com`)
- Automatic HTTPS/TLS termination
- More flexible and cloud-agnostic

**Prerequisites:**

- An Ingress controller must be installed (e.g., NGINX Ingress Controller, Traefik)
- For kind, install it with: `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml`

**Create an Ingress resource:**

```yaml
# ingress.yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: hello-ingress
spec:
  ingressClassName: nginx
  rules:
  - host: hello.local
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: hello-app
            port:
              number: 80
```

**Apply and test:**

```bash
kubectl apply -f ingress.yaml
kubectl get ingress

# Add to your /etc/hosts file:
# 127.0.0.1 hello.local

# Now access via hostname:
curl http://hello.local
```

**Ingress with multiple services:**

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: multi-service-ingress
spec:
  ingressClassName: nginx
  rules:
  - host: example.com
    http:
      paths:
      - path: /api
        pathType: Prefix
        backend:
          service:
            name: api-service
            port:
              number: 8080
      - path: /web
        pathType: Prefix
        backend:
          service:
            name: web-service
            port:
              number: 80
  - host: admin.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: admin-service
            port:
              number: 3000
```

**7 — Choosing the Right Exposure Method**

| Scenario | Use This | Why |
| -------- | -------- | --- |
| Local development | **port-forward** | No setup, quick, only exposes to you |
| Testing on LAN | **NodePort** | Works anywhere, no cloud required |
| Production on cloud | **LoadBalancer** | Cloud manages external IP, simple |
| Multiple HTTP services on one IP | **Ingress** | Cost-efficient, better UX, path/hostname routing |
| Non-HTTP protocol (TCP/UDP) | **LoadBalancer** | Ingress only handles HTTP(S) |
| External service routing | **ExternalName** | DNS alias to outside service |

**8 — Verifying External Access**

```bash
# Verify service is created and has endpoints
kubectl describe service hello-app

# Check if endpoints are assigned (pods are selected)
kubectl get endpoints hello-app

# For LoadBalancer, check for external IP
kubectl get services -o wide

# For Ingress, check ingress status and endpoints
kubectl get ingress
kubectl describe ingress hello-ingress
```

**Common issues:**

| Issue | Fix |
| ----- | --- |
| Service has no endpoints | Selector doesn't match pods; check `kubectl get pods --show-labels` |
| LoadBalancer stuck in `<pending>` | Cloud provider doesn't support it or quota exceeded |
| Ingress has no IP | Ingress controller not installed; install the appropriate controller for your cluster |
| Firewall blocks external traffic | Open required ports in cloud security groups / on-prem firewall |

---

## Conclusion

Kubernetes is the industry-standard platform for running containerized workloads at scale. This section covers the mental model needed before writing a single YAML manifest.

**The Complete Kubernetes Story:**

```
┌──────────────────────────────────────────────────────────────┐
│  Developer / DevOps Engineer                                 │
│  kubectl apply -f deployment.yaml                            │
└─────────────────┬──────────────────────────────────────────────┘
                  │
                  ▼
        ┌─────────────────────┐
        │  Kubernetes Cluster │
        ├─────────────────────┤
        │                     │
        │  Control Plane:     │
        │  ├─ API Server      │
        │  ├─ Scheduler       │
        │  ├─ Controller Mgr  │
        │  └─ etcd (store)    │
        │                     │
        │  Worker Nodes:      │
        │  ├─ Node 1          │
        │  │  ├─ Pods         │
        │  │  ├─ kubelet      │
        │  │  └─ kube-proxy   │
        │  ├─ Node 2          │
        │  └─ Node 3          │
        │                     │
        │  Continuously:      │
        │  Desired State ↔    │
        │  Actual State       │
        │  (Self-healing,     │
        │   Auto-scaling,     │
        │   Load-balancing)   │
        │                     │
        └─────────────────────┘
                  │
                  ▼
        Application Running & Healthy
```

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
