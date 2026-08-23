<h1 align="center">Cloud Engineering Learning Notes</h1>

<p align="center">
  A personal collection of Cloud Engineering services, concepts,<br>
  and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS">
  <img src="https://img.shields.io/badge/Global%20Infrastructure-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" alt="Global Infrastructure">
  <img src="https://img.shields.io/badge/Free%20Tier-29A845?style=for-the-badge&logo=amazonaws&logoColor=white" alt="Free Tier">
  <img src="https://img.shields.io/badge/Pricing%20Models-0D1A26?style=for-the-badge&logo=amazonaws&logoColor=white" alt="Pricing Models">
  <img src="https://img.shields.io/badge/IAM-DD344C?style=for-the-badge&logo=amazonaws&logoColor=white" alt="IAM">
  <img src="https://img.shields.io/badge/S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white" alt="S3">
  <img src="https://img.shields.io/badge/EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white" alt="EC2">
  <img src="https://img.shields.io/badge/Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white" alt="Cloud">
  <img src="https://img.shields.io/badge/DevOps-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="DevOps">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-13-blue?style=flat-square" alt="Sections">
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
  <a href="../Docker/README.md"><b>Docker Notes</b></a>
  &nbsp;·&nbsp;
  <a href="../Kubernetes/README.md"><b>Kubernetes Notes</b></a>
</p>

---

## Table of Contents

- [Introduction](#introduction)
- [Command Note Template](#command-note-template)
- [Cloud Computing Models](#cloud-computing-models)
  - [One Shot Revision](#one-shot-revision)
  - [IaaS — Infrastructure as a Service](#iaas--infrastructure-as-a-service)
  - [PaaS — Platform as a Service](#paas--platform-as-a-service)
  - [SaaS — Software as a Service](#saas--software-as-a-service)
  - [FaaS — Function as a Service](#faas--function-as-a-service)
  - [Deployment Models](#deployment-models)
  - [Shared Responsibility Model](#shared-responsibility-model)
- [AWS Global Infrastructure](#aws-global-infrastructure)
  - [One Shot Revision](#one-shot-revision-1)
  - [Regions](#regions)
  - [Availability Zones](#availability-zones)
  - [Edge Locations & Points of Presence](#edge-locations--points-of-presence)
  - [Local Zones & Wavelength Zones](#local-zones--wavelength-zones)
  - [AWS Outposts](#aws-outposts)
  - [How to Choose a Region](#how-to-choose-a-region)
- [AWS Free Tier](#aws-free-tier)
  - [One Shot Revision](#one-shot-revision-2)
  - [Free Tier Types](#free-tier-types)
  - [Key Services in the Free Tier](#key-services-in-the-free-tier)
  - [Monitoring Free Tier Usage](#monitoring-free-tier-usage)
  - [Avoiding Unexpected Charges](#avoiding-unexpected-charges)
- [AWS Pricing Models](#aws-pricing-models)
  - [One Shot Revision](#one-shot-revision-3)
  - [On-Demand](#on-demand)
  - [Reserved Instances & Savings Plans](#reserved-instances--savings-plans)
  - [Spot Instances](#spot-instances)
  - [Dedicated Hosts & Dedicated Instances](#dedicated-hosts--dedicated-instances)
  - [Pricing Calculators & Cost Tools](#pricing-calculators--cost-tools)
- [AWS Access Methods](#aws-access-methods)
  - [One Shot Revision](#one-shot-revision-4)
  - [AWS Management Console](#aws-management-console)
  - [AWS CLI](#aws-cli)
  - [AWS SDKs](#aws-sdks)
  - [AWS CloudShell](#aws-cloudshell)
  - [AWS REST APIs](#aws-rest-apis)
  - [Infrastructure as Code](#infrastructure-as-code)
- [IAM — Identity and Access Management](#iam--identity-and-access-management)
  - [One Shot Revision](#one-shot-revision-5)
  - [IAM Overview](#iam-overview)
  - [IAM Users & Groups](#iam-users--groups)
  - [IAM Roles](#iam-roles)
  - [IAM Policies](#iam-policies)
  - [IAM Best Practices](#iam-best-practices)
- [Amazon S3](#amazon-s3)
  - [One Shot Revision](#one-shot-revision-6)
  - [S3 Overview](#s3-overview)
  - [S3 Buckets & Objects](#s3-buckets--objects)
  - [S3 Storage Classes](#s3-storage-classes)
  - [S3 Security](#s3-security)
- [Elastic Compute Cloud](#elastic-compute-cloud)
  - [One Shot Revision](#one-shot-revision-7)
  - [EC2 Overview](#ec2-overview)
  - [EC2 Instance Types](#ec2-instance-types)
  - [AMIs — Amazon Machine Images](#amis--amazon-machine-images)
  - [EC2 Security Groups](#ec2-security-groups)
  - [EBS — Elastic Block Store](#ebs--elastic-block-store)
  - [Key Pairs & SSH Access](#key-pairs--ssh-access)
- [AWS CLI](#aws-cli-1)
  - [One Shot Revision](#one-shot-revision-9)
  - [AWS CLI Overview](#aws-cli-overview)
  - [Installation & Configuration](#installation--configuration)
  - [CLI Profiles & Credentials](#cli-profiles--credentials)
  - [Output Formats & Query Syntax](#output-formats--query-syntax)
  - [Common Service Commands](#common-service-commands)
  - [Advanced CLI Techniques](#advanced-cli-techniques)
- [CloudWatch](#cloudwatch)
  - [One Shot Revision](#one-shot-revision-10)
  - [CloudWatch Overview](#cloudwatch-overview)
  - [CloudWatch Logs](#cloudwatch-logs)
  - [CloudWatch Metrics](#cloudwatch-metrics)
  - [Install CloudWatch Agent](#install-cloudwatch-agent)
  - [CloudWatch Alarms](#cloudwatch-alarms)
  - [CloudWatch Dashboards](#cloudwatch-dashboards)
  - [CloudWatch Log Insights](#cloudwatch-log-insights)
  - [Container Insights](#container-insights)
  - [CloudWatch Synthetics](#cloudwatch-synthetics)
- [Elastic Load Balancer (ELB)](#elastic-load-balancer-elb)
  - [One Shot Revision](#one-shot-revision-11)
  - [ELB Overview](#elb-overview)
  - [Types of Load Balancers](#types-of-load-balancers)
  - [ELB Architecture](#elb-architecture)
  - [Listeners & Routing Rules](#listeners--routing-rules)
  - [Target Groups](#target-groups)
  - [Health Checks](#health-checks)
  - [Sticky Sessions](#sticky-sessions)
  - [SSL/TLS Termination](#ssltls-termination)
  - [ELB Best Practices](#elb-best-practices)
  - [Reference](#reference)
- [Auto Scaling](#auto-scaling)
  - [One Shot Revision](#one-shot-revision-12)
  - [Auto Scaling Overview](#auto-scaling-overview)
  - [Auto Scaling Groups (ASG)](#auto-scaling-groups-asg)
  - [Launch Templates & Launch Configurations](#launch-templates--launch-configurations)
  - [Scaling Policies](#scaling-policies)
  - [Scheduled Actions](#scheduled-actions)
  - [Lifecycle Hooks](#lifecycle-hooks)
  - [Health Checks & Instance Replacement](#health-checks--instance-replacement)
  - [Auto Scaling Best Practices](#auto-scaling-best-practices)
  - [Reference](#reference-1)
- [RDS Basics](#rds-basics)
  - [One Shot Revision](#one-shot-revision-13)
  - [RDS Overview](#rds-overview)
  - [Database Engines](#database-engines)
  - [Create an RDS Instance](#create-an-rds-instance)
  - [RDS Storage & Backups](#rds-storage--backups)
  - [Multi-AZ & High Availability](#multi-az--high-availability)
  - [Read Replicas](#read-replicas)
  - [RDS Security](#rds-security)
  - [Parameter Groups](#parameter-groups)
  - [RDS Monitoring & Performance Insights](#rds-monitoring--performance-insights)
  - [RDS Best Practices](#rds-best-practices)
  - [Aurora RDS](#aurora-rds)
  - [Reference](#reference-2)
- [Useful Tips & Tricks](#useful-tips--tricks)
- [References](#references)

---

## Introduction

Brief notes about Cloud Engineering, the major providers and services, and the goal of these notes.

- **Focus:** Cloud-native services on AWS (and equivalents on other providers) used to build, deploy, and scale infrastructure.
- **Scope:** Compute → storage → networking → identity → automation → cost & observability.
- **Goal:** Build strong cloud fundamentals for DevOps interview prep and day-to-day infrastructure work.

---

## Command Note Template

Use this format whenever a new command or service is added.

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

## Cloud Computing Models

Cloud computing is delivered in three primary **service models** and four **deployment models**. Understanding these models helps you choose the right level of control versus managed convenience for any workload, and is the foundation for every AWS architectural decision.

### One Shot Revision

| Topic | Short Description |
| --- | --- |
| [IaaS — Infrastructure as a Service](#iaas--infrastructure-as-a-service) | Raw compute, storage, and networking — you manage the OS upward |
| [PaaS — Platform as a Service](#paas--platform-as-a-service) | Managed runtime — you manage code and data only |
| [SaaS — Software as a Service](#saas--software-as-a-service) | Fully managed application delivered over the internet |
| [FaaS — Function as a Service](#faas--function-as-a-service) | Event-driven serverless execution — you manage functions only |
| [Deployment Models](#deployment-models) | Public, Private, Hybrid, Multi-Cloud |
| [Shared Responsibility Model](#shared-responsibility-model) | What AWS manages vs. what you manage |

---

### IaaS — Infrastructure as a Service

**Infrastructure as a Service (IaaS)** is the most fundamental cloud service model. The cloud provider supplies virtualised compute, storage, and networking resources over the internet. You retain full control of the operating system and everything above it — which means maximum flexibility but also maximum responsibility.

The analogy: the provider gives you an empty plot of land with utilities (power, water, connectivity). You build the house.

#### What is IaaS

| Layer | Managed by |
| --- | --- |
| Physical hardware, data centre | Cloud provider |
| Hypervisor / virtualisation | Cloud provider |
| Virtual Machines (compute) | Cloud provider creates, **you configure** |
| Operating System | **You** |
| Runtime and middleware | **You** |
| Application | **You** |
| Data | **You** |

**Key characteristics:**
- **On-demand provisioning** — spin up and tear down resources in minutes via API, console, or CLI.
- **Pay-as-you-go** — billed per hour or per second; no upfront hardware purchase.
- **Elastic scaling** — increase or decrease resource allocation without physical intervention.
- **Multi-tenancy** — physical hardware is shared across customers; logical isolation is enforced by the hypervisor.
- **Self-service** — you manage resources directly without raising tickets with a vendor.

**Notes:**
- IaaS gives you the same level of access as owning a bare-metal server — minus the physical maintenance. You still need to harden the OS, apply patches, configure firewalls, and manage software.
- Because you control the OS, IaaS is the only model that supports arbitrary kernel modules, custom drivers, or non-standard runtimes.

---

#### IaaS Core Components

Every IaaS offering bundles three resource categories:

**Compute:**

| Resource | Description | AWS service |
| --- | --- | --- |
| Virtual Machine | Emulated server running a full OS | EC2 instance |
| Bare Metal | Physical server without a hypervisor layer | EC2 Bare Metal instance |
| Auto Scaling | Automatically adjust the number of VMs based on load | EC2 Auto Scaling Group |

**Storage:**

| Type | Description | AWS service |
| --- | --- | --- |
| Block storage | Raw disk attached to a single VM; formatted with a filesystem | EBS (Elastic Block Store) |
| Object storage | Flat namespace for files/blobs accessed via HTTP | S3 |
| File storage | Shared NFS/SMB filesystem mounted by multiple VMs | EFS (Elastic File System) |
| Archive storage | Very low-cost, high-latency cold storage | S3 Glacier |

**Networking:**

| Resource | Description | AWS service |
| --- | --- | --- |
| Virtual private network | Isolated virtual network with its own IP space | VPC |
| Public IP address | Static or dynamic public IPv4 address | Elastic IP (EIP) |
| Load balancer | Distributes traffic across multiple instances | ELB (ALB / NLB / CLB) |
| DNS | Domain name routing | Route 53 |
| Firewall | Stateful packet filtering at the instance or subnet level | Security Groups / NACLs |

---

#### IaaS on AWS

AWS is the largest IaaS provider. The core IaaS services:

| Service | Category | What it provides |
| --- | --- | --- |
| **EC2** | Compute | Virtual servers (instances) — choose OS, instance type, region |
| **EBS** | Block storage | Persistent disk volumes attached to EC2 instances |
| **S3** | Object storage | Highly durable object store — 99.999999999% (11 nines) durability |
| **VPC** | Networking | Isolated virtual network — subnets, route tables, internet gateways |
| **ELB** | Load balancing | Application (HTTP/HTTPS), Network (TCP/UDP), and Classic load balancers |
| **EFS** | File storage | Managed NFS file system shared across multiple EC2 instances |
| **Auto Scaling** | Elasticity | Scale EC2 fleets up/down automatically based on CloudWatch metrics |
| **Elastic IP** | Networking | Static public IPv4 address that can be re-associated across instances |

**How the IaaS layers map to AWS services:**

```
Physical hardware       → AWS data centres (customer never sees this)
Hypervisor              → AWS Nitro System (custom hypervisor)
Virtual Machine         → EC2 instance
OS disk                 → EBS root volume
Additional storage      → EBS data volumes / EFS / S3
Network interface       → Elastic Network Interface (ENI) inside a VPC
Public connectivity     → Internet Gateway + Elastic IP or NAT Gateway
Load balancing          → ELB (ALB / NLB)
DNS                     → Route 53
Firewall                → Security Groups (instance-level) + NACLs (subnet-level)
```

---

#### IaaS Use Cases

| Use Case | Why IaaS fits |
| --- | --- |
| **Lift-and-shift migration** | Move an on-premises VM to EC2 with minimal application changes |
| **Custom OS or kernel** | Run Red Hat, Windows Server, or any OS with custom kernel modules |
| **High-performance computing (HPC)** | GPU instances (P-series, G-series) or compute-optimised instances for ML training |
| **Legacy software** | Applications that require a specific OS version or cannot be containerised |
| **Disaster recovery** | Replicate on-premises servers to EC2 AMIs; spin up in minutes during a failover |
| **Dev/test environments** | Provision short-lived environments on demand and terminate when done |
| **Database servers** | Run MySQL, PostgreSQL, or Oracle on EC2 with full DBA control |

**When NOT to use IaaS:**
- When you don't need OS-level control — use PaaS (Elastic Beanstalk, RDS) to reduce operational overhead.
- For stateless, event-driven workloads — use FaaS (Lambda) to eliminate idle compute costs.
- For off-the-shelf applications — use SaaS to eliminate all infrastructure management.

**Notes:**
- The most common IaaS anti-pattern is treating EC2 instances as permanent, manually configured servers ("pet" servers). The modern approach uses Auto Scaling, Launch Templates, and immutable AMIs so that instances are disposable ("cattle").
- Always attach an IAM role to EC2 instances instead of embedding credentials — the role grants temporary, automatically-rotated credentials via the instance metadata service (IMDS).

---

### PaaS — Platform as a Service

**Platform as a Service (PaaS)** abstracts away the operating system, runtime, and underlying infrastructure. You provide application code and configuration; the platform handles provisioning, patching, scaling, and availability automatically.

The analogy: the provider gives you a furnished apartment. You bring your belongings and arrange them — but you don't deal with plumbing, wiring, or structural maintenance.

#### What is PaaS

| Layer | Managed by |
| --- | --- |
| Physical hardware, data centre | Cloud provider |
| Hypervisor / virtualisation | Cloud provider |
| Operating System | Cloud provider |
| Runtime (Node, Python, Java JVM, etc.) | Cloud provider |
| Middleware and app server | Cloud provider |
| Application code and configuration | **You** |
| Data | **You** |

**Key characteristics:**
- **Zero OS management** — the provider patches the OS and runtime; you never SSH into the underlying server.
- **Managed scaling** — the platform automatically scales the runtime environment in response to traffic.
- **Deployment-focused workflow** — you push code (via Git, zip, or container image) and the platform builds and runs it.
- **Managed services** — databases, caches, and queues are offered as fully managed services (you query them, not administer them).
- **Higher abstraction = less control** — you cannot install arbitrary OS packages or tune the kernel.

**Notes:**
- PaaS is the sweet spot for teams that want to ship features quickly without hiring dedicated infrastructure engineers.
- The trade-off is reduced portability — code that relies on platform-specific features (e.g. Elastic Beanstalk environment variables, RDS parameter groups) may need rework to run on a different cloud.

---

#### PaaS Core Components

**Application hosting:**

| Component | Description | AWS service |
| --- | --- | --- |
| Managed runtime | Runs your app in a managed environment (Node, Python, Java, Go, etc.) | Elastic Beanstalk, App Runner |
| Container platform | Runs Docker containers without managing VMs | AWS Fargate (ECS/EKS) |
| CI/CD pipeline | Builds, tests, and deploys code automatically on push | AWS CodePipeline + CodeBuild |

**Managed databases:**

| Type | Description | AWS service |
| --- | --- | --- |
| Relational (SQL) | Fully managed PostgreSQL, MySQL, Oracle, SQL Server | Amazon RDS |
| NoSQL (key-value / document) | Managed serverless NoSQL with single-digit millisecond latency | Amazon DynamoDB |
| In-memory cache | Managed Redis or Memcached clusters | Amazon ElastiCache |
| Data warehouse | Columnar analytics database for petabyte-scale BI workloads | Amazon Redshift |
| Search | Managed OpenSearch / Elasticsearch cluster | Amazon OpenSearch Service |

**Other managed platform services:**

| Component | Description | AWS service |
| --- | --- | --- |
| Message queue | Fully managed message queuing (no broker to manage) | Amazon SQS |
| Event bus | Publish/subscribe messaging and event routing | Amazon SNS / EventBridge |
| API management | Managed API gateway — throttling, auth, caching | Amazon API Gateway |
| Email sending | Managed SMTP / API email delivery | Amazon SES |

---

#### PaaS on AWS

AWS offers a broad PaaS layer on top of its IaaS foundation:

| Service | Category | What it provides |
| --- | --- | --- |
| **Elastic Beanstalk** | App hosting | Deploy web apps in Node, Python, Java, Ruby, PHP, Go, .NET, Docker — zero infra config |
| **AWS App Runner** | Container hosting | Push a container image or source repo; App Runner builds, deploys, and scales it |
| **AWS Fargate** | Container platform | Run ECS/EKS workloads without managing EC2 nodes |
| **Amazon RDS** | Relational DB | Managed PostgreSQL, MySQL, MariaDB, Oracle, SQL Server; automated backups and failover |
| **Amazon Aurora** | Relational DB | AWS-designed MySQL/PostgreSQL-compatible DB with up to 5× performance improvement |
| **Amazon DynamoDB** | NoSQL DB | Serverless key-value / document DB; auto-scales read/write capacity |
| **Amazon ElastiCache** | In-memory cache | Managed Redis or Memcached |
| **Amazon Redshift** | Data warehouse | Columnar SQL analytics at petabyte scale |
| **Amazon SQS** | Messaging | Fully managed message queue |
| **Amazon SNS** | Messaging | Pub/sub notifications — push to HTTP, email, SQS, Lambda |
| **Amazon API Gateway** | API management | Create, publish, and manage REST, HTTP, and WebSocket APIs |
| **AWS CodePipeline** | CI/CD | Automated release pipelines connecting source, build, test, and deploy stages |

**Elastic Beanstalk — the archetypal AWS PaaS:**

```
You provide  →  application code (zip / Git / Docker)
              + environment configuration (instance type, env vars, scaling rules)

Beanstalk manages →  EC2 instances, Auto Scaling Group, Load Balancer
                  →  OS patching, health monitoring, rolling deployments
                  →  CloudWatch alarms and log collection
```

**RDS — the managed database example:**

```
You provide  →  engine choice (PostgreSQL, MySQL, etc.)
              + instance class and storage size
              + parameter group (DB-level config)
              + credentials and VPC placement

RDS manages  →  OS patching
             →  automated daily backups + point-in-time restore
             →  Multi-AZ standby for high availability
             →  Read replicas for read scaling
             →  Minor version upgrades (optional automatic)
```

---

#### PaaS Use Cases

| Use Case | Why PaaS fits |
| --- | --- |
| **Web application deployment** | Push code to Elastic Beanstalk or App Runner; platform handles servers and scaling |
| **Managed relational database** | Use RDS instead of running PostgreSQL on EC2 — no DBA needed for routine ops |
| **Microservices on containers** | Run Fargate tasks — no EC2 worker nodes to patch or scale |
| **Rapid prototyping** | Get an app running in minutes with Beanstalk; swap out for custom infra later if needed |
| **CI/CD automation** | CodePipeline + CodeBuild automates test → build → deploy without managing Jenkins servers |
| **Asynchronous processing** | SQS + Lambda worker decouples producers from consumers; both scale independently |

**When NOT to use PaaS:**
- When you need OS-level control (custom kernel, specific OS packages) — use IaaS (EC2).
- When licensing requires dedicated hardware — use Dedicated Hosts.
- When you need maximum portability and zero platform lock-in — containerise and use Fargate or EKS.

**Notes:**
- Elastic Beanstalk is often the first AWS PaaS service encountered. Despite its "managed" label, it still creates EC2 instances, Auto Scaling Groups, and load balancers in your account — you can inspect and modify them directly.
- RDS Multi-AZ provides automatic failover in under 2 minutes but is not a read-scaling solution — for read scaling, add Read Replicas.
- DynamoDB is serverless and requires zero capacity planning at small scale; enable on-demand mode and it scales to any throughput automatically.

---

### SaaS — Software as a Service

**Software as a Service (SaaS)** is the highest-level cloud model. The provider delivers a complete, ready-to-use application over the internet. You do not manage any infrastructure, platform, or application code — you consume the software as a service.

The analogy: you check into a hotel. The room is furnished, cleaned, and serviced. You bring nothing except your personal belongings and use the provided amenities.

#### What is SaaS

| Layer | Managed by |
| --- | --- |
| Physical hardware | Cloud provider |
| Hypervisor | Cloud provider |
| Operating System | Cloud provider |
| Runtime | Cloud provider |
| Application code | Cloud provider |
| Application updates and patches | Cloud provider |
| Data (content, settings) | **You** |
| User access and permissions | **You** |

**Key characteristics:**
- **Zero infrastructure management** — you never think about servers, OS patches, or scaling.
- **Browser-based or API access** — consumed via a web browser or REST/SDK API; no local installation required.
- **Multi-tenancy** — a single application instance serves multiple customers; data is logically isolated per tenant.
- **Subscription pricing** — billed per user per month or per API call; no upfront hardware or software licence.
- **Automatic updates** — the provider rolls out new features and security patches transparently.
- **Geographic availability** — SaaS applications are globally distributed; latency is handled by the provider.

**Notes:**
- Because the application code is managed by the provider, you have limited ability to customise behaviour beyond what the provider exposes in their configuration UI or API.
- Data sovereignty is a critical concern: sensitive data processed by a SaaS provider resides on their infrastructure. Verify data residency guarantees and compliance certifications (SOC 2, ISO 27001, GDPR, HIPAA) before onboarding regulated data.

---

#### SaaS Core Characteristics

**Multi-tenancy architecture:**

```
Single application instance
├── Tenant A  (logically isolated data and config)
├── Tenant B  (logically isolated data and config)
└── Tenant C  (logically isolated data and config)
```

- Reduces provider cost (one codebase, one deployment) and allows faster feature rollout.
- Customer data isolation is enforced at the application layer (row-level security, separate schemas, or separate encryption keys per tenant).

**Pricing models:**

| Model | Description | Example |
| --- | --- | --- |
| **Per-seat / per-user** | Fixed monthly fee per active user | Slack, GitHub Teams |
| **Per-API-call** | Billed per request or per unit consumed | AWS Rekognition, Translate |
| **Tiered / freemium** | Free tier with paid upgrades for higher limits or features | GitHub Free vs Pro |
| **Usage-based** | Billed on actual consumption (emails sent, storage used) | Amazon SES |

**Availability and SLA:**
- SaaS providers publish Service Level Agreements (SLAs) — typically 99.9% (about 8.7 hours downtime/year) to 99.99% (about 52 minutes/year).
- During outages you are entirely dependent on the provider's incident response. Design your architecture to degrade gracefully or failover to an alternative if the SaaS service is critical.

---

#### SaaS on AWS

AWS offers SaaS products directly, and its platform services are consumed by third-party SaaS companies as the underlying infrastructure:

**AWS-native SaaS products (you consume them as an end user or developer):**

| Service | Category | What it provides |
| --- | --- | --- |
| **Amazon WorkMail** | Email & calendar | Managed business email and calendar compatible with Microsoft Outlook |
| **Amazon Chime** | Collaboration | Managed video conferencing and messaging |
| **Amazon WorkDocs** | Document management | Secure, managed document storage and collaboration |
| **AWS Managed Microsoft AD** | Identity | Fully managed Active Directory in the cloud |
| **Amazon Connect** | Contact centre | Cloud-based contact centre — pay per minute, no hardware |
| **Amazon QuickSight** | BI / analytics | Managed business intelligence and dashboarding |
| **AWS Marketplace** | Software | Thousands of third-party SaaS applications deployable in your AWS account |

**AWS AI/ML services consumed as SaaS APIs:**

| Service | What it provides |
| --- | --- |
| **Amazon Rekognition** | Image and video analysis (object detection, facial recognition, text extraction) |
| **Amazon Comprehend** | Natural language processing (sentiment, entity detection, key phrases) |
| **Amazon Translate** | Real-time and batch language translation |
| **Amazon Polly** | Text-to-speech synthesis |
| **Amazon Transcribe** | Automatic speech recognition (audio → text) |
| **Amazon Textract** | Extract text and structured data from scanned documents |

These services are consumed entirely through an API — you send data in, get results back. No model training, infrastructure provisioning, or runtime management required.

---

#### SaaS Use Cases

| Use Case | Why SaaS fits |
| --- | --- |
| **Business email and collaboration** | WorkMail or Google Workspace — zero mail-server management |
| **CRM and ERP** | Salesforce, SAP — complex enterprise apps with zero infrastructure overhead |
| **BI and reporting** | Amazon QuickSight — connect to data sources and build dashboards without running Tableau servers |
| **AI/ML without a data science team** | Call Rekognition or Comprehend via API — no model training or GPU instances needed |
| **Identity and SSO** | AWS IAM Identity Center (SSO) or Okta — managed identity without running LDAP servers |
| **Monitoring and observability** | Datadog, New Relic, Splunk — ingest logs and metrics without running Elasticsearch clusters |
| **Payment processing** | Stripe, Braintree — PCI-compliant payment APIs consumed as a service |

**When NOT to use SaaS:**
- When you need to customise the application beyond what the provider allows.
- When data cannot leave your infrastructure (on-premises requirement) — use IaaS or private cloud.
- When you need to integrate deeply with proprietary internal systems — PaaS or IaaS gives more control.

**Notes:**
- SaaS vendor lock-in is real. Evaluate your exit strategy before committing to a SaaS provider for a critical system — ensure you can export your data in a portable format.
- For regulated industries (finance, healthcare), verify that the SaaS provider holds the relevant compliance certifications: HIPAA BAA, PCI-DSS, FedRAMP, SOC 2 Type II, ISO 27001.
- The boundary between PaaS and SaaS is blurring — services like Amazon RDS are sometimes described as "database as a service" (DBaaS), which sits between PaaS and SaaS.

---

### FaaS — Function as a Service

**What it is:** A serverless execution model where you write individual functions that are triggered by events. The provider automatically provisions, scales, and tears down compute per invocation. Often considered a subset of PaaS, but distinct enough to call out separately.

**You manage:** Function code and event trigger configuration.
**Provider manages:** Servers, runtime, scaling, and availability.

**AWS examples:** AWS Lambda, Amazon EventBridge, AWS Step Functions.

**Key concepts:**

| Concept | Explanation |
| --- | --- |
| **Event-driven** | Functions run in response to triggers — HTTP (API Gateway), S3 uploads, DynamoDB streams, schedules (EventBridge) |
| **Stateless** | Each invocation is independent; state must be stored externally (DynamoDB, S3, ElastiCache) |
| **Pay-per-invocation** | Billed per request and per 1 ms of execution — no idle cost |
| **Cold start** | First invocation after inactivity may be slower while the runtime initialises |
| **Execution limits** | AWS Lambda max timeout is 15 minutes; not suitable for long-running processes |

**Pros / Cons:**

| Pros | Cons |
| --- | --- |
| No server management at all | Cold starts add latency on first invocation |
| Auto-scales to zero — no idle cost | 15-minute execution time limit on Lambda |
| Pay only for execution duration | Stateless by design — external state store required |
| Rapid deployment of individual functions | Harder to debug and trace than traditional apps |

---

### Deployment Models

Beyond the service models above, cloud workloads are deployed in one of four deployment models:

| Model | Description | When to use |
| --- | --- | --- |
| **Public Cloud** | Fully hosted by a third-party provider (AWS, Azure, GCP); shared physical infrastructure, logically isolated per customer | Default for most new workloads — low cost, high agility |
| **Private Cloud** | Cloud infrastructure operated exclusively for one organisation; on-premises or hosted by a third party | Strict compliance, data sovereignty, or legacy system requirements |
| **Hybrid Cloud** | Mix of public and private cloud connected by a network (VPN or AWS Direct Connect) | Gradual cloud migrations, regulated data kept on-premises, burst capacity |
| **Multi-Cloud** | Using services from two or more public cloud providers simultaneously | Avoid vendor lock-in, leverage best-of-breed services, geo-redundancy |

**AWS tools for hybrid and multi-cloud:**

| Tool | Purpose |
| --- | --- |
| **AWS Outposts** | Extend AWS infrastructure and services into your own data centre |
| **AWS Direct Connect** | Dedicated private network link from on-premises to AWS (bypasses the public internet) |
| **AWS Transit Gateway** | Hub-and-spoke network connecting VPCs across multiple accounts and Regions |
| **AWS Storage Gateway** | Bridge between on-premises storage systems and AWS cloud storage |

**Notes:**
- Hybrid cloud is the most common pattern for enterprises mid-migration — they keep sensitive workloads on-premises while moving stateless services to AWS.
- Multi-cloud adds operational complexity; only adopt it when the business benefit (e.g. using GCP BigQuery + AWS Lambda) outweighs the cost of managing two toolchains.

---

### Shared Responsibility Model

AWS and the customer share security and compliance responsibility. The split depends on which service model is in use. The canonical AWS phrasing is: **AWS is responsible for security *of* the cloud; customers are responsible for security *in* the cloud.**

| Responsibility | AWS | Customer |
| --- | --- | --- |
| Physical security of data centres | ✓ | |
| Hypervisor and virtualisation layer | ✓ | |
| Managed service patching (RDS, Lambda) | ✓ | |
| Network fabric and baseline DDoS protection | ✓ | |
| Guest OS patches (EC2) | | ✓ |
| Application security | | ✓ |
| IAM users, roles, and policies | | ✓ |
| Data encryption at rest and in transit | Tool provided | ✓ to enable |
| Security Groups and Network ACLs | Tool provided | ✓ to configure |
| S3 bucket policies and public-access settings | Tool provided | ✓ to configure |

**How responsibility shifts by service model:**

| Service model | AWS manages | Customer manages |
| --- | --- | --- |
| **IaaS (EC2)** | Hardware, hypervisor | OS, runtime, app, network config, data |
| **PaaS (Elastic Beanstalk, RDS)** | OS, runtime, middleware | App code, configuration, data |
| **SaaS (WorkMail)** | Nearly everything | Access control and data content |
| **FaaS (Lambda)** | Runtime, OS, scaling, infrastructure | Function code, IAM triggers, data |

**Notes:**
- "Security of the cloud vs. security in the cloud" is the exact phrasing used in AWS certifications — memorise it.
- Misconfigurations (open S3 buckets, overly permissive IAM policies) are always the customer's responsibility regardless of service model.
- The shared responsibility model is a guaranteed topic in AWS Solutions Architect and Cloud Practitioner exams.

---

## AWS Global Infrastructure

AWS operates a worldwide network of data centres organized into **Regions**, **Availability Zones**, and **Edge Locations**. Understanding this physical and logical layout is the foundation for designing resilient, low-latency, cost-efficient cloud applications. Every AWS service — whether IAM, EC2, S3, or Lambda — is deployed on top of this infrastructure.

### One Shot Revision

| Topic | Short Description |
| --- | --- |
| [Regions](#regions) | Geographically isolated clusters of data centres; the primary deployment boundary |
| [Availability Zones](#availability-zones) | Physically separated fault domains inside a Region; the HA building block |
| [Edge Locations & Points of Presence](#edge-locations--points-of-presence) | Global CDN and DNS endpoints that cache content close to users |
| [Local Zones & Wavelength Zones](#local-zones--wavelength-zones) | AWS infrastructure extensions for ultra-low latency at the edge or on 5G networks |
| [AWS Outposts](#aws-outposts) | Rack of AWS hardware installed in your own data centre |
| [How to Choose a Region](#how-to-choose-a-region) | Decision framework: latency, compliance, service availability, pricing |

---

### Regions

**Description:** An AWS **Region** is a named, geographically isolated cluster of data centres in one part of the world (e.g., `us-east-1` — N. Virginia, `ap-southeast-1` — Singapore, `eu-west-1` — Ireland). Each Region is a completely independent failure domain — an outage in one Region does not affect another.

**Key facts:**

| Attribute | Details |
| --- | --- |
| **Count (approx.)** | 35+ Regions globally as of 2025, with more announced |
| **Independence** | Regions do not share power, cooling, networking, or control planes |
| **Service availability** | Not every AWS service is available in every Region; check the [AWS Regional Services List](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/) |
| **Data residency** | Data stored in a Region stays in that Region unless you explicitly replicate it |
| **Naming convention** | `<geography>-<direction>-<number>` — e.g., `us-east-1`, `eu-central-1`, `ap-northeast-2` |
| **Opt-in Regions** | Some newer Regions (e.g., `ap-east-1` Hong Kong) must be explicitly enabled per account |

**Common CLI operations:**

```bash
# List all available Regions for your account
aws ec2 describe-regions --output table

# List Regions including opt-in status
aws ec2 describe-regions --all-regions --query 'Regions[*].[RegionName,OptInStatus]' --output table

# Set a default Region for the CLI session
export AWS_DEFAULT_REGION=ap-southeast-1
```

**Notes:**

- AWS global services (IAM, Route 53, CloudFront, WAF) are not tied to any Region — they operate across all Regions automatically.
- When you pick a Region at deployment time, you commit to that Region's latency, compliance jurisdiction, and service catalogue.

---

### Availability Zones

**Description:** An **Availability Zone (AZ)** is one or more discrete data centres inside a Region, each with independent power, cooling, and networking. AZs within a Region are connected by low-latency, high-bandwidth private fibre links. Deploying across multiple AZs is the primary way to achieve **high availability** on AWS.

**Key facts:**

| Attribute | Details |
| --- | --- |
| **AZs per Region** | Typically 3–6 AZs per Region (minimum 2 for new Regions) |
| **Physical separation** | Miles apart — isolated from shared single points of failure |
| **Naming** | `<region><letter>` — e.g., `us-east-1a`, `us-east-1b`, `us-east-1c` |
| **AZ ID** | Canonical identifier (e.g., `use1-az1`) — stable across accounts; the letter suffix is account-specific |
| **Intra-region latency** | Single-digit millisecond round-trip between AZs |
| **Data transfer cost** | Cross-AZ traffic within the same Region incurs a small per-GB charge |

**High-availability pattern:**

```
Region: us-east-1
├── AZ: us-east-1a  → EC2 instance A, RDS primary
├── AZ: us-east-1b  → EC2 instance B, RDS standby (Multi-AZ)
└── AZ: us-east-1c  → EC2 instance C (auto-scaling spare)
         ↑
   Elastic Load Balancer distributes traffic across all three AZs
```

**Common CLI operations:**

```bash
# List AZs in the current Region
aws ec2 describe-availability-zones --output table

# List AZs with their AZ IDs (canonical, account-agnostic)
aws ec2 describe-availability-zones \
  --query 'AvailabilityZones[*].[ZoneName,ZoneId,State]' \
  --output table
```

**Notes:**

- Multi-AZ deployments protect against a data-centre-level failure; they do **not** protect against a full Region failure.
- For Region-level resilience, replicate to a second Region and use Route 53 health checks or Global Accelerator.
- AWS managed services (RDS Multi-AZ, ELB, ECS, EKS) spread across AZs automatically when you enable the option.

---

### Edge Locations & Points of Presence

**Description:** AWS **Edge Locations** (also called **Points of Presence**, or PoPs) are mini-AWS sites located in major cities worldwide — far more numerous than Regions. They are used by **Amazon CloudFront** (CDN), **Amazon Route 53** (DNS), **AWS WAF**, **AWS Shield**, and **AWS Global Accelerator** to serve requests from a location physically close to the end user, reducing latency.

**Key facts:**

| Attribute | Details |
| --- | --- |
| **Count (approx.)** | 600+ Points of Presence (Edge Locations + Regional Edge Caches) as of 2025 |
| **Primary services** | CloudFront (CDN caching), Route 53 (DNS), AWS Shield (DDoS), WAF, Global Accelerator |
| **Regional Edge Caches** | Larger mid-tier caches between edge locations and origin servers — hold objects longer |
| **Not compute** | You cannot run EC2 or Lambda directly at an Edge Location (use Lambda@Edge or CloudFront Functions for edge compute) |
| **Automatic** | CloudFront routes requests to the nearest PoP automatically — no configuration needed |

**How CloudFront uses Edge Locations:**

```
User (Tokyo) → Edge Location (Tokyo PoP)
                    │
              Cache HIT?  ──Yes──→ serve cached response (< 5ms)
                    │
                   No
                    │
              Regional Edge Cache (Asia)
                    │
              Cache HIT?  ──Yes──→ serve & refresh edge cache
                    │
                   No
                    │
              Origin server (S3 / EC2 / ALB in us-east-1)
```

**Notes:**

- CloudFront **TTL** controls how long objects stay in the edge cache. Set appropriate cache headers on your origin.
- **Lambda@Edge** and **CloudFront Functions** let you run lightweight JavaScript/Node.js logic at edge locations — ideal for auth, redirects, and A/B testing without round-tripping to the origin.
- Route 53 uses Anycast routing via edge locations to answer DNS queries from the closest PoP globally.

---

### Local Zones & Wavelength Zones

**Description:** AWS provides two infrastructure extensions for workloads that need latency below what a full Region can provide.

**Local Zones:**

An AWS **Local Zone** places compute, storage, and database services closer to large population centres that are far from existing Regions. They extend a parent Region but are managed as their own AZ-like placement zone.

| Attribute | Details |
| --- | --- |
| **Latency target** | Single-digit milliseconds to end users in that metro area |
| **Use cases** | Media rendering, real-time gaming, live streaming, AR/VR |
| **Example** | `us-east-1-lax-1` (Los Angeles Local Zone, extends `us-east-1`) |
| **Opt-in** | Must be enabled per account in the console or via CLI |
| **Services available** | EC2, EBS, ECS, VPC subnets, RDS — subset of full Region services |

```bash
# List Local Zones
aws ec2 describe-availability-zones \
  --filters Name=zone-type,Values=local-zone \
  --query 'AvailabilityZones[*].[ZoneName,ZoneId,State]' \
  --output table

# Enable a Local Zone for your account
aws ec2 modify-availability-zone-group \
  --group-name us-east-1-lax-1 \
  --opt-in-status opted-in
```

**Wavelength Zones:**

AWS **Wavelength** embeds AWS compute and storage directly inside telecom carriers' 5G networks. Applications deployed in Wavelength Zones reach 5G-connected mobile devices without leaving the carrier network, targeting sub-10ms latency.

| Attribute | Details |
| --- | --- |
| **Latency target** | Ultra-low — traffic stays within the carrier's 5G network |
| **Use cases** | Autonomous vehicles, industrial IoT, connected gaming, AR on mobile |
| **Example** | `us-east-1-wl1-bos-wlz-1` (Verizon Boston Wavelength Zone) |
| **Partners** | Verizon, Vodafone, KDDI, SK Telecom |

**Notes:**

- Local Zones and Wavelength Zones are AZ extensions — they show up as zone options when you launch EC2 instances.
- Both require the parent Region to be active; they inherit the parent Region's IAM, Route 53, and global service plane.

---

### AWS Outposts

**Description:** **AWS Outposts** is a fully managed service that delivers AWS infrastructure, APIs, and tools to virtually any on-premises or co-location facility. AWS physically installs and maintains a rack (or larger installation) in your data centre. From your perspective, the Outpost is just another AZ-like location — you can deploy EC2 instances, EKS nodes, RDS databases, and S3 buckets on it using the same console, CLI, and APIs.

**Key facts:**

| Attribute | Details |
| --- | --- |
| **Form factors** | Outposts rack (42U, 1-96 racks) or Outposts servers (1U/2U for space-constrained sites) |
| **Management** | Fully managed by AWS — hardware monitoring, patching, and replacement are AWS's responsibility |
| **Connectivity** | Requires a reliable, dedicated connection back to the parent AWS Region (service link) |
| **Use cases** | Data residency requirements, ultra-low latency to on-premises systems, hybrid workloads |
| **Services available** | EC2, EBS, ECS, EKS, RDS, S3 on Outposts, ElastiCache — subset of full Region |
| **Pricing** | Capacity reservation fee (hourly or 1/3-year term) — varies by configuration |

**Architecture:**

```
On-premises Data Centre
┌────────────────────────────────────────┐
│  AWS Outposts Rack                     │
│  ├── EC2 instances  (local latency)    │
│  ├── RDS (local data residency)        │
│  └── S3 on Outposts (local storage)   │
│          │                             │
│     Service Link (VPN/Direct Connect)  │
└──────────┼─────────────────────────────┘
           │
    AWS Region (us-east-1)
    └── Control plane, IAM, CloudWatch, APIs
```

**Notes:**

- The Outposts control plane lives in the parent Region — if the service link is severed, existing workloads keep running but you lose the ability to make API calls (launch/terminate instances, etc.).
- S3 on Outposts uses a different endpoint and bucket format than S3 in the cloud — objects stored on Outposts stay on-premises unless explicitly replicated.
- Outposts is ideal for regulated industries (healthcare, finance, government) where data cannot leave a physical facility.

---

### How to Choose a Region

**Description:** Picking the right Region is one of the most consequential architectural decisions. Once data is stored and services are deployed in a Region, migration is expensive. Use this framework to decide.

**Decision framework:**

| Factor | Guidance |
| --- | --- |
| **Compliance & data residency** | Check legal requirements first. If regulations mandate data stays in a country/jurisdiction, only shortlist Regions within it. This is a hard constraint. |
| **Latency to end users** | Deploy in the Region geographically closest to your majority user base. Use [cloudping.info](https://cloudping.info) to measure latency from your users' locations. |
| **Service availability** | Verify every AWS service your architecture needs is available in the target Region ([Regional Services List](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)). Newer Regions have fewer services. |
| **Pricing** | AWS pricing varies by Region — `us-east-1` is typically the cheapest. Compare pricing pages for your key services before committing. |
| **Disaster recovery** | Pick a geographically distant secondary Region for your DR site (e.g., `us-east-1` primary → `us-west-2` DR). |

**Quick checklist:**

```
1. Does compliance force a specific geography? → hard filter
2. Where are most users? → pick nearest Region
3. Do all required services exist there? → check Regional Services List
4. Is pricing acceptable vs. alternatives? → compare
5. Which Region will serve as DR? → pick geographically distant pair
```

**Common CLI operations:**

```bash
# Check which services are available in a specific Region
# (No direct API; check the Regional Services page or use the console)

# Confirm your CLI is targeting the right Region
aws configure get region

# Override Region for a single command
aws s3 ls --region eu-central-1
```

**Notes:**

- `us-east-1` (N. Virginia) is AWS's oldest Region and typically gets new services first — but it also has the most traffic, so don't default to it just for convenience.
- For global applications, pair CloudFront + Route 53 latency-based routing with multi-Region deployments instead of trying to pick one "perfect" Region.
- Review the [AWS Global Infrastructure map](https://aws.amazon.com/about-aws/global-infrastructure/) for a visual overview of all Regions, AZs, and edge locations.

---

## AWS Free Tier

The **AWS Free Tier** lets you explore and try AWS services at no charge, up to specified usage limits. It is the fastest way to get hands-on experience with AWS without a credit card surprise at the end of the month — as long as you understand what is free, for how long, and how to watch for overages.

### One Shot Revision

| Topic | Short Description |
| --- | --- |
| [Free Tier Types](#free-tier-types) | Always Free vs. 12 Months Free vs. Trials — know the difference |
| [Key Services in the Free Tier](#key-services-in-the-free-tier) | The most important services and their monthly free allowances |
| [Monitoring Free Tier Usage](#monitoring-free-tier-usage) | Billing alerts, Cost Explorer, and the Free Tier usage dashboard |
| [Avoiding Unexpected Charges](#avoiding-unexpected-charges) | Common pitfalls and a checklist to stay within limits |

---

### Free Tier Types

**Description:** Not all "free" offers work the same way. AWS has three distinct types, and confusing them is the most common reason people get unexpected bills.

| Type | Duration | How it works | Example |
| --- | --- | --- | --- |
| **Always Free** | Forever | Never expires, for any AWS customer — even after the 12-month period | Lambda: 1M requests/month forever |
| **12 Months Free** | First 12 months after account creation | Resets monthly; expires exactly 12 months from sign-up date | EC2: 750 hrs/month of `t2.micro` or `t3.micro` |
| **Trials** | Short fixed period (30–90 days) | Starts when you first activate the specific service | Amazon SageMaker Canvas: 2-month trial |

**Key distinctions:**

- The 12-month clock starts from your **account creation date**, not from when you first use a service.
- "Always Free" limits are per-account, not per-Region — usage across all Regions counts toward the same limit.
- Trial offers begin when you **first enable** the service, so don't enable a trial service until you are ready to use it.

**Notes:**

- Check the offer type on the [AWS Free Tier page](https://aws.amazon.com/free/) before assuming a service is permanently free.
- When the 12-month period ends, standard on-demand rates apply automatically — AWS does not warn you on the day of expiry.

---

### Key Services in the Free Tier

**Description:** A curated reference of the services most useful for learning and experimentation, with their exact free allowances. Always verify current limits on the [official Free Tier page](https://aws.amazon.com/free/) as AWS updates them periodically.

**Always Free (never expires):**

| Service | Free Allowance | Notes |
| --- | --- | --- |
| **AWS Lambda** | 1,000,000 requests/month + 400,000 GB-seconds compute/month | Most learning workloads never exceed this |
| **Amazon DynamoDB** | 25 GB storage + 25 WCU + 25 RCU | Enough for small apps; no time limit |
| **Amazon CloudFront** | 1 TB data transfer out/month + 10M HTTP/HTTPS requests/month | Generous for personal projects |
| **AWS IAM** | Unlimited users, groups, roles, policies | IAM is always free — no limits |
| **Amazon CloudWatch** | 10 custom metrics + 10 alarms + 1M API requests + 5 GB log ingestion/month | Core observability at no cost |
| **AWS SNS** | 1M publishes + 100K HTTP deliveries/month | Free push notifications |
| **Amazon SQS** | 1M requests/month (standard queues) | Free message queuing for simple workflows |
| **AWS Secrets Manager** | 10,000 API calls/month | Note: storing secrets is NOT free |
| **Amazon Cognito** | 50,000 MAUs (monthly active users) | Free identity for user pools |

**12 Months Free (resets monthly, expires at 12-month mark):**

| Service | Free Allowance | Notes |
| --- | --- | --- |
| **Amazon EC2** | 750 hrs/month of `t2.micro` (or `t3.micro` in Regions where `t2` is unavailable) | Runs 24/7 for a full month — one instance at a time |
| **Amazon S3** | 5 GB standard storage + 20,000 GET + 2,000 PUT requests/month | Enough for static hosting and small backups |
| **Amazon RDS** | 750 hrs/month of `db.t2.micro` or `db.t3.micro` (single-AZ) + 20 GB storage | One database instance running around the clock |
| **Amazon EBS** | 30 GB of SSD (`gp2`/`gp3`) storage/month | Covers the root volume of a `t2.micro` EC2 instance |
| **Amazon ELB** | 750 hrs/month + 15 GB data processing | One load balancer running continuously |
| **Amazon ElastiCache** | 750 hrs/month of `cache.t2.micro` | One Redis or Memcached node |
| **AWS Data Transfer** | 100 GB outbound data transfer/month | Shared across all services |
| **Amazon API Gateway** | 1M API calls/month (REST) | Pairs well with Lambda for serverless APIs |

**Trial (time-limited, starts on first use):**

| Service | Trial Offer |
| --- | --- |
| **Amazon SageMaker** | 250 hrs/month of `ml.t3.medium` notebook for 2 months |
| **Amazon Redshift** | 750 hrs/month of `dc2.large` for 2 months |
| **AWS Certificate Manager (ACM)** | Always free for public SSL/TLS certificates |
| **Amazon Inspector** | 15-day free trial |
| **Amazon GuardDuty** | 30-day free trial |

**Notes:**

- EC2 `t2.micro` hours accumulate across all running instances in the month — two `t2.micro` instances running simultaneously eat 2× the hours.
- S3 storage is measured in GB-months (average storage across the month, not peak).
- **Data transfer IN** to AWS is always free; only **data transfer OUT** (egress) counts toward limits and billing.

---

### Monitoring Free Tier Usage

**Description:** AWS provides built-in tools to track how close you are to your Free Tier limits. Use them — do not rely on memory or estimates.

**AWS Billing Console → Free Tier usage dashboard:**

The easiest place to see your current month's free tier consumption at a glance.

```
AWS Console → Billing & Cost Management → Free Tier
```

It shows:
- Each service's free allowance
- Current month's usage
- Percentage consumed
- Forecasted usage for the rest of the month

**Set up a Free Tier usage alert:**

AWS can email you when you exceed (or are forecasted to exceed) a Free Tier limit. Enable it once per account:

```
AWS Console → Billing & Cost Management → Billing Preferences
→ Check: "Receive Free Tier Usage Alerts"
→ Enter your email address → Save
```

**Set up a billing alert with CloudWatch:**

For a hard dollar guardrail, create a CloudWatch alarm that fires when estimated charges exceed a threshold:

```bash
# Enable billing metrics (one-time, us-east-1 only)
aws cloudwatch put-metric-alarm \
  --alarm-name "FreeTierBillingAlert" \
  --alarm-description "Alert if estimated charges exceed $5" \
  --metric-name EstimatedCharges \
  --namespace AWS/Billing \
  --statistic Maximum \
  --period 86400 \
  --threshold 5 \
  --comparison-operator GreaterThanOrEqualToThreshold \
  --dimensions Name=Currency,Value=USD \
  --evaluation-periods 1 \
  --alarm-actions arn:aws:sns:us-east-1:123456789012:BillingAlertTopic \
  --region us-east-1
```

**Check current month charges via CLI:**

```bash
# View MTD (month-to-date) costs by service
aws ce get-cost-and-usage \
  --time-period Start=$(date +%Y-%m-01),End=$(date +%Y-%m-%d) \
  --granularity MONTHLY \
  --metrics UnblendedCost \
  --group-by Type=DIMENSION,Key=SERVICE \
  --region us-east-1

# Check Free Tier usage per service
aws ce get-dimension-values \
  --dimension SERVICE \
  --time-period Start=$(date +%Y-%m-01),End=$(date +%Y-%m-%d) \
  --region us-east-1
```

**Notes:**

- Billing metrics are only available in `us-east-1` — always include `--region us-east-1` for billing-related CLI commands.
- CloudWatch billing alarms fire on **estimated charges**, which AWS updates several times a day — not in real time.
- AWS Cost Explorer gives a historical view; the Free Tier dashboard gives the real-time current-month picture.

---

### Avoiding Unexpected Charges

**Description:** Most "surprise bills" on a new AWS account come from a small set of recurring mistakes. Know these before you start experimenting.

**Top causes of unexpected Free Tier charges:**

| Pitfall | What happens | How to avoid it |
| --- | --- | --- |
| **Running multiple EC2 instances** | 750 hrs covers one `t2.micro` running 24/7; two instances burn through it in half a month | Stop instances you are not actively using; terminate instead of stopping to avoid EBS charges |
| **Forgetting to terminate RDS** | Stopped RDS instances restart automatically after 7 days; storage continues to accrue | Delete the instance (take a final snapshot if needed) rather than stopping it |
| **Elastic IP left unattached** | AWS charges for Elastic IPs that are allocated but not attached to a running instance | Release EIPs immediately when you no longer need them |
| **NAT Gateway** | Not in the Free Tier — charges start immediately at ~$0.045/hr + data | Use a NAT instance (`t2.micro`) in the Free Tier, or avoid private subnets during learning |
| **Data transfer out exceeding 100 GB** | Egress over the 100 GB free allowance is billed per GB | Keep large file transfers inside the same Region; use S3 Transfer Acceleration sparingly |
| **Snapshots and AMIs** | EBS snapshots stored in S3 incur standard S3 storage charges | Delete old snapshots when done |
| **CloudWatch Logs with no expiry** | Log groups with no retention policy fill up and cost money over time | Set a retention policy (e.g., 7 or 30 days) on every log group |
| **Secrets Manager storing secrets** | Each secret costs ~$0.40/month — not free even in the Free Tier | Use SSM Parameter Store (standard tier) for free secret storage during learning |

**Cleanup checklist after a learning session:**

```bash
# List running EC2 instances
aws ec2 describe-instances \
  --filters Name=instance-state-name,Values=running \
  --query 'Reservations[*].Instances[*].[InstanceId,InstanceType,State.Name]' \
  --output table

# List all RDS instances
aws rds describe-db-instances \
  --query 'DBInstances[*].[DBInstanceIdentifier,DBInstanceStatus,DBInstanceClass]' \
  --output table

# List allocated Elastic IPs
aws ec2 describe-addresses \
  --query 'Addresses[*].[AllocationId,PublicIp,AssociationId]' \
  --output table

# List EBS snapshots you own
aws ec2 describe-snapshots --owner-ids self \
  --query 'Snapshots[*].[SnapshotId,VolumeSize,StartTime,Description]' \
  --output table

# List NAT Gateways (billed hourly)
aws ec2 describe-nat-gateways \
  --filter Name=state,Values=available \
  --query 'NatGateways[*].[NatGatewayId,State,CreateTime]' \
  --output table
```

**Recommended account-level safeguards:**

1. Enable **Free Tier usage alerts** (email) via Billing Preferences.
2. Create a **CloudWatch billing alarm** at $1 and $5.
3. Set a **budget** in AWS Budgets with an alert at $0.01 — any charge at all triggers a notification.
4. Enable **AWS Cost Anomaly Detection** — it uses ML to flag spending spikes automatically.
5. Enable **MFA on root** and lock it away — a compromised root account can rack up massive charges.

```bash
# Create a zero-spend budget (alert if any charge occurs)
aws budgets create-budget \
  --account-id $(aws sts get-caller-identity --query Account --output text) \
  --budget '{
    "BudgetName": "ZeroSpendBudget",
    "BudgetLimit": {"Amount": "1", "Unit": "USD"},
    "TimeUnit": "MONTHLY",
    "BudgetType": "COST"
  }' \
  --notifications-with-subscribers '[{
    "Notification": {
      "NotificationType": "ACTUAL",
      "ComparisonOperator": "GREATER_THAN",
      "Threshold": 0.01,
      "ThresholdType": "ABSOLUTE_VALUE"
    },
    "Subscribers": [{
      "SubscriptionType": "EMAIL",
      "Address": "your-email@example.com"
    }]
  }]'
```

**Notes:**

- AWS will not automatically stop a service when it exceeds the Free Tier limit — it will simply start billing you. There is no hard cap unless you explicitly set one via AWS Service Quotas or service-level limits.
- The only true safety net is a combination of billing alerts + regular manual cleanup + understanding which services are not in the Free Tier at all (NAT Gateway, Route 53 hosted zones, Support plans, etc.).

---

## AWS Pricing Models

AWS offers multiple pricing models so you can match cost to workload behaviour — from unpredictable bursts to steady 24/7 baselines. Picking the wrong model is one of the biggest sources of avoidable cloud spend. Understanding how each model works, when to use it, and how to combine them is a core cloud engineering skill.

### One Shot Revision

| Topic | Short Description |
| --- | --- |
| [On-Demand](#on-demand) | Pay per second/hour with no commitment — the default, highest per-unit price |
| [Reserved Instances & Savings Plans](#reserved-instances--savings-plans) | 1- or 3-year commitment in exchange for up to 72% discount |
| [Spot Instances](#spot-instances) | Bid on unused AWS capacity — up to 90% cheaper, but can be interrupted |
| [Dedicated Hosts & Dedicated Instances](#dedicated-hosts--dedicated-instances) | Physical isolation for licensing or compliance requirements |
| [Pricing Calculators & Cost Tools](#pricing-calculators--cost-tools) | Tools to estimate, track, and optimise AWS spend |

---

### On-Demand

**Description:** **On-Demand** is the baseline pricing model — you pay for compute capacity by the second (Linux/Windows EC2) or by the hour with no upfront commitments or long-term contracts. You can start and stop at any time. This is the highest per-unit price AWS charges, and is meant for short-term, unpredictable, or irregular workloads.

**Key facts:**

| Attribute | Details |
| --- | --- |
| **Commitment** | None — start and stop any time |
| **Billing granularity** | Per second (minimum 60 seconds) for most Linux instances; per hour for Windows |
| **Price** | Highest of all EC2 models — acts as the baseline |
| **Best for** | Dev/test environments, unpredictable traffic, short jobs, new applications being profiled |
| **Worst for** | Steady 24/7 workloads — you overpay vs. Reserved or Savings Plans |

**On-Demand pricing example (approximate, us-east-1):**

| Instance | vCPU | RAM | On-Demand/hr |
| --- | --- | --- | --- |
| `t3.micro` | 2 | 1 GB | ~$0.0104 |
| `t3.medium` | 2 | 4 GB | ~$0.0416 |
| `m5.large` | 2 | 8 GB | ~$0.096 |
| `c5.xlarge` | 4 | 8 GB | ~$0.17 |

**Common CLI operations:**

```bash
# Get current On-Demand price for an instance type in a Region
aws pricing get-products \
  --service-code AmazonEC2 \
  --filters \
    "Type=TERM_MATCH,Field=instanceType,Value=t3.micro" \
    "Type=TERM_MATCH,Field=location,Value=US East (N. Virginia)" \
    "Type=TERM_MATCH,Field=operatingSystem,Value=Linux" \
    "Type=TERM_MATCH,Field=tenancy,Value=Shared" \
    "Type=TERM_MATCH,Field=preInstalledSw,Value=NA" \
    "Type=TERM_MATCH,Field=capacitystatus,Value=Used" \
  --region us-east-1 \
  --query 'PriceList[0]' \
  --output text | python3 -m json.tool
```

**Notes:**

- On-Demand is the right starting point while you profile a new workload — switch to Reserved or Savings Plans once usage patterns are stable.
- AWS data transfer charges are separate from compute pricing — always factor in egress costs.

---

### Reserved Instances & Savings Plans

**Description:** For workloads with predictable, steady-state usage, AWS offers significant discounts in exchange for a 1-year or 3-year usage commitment. There are two mechanisms: the older **Reserved Instances (RIs)** and the newer, more flexible **Savings Plans**.

**Reserved Instances (RIs):**

| RI Type | Flexibility | Discount vs On-Demand |
| --- | --- | --- |
| **Standard RI** | Locked to instance family, size, OS, and Region | Up to 72% |
| **Convertible RI** | Can exchange for different instance type/OS/tenancy | Up to 66% |
| **Scheduled RI** | Reserved for specific recurring windows (deprecated) | N/A |

| Payment option | How it works | Discount level |
| --- | --- | --- |
| **All Upfront** | Pay full term cost upfront | Highest discount |
| **Partial Upfront** | Pay part upfront, rest monthly | Mid discount |
| **No Upfront** | Pay monthly — no upfront cost | Lowest discount (still beats On-Demand) |

**Savings Plans (recommended over RIs for most teams):**

Savings Plans are a newer commitment model that applies automatically across a broader range of services and sizes — no need to specify the exact instance type upfront.

| Plan Type | Covers | Flexibility |
| --- | --- | --- |
| **Compute Savings Plan** | EC2 (any family/size/Region/OS), Lambda, Fargate | Most flexible — discount applies automatically |
| **EC2 Instance Savings Plan** | EC2 within a specific instance family in a Region | Less flexible, slightly higher discount (up to 72%) |
| **SageMaker Savings Plan** | SageMaker ML instances | SageMaker-specific |

```
Commitment: $/hour spend (e.g. "I commit to spending at least $0.10/hr on compute")
→ AWS applies the discounted rate to all eligible usage up to that commitment
→ Usage above the commitment is billed at On-Demand rates
```

**Comparison — RI vs Savings Plan:**

| | Reserved Instances | Savings Plans |
| --- | --- | --- |
| Scope | Single instance type + Region | Compute family, cross-Region (Compute SP) |
| Flexibility | Low (Standard RI) to Medium (Convertible) | High |
| Discount | Up to 72% | Up to 66% (Compute) / 72% (EC2 SP) |
| Management | Must track RI inventory | Automatic — applies to eligible spend |
| Recommendation | Legacy; still useful for specific DB/OS combos | Preferred for EC2 and Lambda |

**Common CLI operations:**

```bash
# List your active Reserved Instances
aws ec2 describe-reserved-instances \
  --filters Name=state,Values=active \
  --query 'ReservedInstances[*].[ReservedInstancesId,InstanceType,InstanceCount,End,FixedPrice]' \
  --output table

# List your active Savings Plans
aws savingsplans describe-savings-plans \
  --states active \
  --query 'savingsPlans[*].[savingsPlanId,savingsPlanType,commitment,currency,end]' \
  --output table

# View Savings Plans utilisation report
aws ce get-savings-plans-utilization \
  --time-period Start=$(date +%Y-%m-01),End=$(date +%Y-%m-%d) \
  --region us-east-1
```

**Notes:**

- RIs and Savings Plans do not "expire" mid-usage — if you stop the instance, you still pay for the reservation. Size your commitment to your minimum guaranteed usage, not your peak.
- Unused RI capacity can be listed in the **Reserved Instance Marketplace** to sell to other AWS customers.
- Use **AWS Cost Explorer** → "Savings Plans recommendations" or "RI recommendations" to get data-driven suggestions based on your last 7/30/60 days of usage.

---

### Spot Instances

**Description:** **Spot Instances** let you bid on spare EC2 capacity that AWS is not currently using. In exchange for accepting that the instance can be **interrupted with a 2-minute warning**, you get discounts of up to 90% compared to On-Demand. Spot is the most cost-efficient EC2 pricing model but requires fault-tolerant workloads.

**Key facts:**

| Attribute | Details |
| --- | --- |
| **Discount** | Up to 90% off On-Demand price (varies by supply/demand) |
| **Interruption** | AWS can reclaim the instance with 2 minutes notice; your workload must handle this gracefully |
| **Price variability** | Spot price fluctuates; you set a max price (or use the current Spot price automatically) |
| **Interruption notice** | Available via EC2 instance metadata: `http://169.254.169.254/latest/meta-data/spot/termination-time` |
| **Best for** | Batch processing, big data (Spark/EMR), CI/CD build agents, ML training, stateless web workers |
| **Worst for** | Databases, stateful apps, anything that cannot tolerate sudden loss of a node |

**Spot Instance lifecycle:**

```
You request Spot capacity
        │
   Capacity available?
   ├── Yes → Instance launches at current Spot price
   └── No  → Request stays pending until capacity frees up (or times out)

While running:
   AWS demand spikes → Spot price rises above your max bid
        │
   2-minute termination notice (via metadata + CloudWatch event)
        │
   Instance terminates (state: spot-instance-termination)
```

**Spot strategies for resilience:**

| Strategy | How it works |
| --- | --- |
| **Spot Fleet** | Request a mix of instance types and AZs; AWS fulfils from whichever pool has capacity |
| **EC2 Auto Scaling with mixed instances** | Combine On-Demand base capacity + Spot for scale-out workers |
| **Capacity-Optimised allocation** | AWS picks the pool least likely to be interrupted — recommended over lowest-price |
| **Spot with checkpointing** | Save progress to S3/EBS periodically so an interruption doesn't lose all work |

**Common CLI operations:**

```bash
# Check current Spot prices for an instance type across AZs
aws ec2 describe-spot-price-history \
  --instance-types t3.medium \
  --product-descriptions "Linux/UNIX" \
  --start-time $(date -u +%Y-%m-%dT%H:%M:%SZ) \
  --query 'SpotPriceHistory[*].[AvailabilityZone,SpotPrice,Timestamp]' \
  --output table

# Request a Spot Instance
aws ec2 run-instances \
  --image-id ami-0abcdef1234567890 \
  --instance-type t3.medium \
  --instance-market-options '{"MarketType":"spot","SpotOptions":{"SpotInstanceType":"one-time","MaxPrice":"0.05"}}' \
  --key-name my-key-pair

# Check for a termination notice from inside the instance
curl -s http://169.254.169.254/latest/meta-data/spot/termination-time
# Returns empty if not being terminated; returns timestamp if interruption is imminent

# List active Spot requests
aws ec2 describe-spot-instance-requests \
  --filters Name=state,Values=active \
  --query 'SpotInstanceRequests[*].[SpotInstanceRequestId,InstanceId,SpotPrice,State]' \
  --output table
```

**Notes:**

- Never run a Spot Instance without handling the interruption notice — at minimum, catch SIGTERM and checkpoint your state.
- Use **Spot Fleet** or **Auto Scaling groups with mixed instances policy** rather than individual Spot requests — they automatically replace interrupted instances from alternative pools.
- Spot Instances can also be **hibernated** (state saved to EBS) instead of terminated, if the root volume supports it and the instance type qualifies.

---

### Dedicated Hosts & Dedicated Instances

**Description:** Most EC2 instances run on shared physical hardware alongside other customers' VMs (multi-tenant). For workloads that require physical isolation — typically due to software licensing restrictions or regulatory compliance — AWS offers two dedicated options.

**Dedicated Instances:**

| Attribute | Details |
| --- | --- |
| **What** | Your VMs run on hardware used only by your AWS account, but the specific host can change over time |
| **Billing** | Per-instance hourly fee + a per-Region fee ($2/hr) when any Dedicated Instance is running |
| **Use case** | Compliance requirements that forbid sharing physical hardware with other organisations |
| **Control** | No visibility into or control over the underlying host |

**Dedicated Hosts:**

| Attribute | Details |
| --- | --- |
| **What** | You rent an entire physical server — full visibility and control over the host |
| **Billing** | Per-host per-hour (varies by instance family); On-Demand or via RI/Savings Plans |
| **BYOL** | Bring Your Own License (BYOL) — use existing per-socket or per-core Microsoft/Oracle licenses |
| **Host affinity** | Control which host your instances are placed on; instances can be stopped and restarted on the same host |
| **Use case** | BYOL for Windows Server, SQL Server, Oracle; strict regulatory isolation |

**Comparison:**

| | Multi-Tenant (default) | Dedicated Instance | Dedicated Host |
| --- | --- | --- | --- |
| Hardware shared with others | Yes | No | No |
| Know the physical host | No | No | Yes |
| BYOL support | No | No | Yes |
| Cost vs On-Demand | Baseline | +$2/Region/hr | Most expensive |
| Flexibility | Highest | Medium | Lowest |

**Common CLI operations:**

```bash
# Allocate a Dedicated Host for a specific instance family
aws ec2 allocate-hosts \
  --availability-zone us-east-1a \
  --instance-family m5 \
  --auto-placement on \
  --quantity 1

# List your Dedicated Hosts
aws ec2 describe-hosts \
  --query 'Hosts[*].[HostId,State,InstanceFamily,AvailabilityZone]' \
  --output table

# Launch an instance on a specific Dedicated Host
aws ec2 run-instances \
  --image-id ami-0abcdef1234567890 \
  --instance-type m5.large \
  --placement "Tenancy=host,HostId=h-0123456789abcdef0"
```

**Notes:**

- Dedicated Hosts are the only EC2 option that satisfies Microsoft and Oracle BYOL licensing terms on AWS — Dedicated Instances do not.
- If you don't need BYOL but just need hardware isolation, Dedicated Instances are cheaper and simpler.
- For most applications, multi-tenant On-Demand or Spot is sufficient — don't pay for Dedicated unless you have a clear licensing or compliance driver.

---

### Pricing Calculators & Cost Tools

**Description:** AWS provides a set of tools to estimate costs before deployment, analyse spend after the fact, and get recommendations for saving money. Use these before making any significant infrastructure decision.

| Tool | Purpose | When to use |
| --- | --- | --- |
| **AWS Pricing Calculator** | Estimate monthly costs before deploying | Architecture planning, budgeting, client proposals |
| **AWS Cost Explorer** | Visualise and analyse historical spend by service, Region, tag | Monthly reviews, identifying cost drivers |
| **AWS Budgets** | Set spend or usage thresholds and get alerted | Ongoing cost governance, Free Tier monitoring |
| **AWS Cost Anomaly Detection** | ML-based automatic detection of unusual spend | Catch runaway resources or accidental deployments |
| **AWS Trusted Advisor** | Best-practice checks including cost optimisation | Periodic account health checks |
| **Savings Plans / RI recommendations** | Data-driven suggestions based on your usage history | When considering a commitment purchase |
| **AWS Compute Optimizer** | Rightsizing recommendations for EC2, Lambda, EBS | Eliminating over-provisioned resources |
| **CloudWatch Billing Alarms** | Real-time alerts when estimated charges cross a threshold | Per-project or per-account guardrails |

**AWS Pricing Calculator (no sign-in required):**

Use it at [calculator.aws](https://calculator.aws/) to model any combination of services and get a monthly estimate. You can save and share estimates via a URL.

```
Useful for:
- Comparing On-Demand vs Reserved vs Spot for a given workload
- Estimating data transfer costs between Regions
- Modelling the cost of a multi-tier architecture (ALB + EC2 + RDS + S3)
```

**Cost Explorer via CLI:**

```bash
# Monthly spend by service for the current month
aws ce get-cost-and-usage \
  --time-period Start=$(date +%Y-%m-01),End=$(date +%Y-%m-%d) \
  --granularity MONTHLY \
  --metrics UnblendedCost \
  --group-by Type=DIMENSION,Key=SERVICE \
  --region us-east-1 \
  --query 'ResultsByTime[0].Groups[*].[Keys[0],Metrics.UnblendedCost.Amount]' \
  --output table

# Get RI purchase recommendations
aws ce get-reservation-purchase-recommendation \
  --service EC2 \
  --lookback-period-in-days SIXTY_DAYS \
  --payment-option NO_UPFRONT \
  --term-in-years ONE_YEAR \
  --region us-east-1

# Get Savings Plans recommendations
aws ce get-savings-plans-purchase-recommendation \
  --savings-plans-type COMPUTE_SP \
  --term-in-years ONE_YEAR \
  --payment-option NO_UPFRONT \
  --lookback-period-in-days SIXTY_DAYS \
  --region us-east-1
```

**General cost optimisation hierarchy:**

```
1. Right-size first  — use Compute Optimizer to eliminate waste
2. Commit to baselines — buy Savings Plans / RIs for steady-state
3. Spot the rest — use Spot for fault-tolerant scale-out
4. Architect efficiently — fewer API calls, same-Region data transfer, S3 lifecycle policies
5. Monitor continuously — Cost Anomaly Detection + Budgets alerts
```

**Notes:**

- Pricing varies by Region — `us-east-1` is typically the cheapest for most services. Always model costs in your target Region.
- AWS releases pricing changes regularly; use the [AWS Pricing API](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/price-changes.html) or the Pricing Calculator for up-to-date figures rather than memorised numbers.
- Tagging resources with `Project`, `Environment`, and `Owner` tags enables cost allocation reports that break down spend per team or product — essential for multi-team accounts.

---

## AWS Access Methods

AWS exposes every service through a unified underlying REST API. On top of that API, AWS provides several access methods suited to different workflows — from interactive point-and-click exploration to fully automated infrastructure pipelines. Every method ultimately signs and sends HTTPS requests to the same AWS API endpoints.

### One Shot Revision

| Topic | Short Description |
| --- | --- |
| [AWS Management Console](#aws-management-console) | Browser-based GUI — ideal for exploration, visualisation, and one-off tasks |
| [AWS CLI](#aws-cli) | Command-line tool for scripting, automation, and fast terminal-based management |
| [AWS SDKs](#aws-sdks) | Language-native libraries (Python, JS, Java, Go …) for programmatic access |
| [AWS CloudShell](#aws-cloudshell) | Browser-based shell with AWS CLI and SDKs pre-installed — no local setup |
| [AWS REST APIs](#aws-rest-apis) | Raw HTTPS calls signed with SigV4 — the foundation all other methods use |
| [Infrastructure as Code](#infrastructure-as-code) | CloudFormation and Terraform — declarative, version-controlled resource provisioning |

---

### AWS Management Console

The AWS Management Console is a web-based graphical interface for managing all AWS services. It is the starting point for most people learning AWS.

**URL:** `https://console.aws.amazon.com`

**Key features:**

| Feature | Description |
| --- | --- |
| **Service search bar** | Type any service name at the top to navigate directly to it |
| **Region selector** | Top-right dropdown — always confirm the correct region before making changes |
| **Resource Groups** | Group related resources from multiple services under a single tag-based view |
| **Cost Explorer** | Visualise and analyse your AWS spend directly in the console |
| **CloudWatch dashboards** | Built-in monitoring graphs for all services |
| **IAM integration** | Users log in with email + password + optional MFA; permissions are enforced by IAM policies |

**Login paths:**

| Account type | Login URL |
| --- | --- |
| Root user | `https://console.aws.amazon.com` → "Root user" tab |
| IAM user | `https://<account-id>.signin.aws.amazon.com/console` or the account alias URL |
| SSO / Identity Centre user | Custom SSO portal URL provided by the organisation |

**Best practices:**
- Enable MFA on the root account immediately after creating an AWS account.
- Do not use the root account for day-to-day work — create an IAM admin user and use that instead.
- Use the console for exploration and learning; switch to CLI or IaC for anything repeatable.

**Notes:**
- Changes made in the console take effect immediately — there is no "draft" or "preview" mode for most actions.
- Some console actions (e.g. terminating EC2 instances) cannot be undone. Always check the region selector before destructive operations.
- The console URL embeds the account ID: `https://console.aws.amazon.com/ec2/v2/home?region=us-east-1` — bookmark region-specific service pages for fast access.

---

### AWS CLI

The AWS CLI (Command Line Interface) is an open-source tool that lets you interact with AWS services directly from your terminal. It wraps the AWS REST APIs into easy-to-remember commands.

**Current version:** AWS CLI v2 (v1 is deprecated for new setups).

**Installation:**

```bash
# macOS (Homebrew)
brew install awscli

# Linux (official installer)
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip && sudo ./aws/install

# Windows (MSI installer)
# Download from https://awscli.amazonaws.com/AWSCLIV2.msi

# Verify installation
aws --version
# aws-cli/2.x.x Python/3.x.x ...
```

**Configuration:**

```bash
# Interactive setup — prompts for Access Key ID, Secret, Region, output format
aws configure

# Stored in:
#   ~/.aws/credentials  (Access Key ID and Secret Access Key)
#   ~/.aws/config       (region, output format, profiles)

# View current identity
aws sts get-caller-identity
```

**Named profiles** — use multiple AWS accounts or roles from the same machine:

```bash
# Create a named profile
aws configure --profile dev

# Use a named profile for a single command
aws s3 ls --profile dev

# Set a default profile for a shell session
export AWS_PROFILE=dev
```

**Environment variables** — override config files at runtime:

```bash
export AWS_ACCESS_KEY_ID=AKIA...
export AWS_SECRET_ACCESS_KEY=...
export AWS_DEFAULT_REGION=us-east-1
```

**Command structure:**

```
aws <service> <operation> [options]
       │           │
       │           └── list-buckets, describe-instances, create-key-pair ...
       └── s3, ec2, iam, lambda, rds ...
```

**Common examples:**

```bash
# List all S3 buckets
aws s3 ls

# Describe all EC2 instances in the current region
aws ec2 describe-instances

# Filter output with JMESPath query
aws ec2 describe-instances \
  --query "Reservations[*].Instances[*].[InstanceId,State.Name,PublicIpAddress]" \
  --output table

# Upload a file to S3
aws s3 cp myfile.txt s3://my-bucket/myfile.txt

# Create an S3 bucket
aws s3api create-bucket --bucket my-new-bucket --region us-east-1

# Invoke a Lambda function
aws lambda invoke \
  --function-name my-function \
  --payload '{"key": "value"}' \
  response.json

# Assume a role (returns temporary credentials)
aws sts assume-role \
  --role-arn arn:aws:iam::123456789012:role/MyRole \
  --role-session-name MySession
```

**Output formats:**

| Format | Description | When to use |
| --- | --- | --- |
| `json` | Full JSON output (default) | Piping to `jq` or scripting |
| `table` | Human-readable ASCII table | Quick visual inspection |
| `text` | Tab-separated values | `awk`/`cut` pipelines |
| `yaml` | YAML output | CloudFormation-style readability |

**Notes:**
- Always use `--dry-run` on destructive EC2 operations (e.g. `aws ec2 terminate-instances --dry-run`) to validate permissions without making changes.
- The CLI reads credentials in this precedence order: environment variables → `~/.aws/credentials` → IAM role on EC2/Lambda (instance profile).
- Use `aws configure sso` to set up SSO-based authentication instead of long-term access keys.
- Add `--no-cli-pager` to suppress the default pager for commands with long output.

---

### AWS SDKs

AWS SDKs are language-native libraries that wrap the AWS REST API into idiomatic function calls. They handle request signing (SigV4), retries with exponential backoff, pagination, and credential chain resolution automatically.

**Available SDKs:**

| Language | Package / Import |
| --- | --- |
| **Python** | `boto3` (`pip install boto3`) |
| **JavaScript / TypeScript** | `@aws-sdk/client-*` (AWS SDK for JavaScript v3) |
| **Java** | `software.amazon.awssdk.*` (AWS SDK for Java v2) |
| **Go** | `github.com/aws/aws-sdk-go-v2` |
| **Ruby** | `aws-sdk-*` (modular gems) |
| **.NET / C#** | `AWSSDK.*` NuGet packages |
| **PHP** | `aws/aws-sdk-php` |
| **Rust** | `aws-sdk-*` (official AWS SDK for Rust) |
| **Swift** | `aws-sdk-swift` |
| **Kotlin** | `aws.sdk.kotlin` |

**Python (boto3) — most common SDK examples:**

```python
import boto3

# Create a client (low-level, maps 1:1 to API operations)
s3 = boto3.client("s3", region_name="us-east-1")

# List buckets
response = s3.list_buckets()
for bucket in response["Buckets"]:
    print(bucket["Name"])

# Upload a file
s3.upload_file("local_file.txt", "my-bucket", "remote_key.txt")

# Create a resource (higher-level, object-oriented)
s3_resource = boto3.resource("s3")
bucket = s3_resource.Bucket("my-bucket")
for obj in bucket.objects.all():
    print(obj.key)
```

```python
import boto3

# EC2 — list running instances
ec2 = boto3.client("ec2", region_name="us-east-1")
response = ec2.describe_instances(
    Filters=[{"Name": "instance-state-name", "Values": ["running"]}]
)
for reservation in response["Reservations"]:
    for instance in reservation["Instances"]:
        print(instance["InstanceId"], instance["PublicIpAddress"])
```

```python
import boto3

# Lambda — invoke a function
lam = boto3.client("lambda", region_name="us-east-1")
response = lam.invoke(
    FunctionName="my-function",
    InvocationType="RequestResponse",
    Payload=b'{"key": "value"}',
)
print(response["Payload"].read())
```

**Credential resolution order (same for CLI and SDKs):**

```
1. Explicit code parameters (not recommended — hardcoding credentials)
2. Environment variables (AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY)
3. AWS credentials file (~/.aws/credentials)
4. AWS config file (~/.aws/config)
5. Container credentials (ECS task role)
6. EC2 instance profile / Lambda execution role  ← best for production
```

**Notes:**
- Never hardcode AWS credentials in application code. Use IAM roles for EC2/Lambda and environment variables or a secrets manager for local dev.
- `boto3.client` gives low-level access (mirrors the API exactly). `boto3.resource` gives a higher-level object-oriented interface (e.g. `s3.Bucket`, `ec2.Instance`). Both are valid.
- Use paginators for list operations that return more results than the API maximum per call: `paginator = s3.get_paginator("list_objects_v2")`.

---

### AWS CloudShell

AWS CloudShell is a browser-based shell environment provided directly inside the AWS Management Console. It comes pre-configured with AWS CLI v2, Python, Node.js, Git, and common DevOps tools.

**How to open:** In the AWS Console, click the CloudShell icon (terminal icon) in the top navigation bar, or press the keyboard shortcut.

**Key features:**

| Feature | Description |
| --- | --- |
| **Pre-authenticated** | Inherits the credentials of the currently logged-in console user — no `aws configure` needed |
| **Persistent storage** | 1 GB of persistent home directory storage per region — files survive session restarts |
| **Pre-installed tools** | AWS CLI v2, Python 3, Node.js, Git, `jq`, `bash`, `zsh` |
| **No cost** | CloudShell itself is free; you pay only for any AWS resources you create from it |
| **Regional** | Each AWS region has its own CloudShell environment with separate persistent storage |
| **File upload/download** | Drag-and-drop file uploads; download files via the Actions menu |

**Common use cases:**
- Run AWS CLI commands without installing anything locally — ideal in environments where you cannot install software.
- Quick scripting and testing during incidents.
- Demonstrating AWS CLI usage during training without shared credentials.
- Access a region-specific shell when working with resources in that region.

**Notes:**
- CloudShell sessions time out after ~20 minutes of inactivity but the persistent storage remains.
- Not a replacement for a local development environment — no Docker, limited compute, and no inbound network connections.
- The pre-authenticated credentials have the same permissions as your console IAM user — be mindful of what you run.

---

### AWS REST APIs

All AWS CLI commands, SDK calls, and console actions ultimately translate into **HTTPS requests** to AWS REST API endpoints. Understanding the raw API helps you work with unsupported SDKs, debug issues, and grasp how the other access methods work under the hood.

**Endpoint format:**

```
https://<service>.<region>.amazonaws.com/<path>
       │           │
       │           └── us-east-1, eu-west-1, ap-southeast-1 ...
       └── s3, ec2, iam, lambda, sts ...

Examples:
  https://ec2.us-east-1.amazonaws.com/
  https://s3.us-east-1.amazonaws.com/my-bucket/my-object
  https://sts.amazonaws.com/   (IAM and STS are global)
```

**Authentication — AWS Signature Version 4 (SigV4):**

Every AWS API request must be signed with your credentials using the SigV4 algorithm. The signature proves the request came from an authorised identity and prevents tampering.

SigV4 signing steps (handled automatically by CLI and SDKs):

```
1. Create a canonical request  (HTTP method, URI, query string, headers, body hash)
2. Create a string to sign      (algorithm, date, credential scope, hash of canonical request)
3. Calculate the signature      (HMAC-SHA256 using the derived signing key)
4. Add the signature to the request in the Authorization header
```

**Example: raw curl request to EC2 (SigV4 signed):**

```bash
# The AWS CLI can output the equivalent curl command for any operation
aws ec2 describe-instances \
  --region us-east-1 \
  --debug 2>&1 | grep "curl"

# Or use awscurl (pip install awscurl) for SigV4-signed curl commands:
awscurl --service ec2 --region us-east-1 \
  "https://ec2.us-east-1.amazonaws.com/?Action=DescribeInstances&Version=2016-11-15"
```

**Common API response codes:**

| HTTP Code | Meaning |
| --- | --- |
| `200 OK` | Request succeeded |
| `400 Bad Request` | Invalid parameters or malformed request |
| `403 Forbidden` | Missing or invalid credentials, or IAM policy denied the action |
| `404 Not Found` | Resource does not exist |
| `429 Too Many Requests` | API throttling — implement exponential backoff |
| `500 Internal Server Error` | AWS-side error — retry with backoff |

**Notes:**
- You rarely need to call the raw REST API directly — use the CLI or an SDK. The primary reason to know the API is for debugging (checking what the CLI is actually sending) or for environments without an SDK.
- AWS API throttling is per-account and per-region. If you hit `429` errors, implement exponential backoff with jitter. The SDKs do this automatically.
- Some services (e.g. S3) use REST-style APIs; others (e.g. EC2) use query-string-based APIs. The SDK abstracts this difference.

---

### Infrastructure as Code

Infrastructure as Code (IaC) means defining and provisioning AWS resources using declarative configuration files checked into version control. IaC eliminates manual console clicks, makes infrastructure reproducible, and enables change tracking via Git.

**AWS CloudFormation:**

CloudFormation is AWS's native IaC service. You write templates in JSON or YAML that describe the desired state of your resources, and CloudFormation handles create, update, and delete operations.

```yaml
# cloudformation-example.yaml — create an S3 bucket with versioning
AWSTemplateFormatVersion: "2010-09-09"
Description: Example S3 bucket with versioning enabled

Resources:
  MyBucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: my-versioned-bucket-2024
      VersioningConfiguration:
        Status: Enabled
      Tags:
        - Key: Environment
          Value: production

Outputs:
  BucketArn:
    Value: !GetAtt MyBucket.Arn
    Description: ARN of the created S3 bucket
```

```bash
# Deploy a CloudFormation stack
aws cloudformation deploy \
  --template-file cloudformation-example.yaml \
  --stack-name my-s3-stack

# Describe the stack outputs
aws cloudformation describe-stacks \
  --stack-name my-s3-stack \
  --query "Stacks[0].Outputs"

# Delete the stack (removes all resources it created)
aws cloudformation delete-stack --stack-name my-s3-stack
```

**Key CloudFormation concepts:**

| Concept | Description |
| --- | --- |
| **Stack** | A collection of AWS resources managed as a single unit |
| **Template** | YAML/JSON file describing the desired resources and their configuration |
| **Change Set** | Preview of what will change before applying an update — prevents surprises |
| **Drift detection** | Identifies resources that were manually changed outside CloudFormation |
| **Rollback** | If a stack update fails, CloudFormation automatically reverts to the last known good state |
| **Stack parameters** | Input values passed at deploy time — allows reusing one template across environments |
| **Stack outputs** | Values exported from the stack (ARNs, endpoints) that other stacks can import |

**AWS CDK (Cloud Development Kit):**

CDK lets you define AWS infrastructure using familiar programming languages (TypeScript, Python, Java, Go, C#). CDK synthesises your code into CloudFormation templates and deploys them.

```python
# cdk_example.py — S3 bucket with CDK (Python)
from aws_cdk import App, Stack
from aws_cdk import aws_s3 as s3
from constructs import Construct

class MyStack(Stack):
    def __init__(self, scope: Construct, id: str, **kwargs):
        super().__init__(scope, id, **kwargs)
        s3.Bucket(self, "MyBucket",
            versioned=True,
            bucket_name="my-cdk-bucket-2024"
        )

app = App()
MyStack(app, "MyStack")
app.synth()
```

```bash
cdk synth    # generate CloudFormation template
cdk diff     # show what will change
cdk deploy   # deploy to AWS
cdk destroy  # remove all resources
```

**Terraform (HashiCorp):**

Terraform is the most widely used multi-cloud IaC tool. It supports AWS, GCP, Azure, and hundreds of other providers through a plugin architecture.

```hcl
# main.tf — S3 bucket with Terraform
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

resource "aws_s3_bucket" "my_bucket" {
  bucket = "my-terraform-bucket-2024"
  tags = {
    Environment = "production"
  }
}

resource "aws_s3_bucket_versioning" "versioning" {
  bucket = aws_s3_bucket.my_bucket.id
  versioning_configuration {
    status = "Enabled"
  }
}
```

```bash
terraform init      # download providers
terraform plan      # preview changes
terraform apply     # apply changes
terraform destroy   # remove all resources
```

**CloudFormation vs CDK vs Terraform:**

| Feature | CloudFormation | CDK | Terraform |
| --- | --- | --- | --- |
| **Language** | YAML / JSON | TypeScript, Python, Java, Go, C# | HCL (HashiCorp Config Language) |
| **Provider support** | AWS only | AWS only (synths to CF) | Multi-cloud (AWS, GCP, Azure, 1000+ providers) |
| **State management** | Managed by AWS (stacks) | Managed by AWS (via CF) | Terraform state file (local or remote backend) |
| **Abstraction level** | Low — every resource property explicit | High — constructs, defaults, patterns | Medium — resource-level with modules |
| **Learning curve** | Low | Medium (requires programming knowledge) | Medium |
| **Rollback** | Automatic | Automatic (via CF) | Manual (`terraform apply` previous state) |
| **Best for** | Pure AWS, simple stacks | Developers comfortable with code | Multi-cloud, large teams, complex infra |

**Notes:**
- Always use IaC for production infrastructure. Manual console changes lead to configuration drift — two environments that look the same but behave differently.
- Store IaC templates in the same Git repository as the application code they support. Treat infrastructure changes as pull requests with review and approval.
- CloudFormation change sets are equivalent to `terraform plan` — always run one before applying an update to a production stack.
- CDK is the best choice for teams that are already proficient in Python or TypeScript and want to use programming constructs (loops, conditionals, classes) to avoid repetitive YAML.

---

## IAM — Identity and Access Management

AWS IAM (Identity and Access Management) is a **global, free service** that controls who can authenticate (sign in) and what they are authorized to do inside your AWS account. Every API call made to any AWS service — whether from the console, CLI, or SDK — is evaluated by IAM before it is allowed or denied. Because IAM underpins every other AWS service, it is the first thing to understand before working with EC2, S3, Lambda, or any other resource.

### One Shot Revision

| Topic                                           | Short Description                                                                          |
| ----------------------------------------------- | ------------------------------------------------------------------------------------------ |
| [IAM Overview](#iam-overview)                   | Core IAM concepts — the global identity plane, principals, authentication vs authorization |
| [IAM Users & Groups](#iam-users--groups)        | Long-term credentials for humans; groups as a policy-attachment shortcut                   |
| [IAM Roles](#iam-roles)                         | Short-term credentials for services, cross-account, and federated identities               |
| [IAM Policies](#iam-policies)                   | JSON documents that define permissions; managed vs inline; policy evaluation logic         |
| [IAM Best Practices](#iam-best-practices)       | Least privilege, MFA, root account hygiene, access key rotation, and more                  |

---

### IAM Overview

**Description:** IAM is the centralized security framework for an AWS account. It answers two questions for every API call: *Who are you?* (authentication) and *What are you allowed to do?* (authorization). IAM operates globally — it has no region — and its entities (users, groups, roles, policies) are shared across all AWS regions in the account.

**Key concepts:**

| Term            | What it is                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------- |
| **Principal**   | Any identity that can make a request: root user, IAM user, IAM role, AWS service            |
| **Authentication** | Proving identity — via password + MFA (console), access key + secret (CLI/SDK), or signed token (role) |
| **Authorization** | Deciding what the authenticated principal may do — evaluated against attached policies     |
| **ARN**         | Amazon Resource Name — the globally unique identifier for every AWS resource and IAM entity |
| **Account root** | The original email/password identity; has unrestricted access; should be locked away        |

**How a request is evaluated:**

1. AWS receives the API call with the caller's identity.
2. It looks up all policies attached to that identity (user policies, group policies, role session policies, resource-based policies, SCPs).
3. **Default deny** — if no policy explicitly allows the action, it is denied.
4. An **explicit deny** in any policy overrides all allows.
5. Only if an **explicit allow** exists and no explicit deny exists is the action permitted.

**Learn from the official source:**

→ [AWS IAM — Official Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)

**Notes:**

- IAM is **eventually consistent** — policy changes may take a few seconds to propagate globally.
- IAM itself is **free**; you pay nothing for the number of users, roles, or policies.
- The **account root user** should never be used for day-to-day work. Create an admin IAM user or role instead and enable MFA on root immediately.

---

### IAM Users & Groups

**Description:** An IAM **user** is a long-term identity with a fixed username, optional console password, and optional programmatic access keys. A **group** is a collection of users — attaching a policy to a group automatically grants it to every member. Groups exist purely as a permission-management shortcut; they are not principals themselves and cannot be used in trust policies.

**IAM Users — key facts:**

| Attribute              | Details                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| **Console access**     | Enabled with a password; optionally enforced with MFA                                       |
| **Programmatic access**| `Access Key ID` + `Secret Access Key` pair used by CLI, SDK, and API calls                  |
| **Max access keys**    | 2 per user (rotate by creating the second, updating apps, then deleting the old one)        |
| **ARN format**         | `arn:aws:iam::123456789012:user/alice`                                                      |
| **Max users/account**  | 5,000 (soft limit, can request increase)                                                    |

**IAM Groups — key facts:**

| Attribute              | Details                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| **Purpose**            | Attach policies once to the group; all members inherit permissions automatically            |
| **Nesting**            | Groups **cannot** contain other groups — one level only                                     |
| **A user in many groups** | A user can belong to up to 10 groups; all group policies are merged                     |
| **ARN format**         | `arn:aws:iam::123456789012:group/developers`                                                |

**Common CLI operations:**

```bash
# Create a user
aws iam create-user --user-name alice

# Create a group and add a user
aws iam create-group --group-name developers
aws iam add-user-to-group --user-name alice --group-name developers

# Attach an AWS managed policy to a group
aws iam attach-group-policy \
  --group-name developers \
  --policy-arn arn:aws:iam::aws:policy/AmazonEC2ReadOnlyAccess

# Create an access key for programmatic access
aws iam create-access-key --user-name alice

# List users
aws iam list-users

# List groups for a user
aws iam list-groups-for-user --user-name alice
```

**Notes:**

- Never embed access keys in source code or commit them to git. Use environment variables, `~/.aws/credentials`, or — better — an IAM role.
- Rotate access keys regularly. Audit unused keys with `aws iam generate-credential-report`.
- Prefer groups over attaching policies directly to users — it keeps permissions auditable and consistent.

---

### IAM Roles

**Description:** An IAM **role** is an identity that can be *assumed* temporarily. Unlike a user, a role has no password or long-term access key — it issues short-lived **STS tokens** (valid 15 min–12 h). Roles are the standard way to grant permissions to AWS services (EC2, Lambda, ECS), cross-account access, and federated/SSO identities. Any principal that assumes a role gets a temporary `AccessKeyId`, `SecretAccessKey`, and `SessionToken`.

**Role anatomy:**

| Component              | Purpose                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| **Trust policy**       | Defines *who* is allowed to assume this role (the principal — a service, account, or user) |
| **Permission policy**  | Defines *what* the role can do once assumed                                                 |
| **Session duration**   | How long the temporary credentials last (15 min – 12 h)                                    |
| **ARN format**         | `arn:aws:iam::123456789012:role/MyRole`                                                     |

**Example trust policy — allow EC2 to assume the role:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": { "Service": "ec2.amazonaws.com" },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

**Example trust policy — allow cross-account assume:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": { "AWS": "arn:aws:iam::111122223333:root" },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

**Common CLI operations:**

```bash
# Create a role with a trust policy file
aws iam create-role \
  --role-name MyEC2Role \
  --assume-role-policy-document file://trust-policy.json

# Attach a permission policy to the role
aws iam attach-role-policy \
  --role-name MyEC2Role \
  --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess

# Create an instance profile and add the role (required to attach a role to EC2)
aws iam create-instance-profile --instance-profile-name MyEC2Profile
aws iam add-role-to-instance-profile \
  --instance-profile-name MyEC2Profile \
  --role-name MyEC2Role

# Assume a role manually (returns temp credentials)
aws sts assume-role \
  --role-arn arn:aws:iam::123456789012:role/MyRole \
  --role-session-name my-session
```

**Common role use cases:**

| Use case                   | How it works                                                                        |
| -------------------------- | ----------------------------------------------------------------------------------- |
| EC2 instance role          | Attach via Instance Profile; app uses IMDS to get temp creds automatically          |
| Lambda execution role      | Lambda assumes the role on every invocation; no key management needed               |
| Cross-account access       | Account B role trusts Account A; Account A users/roles call `sts:AssumeRole`        |
| OIDC / GitHub Actions      | GitHub OIDC provider issues a token; AWS validates it and issues role credentials   |
| AWS SSO / Identity Center  | Federated users assume permission-set-backed roles; no long-term IAM users needed   |

**Notes:**

- Prefer roles over access keys wherever possible. Temp credentials auto-expire, limiting blast radius if leaked.
- For EC2, the credentials are automatically rotated by the **Instance Metadata Service (IMDS)** — your app just calls the AWS SDK normally.
- Use `aws sts get-caller-identity` to verify which identity (user or role session) you are currently operating as.

---

### IAM Policies

**Description:** IAM **policies** are JSON documents that specify what actions are allowed or denied on which resources under what conditions. They are the building blocks of authorization in AWS. Every allow or deny decision traces back to one or more policies.

**Policy types:**

| Type                       | Attached to                         | Typical use                                                         |
| -------------------------- | ----------------------------------- | ------------------------------------------------------------------- |
| **AWS Managed**            | User, group, role                   | Pre-built, AWS-maintained — e.g., `AdministratorAccess`, `AmazonS3FullAccess` |
| **Customer Managed**       | User, group, role                   | Custom policies you own and version                                 |
| **Inline**                 | Embedded directly in a single entity | Strict 1-to-1 relationship; deleted with the entity                 |
| **Resource-based**         | The resource itself (S3 bucket, SQS) | Grants cross-account access without assuming a role                 |
| **Service Control Policy** | AWS Organization OU or account      | Hard ceiling on what any principal in the account can ever do       |
| **Session policy**         | Passed during `AssumeRole`          | Further restricts (never expands) the role's permissions            |

**Policy JSON structure:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowS3ListBucket",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::my-bucket",
        "arn:aws:s3:::my-bucket/*"
      ],
      "Condition": {
        "StringEquals": { "s3:prefix": ["logs/"] }
      }
    },
    {
      "Sid": "DenyDeleteOnProd",
      "Effect": "Deny",
      "Action": "s3:DeleteObject",
      "Resource": "arn:aws:s3:::prod-bucket/*"
    }
  ]
}
```

**Policy JSON fields:**

| Field         | Required | Description                                                                          |
| ------------- | -------- | ------------------------------------------------------------------------------------ |
| `Version`     | Yes      | Always `"2012-10-17"` (the current policy language version)                          |
| `Statement`   | Yes      | Array of one or more permission statements                                           |
| `Sid`         | No       | Statement ID — a human-readable label; no functional effect                          |
| `Effect`      | Yes      | `"Allow"` or `"Deny"`                                                                |
| `Action`      | Yes      | API action(s) — `"s3:GetObject"`, `"ec2:*"`, etc.                                   |
| `Resource`    | Yes      | ARN(s) the statement applies to; `"*"` means all resources                           |
| `Condition`   | No       | Optional context conditions (IP range, MFA present, tag match, time of day, etc.)   |

**Policy evaluation order:**

```
Default Deny → SCP → Resource-based → Identity-based → Session policy → Explicit Deny wins over all
```

**Common CLI operations:**

```bash
# Create a customer-managed policy from a file
aws iam create-policy \
  --policy-name MyS3Policy \
  --policy-document file://s3-policy.json

# Attach to a user / group / role
aws iam attach-user-policy   --user-name alice   --policy-arn arn:aws:iam::123456789012:policy/MyS3Policy
aws iam attach-group-policy  --group-name devs   --policy-arn arn:aws:iam::123456789012:policy/MyS3Policy
aws iam attach-role-policy   --role-name MyRole  --policy-arn arn:aws:iam::123456789012:policy/MyS3Policy

# List policies attached to a user
aws iam list-attached-user-policies --user-name alice

# Simulate a policy (check if an action would be allowed)
aws iam simulate-principal-policy \
  --policy-source-arn arn:aws:iam::123456789012:user/alice \
  --action-names s3:DeleteObject \
  --resource-arns arn:aws:s3:::my-bucket/file.txt
```

**Notes:**

- **Explicit Deny always wins** — even if ten policies allow an action, a single deny blocks it.
- Use `aws iam simulate-principal-policy` or the **IAM Policy Simulator** in the console to test permissions before deploying.
- Wildcards in actions (`"ec2:*"`) and resources (`"*"`) are powerful but dangerous — always scope down to the minimum needed.
- A policy with `"Resource": "*"` and `"Action": "*"` is effectively administrator access.

---

### IAM Best Practices

**Description:** A checklist of IAM security practices recommended by AWS and the security community. Following these drastically reduces the attack surface of an AWS account.

| Practice                          | Why it matters                                                                                     |
| --------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Lock away the root user**       | Root has unrestricted access and cannot be constrained by SCPs. Enable MFA, remove access keys, and never use it for routine tasks. |
| **Apply least-privilege**         | Grant only the permissions needed for a specific task. Start minimal and expand as needed.          |
| **Use roles, not access keys**    | Roles issue short-lived credentials that auto-rotate. Access keys are long-lived and risky if leaked. |
| **Enable MFA everywhere**         | Require MFA for console sign-in, especially for privileged users and root.                          |
| **Rotate access keys regularly**  | If long-term keys must exist, rotate them on a schedule and deactivate unused keys.                 |
| **Use groups to assign policies** | Attach policies to groups, not individual users — easier to audit and change at scale.              |
| **Use AWS managed policies first**| AWS maintains and updates them. Create customer-managed policies only when you need custom logic.   |
| **Use conditions to restrict access** | Add `aws:MultiFactorAuthPresent`, `aws:SourceIp`, or tag conditions to narrow policy scope.    |
| **Enable IAM Access Analyzer**    | Automatically flags resources (S3, IAM roles) that are accessible from outside your account.       |
| **Generate and review credential reports** | `aws iam generate-credential-report` lists all users with password/key age and MFA status. |
| **Prefer AWS SSO / Identity Center** | Centrally manage human access across accounts without creating per-account IAM users.           |
| **Tag IAM resources**             | Tag users, roles, and policies for cost allocation, automation, and ABAC (attribute-based access control). |

**Quick commands for auditing:**

```bash
# Generate a credential report (wait ~30 s, then download)
aws iam generate-credential-report
aws iam get-credential-report --output text --query Content | base64 --decode

# Find users with no MFA enabled
aws iam list-users --query 'Users[*].UserName' --output text | \
  tr '\t' '\n' | xargs -I{} aws iam list-mfa-devices --user-name {}

# List all access keys and their status
aws iam list-users --output text --query 'Users[*].UserName' | \
  tr '\t' '\n' | xargs -I{} aws iam list-access-keys --user-name {}

# Check if root has active access keys (should always return empty)
aws iam get-account-summary --query 'SummaryMap.AccountAccessKeysPresent'
```

**Notes:**

- An account score of 0 on `AccountAccessKeysPresent` is what you want — root should have no active keys.
- AWS **IAM Access Analyzer** and **AWS Trusted Advisor** both surface IAM misconfigurations automatically in the console.
- For organizations with many accounts, enforce guardrails via **Service Control Policies (SCPs)** in AWS Organizations, not per-account IAM policies.

---

## Amazon S3

Amazon S3 (Simple Storage Service) is AWS's foundational **object storage** service. It stores data as discrete objects inside containers called **buckets**, and exposes them through a simple HTTP API. S3 underpins a vast portion of the AWS ecosystem — CloudFront origins, Lambda deployment packages, EC2 AMIs, data lakes, static website hosting, and more.

### One Shot Revision

| Topic                                               | Short Description                                                                       |
| --------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [S3 Overview](#s3-overview)                         | Core S3 concepts — buckets, objects, keys, regions, durability                          |
| [S3 Buckets & Objects](#s3-buckets--objects)        | Bucket naming rules, object structure, metadata, presigned URLs                         |
| [S3 Storage Classes](#s3-storage-classes)           | Standard, IA, Glacier, Intelligent-Tiering — cost vs retrieval trade-offs               |
| [S3 Security](#s3-security)                         | Bucket policies, ACLs, encryption, Block Public Access, VPC endpoints                  |

---

### S3 Overview

**Description:** S3 stores arbitrary data as **objects** inside regionally-scoped **buckets**. Each object consists of the binary data, metadata, and a **key** — its unique name within the bucket. S3 is designed for 99.999999999% (11 nines) durability by automatically replicating data across three or more AZs within a region.

**Core concepts:**

| Term             | What it is                                                                                        |
| ---------------- | ------------------------------------------------------------------------------------------------- |
| **Bucket**       | A container for objects; created in a specific AWS region                                         |
| **Object**       | A file plus its metadata; up to 5 TB per object                                                   |
| **Key**          | The unique identifier (path) of an object within a bucket                                         |
| **Region**       | Buckets are regional; data stays in the region unless you configure replication                   |
| **Versioning**   | When enabled, S3 preserves every version of an object on overwrite or delete                      |
| **Durability**   | 99.999999999% — 11 nines; AWS replicates across ≥3 AZs automatically                            |
| **Availability** | Varies by storage class; Standard = 99.99%                                                        |

**Object URL format:**

```
https://<bucket-name>.s3.<region>.amazonaws.com/<key>
```

**Learn from the official source:**

→ [Amazon S3 — Official AWS Documentation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)

**Notes:**

- S3 is **not a filesystem** — there are no true directories. What look like folders are key prefixes (e.g. `logs/2024/01/app.log` is one flat key).
- Since December 2020, S3 offers **strong read-after-write consistency** for all operations in all regions.
- S3 operates on a **global namespace** for bucket names — two accounts cannot own the same bucket name simultaneously.

---

### S3 Buckets & Objects

**Description:** Everything in S3 lives inside a bucket. Understanding bucket naming, object structure, and access patterns is essential for using S3 correctly.

**Bucket rules:**

| Rule                  | Detail                                                                                          |
| --------------------- | ----------------------------------------------------------------------------------------------- |
| **Global uniqueness** | Bucket names are globally unique across all AWS accounts and regions                            |
| **Name format**       | 3–63 characters; lowercase letters, numbers, hyphens; must start with a letter or number        |
| **No IPs**            | Names must not be formatted as IP addresses (e.g. `192.168.1.1`)                               |
| **Regional resource** | Created in a specific region; data stays there unless replicated                                |
| **Default limit**     | 100 buckets per account (soft limit; raise via Support to 1,000)                               |

**Object structure:**

| Component        | Detail                                                                                            |
| ---------------- | ------------------------------------------------------------------------------------------------- |
| **Key**          | The full "path" within the bucket (e.g. `images/2024/photo.jpg`)                                 |
| **Value**        | The actual binary data                                                                            |
| **Metadata**     | System metadata (Content-Type, Last-Modified) + up to 10 user-defined key-value pairs            |
| **Version ID**   | Present when versioning is enabled; null otherwise                                                |
| **Max size**     | 5 TB per object                                                                                   |
| **Multipart upload** | Required for objects > 5 GB; recommended above 100 MB                                        |

**Presigned URLs:**

A presigned URL grants time-limited access to a private S3 object without exposing credentials. Useful for allowing a browser or third party to upload or download a specific object directly.

```bash
# Generate a presigned download URL (valid for 1 hour)
aws s3 presign s3://my-bucket/private/report.pdf --expires-in 3600
```

**Notes:**

- S3 **simulates folders** via key prefixes; the console renders these as folders but the underlying model is a flat key-value store.
- Use **multipart upload** for large files — it enables parallel uploads, is resumable on failure, and is required for objects > 5 GB.
- **S3 Transfer Acceleration** uses CloudFront edge locations to speed up long-distance uploads.

---

### S3 Storage Classes

**Description:** S3 offers multiple storage classes optimised for different access patterns and cost profiles. Choosing the right class reduces costs without sacrificing durability.

| Storage Class                       | Use Case                                        | Durability  | Availability | Retrieval            |
| ----------------------------------- | ----------------------------------------------- | ----------- | ------------ | -------------------- |
| **Standard**                        | Frequently accessed data                        | 11 nines    | 99.99%       | Milliseconds         |
| **Standard-IA**                     | Infrequently accessed; must survive AZ failure  | 11 nines    | 99.9%        | Milliseconds + fee   |
| **One Zone-IA**                     | Infrequent access; can be recreated if lost     | 11 nines    | 99.5%        | Milliseconds + fee   |
| **Glacier Instant Retrieval**       | Archives needing instant access                 | 11 nines    | 99.9%        | Milliseconds         |
| **Glacier Flexible Retrieval**      | Archives; occasional access                     | 11 nines    | 99.99%       | Minutes–hours        |
| **Glacier Deep Archive**            | Long-term compliance archives (7–10 years)      | 11 nines    | 99.99%       | 12–48 hours          |
| **Intelligent-Tiering**             | Unknown or changing access patterns             | 11 nines    | 99.9%        | Depends on tier      |

**Key distinctions:**

- **Standard vs Standard-IA:** Standard-IA costs less per GB stored but adds a per-GB retrieval fee. Break-even is roughly 30 access days per month.
- **One Zone-IA:** ~20% cheaper than Standard-IA but data lives in a single AZ — only appropriate for reproducible data (e.g. derived thumbnails).
- **Intelligent-Tiering:** Automatically moves objects between Frequent and Infrequent tiers with no retrieval fees within tiers; monitoring fee per object per month.
- **Glacier:** For data accessed once per quarter or less. Deep Archive is the cheapest option with the highest retrieval latency.

**S3 Lifecycle policies** let you automatically transition objects between storage classes or expire them:

```json
{
  "Rules": [
    {
      "ID": "move-to-glacier",
      "Status": "Enabled",
      "Transitions": [
        { "Days": 90, "StorageClass": "GLACIER" }
      ],
      "Expiration": { "Days": 365 }
    }
  ]
}
```

**Notes:**

- All S3 storage classes share the same 11-nines durability (One Zone-IA is the same numerically but exposed to AZ-level loss events).
- When versioning is enabled, lifecycle rules apply per version. Expired versions become **noncurrent** and can be separately transitioned or deleted.

---

### S3 Security

**Description:** S3 security is controlled through a layered permission model: IAM identity policies (who can act), bucket policies (what can be done on this bucket), ACLs (legacy per-object grants), and the account-level Block Public Access override.

**Permission layers:**

| Layer                     | Scope              | Recommended use                                                         |
| ------------------------- | ------------------ | ----------------------------------------------------------------------- |
| **IAM identity policy**   | Principal-level    | Grant/deny S3 actions to IAM users, roles, and services                 |
| **Bucket policy**         | Bucket/object      | Cross-account access, enforce HTTPS, IP restrictions                    |
| **ACL**                   | Object/bucket      | Legacy — avoid for new deployments; prefer bucket policies              |
| **Block Public Access**   | Account or bucket  | Hard override that prevents any public ACL or policy from taking effect |

**Block Public Access (recommended default ON):**

```bash
# Block all public access on a specific bucket
aws s3api put-public-access-block \
  --bucket my-bucket \
  --public-access-block-configuration \
    "BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true"
```

**Bucket policy example — enforce HTTPS only:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyHTTP",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:*",
      "Resource": [
        "arn:aws:s3:::my-bucket",
        "arn:aws:s3:::my-bucket/*"
      ],
      "Condition": {
        "Bool": { "aws:SecureTransport": "false" }
      }
    }
  ]
}
```

**Encryption options:**

| Type                       | Who manages the key | Detail                                                   |
| -------------------------- | ------------------- | -------------------------------------------------------- |
| **SSE-S3**                 | AWS (S3-managed)    | Default since Jan 2023; AES-256; no additional cost      |
| **SSE-KMS**                | AWS KMS             | Audit trail via CloudTrail; key rotation; per-call cost  |
| **SSE-C**                  | Customer            | You provide the key per request; AWS never stores it     |
| **Client-side encryption** | Customer            | Encrypt before upload; AWS never sees plaintext          |

**Notes:**

- As of **January 2023**, S3 enables **SSE-S3 encryption by default** on all new objects — no configuration required.
- A bucket policy alone does **not** make a bucket private if Block Public Access is off — always enable Block Public Access unless you intentionally serve public content.
- Use **S3 Access Logs** or **AWS CloudTrail Data Events** to audit object access and modifications.
- **VPC Gateway Endpoints** for S3 route traffic from a VPC to S3 without traversing the public internet — no NAT Gateway required.

---

## Elastic Compute Cloud

Amazon EC2 (Elastic Compute Cloud) provides resizable virtual servers — called **instances** — in the AWS cloud. It's the foundational compute service for most AWS workloads, letting you launch, configure, scale, and terminate machines on demand without owning physical hardware.

### One Shot Revision

| Topic                                                           | Short Description                                                                  |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| [EC2 Overview](#ec2-overview)                                   | Core EC2 concepts — instances, AMIs, instance types, key pairs, regions            |
| [EC2 Instance Types](#ec2-instance-types)                       | General purpose, compute, memory, storage, and accelerated computing families      |
| [AMIs — Amazon Machine Images](#amis--amazon-machine-images)    | Pre-configured templates used to launch EC2 instances                              |
| [EC2 Security Groups](#ec2-security-groups)                     | Stateful virtual firewalls that control instance-level traffic                     |
| [EBS — Elastic Block Store](#ebs--elastic-block-store)          | Persistent block-storage volumes attached to EC2 instances                         |
| [Key Pairs & SSH Access](#key-pairs--ssh-access)                | Asymmetric key authentication for Linux EC2 instances                              |

---

### EC2 Overview

**Description:** An EC2 instance is a virtual machine running on AWS hardware. You choose the OS (via an AMI), the hardware profile (instance type), the network placement (VPC and subnet), security rules (security groups), and storage (EBS volumes). EC2 gives IaaS-level control — you are responsible for the OS, runtime, and application; AWS manages the physical host.

**Core concepts:**

| Term                   | What it is                                                                                        |
| ---------------------- | ------------------------------------------------------------------------------------------------- |
| **Instance**           | A running virtual machine; uniquely identified by an Instance ID                                 |
| **AMI**                | Amazon Machine Image — the OS template used to boot an instance                                  |
| **Instance type**      | The hardware profile: vCPU count, memory, network bandwidth                                      |
| **Key pair**           | Asymmetric key used for SSH (Linux) or password decryption (Windows)                             |
| **Security group**     | Stateful virtual firewall attached to an instance's network interface                            |
| **EBS volume**         | Persistent block storage attached to an instance; survives instance stop/start                   |
| **Elastic IP**         | Static public IPv4 address that can be re-associated across instances                            |
| **User data**          | A bootstrap script that runs once when an instance first launches                                |
| **Instance metadata**  | Endpoint at `169.254.169.254` exposing instance attributes and temporary IAM credentials         |

**Instance lifecycle:**

```
Pending → Running → Stopping → Stopped → Terminated
                 ↘ Shutting-down → Terminated
```

- **Stop:** EBS data persists; compute billing stops; EBS storage continues to be billed.
- **Terminate:** Instance and root volume are deleted (unless delete-on-termination is disabled).
- **Hibernate:** RAM state is saved to EBS; instance resumes from where it left off.

**Learn from the official source:**

→ [AWS EC2 Concepts — Official AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)

**Notes:**

- Instances not in a stopped or terminated state incur compute charges. Always terminate unused instances.
- Attach an **IAM role** to an instance instead of embedding credentials — temporary credentials are delivered via IMDS and auto-rotate.
- Use **EC2 Instance Connect** or **AWS Systems Manager Session Manager** for SSH access without managing key pairs or opening port 22.

---

### EC2 Instance Types

**Description:** Instance types define the hardware profile — vCPUs, memory, network performance, and available storage. They follow the naming convention `<family><generation>.<size>` (e.g. `t3.medium`, `c6i.xlarge`).

**Instance families:**

| Family                              | Optimised for                   | Example types       | Typical use cases                                   |
| ----------------------------------- | ------------------------------- | ------------------- | --------------------------------------------------- |
| **General Purpose (T, M)**          | Balanced CPU/memory             | t3, t4g, m6i, m7g   | Web servers, dev/test, small databases              |
| **Compute Optimised (C)**           | High CPU-to-memory ratio        | c6i, c7g            | Batch processing, web tier, HPC front-end           |
| **Memory Optimised (R, X, z)**      | Large in-memory datasets        | r6i, x2iedn         | In-memory DBs (Redis, SAP HANA), big data           |
| **Storage Optimised (I, D, H)**     | High sequential disk throughput | i4i, d3en           | NoSQL DBs, data warehouses, Hadoop                  |
| **Accelerated Computing (P, G, Inf, Trn)** | GPUs / custom ASICs      | p4d, g5, inf2, trn1 | ML training, inference, video rendering             |
| **HPC (Hpc)**                       | Tightly coupled HPC workloads   | hpc6a               | Computational fluid dynamics, genomics              |

**Size suffixes (smallest → largest):**

`nano` → `micro` → `small` → `medium` → `large` → `xlarge` → `2xlarge` → … → `metal`

**T-series burstable instances:**

T-series instances (t2, t3, t4g) earn CPU credits during idle periods and spend them during bursts. With `unlimited` mode enabled, the instance can burst beyond its credit balance at an additional per-CPU-hour charge.

**Notes:**

- **Graviton (Arm-based)** instance types (`t4g`, `m7g`, `c7g`, `r7g`) provide up to 40% better price/performance than x86 equivalents for compatible workloads.
- Use the **AWS Instance Type Explorer** in the EC2 console to compare families and filter by vCPU, memory, and network requirements.

---

### AMIs — Amazon Machine Images

**Description:** An AMI is the template used to launch an EC2 instance. It bundles the OS, pre-installed software, configuration, and optional data volumes into a reusable snapshot. Every instance is launched from exactly one AMI.

**AMI components:**

| Component                | Detail                                                                                             |
| ------------------------ | -------------------------------------------------------------------------------------------------- |
| **Root volume snapshot** | EBS snapshot with the OS and pre-installed software                                                |
| **Launch permissions**   | Who can use the AMI: public, specific accounts, or private                                         |
| **Block device mapping** | Defines volumes attached at launch: root device + any additional EBS/ephemeral volumes             |

**AMI sources:**

| Source              | Examples                                                               |
| ------------------- | ---------------------------------------------------------------------- |
| **AWS-provided**    | Amazon Linux 2023, Ubuntu, Windows Server, RHEL, SUSE                 |
| **AWS Marketplace** | Third-party commercial/open-source images (pre-licensed software)      |
| **Community AMIs**  | Public images shared by other AWS accounts                             |
| **Custom**          | Created from a running or stopped instance; golden images              |

**Creating a custom AMI:**

```bash
# Create an AMI from a running instance
aws ec2 create-image \
  --instance-id i-0abcd1234efgh5678 \
  --name "my-golden-image-v1" \
  --no-reboot
```

**Copying an AMI to another region:**

```bash
aws ec2 copy-image \
  --source-region us-east-1 \
  --source-image-id ami-0abcdef1234567890 \
  --region eu-west-1 \
  --name "my-image-eu-west-1"
```

**Notes:**

- AMIs are **regional** — an AMI in `us-east-1` cannot launch instances in `eu-west-1` without copying it first.
- Use **EC2 Image Builder** to automate creation, testing, and distribution of custom AMIs on a schedule.
- An AMI is backed by EBS snapshots; you pay for snapshot storage even if the AMI isn't actively used. Deregister unused AMIs and delete their backing snapshots.

---

### EC2 Security Groups

**Description:** A security group is a **stateful virtual firewall** that controls inbound and outbound traffic for one or more EC2 instances. Rules allow traffic by protocol, port range, and source/destination (CIDR or another security group reference).

**Key properties:**

| Property             | Detail                                                                                                      |
| -------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Stateful**         | Inbound response traffic is automatically allowed — no explicit return rule needed                          |
| **Default deny**     | All traffic is denied unless an explicit allow rule exists                                                   |
| **No deny rules**    | Security groups can only allow traffic; use Network ACLs (NACLs) for subnet-level deny rules                |
| **Multiple groups**  | An instance can have up to 5 security groups; rules are unioned                                             |
| **Group-as-source**  | Rules can reference another security group as source, enabling dynamic allow-listing (e.g. ALB → app tier)  |

**Common rule examples:**

```bash
# Allow SSH from a specific IP
aws ec2 authorize-security-group-ingress \
  --group-id sg-0abc1234 \
  --protocol tcp --port 22 \
  --cidr 203.0.113.10/32

# Allow HTTP from anywhere
aws ec2 authorize-security-group-ingress \
  --group-id sg-0abc1234 \
  --protocol tcp --port 80 \
  --cidr 0.0.0.0/0

# Allow all traffic from another security group (e.g. ALB)
aws ec2 authorize-security-group-ingress \
  --group-id sg-0abc1234 \
  --protocol -1 \
  --source-group sg-0loadbalancer
```

**Security group vs NACL:**

| Feature          | Security Group           | NACL                            |
| ---------------- | ------------------------ | ------------------------------- |
| Level            | Instance (ENI)           | Subnet                          |
| Stateful         | Yes                      | No                              |
| Deny rules       | No                       | Yes                             |
| Evaluation       | All rules evaluated      | Rules evaluated in number order |

**Notes:**

- Never open port 22 to `0.0.0.0/0` in production. Use EC2 Instance Connect, Session Manager, or restrict to a bastion host IP.
- Security groups are **free** — create as many granular groups as needed. Consolidating all rules into one SG makes auditing harder.

---

### EBS — Elastic Block Store

**Description:** EBS provides persistent **block storage** volumes that attach to EC2 instances over the network. Unlike instance store (ephemeral, physically attached), EBS volumes persist independently of the instance lifecycle — data survives instance stops and volumes can be detached and reattached.

**EBS volume types:**

| Type                          | Use case                   | Max IOPS   | Max throughput | Notes                                            |
| ----------------------------- | -------------------------- | ---------- | -------------- | ------------------------------------------------ |
| **gp3** (General Purpose SSD) | Most workloads             | 16,000     | 1,000 MB/s     | Default; IOPS independent of size; cheaper than gp2 |
| **gp2** (General Purpose SSD) | Legacy default             | 16,000     | 250 MB/s       | IOPS tied to volume size (3 IOPS/GB)             |
| **io2 Block Express**         | Mission-critical DBs       | 256,000    | 4,000 MB/s     | 99.999% durability; sub-millisecond latency      |
| **io1**                       | I/O-intensive workloads    | 64,000     | 1,000 MB/s     | Legacy provisioned IOPS                          |
| **st1** (Throughput HDD)      | Big data, log processing   | 500        | 500 MB/s       | Sequential read/write; cannot be boot volume     |
| **sc1** (Cold HDD)            | Infrequently accessed      | 250        | 250 MB/s       | Lowest cost; cannot be boot volume               |

**Key EBS concepts:**

| Concept            | Detail                                                                                                         |
| ------------------ | -------------------------------------------------------------------------------------------------------------- |
| **Snapshot**       | Point-in-time backup stored in S3; incremental; used to create new volumes or AMIs                             |
| **Encryption**     | AES-256 via AWS KMS; optional but low-overhead — enable at creation                                            |
| **Multi-attach**   | io1/io2 volumes can attach to up to 16 Nitro instances simultaneously (same AZ)                               |
| **AZ-bound**       | A volume exists in one AZ; to move, snapshot it and create a new volume in the target AZ                      |

**Common operations:**

```bash
# Create a gp3 volume
aws ec2 create-volume --volume-type gp3 --size 100 \
  --availability-zone us-east-1a

# Attach to an instance
aws ec2 attach-volume --volume-id vol-0abc1234 \
  --instance-id i-0efgh5678 --device /dev/sdf

# Create a snapshot for backup
aws ec2 create-snapshot --volume-id vol-0abc1234 \
  --description "Pre-deployment backup"
```

**Notes:**

- **Prefer gp3 over gp2** for new volumes — gp3 lets you provision IOPS and throughput independently and costs ~20% less per GB.
- Enable **EBS encryption by default** at the account level so all new volumes and snapshots are encrypted automatically: `aws ec2 enable-ebs-encryption-by-default`.
- Use **Amazon Data Lifecycle Manager (DLM)** to automate snapshot schedules and retention.

---

### Key Pairs & SSH Access

**Description:** EC2 uses asymmetric key pairs for initial authentication. AWS stores the public key; you store the private key. At launch, EC2 injects the public key into the instance's `~/.ssh/authorized_keys`. You use the private key to SSH in.

**Creating and using a key pair:**

```bash
# Create a key pair and save the private key
aws ec2 create-key-pair --key-name my-key \
  --query 'KeyMaterial' --output text > my-key.pem

# Set permissions (SSH refuses keys readable by others)
chmod 400 my-key.pem

# Connect to a Linux instance
ssh -i my-key.pem ec2-user@<public-ip-or-dns>
```

**Default usernames by OS:**

| AMI                          | Default username         |
| ---------------------------- | ------------------------ |
| Amazon Linux 2 / 2023        | `ec2-user`               |
| Ubuntu                       | `ubuntu`                 |
| RHEL                         | `ec2-user` or `root`     |
| SUSE                         | `ec2-user`               |
| Debian                       | `admin`                  |
| Windows                      | Decrypt password via console or CLI |

**Modern alternatives to key pairs:**

| Method                     | How                                              | Advantage                                                |
| -------------------------- | ------------------------------------------------ | -------------------------------------------------------- |
| **EC2 Instance Connect**   | Browser/CLI one-time SSH certificate             | No long-lived key needed; IAM-controlled                 |
| **Session Manager (SSM)**  | WebSocket tunnel via SSM agent                   | No port 22 open; fully audited; works from private subnet |

```bash
# Start a Session Manager session (no key pair or port 22 required)
aws ssm start-session --target i-0abcd1234efgh5678
```

**Notes:**

- Key pairs are **regional** — a key pair created in `us-east-1` is not visible in `eu-west-1`.
- The private key is shown **only once** at creation time; AWS does not store it. If you lose it, you must create a new pair and update the instance.
- For production, prefer **Session Manager** — it removes the need for port 22 and creates a full audit trail in CloudTrail.

---

## AWS CLI

The **AWS CLI (Command Line Interface)** is the primary tool for interacting with AWS services from the terminal. It wraps AWS REST APIs into easy-to-remember commands with structured output, filtering, and multi-account support via named profiles.

### One Shot Revision

| Topic                                                        | Short Description                                                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| [AWS CLI Overview](#aws-cli-overview)                        | What is the CLI, when to use it, v2 vs v1                                                 |
| [Installation & Configuration](#installation--configuration) | Installing AWS CLI v2, initial setup, credentials storage, verification                   |
| [CLI Profiles & Credentials](#cli-profiles--credentials)     | Named profiles, credential precedence, environment variables, credential chain             |
| [Output Formats & Query Syntax](#output-formats--query-syntax) | JSON, table, text output; JMESPath filtering and querying; column/tree output             |
| [Common Service Commands](#common-service-commands)          | Core patterns for S3, EC2, IAM, Lambda, and generic operations                            |
| [Advanced CLI Techniques](#advanced-cli-techniques)          | Pagination, waiters, dry-runs, batch operations, scripting best practices                 |

### AWS CLI Overview

**Description:** The AWS CLI is the canonical command-line tool for AWS. Available in versions 1 and 2 (v2 recommended for new setups). It provides typed, consistent access to AWS service APIs with output formatting, querying, and credential management.

**When to use the AWS CLI:**

| Use Case                              | Why CLI is ideal                                                      |
| ------------------------------------- | --------------------------------------------------------------------- |
| **Ad-hoc operations** (manual testing)| Quick one-off commands; no boilerplate                                |
| **Scripting & automation**            | Shell scripts, CI/CD pipelines, Lambda initialisation                 |
| **DevOps workflows**                  | Deploying infra, managing resources, monitoring                       |
| **Exploring services**                | `describe-*` commands to list resources and understand configuration  |
| **Batch operations**                  | Processing multiple resources in a loop or via xargs                  |

**Why not CLI:**

- **Infrastructure as Code:** Use CloudFormation, Terraform, or CDK for reproducible, versionable infrastructure.
- **Complex multi-step workflows:** Use AWS Step Functions or orchestration tools.
- **GUI management:** AWS Console for learning, permissions audits, cost analysis.

**CLI versions:**

| Version | Status                | When to use                          |
| ------- | --------------------- | ------------------------------------ |
| **v2**  | Current & recommended | All new setups; Python 3.7+          |
| **v1**  | Deprecated            | Legacy scripts; avoid new projects   |

### Installation & Configuration

**Installation steps:**

```bash
# macOS (Homebrew)
brew install awscli

# Linux (latest v2)
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip && sudo ./aws/install

# Windows (MSI or Chocolatey)
# Download: https://awscli.amazonaws.com/AWSCLIV2.msi
# OR: choco install awscli

# Verify installation
aws --version
# aws-cli/2.15.x Python/3.11.x ...
```

**Initial setup with `aws configure`:**

```bash
aws configure
# AWS Access Key ID [None]: AKIA...
# AWS Secret Access Key [None]: (paste secret key)
# Default region name [None]: us-east-1
# Default output format [None]: json
```

This writes credentials and config to:

```
~/.aws/credentials  # Access Key ID and Secret Access Key
~/.aws/config       # Region, output format, profiles
```

**Verify credentials:**

```bash
aws sts get-caller-identity
# {
#   "UserId": "AIDAI...",
#   "Account": "123456789012",
#   "Arn": "arn:aws:iam::123456789012:user/john"
# }
```

**Command structure:**

```
aws [--profile PROFILE] [--region REGION] <service> <operation> [--option VALUE] [--flag]
    └─ global options                       └─ service       └─ operation
```

### CLI Profiles & Credentials

**Named profiles** enable multi-account or multi-role workflows on a single machine:

```bash
# Create a profile for a different AWS account
aws configure --profile dev
# → stores credentials under [dev] in ~/.aws/credentials and config

# Create a profile that assumes a role (advanced)
# Edit ~/.aws/config:
# [profile prod]
# role_arn = arn:aws:iam::987654321098:role/CloudEngineer
# source_profile = primary  # must have permissions to assume the role

# Use a profile for a single command
aws s3 ls --profile dev

# Use a profile for a shell session
export AWS_PROFILE=dev
aws ec2 describe-instances  # uses dev profile

# View all configured profiles
cat ~/.aws/config
```

**Credential precedence** (highest to lowest):

1. **Command-line flags:** `--access-key-id`, `--secret-access-key`
2. **Environment variables:** `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_SESSION_TOKEN`
3. **Named profile:** `$AWS_PROFILE` or `--profile`
4. **Default profile** in `~/.aws/credentials`
5. **EC2 instance IAM role:** if running on EC2 (highest on instances)

**Credential security best practices:**

```bash
# ✅ Never commit credentials to git
echo "~/.aws/credentials" >> ~/.gitignore

# ✅ Use IAM roles on EC2/ECS/Lambda (no credentials needed)
# ✅ Use temporary credentials from `sts assume-role`
aws sts assume-role \
  --role-arn arn:aws:iam::123456789012:role/MyRole \
  --role-session-name my-session
# → Returns: AccessKeyId, SecretAccessKey, SessionToken (valid 1 hour)

# ✅ Store long-lived credentials in AWS Secrets Manager or Systems Manager Parameter Store
# Then retrieve them at runtime:
aws secretsmanager get-secret-value --secret-id my-secret \
  --query 'SecretString' --output text
```

### Output Formats & Query Syntax

**Output format options:**

```bash
aws ec2 describe-instances --output json   # Full JSON (default)
aws ec2 describe-instances --output table  # Human-readable table
aws ec2 describe-instances --output text   # Whitespace-separated values
aws ec2 describe-instances --output yaml   # YAML format (also supported)
```

**Example responses:**

```bash
# JSON (default, best for scripting)
aws s3 ls --output json
# {
#   "Buckets": [
#     { "Name": "my-bucket", "CreationDate": "2023-01-15T10:30:00+00:00" }
#   ]
# }

# Table (human-readable)
aws s3 ls --output table
# ────────────────────────────────────────────────────
# |  ListBuckets                                      |
# +──────────────────────────────────────────────────+
# |  Name       |  CreationDate                       |
# +─────────────+─────────────────────────────────────+
# |  my-bucket  |  2023-01-15T10:30:00+00:00          |
```

**Query with JMESPath** (filter and extract fields):

```bash
# Get only instance IDs and states
aws ec2 describe-instances \
  --query 'Reservations[*].Instances[*].[InstanceId,State.Name]' \
  --output table

# Filter by instance state (running only)
aws ec2 describe-instances \
  --query 'Reservations[].Instances[?State.Name==`running`].InstanceId' \
  --output text

# Extract a single field (join with newlines)
aws ec2 describe-instances \
  --query 'Reservations[*].Instances[*].PublicIpAddress' \
  --output text

# Sort by name (JMESPath sort_by)
aws ec2 describe-instances \
  --query 'sort_by(Reservations[*].Instances[], &Tags[?Key==`Name`].Value | [0])' \
  --output table
```

**JMESPath basics:**

| Expression | Meaning |
| --- | --- |
| `Reservations[*]` | Select all items in the `Reservations` array |
| `Reservations[0]` | Select the first reservation |
| `Instances[?State.Name==\`running\`]` | Filter: only instances with state = running |
| `&Tags[?Key==\`Name\`].Value` | Sort key: extract the Name tag value |
| `[0]` | Get the first element |
| `length(@)` | Count items |

**Piping to `jq` for advanced filtering:**

```bash
# Get all running instance IPs (jq alternative to JMESPath)
aws ec2 describe-instances --output json | \
  jq '.Reservations[].Instances[] | select(.State.Name=="running") | .PublicIpAddress'

# Extract tags into a flat key=value format
aws ec2 describe-instances --output json | \
  jq '.Reservations[].Instances[] | {InstanceId, Tags: ((.Tags // []) | map("\(.Key)=\(.Value)") | join(", "))}'
```

### Common Service Commands

**Pattern for any service:**

```
aws <service> <operation> [--filters or --query-params] [--output format]
```

**S3 operations:**

```bash
# List buckets
aws s3 ls

# List objects in a bucket
aws s3 ls s3://my-bucket/

# Upload a file (high-level, multipart-aware)
aws s3 cp myfile.txt s3://my-bucket/myfile.txt

# Sync a directory
aws s3 sync ./local-dir s3://my-bucket/remote-dir

# Remove an object
aws s3 rm s3://my-bucket/myfile.txt

# Create a bucket (low-level api — region handling)
aws s3api create-bucket \
  --bucket my-new-bucket \
  --region us-east-1
  # For non-us-east-1: --create-bucket-configuration LocationConstraint=us-west-2

# Get bucket versioning
aws s3api get-bucket-versioning --bucket my-bucket
```

**EC2 operations:**

```bash
# Describe all instances
aws ec2 describe-instances --output table

# Describe running instances only
aws ec2 describe-instances \
  --filters "Name=instance-state-name,Values=running"

# Get instance IDs and IPs (JMESPath)
aws ec2 describe-instances \
  --query 'Reservations[*].Instances[*].[InstanceId,PrivateIpAddress,PublicIpAddress]' \
  --output table

# Start/stop instances
aws ec2 start-instances --instance-ids i-1234567890abcdef0
aws ec2 stop-instances --instance-ids i-1234567890abcdef0

# Terminate an instance
aws ec2 terminate-instances --instance-ids i-1234567890abcdef0

# Create a key pair (one-time setup)
aws ec2 create-key-pair --key-name my-key \
  --query 'KeyMaterial' --output text > my-key.pem
chmod 400 my-key.pem
```

**IAM operations:**

```bash
# List users
aws iam list-users --query 'Users[*].[UserName,Arn]' --output table

# Create a user
aws iam create-user --user-name john

# Create and attach a policy
aws iam put-user-policy \
  --user-name john \
  --policy-name S3ReadOnly \
  --policy-document file://policy.json

# List access keys for a user
aws iam list-access-keys --user-name john

# Assume a role (get temporary credentials)
aws sts assume-role \
  --role-arn arn:aws:iam::123456789012:role/MyRole \
  --role-session-name my-session \
  --duration-seconds 3600
```

**Lambda operations:**

```bash
# List functions
aws lambda list-functions --output table

# Invoke a function synchronously
aws lambda invoke \
  --function-name my-function \
  --payload '{"key": "value"}' \
  response.json && cat response.json

# Update function code
aws lambda update-function-code \
  --function-name my-function \
  --zip-file fileb://function.zip

# Set environment variables
aws lambda update-function-configuration \
  --function-name my-function \
  --environment Variables={ENV=prod,LOG_LEVEL=debug}

# Get function details
aws lambda get-function --function-name my-function
```

### Advanced CLI Techniques

**Pagination** — handle large result sets:

```bash
# Manual pagination (returns one page; use --starting-token if results are truncated)
aws s3api list-objects-v2 --bucket my-bucket --max-items 10

# Auto-pagination (fetch all results)
aws s3api list-objects-v2 --bucket my-bucket \
  --query 'Contents[].Key' --output text | tr '\t' '\n'
  # Tip: use `--page-iterator` for explicit control in scripts

# Built-in pagination (some services)
aws ec2 describe-instances --max-results 10  # Returns up to 10 per page
```

**Waiters** — poll until a condition is met:

```bash
# Wait for an instance to be running
aws ec2 wait instance-running --instance-ids i-1234567890abcdef0

# Wait for an instance to be terminated
aws ec2 wait instance-terminated --instance-ids i-1234567890abcdef0

# Available waiters depend on the service
aws ec2 wait help
```

**Dry-run and validation:**

```bash
# Test a command without executing (auth + syntax check)
aws ec2 run-instances \
  --image-id ami-12345678 \
  --instance-type t2.micro \
  --dry-run
# UnauthorizedOperation: You are not authorized to perform this operation. (if no permissions)

# Validate a CloudFormation template
aws cloudformation validate-template --template-body file://template.yaml
```

**Batch operations in shell loops:**

```bash
# Stop all running instances in a region
aws ec2 describe-instances \
  --filters "Name=instance-state-name,Values=running" \
  --query 'Reservations[*].Instances[*].InstanceId' \
  --output text | xargs -I {} aws ec2 stop-instances --instance-ids {}

# Tag all buckets with a lifecycle rule
for bucket in $(aws s3 ls --query 'Buckets[].Name' --output text); do
  aws s3api put-bucket-tagging \
    --bucket "$bucket" \
    --tagging 'TagSet=[{Key=Environment,Value=prod}]'
done

# Delete multiple objects from S3
aws s3api delete-objects \
  --bucket my-bucket \
  --delete "Objects=[{Key=file1.txt},{Key=file2.txt}]"
```

**Scripting best practices:**

```bash
#!/bin/bash
set -euo pipefail  # Exit on error, undefined vars, pipe failures

# Use --query to extract only what you need (faster, less parsing)
INSTANCE_ID=$(aws ec2 describe-instances \
  --filters "Name=tag:Name,Values=my-server" \
  --query 'Reservations[0].Instances[0].InstanceId' \
  --output text)

# Check if result is empty
if [ -z "$INSTANCE_ID" ]; then
  echo "No instance found" >&2
  exit 1
fi

# Store the profile in a variable
export AWS_PROFILE=dev

# Use `--output text` for scripting; `--output json` for further processing
aws ec2 describe-instances \
  --instance-ids "$INSTANCE_ID" \
  --query 'Reservations[0].Instances[0].State.Name' \
  --output text
```

**Learn from the official source:**

→ [AWS CLI User Guide v2](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

**Notes:**

- The CLI is **stateless** — each command is independent. Use scripts or orchestration tools to manage multi-step workflows.
- Always use **named profiles** for multi-account work; never hardcode account IDs in scripts.
- Prefer **`--query`** over piping to `jq` when possible — it's faster and doesn't require external tools.
- When scripting, prefer **environment variables** or **AWS Systems Manager Parameter Store** over config files to avoid versioning secrets.
- Use **`--output text`** with `xargs` for batch processing; **`--output json`** when piping to tools like `jq`.
- The CLI supports **credential caching** — temporary credentials from `sts assume-role` are automatically cached in `~/.aws/cli/cache/`.

---

## CloudWatch

**CloudWatch** is AWS's native monitoring and observability service. It collects, stores, and provides access to metrics, logs, and traces from AWS resources and applications. It's the foundation for operational visibility — tracking resource health, application performance, and troubleshooting issues.

### One Shot Revision

| Topic                                                           | Short Description                                                                         |
| --------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| [CloudWatch Overview](#cloudwatch-overview)                    | What CloudWatch is, core concepts (metrics, logs, alarms), namespaces, units, pricing   |
| [CloudWatch Logs](#cloudwatch-logs)                            | Log groups, log streams, retention, filtering, streaming, log agents                     |
| [CloudWatch Metrics](#cloudwatch-metrics)                      | Built-in metrics, custom metrics, dimensions, aggregation, statistics, retrieval          |
| [Install CloudWatch Agent](#install-cloudwatch-agent)          | CloudWatch Agent installation, configuration, metrics & logs collection from instances    |
| [CloudWatch Alarms](#cloudwatch-alarms)                        | Alarm states, thresholds, actions (SNS, EC2, Lambda), anomaly detection, composite alarms |
| [CloudWatch Dashboards](#cloudwatch-dashboards)                | Building custom visualizations, widgets, JSON configuration, dashboard management         |
| [CloudWatch Log Insights](#cloudwatch-log-insights)            | Query syntax, aggregation, statistics, common queries, performance optimization           |
| [Container Insights](#container-insights)                      | ECS and EKS monitoring, container metrics, performance dashboards                         |
| [CloudWatch Synthetics](#cloudwatch-synthetics)                | Canary tests, endpoint monitoring, availability checks, synthetic transactions            |

### CloudWatch Overview

**Description:** CloudWatch is AWS's integrated monitoring and observability service. It collects metrics from AWS services and applications, ingests logs from EC2 instances and custom sources, and enables alarms that trigger actions when thresholds are breached. All AWS services publish metrics to CloudWatch automatically; you can also publish custom metrics from applications.

**Core concepts:**

| Term                  | What it is                                                                                           |
| --------------------- | ---------------------------------------------------------------------------------------------------- |
| **Metric**            | A time-stamped data point representing a measurement (e.g. CPU utilization, request count)          |
| **Namespace**         | A logical grouping for metrics (e.g. `AWS/EC2`, `AWS/Lambda`, custom app namespaces)               |
| **Dimension**         | A key-value pair that identifies a specific instance of a metric (e.g. InstanceId, FunctionName)    |
| **Statistic**         | An aggregation of metric data points (Sum, Average, Maximum, Minimum, SampleCount)                  |
| **Log group**         | A container for log streams from a single source (e.g. `/aws/lambda/my-function`)                   |
| **Log stream**        | A sequence of log events from a specific source (e.g. `/aws/lambda/my-function/[$LATEST]abcd1234`) |
| **Alarm**             | A rule that triggers an action when a metric crosses a threshold                                    |
| **Dashboard**         | A custom visualization combining multiple widgets (graphs, numbers, logs)                           |

**Metric characteristics:**

| Attribute        | Details                                                                                                |
| ---------------- | ------------------------------------------------------------------------------------------------------ |
| **Data retention** | 15 months at minute resolution; older data aggregated to 5-minute then 1-hour intervals               |
| **Resolution**   | 1 second (high-resolution) or 1 minute (standard)                                                    |
| **Granularity**  | Data stored at the same granularity submitted; queries can aggregate further                          |
| **Dimensions**   | Up to 10 key-value pairs per metric for filtering/grouping                                            |
| **Unit**         | Optional; CloudWatch understands standard units (Seconds, Bytes, Count, Percent, etc.)                |

**Pricing overview:**

| Component         | Free tier (always free)      | Paid tier                         |
| ----------------- | ---------------------------- | --------------------------------- |
| **Metrics**       | 10 custom metrics per month  | $0.30 per metric per month        |
| **Log ingestion** | 5 GB per month               | $0.50 per GB ingested             |
| **Log storage**   | 5 GB per month               | $0.03 per GB-month                |
| **API requests**  | 1 million requests per month | $0.01 per 1,000 requests (some)  |
| **Alarms**        | 10 alarms per month          | $0.10 per alarm per month         |
| **Dashboards**    | 3 dashboards per month       | $3.00 per dashboard per month     |

### CloudWatch Logs

**Description:** CloudWatch Logs is the log storage and analysis service within CloudWatch. You can stream logs from EC2 instances, Lambda functions, on-premises servers, and any application that sends data to the CloudWatch Logs API. Logs are organized hierarchically: log groups contain log streams; log streams contain log events.

**Log group and log stream structure:**

```
Log Group: /aws/lambda/my-function
├── Log Stream: 2024/08/10/[$LATEST]a1b2c3d4
│   ├── Event: [timestamp] message 1
│   ├── Event: [timestamp] message 2
│   └── Event: [timestamp] message 3
└── Log Stream: 2024/08/10/[$LATEST]e5f6g7h8
    ├── Event: [timestamp] message 4
    └── Event: [timestamp] message 5
```

**Log retention and storage:**

```bash
# Set log retention policy (1 day to 10 years or indefinite)
aws logs put-retention-policy \
  --log-group-name /aws/lambda/my-function \
  --retention-in-days 30

# List log groups
aws logs describe-log-groups --output table

# Create a log group manually
aws logs create-log-group --log-group-name /myapp/api

# Delete a log group (removes all log streams and events)
aws logs delete-log-group --log-group-name /myapp/api
```

**Log group structure and costs:**

- **Unbounded ingestion** — all logs are stored as-is; storage is billed by volume and retention duration.
- **Retention policy** — apply retention to avoid indefinite (and costly) log storage.
- **Log group cost** — incurs per-GB-month storage cost after the free tier is exhausted.

**Filtering and searching logs:**

```bash
# Filter log events by pattern (simple text match)
aws logs filter-log-events \
  --log-group-name /aws/lambda/my-function \
  --filter-pattern "ERROR" \
  --output table

# Filter for a specific field value (JSON logs)
aws logs filter-log-events \
  --log-group-name /aws/lambda/my-function \
  --filter-pattern "{ $.level = \"ERROR\" }" \
  --output table

# Get log events from a specific stream
aws logs get-log-events \
  --log-group-name /aws/lambda/my-function \
  --log-stream-name '2024/08/10/[$LATEST]a1b2c3d4' \
  --output table
```

**Log streaming to other services:**

```bash
# Create a subscription filter (stream logs to Lambda, Kinesis, or Firehose)
aws logs put-subscription-filter \
  --log-group-name /aws/lambda/my-function \
  --filter-name my-filter \
  --filter-pattern "" \
  --destination-arn arn:aws:lambda:us-east-1:123456789012:function:log-processor

# List subscription filters on a log group
aws logs describe-subscription-filters \
  --log-group-name /aws/lambda/my-function

# Delete a subscription filter
aws logs delete-subscription-filter \
  --log-group-name /aws/lambda/my-function \
  --filter-name my-filter
```

**Log agents — send logs from EC2 instances:**

CloudWatch Logs Agent and CloudWatch Agent both collect logs from EC2 instances and on-premises servers:

| Agent                    | Use case                                                         |
| ------------------------ | ---------------------------------------------------------------- |
| **CloudWatch Logs Agent** | Legacy; logs-only; simpler for basic use cases                   |
| **CloudWatch Agent**      | Modern; logs + metrics; more flexible; recommended for new setup  |

**Structured logging (JSON):**

```bash
# Log as JSON so Log Insights can query specific fields
echo '{"timestamp":"2024-08-10T12:00:00Z","level":"ERROR","requestId":"abc123","message":"Database connection failed","duration_ms":5000}' | \
aws logs put-log-events \
  --log-group-name /myapp/api \
  --log-stream-name prod \
  --log-events timestamp=$(date +%s000),message='{"level":"ERROR","requestId":"abc123"}'
```

**CloudWatch Logs insights integration:**

- When you send **structured JSON logs**, Log Insights automatically extracts fields.
- Query using field names: `fields @timestamp, @message, level, requestId`
- Filter by specific fields: `filter level = "ERROR" and duration_ms > 1000`

### CloudWatch Metrics

**Description:** Metrics are the heartbeat of CloudWatch — time-stamped data points representing measurements. AWS services automatically publish built-in metrics; applications can publish custom metrics via the CloudWatch Metrics API or agent.

**Built-in metrics by service:**

| Service | Key Metrics                                                                      |
| ------- | -------------------------------------------------------------------------------- |
| **EC2** | CPUUtilization, NetworkIn, NetworkOut, DiskReadBytes, DiskWriteBytes, StatusCheck* |
| **RDS** | DatabaseConnections, CPUUtilization, ReadThroughput, WriteThroughput, DiskQueueDepth |
| **Lambda** | Invocations, Duration, Errors, Throttles, ConcurrentExecutions, UnreservedConcurrentExecutions |
| **S3** | NumberOfObjects, BucketSizeBytes (stored in separate `AWS/S3` namespace)        |
| **DynamoDB** | ConsumedReadCapacityUnits, ConsumedWriteCapacityUnits, UserErrors, SystemErrors |
| **ELB** | TargetResponseTime, RequestCount, HTTPCode_Target_5XX, UnHealthyHostCount      |

**Publish custom metrics:**

```bash
# Publish a single metric data point
aws cloudwatch put-metric-data \
  --namespace MyApplication \
  --metric-name ProcessingTime \
  --value 123.45 \
  --unit Milliseconds \
  --timestamp 2024-08-10T12:00:00Z

# Publish a metric with dimensions
aws cloudwatch put-metric-data \
  --namespace MyApplication \
  --metric-name RequestCount \
  --dimensions Environment=prod,Service=api \
  --value 1234 \
  --unit Count

# Batch publish multiple metrics
aws cloudwatch put-metric-data \
  --namespace MyApplication \
  --metric-data '[
    {"MetricName":"CPUUsage","Value":45.5,"Unit":"Percent","Dimensions":[{"Name":"Host","Value":"server-1"}]},
    {"MetricName":"MemoryUsage","Value":3072,"Unit":"Megabytes","Dimensions":[{"Name":"Host","Value":"server-1"}]}
  ]'
```

**Retrieve and analyze metrics:**

```bash
# Get metric statistics (aggregations over a time period)
aws cloudwatch get-metric-statistics \
  --namespace AWS/EC2 \
  --metric-name CPUUtilization \
  --dimensions Name=InstanceId,Value=i-1234567890abcdef0 \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average,Maximum,Minimum \
  --output table

# List all metrics in a namespace
aws cloudwatch list-metrics \
  --namespace AWS/Lambda \
  --output table

# List metrics with specific dimension
aws cloudwatch list-metrics \
  --namespace AWS/Lambda \
  --dimensions Name=FunctionName,Value=my-function \
  --output table
```

**Metric aggregation (statistics):**

| Statistic   | What it means                                                  | Use case                                              |
| ----------- | -------------------------------------------------------------- | ----------------------------------------------------- |
| **Average** | Mean value across all data points in the period                | CPU avg, response time avg, memory usage              |
| **Sum**     | Total of all data points (for counters: total requests)        | Request count, total throughput, total errors         |
| **Maximum** | Highest value in the period                                    | Peak CPU, max response time, highest memory spike     |
| **Minimum** | Lowest value in the period                                     | Min response time, lowest throughput                  |
| **SampleCount** | Number of data points included in the calculation             | How many measurements were aggregated                 |

**Metric naming conventions:**

```
Namespace: AWS/ServiceName or CustomNamespace
MetricName: DescriptiveNameInPascalCase
Dimensions: Key=Value pairs identifying the resource

Example:
  Namespace: MyApplication/API
  MetricName: RequestLatency
  Dimensions: Environment=prod, Service=auth-service, Region=us-east-1
```

**Metric math and composite metrics:**

```bash
# Create an alarm based on multiple metrics (metric math)
aws cloudwatch put-metric-alarm \
  --alarm-name app-health-alarm \
  --metrics '[
    {
      "Id": "e1",
      "Expression": "(m1 + m2) / 2",
      "Label": "Average across services"
    },
    {
      "Id": "m1",
      "ReturnData": false,
      "MetricStat": {
        "Metric": {
          "Namespace": "MyApp",
          "MetricName": "RequestCount",
          "Dimensions": [{"Name": "Service", "Value": "api"}]
        },
        "Period": 300,
        "Stat": "Sum"
      }
    },
    {
      "Id": "m2",
      "ReturnData": false,
      "MetricStat": {
        "Metric": {
          "Namespace": "MyApp",
          "MetricName": "RequestCount",
          "Dimensions": [{"Name": "Service", "Value": "worker"}]
        },
        "Period": 300,
        "Stat": "Sum"
      }
    }
  ]' \
  --comparison-operator GreaterThanThreshold \
  --threshold 1000 \
  --evaluation-periods 2
```

**Metric filters — derive metrics from logs:**

```bash
# Extract error count from logs as a custom metric
aws logs put-metric-filter \
  --log-group-name /aws/lambda/my-function \
  --filter-name error-count \
  --filter-pattern "[ERROR]" \
  --metric-transformations \
    metricName=ErrorCount,metricNamespace=MyApp,metricValue=1,defaultValue=0

# Now query the derived metric
aws cloudwatch get-metric-statistics \
  --namespace MyApp \
  --metric-name ErrorCount \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Sum
```

**High-resolution metrics:**

```bash
# Publish high-resolution metric (1-second granularity, costs more)
aws cloudwatch put-metric-data \
  --namespace MyApplication \
  --metric-data '[
    {
      "MetricName": "HighResolutionCounter",
      "Value": 123,
      "StorageResolution": 1,
      "Timestamp": "'$(date -u +%Y-%m-%dT%H:%M:%SZ)'"
    }
  ]'

# Query high-resolution metrics with 1-second period
aws cloudwatch get-metric-statistics \
  --namespace MyApplication \
  --metric-name HighResolutionCounter \
  --start-time 2024-08-10T12:00:00Z \
  --end-time 2024-08-10T12:01:00Z \
  --period 1 \
  --statistics Average
```

### Install CloudWatch Agent

**Description:** The CloudWatch Agent is a standalone application that collects both metrics and logs from EC2 instances and on-premises servers. Unlike built-in EC2 metrics (which are limited), the agent enables detailed OS-level metrics (memory, disk, processes) and custom application logs.

**Why use CloudWatch Agent:**

| Need                              | Solution                                                    |
| --------------------------------- | ----------------------------------------------------------- |
| **Memory/disk metrics from EC2**  | Built-in EC2 metrics don't include these; use the agent    |
| **Process-level metrics**         | Monitor specific application processes (CPU, memory)        |
| **Custom application logs**       | Forward logs from /var/log to CloudWatch                    |
| **On-premises servers**           | CloudWatch Agent works on non-AWS servers too               |
| **Centralized log aggregation**   | Collect logs from multiple instances to one log group       |

**Agent vs. Built-in EC2 metrics:**

| Metric                | Built-in EC2 | CloudWatch Agent |
| --------------------- | ------------ | ---------------- |
| CPU Utilization       | ✅           | ✅               |
| Network In/Out        | ✅           | ✅               |
| Disk Read/Write Bytes | ✅           | ✅               |
| **Memory Usage**       | ❌           | ✅               |
| **Disk Space Used**    | ❌           | ✅               |
| **Process Metrics**    | ❌           | ✅               |
| **Custom Logs**        | ❌           | ✅               |

**Installation on EC2:**

```bash
# Step 1: Create IAM role for EC2 instance (one-time setup)
# Trust relationship: allow EC2 service
# Permissions: AmazonSSMManagedInstanceCore + CloudWatchAgentServerPolicy

# Step 2: Attach IAM role to EC2 instance
aws ec2 associate-iam-instance-profile \
  --iam-instance-profile Name=CloudWatchAgentRole \
  --instance-id i-1234567890abcdef0

# Step 3: Download and install CloudWatch Agent on EC2
# SSH into the instance first, then:
wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm
sudo rpm -U ./amazon-cloudwatch-agent.rpm

# For Ubuntu:
wget https://s3.amazonaws.com/amazoncloudwatch-agent/ubuntu/amd64/latest/amazon-cloudwatch-agent.deb
sudo dpkg -i -E ./amazon-cloudwatch-agent.deb

# Step 4: Configure the agent using wizard
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard

# Step 5: Start the agent
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
  -a fetch-config \
  -m ec2 \
  -s -c file:/opt/aws/amazon-cloudwatch-agent/etc/amazon-cloudwatch-agent.json
```

**Agent configuration file (JSON):**

```json
{
  "agent": {
    "metrics_collection_interval": 60,
    "run_as_user": "root"
  },
  "logs": {
    "logs_collected": {
      "files": {
        "collect_list": [
          {
            "file_path": "/var/log/application.log",
            "log_group_name": "/myapp/application",
            "log_stream_name": "{instance_id}",
            "timestamp_format": "%Y-%m-%d %H:%M:%S"
          },
          {
            "file_path": "/var/log/secure",
            "log_group_name": "/system/secure",
            "log_stream_name": "{instance_id}"
          }
        ]
      }
    }
  },
  "metrics": {
    "namespace": "CustomMetrics",
    "metrics_collected": {
      "mem": {
        "measurement": [
          {
            "name": "mem_used_percent",
            "rename": "MemoryUtilization",
            "unit": "Percent"
          }
        ],
        "metrics_collection_interval": 60
      },
      "disk": {
        "measurement": [
          {
            "name": "used_percent",
            "rename": "DiskUtilization",
            "unit": "Percent"
          }
        ],
        "metrics_collection_interval": 60,
        "resources": [
          "/"
        ]
      },
      "cpu": {
        "measurement": [
          {
            "name": "cpu_usage_active",
            "rename": "CPUUtilization",
            "unit": "Percent"
          }
        ],
        "metrics_collection_interval": 60
      },
      "processes": {
        "measurement": [
          {
            "name": "running",
            "rename": "ProcessCount",
            "unit": "Count"
          }
        ]
      }
    }
  }
}
```

**Common agent commands:**

```bash
# Check agent status
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
  -m ec2 \
  -a query

# Restart agent
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
  -m ec2 \
  -a stop
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
  -m ec2 \
  -a start

# Fetch configuration from Parameter Store
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl \
  -a fetch-config \
  -m ec2 \
  -c ssm:AmazonCloudWatch-Config \
  -s

# View agent logs
tail -f /opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log
```

**Deploy agent via AWS Systems Manager:**

```bash
# Store configuration in Parameter Store
aws ssm put-parameter \
  --name AmazonCloudWatch-Config \
  --type String \
  --value file://amazon-cloudwatch-agent.json

# Run agent installation command on multiple instances (via Systems Manager)
aws ssm send-command \
  --instance-ids i-1234567890abcdef0 i-0987654321fedcba0 \
  --document-name AWS-RunShellScript \
  --parameters 'commands=[
    "wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm",
    "sudo rpm -U ./amazon-cloudwatch-agent.rpm",
    "sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c ssm:AmazonCloudWatch-Config -s"
  ]'
```

**Agent IAM permissions required:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "cloudwatch:PutMetricData",
        "ec2:DescribeVolumes",
        "ec2:DescribeTags",
        "logs:PutLogEvents",
        "logs:CreateLogStream",
        "logs:CreateLogGroup"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "ssm:GetParameter"
      ],
      "Resource": "arn:aws:ssm:*:*:parameter/AmazonCloudWatch-*"
    }
  ]
}
```

**Troubleshooting agent issues:**

```bash
# Agent not sending metrics?
# 1. Check IAM role has CloudWatchAgentServerPolicy
# 2. Verify configuration file is valid JSON
# 3. Check agent status: sudo systemctl status amazon-cloudwatch-agent
# 4. Review agent logs: tail -f /opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log

# Test metric publication
aws cloudwatch get-metric-statistics \
  --namespace CustomMetrics \
  --metric-name MemoryUtilization \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average

# Logs not appearing?
# 1. Verify log group and stream exist
# 2. Check file paths in config are correct and readable
# 3. Verify agent has read permission on log files
# 4. Check agent error logs for file access issues
```

**Cost considerations:**

| Component          | Cost                                                   | Optimization                                |
| ------------------ | ------------------------------------------------------ | ------------------------------------------- |
| **Custom metrics** | $0.30 per metric per month (after free tier)           | Aggregate multiple metrics if possible     |
| **Log ingestion**  | $0.50 per GB ingested (after 5 GB free tier)           | Filter unnecessary logs, enable retention  |
| **Log storage**    | $0.03 per GB-month (after 5 GB free tier)              | Set retention policies to auto-delete      |

---

### CloudWatch Alarms

**Description:** Alarms monitor metric values and trigger actions (SNS notifications, Auto Scaling, EC2 actions, Lambda invocations) when thresholds are crossed. An alarm has three states: OK (metric is healthy), ALARM (threshold breached), and INSUFFICIENT_DATA (not enough data to evaluate).

**Alarm states:**

```
┌─────────────────────┐
│    ALARM            │  Threshold breached; actions triggered
├─────────────────────┤
│    OK               │  Metric is within threshold
├─────────────────────┤
│ INSUFFICIENT_DATA   │  Not enough data to evaluate yet
└─────────────────────┘
```

**Create an alarm:**

```bash
# Create an alarm for high CPU utilization
aws cloudwatch put-metric-alarm \
  --alarm-name high-cpu-alarm \
  --alarm-description "Alert when CPU > 80%" \
  --metric-name CPUUtilization \
  --namespace AWS/EC2 \
  --statistic Average \
  --period 300 \
  --threshold 80 \
  --comparison-operator GreaterThanThreshold \
  --evaluation-periods 2 \
  --dimensions Name=InstanceId,Value=i-1234567890abcdef0 \
  --alarm-actions arn:aws:sns:us-east-1:123456789012:my-topic

# Create an alarm with two thresholds (high and low)
aws cloudwatch put-metric-alarm \
  --alarm-name cpu-normal-alarm \
  --metric-name CPUUtilization \
  --namespace AWS/EC2 \
  --statistic Average \
  --period 300 \
  --threshold 30 \
  --comparison-operator LessThanOrEqualToThreshold \
  --evaluation-periods 1 \
  --dimensions Name=InstanceId,Value=i-1234567890abcdef0 \
  --alarm-actions arn:aws:sns:us-east-1:123456789012:scale-down-topic
```

**Alarm configuration:**

| Parameter            | Meaning                                                              |
| -------------------- | -------------------------------------------------------------------- |
| **Period**           | Time window for metric aggregation (60, 300, 3600 seconds typical)   |
| **Evaluation periods** | Number of periods that must breach threshold before triggering       |
| **Threshold**        | The value the metric is compared against                              |
| **Comparison**       | GreaterThan, GreaterThanOrEqual, LessThan, LessThanOrEqual           |
| **Statistic**        | How to aggregate the metric (Average, Sum, Maximum, Minimum)         |

**Alarm actions:**

```bash
# SNS notification (most common)
--alarm-actions arn:aws:sns:us-east-1:123456789012:alerts

# Auto Scaling action (scale up or down)
--alarm-actions arn:aws:autoscaling:us-east-1:123456789012:scalingPolicy:...

# EC2 action (reboot, stop, terminate instance)
--alarm-actions arn:aws:autoscaling:us-east-1:123456789012:action:...

# Lambda action (trigger a function)
--alarm-actions arn:aws:lambda:us-east-1:123456789012:function:my-handler

# Systems Manager action (execute automation)
--alarm-actions arn:aws:ssm:us-east-1:123456789012:automation-definition:...
```

**Manage alarms:**

```bash
# List alarms
aws cloudwatch describe-alarms --output table

# Describe a specific alarm
aws cloudwatch describe-alarms --alarm-names high-cpu-alarm --output table

# Set alarm state manually (for testing)
aws cloudwatch set-alarm-state \
  --alarm-name high-cpu-alarm \
  --state-value ALARM \
  --state-reason "Testing alarm action"

# Disable an alarm temporarily
aws cloudwatch disable-alarm-actions --alarm-names high-cpu-alarm

# Re-enable an alarm
aws cloudwatch enable-alarm-actions --alarm-names high-cpu-alarm

# Delete an alarm
aws cloudwatch delete-alarms --alarm-names high-cpu-alarm
```

**Anomaly detection:**

```bash
# Create an alarm based on anomaly detection (Machine Learning)
aws cloudwatch put-metric-alarm \
  --alarm-name anomaly-detection-alarm \
  --alarm-description "Alert on anomalous CPU behavior" \
  --metric-name CPUUtilization \
  --namespace AWS/EC2 \
  --statistic Average \
  --period 300 \
  --evaluation-periods 1 \
  --threshold-metric-id e1 \
  --metrics '[
    {
      "Id": "e1",
      "Expression": "ANOMALY_DETECTION_BAND(m1, 2)",
      "Label": "CPUUtilization (Expected)"
    },
    {
      "Id": "m1",
      "ReturnData": true,
      "MetricStat": {
        "Metric": {
          "Namespace": "AWS/EC2",
          "MetricName": "CPUUtilization",
          "Dimensions": [{"Name": "InstanceId", "Value": "i-1234567890abcdef0"}]
        },
        "Period": 300,
        "Stat": "Average"
      }
    }
  ]'
```

### CloudWatch Dashboards

**Description:** Dashboards provide custom visualizations of metrics and logs. You can create multiple dashboards to monitor different aspects of your infrastructure — one for application health, another for cost, another for security.

**Create a dashboard:**

```bash
# Create a dashboard via CLI (using JSON body)
aws cloudwatch put-dashboard \
  --dashboard-name MyApplicationDashboard \
  --dashboard-body file://dashboard.json
```

**Dashboard JSON structure:**

```json
{
  "widgets": [
    {
      "type": "metric",
      "properties": {
        "metrics": [
          ["AWS/Lambda", "Invocations", {"stat": "Sum"}],
          ["AWS/Lambda", "Duration", {"stat": "Average"}],
          ["AWS/Lambda", "Errors", {"stat": "Sum"}]
        ],
        "period": 300,
        "stat": "Average",
        "region": "us-east-1",
        "title": "Lambda Function Metrics",
        "yAxis": {
          "left": {
            "min": 0
          }
        }
      }
    },
    {
      "type": "log",
      "properties": {
        "query": "fields @timestamp, @message | filter @message like /ERROR/ | stats count() by @message",
        "region": "us-east-1",
        "title": "Error Logs"
      }
    }
  ]
}
```

**Dashboard widget types:**

| Type       | Purpose                                                          |
| ---------- | ---------------------------------------------------------------- |
| **metric** | Line graph, stacked area, bar chart of metrics over time         |
| **log**    | Results of CloudWatch Logs Insights queries                     |
| **number** | Single metric value (e.g. "5,234 requests in last hour")         |
| **text**   | Static text for documentation or headers                         |

**Manage dashboards:**

```bash
# List dashboards
aws cloudwatch list-dashboards --output table

# Get dashboard details
aws cloudwatch get-dashboard --dashboard-name MyApplicationDashboard

# Update a dashboard
aws cloudwatch put-dashboard \
  --dashboard-name MyApplicationDashboard \
  --dashboard-body file://updated-dashboard.json

# Delete a dashboard
aws cloudwatch delete-dashboards --dashboard-names MyApplicationDashboard
```

### CloudWatch Log Insights

**Description:** CloudWatch Logs Insights is a query language and engine for analyzing logs. You write queries in a SQL-like syntax to search, filter, aggregate, and visualize log data across millions of log events in seconds.

**Query syntax basics:**

```
fields <fields>      # Select which fields to return
| filter <condition> # Filter log events by condition
| stats <aggregation> # Aggregate results (count, sum, avg, max, min)
| sort <field>       # Sort results by field
| limit <n>          # Limit results to N rows
```

**Common queries:**

```bash
# Count total log events
fields @timestamp, @message | stats count()

# Filter for errors and count by error message
fields @message | filter @message like /ERROR/ | stats count() as ErrorCount by @message

# Calculate average response time
fields @duration | stats avg(@duration), max(@duration), min(@duration)

# Count requests by status code (JSON logs)
fields @timestamp, status | stats count() as RequestCount by status

# Top 10 slowest requests
fields @timestamp, @duration, @request_id | sort @duration desc | limit 10

# Errors in the last hour with context
fields @timestamp, @message, @stack_trace | filter @message like /Exception/ | limit 100

# Hourly request distribution
fields @timestamp | stats count() as RequestCount by bin(5m)

# Memory usage trend
fields @memory_usage | stats avg(@memory_usage) as AvgMemory by bin(1m)

# Multi-field aggregation (errors by service and region)
fields @timestamp, service, region, @message | filter @message like /ERROR/ | stats count() as ErrorCount by service, region
```

**Advanced query techniques:**

```
# Pattern matching
filter @message like /pattern/           # Regex match
filter @message = "exact string"         # Exact match
filter field in [value1, value2]         # Match multiple values

# Numeric comparisons
filter @duration > 1000                  # Greater than
filter status >= 400 AND status < 500    # Range

# Type conversion and functions
filter ispresent(@error_id)              # Field exists
filter isempty(@error_id)                # Field is empty
strlen(field)                            # String length
sqrt(field)                              # Square root
toNumber(field)                          # Convert to number
```

**Execute Logs Insights query via CLI:**

```bash
# Start a query
QUERY_ID=$(aws logs start-query \
  --log-group-name /aws/lambda/my-function \
  --start-time $(date -d '1 hour ago' +%s) \
  --end-time $(date +%s) \
  --query-string 'fields @timestamp, @message | filter @message like /ERROR/ | stats count()' \
  --query 'queryId' \
  --output text)

# Wait for query to complete and get results
sleep 2
aws logs get-query-results --query-id "$QUERY_ID" --output table
```

**Query performance tips:**

- Use **time filters** to narrow the search window (faster than scanning all logs).
- Include **specific fields** in `fields` clause instead of `fields *` (reduces data processing).
- Filter as early as possible (`filter` after `fields` reduces downstream processing).
- Use **stats** instead of manually aggregating in post-processing.
- Test queries on smaller time windows first, then expand once working.

**Learn from the official source:**

→ [CloudWatch Documentation](https://docs.aws.amazon.com/cloudwatch/)

**Notes:**

- CloudWatch Logs **ingestion is real-time** — logs appear in the console within seconds of being sent.
- **Log Insights queries cost** — you pay per GB of log data scanned; use retention policies and filters to control costs.
- **Alarm state transitions** are not retroactive — alarms check thresholds going forward. Backfilling historical alarm data requires manual state management.
- Use **metric filters** to extract metrics from log patterns (e.g. count ERROR entries as a custom metric), then alarm on the derived metric.
- CloudWatch integrates with **AWS X-Ray** for distributed tracing; use X-Ray insights for end-to-end request tracking across services.

---

### Container Insights

**Description:** Container Insights provides deep visibility into containerized applications running on ECS and EKS. It collects container-level and pod-level metrics (CPU, memory, network), organizes them hierarchically by cluster, service, and container, and provides built-in dashboards for quick troubleshooting.

**When to use Container Insights:**

| Scenario                          | Benefit                                                     |
| --------------------------------- | ----------------------------------------------------------- |
| **ECS/EKS cluster monitoring**    | Single view across all containers and pods                  |
| **Performance troubleshooting**   | Identify high CPU/memory containers; find bottlenecks       |
| **Resource optimization**         | Right-size container requests based on actual usage         |
| **Multi-cluster visibility**      | Monitor multiple EKS/ECS clusters from one dashboard         |
| **Compliance tracking**           | Audit container resource usage and health                   |

**Container Insights metrics hierarchy:**

```
Cluster (e.g. production-eks)
├── Node (e.g. ip-10-0-1-100)
│   ├── Container metrics: cpu_utilization, memory_utilization, network_io
│   └── Pod (Kubernetes): pod-name
│       └── Container: container-name
├── Service (e.g. api-service)
│   └── Task/Pod instance
│       └── Container metrics
└── Task Metadata (ECS)
```

**Enable Container Insights on ECS:**

```bash
# For ECS EC2 launch type
# 1. Install CloudWatch Agent on EC2 instances (as shown above)
# 2. Add agent config to task definition:

{
  "containerDefinitions": [
    {
      "name": "my-app",
      "image": "my-image:latest"
    },
    {
      "name": "cloudwatch-agent",
      "image": "amazon/cloudwatch-agent:latest",
      "mountPoints": [
        {
          "sourceVolume": "proc",
          "containerPath": "/proc"
        },
        {
          "sourceVolume": "devdisk",
          "containerPath": "/dev"
        }
      ]
    }
  ],
  "volumes": [
    {
      "name": "proc",
      "host": {
        "sourcePath": "/proc"
      }
    },
    {
      "name": "devdisk",
      "host": {
        "sourcePath": "/dev"
      }
    }
  ]
}

# For ECS Fargate launch type
# Use awsfirelens log router with CloudWatch agent

# Check Container Insights is enabled
aws ecs describe-clusters --clusters my-cluster \
  --query 'clusters[0].settings'
```

**Enable Container Insights on EKS:**

```bash
# Install CloudWatch Agent DaemonSet on EKS
# 1. Create namespace
kubectl create namespace amazon-cloudwatch

# 2. Deploy CloudWatch Agent via Helm (recommended)
helm repo add eks https://aws.github.io/eks-charts
helm install aws-cloudwatch-metrics eks/aws-cloudwatch-metrics -n amazon-cloudwatch

# 3. Verify metrics are flowing
aws cloudwatch get-metric-statistics \
  --namespace ContainerInsights \
  --metric-name ContainerInstanceCount \
  --dimensions Name=ClusterName,Value=my-cluster \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average
```

**Common Container Insights queries:**

```bash
# List all metrics in Container Insights namespace
aws cloudwatch list-metrics --namespace ContainerInsights

# Get CPU utilization by container
aws cloudwatch get-metric-statistics \
  --namespace ContainerInsights \
  --metric-name ContainerCpuUtilized \
  --dimensions Name=ClusterName,Value=prod-cluster Name=ServiceName,Value=api \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average,Maximum

# Memory pressure by cluster
aws cloudwatch get-metric-statistics \
  --namespace ContainerInsights \
  --metric-name ContainerMemoryUtilized \
  --dimensions Name=ClusterName,Value=prod-cluster \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average
```

**Container Insights dashboard includes:**

- **Cluster overview** — node count, running tasks/pods, CPU/memory aggregates
- **Service performance** — per-service CPU, memory, network I/O
- **Node health** — per-node resource utilization and status
- **Container drill-down** — individual container metrics and logs

**Pricing:**

Container Insights charges per metric published:

```
First 1,000 metrics: Free (per month)
Additional metrics: $0.30 per metric per month
```

Cost optimization:

- Use **metrics filters** to reduce high-cardinality metrics (e.g. limit to key services).
- **Aggregate metrics** where possible (cluster-level vs service-level vs pod-level).
- Set **log retention** to control log storage costs alongside metrics.

---

### CloudWatch Synthetics

**Description:** CloudWatch Synthetics lets you create canary tests that periodically run synthetic transactions against your application endpoints, APIs, and workflows. Canaries verify availability, latency, and correctness of critical paths before users detect problems.

**When to use CloudWatch Synthetics:**

| Use case                              | Benefit                                                          |
| ------------------------------------- | ---------------------------------------------------------------- |
| **Endpoint availability monitoring**  | Verify API/website is reachable 24/7; alert on outage           |
| **SSL/TLS certificate expiration**    | Monitor certificate validity; avoid certificate expiration      |
| **API response validation**           | Check that API returns expected status codes and response body   |
| **User workflow simulation**          | Create synthetic users performing login, purchase, etc.         |
| **Multi-region availability**         | Run same canary from multiple AWS regions; detect regional issues |
| **Latency SLO monitoring**            | Track p99 latency; trigger alarms when SLO is breached          |

**Canary types:**

| Type                  | Purpose                                                      |
| --------------------- | ------------------------------------------------------------ |
| **API Canary**        | Calls REST API, checks status code and response body         |
| **Endpoint Check**    | HTTP GET request; validates response code and timing         |
| **Broken Link Check** | Crawls website; finds broken links and missing resources     |
| **Visual Regression** | Compares screenshots; detects UI changes                     |
| **Canary Script**     | Custom Node.js script; full control over test logic          |

**Create a simple API canary:**

```bash
# Create a canary that checks an API endpoint
aws synthetics create-canary \
  --name api-health-check \
  --artifact-s3-location s3://my-bucket/canary-artifacts/ \
  --execution-role-arn arn:aws:iam::123456789012:role/CloudWatchSyntheticsRole \
  --schedule-expression "rate(5 minutes)" \
  --run-config MemoryInMB=960,TimeoutInSeconds=60 \
  --code Handler=apiCanary.handler,Script='
const synthetics = require("Synthetics");
const http = require("http");

const apiCanary = async function() {
  const url = "https://api.example.com/health";
  let response = await http.get(url);
  
  if (response.statusCode !== 200) {
    throw new Error(`API returned ${response.statusCode}`);
  }
  
  const body = JSON.parse(response.body);
  if (body.status !== "healthy") {
    throw new Error("API status is not healthy");
  }
};

exports.handler = apiCanary;
'
```

**Create a canary via CloudFormation/CDK:**

```json
{
  "Type": "AWS::Synthetics::Canary",
  "Properties": {
    "Name": "website-availability",
    "ArtifactS3Location": "s3://my-bucket/canary-results/",
    "ExecutionRoleArn": "arn:aws:iam::123456789012:role/CloudWatchSyntheticsRole",
    "Handler": "apiCanary.handler",
    "Code": {
      "S3Bucket": "my-bucket",
      "S3Key": "canary-scripts/apiCanary.zip"
    },
    "RunConfig": {
      "TimeoutInSeconds": 60,
      "MemoryInMB": 960,
      "ActiveTracing": true
    },
    "Schedule": {
      "Expression": "rate(5 minutes)"
    },
    "FailureRetentionPeriod": 31,
    "SuccessRetentionPeriod": 31,
    "Tags": {
      "Environment": "production"
    }
  }
}
```

**Canary metrics and alarms:**

```bash
# List canary results
aws synthetics list-runs \
  --canary-name api-health-check

# Get canary metrics (success/failure rate)
aws cloudwatch get-metric-statistics \
  --namespace CloudWatchSynthetics \
  --metric-name SuccessPercent \
  --dimensions Name=CanaryName,Value=api-health-check \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average

# Get canary latency
aws cloudwatch get-metric-statistics \
  --namespace CloudWatchSynthetics \
  --metric-name Duration \
  --dimensions Name=CanaryName,Value=api-health-check \
  --start-time 2024-08-10T00:00:00Z \
  --end-time 2024-08-10T01:00:00Z \
  --period 300 \
  --statistics Average,Maximum

# Create alarm: canary failure
aws cloudwatch put-metric-alarm \
  --alarm-name canary-failure-alarm \
  --metric-name SuccessPercent \
  --namespace CloudWatchSynthetics \
  --statistic Average \
  --period 300 \
  --threshold 90 \
  --comparison-operator LessThanThreshold \
  --evaluation-periods 1 \
  --dimensions Name=CanaryName,Value=api-health-check \
  --alarm-actions arn:aws:sns:us-east-1:123456789012:alerts
```

**Canary script examples:**

```javascript
// Example 1: Check API response with validation
const synthetics = require("Synthetics");
const http = require("http");

const validateAPI = async function() {
  const url = "https://api.example.com/users";
  const response = await http.get(url);
  
  if (response.statusCode !== 200) {
    throw new Error(`Expected 200, got ${response.statusCode}`);
  }
  
  const data = JSON.parse(response.body);
  if (!Array.isArray(data.users)) {
    throw new Error("Response does not contain users array");
  }
};

exports.handler = validateAPI;

// Example 2: Verify certificate expiration
const synthetics = require("Synthetics");
const tls = require("tls");

const checkCert = async function() {
  const options = {
    host: "api.example.com",
    port: 443,
    method: "HEAD"
  };
  
  let cert = await new Promise((resolve, reject) => {
    const req = tls.connect(options, () => {
      resolve(req.getPeerCertificate());
      req.destroy();
    });
    req.on("error", reject);
  });
  
  const expiryDate = new Date(cert.valid_to);
  const daysUntilExpiry = (expiryDate - new Date()) / (1000 * 60 * 60 * 24);
  
  if (daysUntilExpiry < 30) {
    throw new Error(`Certificate expires in ${daysUntilExpiry.toFixed(1)} days`);
  }
};

exports.handler = checkCert;
```

**Manage canaries:**

```bash
# List all canaries
aws synthetics list-canaries --output table

# Get canary details
aws synthetics get-canary --name api-health-check

# Update canary schedule
aws synthetics update-canary \
  --name api-health-check \
  --schedule-expression "rate(10 minutes)"

# Start a canary (begin running scheduled tests)
aws synthetics start-canary --name api-health-check

# Stop a canary (pause scheduled tests)
aws synthetics stop-canary --name api-health-check

# Delete a canary
aws synthetics delete-canary --name api-health-check

# View canary logs
aws logs tail /aws/lambda/cwsyn-api-health-check-abc123 --follow
```

**Canary best practices:**

| Best Practice                    | Why                                                         |
| -------------------------------- | ----------------------------------------------------------- |
| **Test critical paths only**     | Minimize cost; focus on user-facing workflows               |
| **Run from multiple regions**    | Detect regional outages; verify global availability         |
| **Set realistic thresholds**     | Avoid alert fatigue; tune for actual SLOs                   |
| **Validate response content**    | Check not just availability but also correctness            |
| **Use VPC endpoints in Synthetics** | Test private endpoints; ensure canary can reach internal APIs |
| **Monitor canary metrics**       | Create alarms on SuccessPercent and Duration                |
| **Version control scripts**      | Track canary code changes in Git                            |
| **Test from CloudWatch Console** | Run canary once before scheduling to verify config          |

**Cost considerations:**

```
Canary executions: $0.0015 per execution (runs count as API calls)
Example: 5-minute schedule × 288/day × 30 days = 4,320 executions = $6.48/month
```

Optimize cost by:

- Increasing run frequency (e.g. every 15 minutes vs every 1 minute).
- Limiting number of canaries to critical workflows only.
- Using simpler checks (endpoint check vs full script).

---

## Elastic Load Balancer (ELB)

**What you will build in this section:**
You will create a production-like load-balanced web application entirely through the AWS Console. By the end you will have a real working system that:
- Distributes HTTP/HTTPS traffic across two EC2 instances in different Availability Zones
- Automatically removes unhealthy instances from rotation and restores them when they recover
- Routes `/api/*` requests to a dedicated backend target group using path-based rules

**Architecture of what we're building:**

```
            Internet Users
                  │
                  ▼
      [Application Load Balancer]   ← single stable DNS, spans 2 AZs
       HTTP:80 ──redirect──► HTTPS:443
                  │
         ┌────────┴──────────┐
         │    Routing Rules   │
         └────────┬──────────┘
                  │
      ┌───────────┴────────────┐
      ▼                        ▼
 Rule: /api/*           Default rule
      │                        │
      ▼                        ▼
[Target Group A]        [Target Group B]
  api-servers             web-servers
  health: /api/health     health: /health
      │                        │
 [EC2 api-1]            [EC2 web-1]
     AZ-a                    AZ-b
```

**The five things we'll build — in order:**

```
1. EC2 Targets  →  2. Target Groups  →  3. Application Load Balancer
                                               │
                          4. Listeners & Rules  +  5. HTTPS with ACM
```

**Prerequisites — check these before starting:**
- [ ] An AWS account with EC2 and ELB access
- [ ] Two EC2 instances running a web server (Apache/Nginx on port 80) in different AZs *(launch two t2.micro instances — your default VPC already has subnets in multiple AZs)*
- [ ] A VPC with public subnets in at least 2 Availability Zones *(your default VPC has this)*
- [ ] A domain name in Route 53 *(optional — needed only for HTTPS with ACM)*

---

### One Shot Revision

| Step | Topic | What you do |
| ---- | ----- | ----------- |
| 1 | [ELB Overview](#elb-overview) | Understand what ELB is and explore the Load Balancers console before creating anything |
| 2 | [Types of Load Balancers](#types-of-load-balancers) | Compare ALB, NLB, GWLB, and CLB — choose the right one for your workload |
| 3 | [ELB Architecture](#elb-architecture) | Trace a request step-by-step from client → listener → rule → target group → EC2 |
| 4 | [Target Groups](#target-groups) | Create two target groups, register your EC2 instances, and verify healthy status |
| 5 | [Listeners & Routing Rules](#listeners--routing-rules) | Create the ALB, add an HTTP listener, and add a path-based rule for `/api/*` |
| 6 | [Health Checks](#health-checks) | Tune health check thresholds, then stop a web server to watch a target go unhealthy |
| 7 | [Sticky Sessions](#sticky-sessions) | Enable duration-based stickiness on a target group and observe cookie-based routing |
| 8 | [SSL/TLS Termination](#ssltls-termination) | Request an ACM certificate and add an HTTPS listener with HTTP → HTTPS redirect |
| 9 | [ELB Best Practices](#elb-best-practices) | Enable access logs, deletion protection, and audit your ALB against the production checklist |
| 10 | [Reference](#reference) | Clean up all resources + official docs |

---

### ELB Overview

**What it is:** An Elastic Load Balancer is a managed reverse-proxy that accepts client traffic on one or more listeners and forwards it to healthy backend targets. AWS handles the load balancer's own capacity, patching, and Multi-AZ availability — you only configure listeners, rules, target groups, and health checks. Because clients only ever see the load balancer's DNS name, you can scale, replace, or move backends without any client-side change.

| Term | What it is |
| ---- | ---------- |
| **Load Balancer** | The managed entry-point with a stable DNS name — e.g. `my-alb-123.us-east-1.elb.amazonaws.com` |
| **Listener** | A process on the LB that accepts connections on a protocol + port (e.g. HTTPS:443) |
| **Rule** | An ordered condition attached to a listener that decides which target group receives a request |
| **Target Group** | A logical group of backend targets (EC2, IP, Lambda) that receive traffic from a rule |
| **Target** | An individual backend — EC2 instance, IP address, container, or Lambda function |
| **Health Check** | A probe that decides whether a target is healthy enough to receive new traffic |
| **Cross-Zone LB** | When enabled, each LB node distributes traffic evenly across targets in all enabled AZs |

**Why use a load balancer:**

- **High availability** — health-aware routing plus multi-AZ deployment survives instance and AZ failures
- **Elasticity** — pairs with Auto Scaling; new instances register automatically, unhealthy ones are drained
- **Decoupled DNS** — clients hit one endpoint; backends can change without client-side DNS updates
- **TLS offload** — terminate HTTPS at the LB with an ACM certificate; automatic free renewal
- **Security** — the LB is the public edge; backends live in private subnets only reachable from the LB SG

**Pricing overview:**

| Component | Detail |
| --------- | ------ |
| **Hourly charge** | Per load balancer per hour (~$0.0225/hr for ALB in `us-east-1`) |
| **LCU / capacity** | Additional charge based on connections, bandwidth, and rule evaluations |
| **Data transfer** | Standard AWS data-transfer pricing for traffic leaving the load balancer |
| **Free tier** | 750 hours/month of an Application Load Balancer for 12 months (new accounts only) |

> **Deep-dive resource:** [Elastic Load Balancing — Official AWS Documentation](https://docs.aws.amazon.com/elasticloadbalancing/)

---

**HANDS-ON — Explore the ELB Console (3 min)**

**Navigate:** AWS Console → search **EC2** → scroll the left sidebar to **Load Balancing**

Click through each item:

| Item | What you'll find |
| ---- | ---------------- |
| **Load Balancers** | All your ALBs, NLBs, and CLBs — empty for now |
| **Target Groups** | Named groups of backends — empty for now |
| **Trust Stores** | mTLS certificate authorities for mutual TLS |

> **Key insight:** Every item here is something ELB manages for you. Without ELB, you would run your own HAProxy or Nginx, manually update server lists as instances come and go, and write your own health-check scripts.

---

### Types of Load Balancers

**What it is:** AWS offers four load-balancer types. You pick the type at creation time and cannot change it later. Each type targets a different OSI layer and use case.

| Type | OSI Layer | Protocols | Best for |
| ---- | --------- | --------- | -------- |
| **Application LB (ALB)** | Layer 7 | HTTP, HTTPS, gRPC, WebSocket | Microservices, path/host-based routing, WAF, Lambda targets |
| **Network LB (NLB)** | Layer 4 | TCP, UDP, TLS | Extreme low latency, static IPs, non-HTTP workloads |
| **Gateway LB (GWLB)** | Layer 3/4 | IP via GENEVE | Third-party virtual appliances — firewalls, IDS/IPS |
| **Classic LB (CLB)** | Layer 4/7 | HTTP, HTTPS, TCP | Legacy only — do not use for new workloads |

**Quick decision guide:**

```
Is it HTTP/HTTPS and you need path or host routing? ──Yes──► ALB
Do you need TCP/UDP, static IP, or extreme performance? ──Yes──► NLB
Are you inserting a third-party network appliance? ──Yes──► GWLB
Legacy EC2-Classic workload only? ──Yes──► CLB (avoid)
```

**Feature comparison:**

| Feature | ALB | NLB | GWLB | CLB |
| ------- | --- | --- | ---- | --- |
| **Static / Elastic IP** | No | Yes | No | No |
| **Preserves client IP** | Via `X-Forwarded-For` header | Yes (native) | Yes (GENEVE) | Via header |
| **Lambda as target** | Yes | No | No | No |
| **HTTP/2, WebSocket, gRPC** | Yes | No | No | HTTP/1.1 only |
| **WAF integration** | Yes | No | No | No |
| **Slow start mode** | Yes | No | No | No |

> **Rule of thumb:** Use ALB for anything HTTP-based. Use NLB when you need a static IP or sub-millisecond latency. GWLB is only for inserting network security appliances.

---

**HANDS-ON — Compare load balancer types in the console (3 min)**

**Navigate:** EC2 → **Load Balancers** → **Create load balancer**

You will see four tiles: Application, Network, Gateway, Classic.

1. Read the short description under each tile — notice ALB says "HTTP/HTTPS", NLB says "TCP/UDP/TLS"
2. Click **Compare** (if available) to see the feature matrix side by side
3. Click **Cancel** — no resources created

> **What to notice:** The console shows the same information as the table above, but interactively. Get comfortable reading it before you create anything.

---

### ELB Architecture

**What it is:** Every ELB request flows through the same layered pipeline. Understanding this pipeline tells you exactly where to look when a request is dropped or routed incorrectly.

**End-to-end request flow:**

```
                                 ┌─────────────────────────────────────────┐
                                 │             Route 53 DNS                │
                                 │  my-alb-123.us-east-1.elb.amazonaws.com │
                                 └──────────────────┬──────────────────────┘
                                                    │ resolves to LB node IPs (one per AZ)
                                                    ▼
                                 ┌─────────────────────────────────────────┐
    ┌────────┐   Request         │       Elastic Load Balancer (ALB)       │
    │ Client │ ────────────────► │  ┌───────────────────────────────────┐  │
    └────────┘                   │  │ Listener :443 (HTTPS)             │  │
                                 │  │  ├── Rule 1: path = /api/*   ─────┼──┼──► Target Group A
                                 │  │  └── Default action          ─────┼──┼──► Target Group B
                                 │  └───────────────────────────────────┘  │
                                 │      (Listener :80 → redirect to :443)  │
                                 └─────────────────────────────────────────┘
                                                    │
                                   ┌────────────────┴────────────────┐
                                   ▼                                 ▼
                       ┌───────────────────────┐       ┌───────────────────────┐
                       │   Target Group A       │       │   Target Group B       │
                       │   (api-servers)        │       │   (web-servers)        │
                       │   Health: /api/health  │       │   Health: /health      │
                       └──────────┬────────────┘       └──────────┬────────────┘
                                  │                               │
                         ┌────────┴────────┐             ┌────────┴────────┐
                         ▼                 ▼             ▼                 ▼
                    ┌────────┐        ┌────────┐    ┌────────┐        ┌────────┐
                    │EC2 api1│        │EC2 api2│    │EC2 web1│        │EC2 web2│
                    │  AZ-a  │        │  AZ-b  │    │  AZ-a  │        │  AZ-b  │
                    └────────┘        └────────┘    └────────┘        └────────┘
```

**How a single request is handled — step by step:**

1. **DNS resolution** — the client resolves the ALB's DNS name; Route 53 returns an IP per enabled AZ
2. **Listener accepts** — the LB node in that AZ accepts the connection on the listener's protocol/port
3. **TLS termination** — if HTTPS, the LB decrypts the request using its ACM certificate
4. **Rule evaluation** — listener rules run in priority order; the first matching rule wins
5. **Target selection** — a healthy target is chosen from the matched target group (round-robin by default)
6. **Forwarding** — the LB opens or reuses a connection to the target and streams the request/response

---

**HANDS-ON — Read a real ALB request flow in the console (2 min)**

*(Do this after you create the ALB in the next section — come back here.)*

**Navigate:** EC2 → **Load Balancers** → select `my-web-alb` → **Listeners** tab

1. Click your HTTPS listener → **View/edit rules**
2. You will see rules listed top-to-bottom in priority order — this is exactly step 4 above
3. Click any rule to see its **Condition** (path pattern) and **Action** (forward to target group)

> **Key insight:** The console rule editor is a visual representation of the decision tree every request passes through. When traffic goes to the wrong target, always check this page first.

---

### Target Groups

**What it is:** A target group is the routing destination for a listener rule. It groups similar backends together, owns the health-check configuration for those backends, and controls how traffic is distributed among registered targets.

**Target types:**

| Target type | What it is | Supported on |
| ----------- | ---------- | ------------ |
| **instance** | An EC2 instance registered by Instance ID | ALB, NLB, CLB |
| **ip** | An IP address — VPC, on-prem, or EKS pod IPs | ALB, NLB, GWLB |
| **lambda** | A Lambda function invoked with an ALB event | ALB only |
| **alb** | Another ALB (front an ALB behind an NLB for static IPs) | NLB only |

**Routing algorithms (ALB):**

| Algorithm | Behaviour |
| --------- | --------- |
| **Round robin** (default) | Cycles through targets in order — best when all targets have similar capacity |
| **Least outstanding requests** | Picks the target with fewest in-flight requests — best when latency varies across targets |
| **Weighted random** | Random by weight — used to shift traffic gradually between two target groups |

**Cross-zone load balancing:**

```
Cross-zone OFF:                            Cross-zone ON:
LB node in AZ-a → only targets in AZ-a     LB node in AZ-a → targets in AZ-a, AZ-b, AZ-c
LB node in AZ-b → only targets in AZ-b     LB node in AZ-b → targets in AZ-a, AZ-b, AZ-c
```

| Load Balancer | Cross-zone default | Cost when enabled |
| ------------- | ------------------ | ----------------- |
| **ALB** | Always **on** (free) | Included in hourly charge |
| **NLB** | **Off** by default | Inter-AZ data transfer billed |
| **GWLB** | **Off** by default | Inter-AZ data transfer billed |

> **Deregistration delay** (default 300 s) lets in-flight requests finish before a target is fully removed — critical for zero-downtime deployments.

---

**HANDS-ON — Create two target groups and register EC2 instances (10 min)**

**Navigate:** EC2 → **Target Groups** → **Create target group**

---

**Target Group 1 — web-servers**

| Field | Value | Why |
| ----- | ----- | --- |
| Target type | **Instances** | We're targeting EC2 instance IDs |
| Target group name | `web-servers-tg` | Descriptive name |
| Protocol | **HTTP** | Traffic from ALB to target is plain HTTP inside the VPC |
| Port | **80** | Where your web server listens |
| VPC | **Default VPC** | Must match the ALB's VPC |
| Health check protocol | **HTTP** | |
| Health check path | `/health` | A lightweight endpoint on your web server |

Click **Next** → Select both your EC2 instances → **Include as pending below** → **Create target group**

---

**Target Group 2 — api-servers**

Repeat the same steps with:

| Field | Value |
| ----- | ----- |
| Target group name | `api-servers-tg` |
| Health check path | `/api/health` |

Register your EC2 instances the same way → **Create target group**

---

**Verify health status:**

1. EC2 → **Target Groups** → click `web-servers-tg` → **Targets** tab
2. Wait 30–60 seconds for the initial health check to run
3. **Status** column should show **healthy** for each instance

**If targets show `unhealthy`:**
- SSH into the instance and confirm the web server is running on port 80
- Check the instance's Security Group has an inbound rule for port 80 from the ALB security group

> **Key insight:** The Target Groups page shows exactly which backends the ALB considers healthy at any given moment. When users see errors, this is the second place to check (after the listener rules).

---

### Listeners & Routing Rules

**What it is:** A listener is a per-load-balancer process that accepts client connections on a protocol + port combination. Each listener holds rules — ordered conditions that route requests to different target groups or perform other actions like redirects.

**Listener protocol/port combinations:**

| Load Balancer | Listener protocols | Typical ports |
| ------------- | ----------------- | ------------- |
| **ALB** | HTTP, HTTPS | 80, 443, custom |
| **NLB** | TCP, UDP, TCP_UDP, TLS | 22, 25, 53, 80, 443, custom |
| **GWLB** | GENEVE | 6081 (fixed) |

**ALB rule condition types:**

| Condition type | Example |
| -------------- | ------- |
| **Host header** | `api.example.com`, `*.example.com` |
| **Path pattern** | `/api/*`, `/images/*.jpg` |
| **HTTP header** | Match on any header value — e.g. `X-Version: 2` |
| **HTTP method** | `GET`, `POST`, `PUT`, ... |
| **Query string** | `?env=staging` |
| **Source IP** | CIDR-based — e.g. `10.0.0.0/8` |

**ALB rule actions:**

| Action | What it does |
| ------ | ------------ |
| **forward** | Send the request to one or more target groups (supports weighted split) |
| **redirect** | HTTP 301/302 to another URL — e.g. force HTTP → HTTPS |
| **fixed-response** | Return a static status code and body — e.g. 503 during maintenance |
| **authenticate-cognito / -oidc** | Require user authentication before forwarding |

> **Rule priority:** Rules are evaluated lowest-number-first. The listener's **default action** runs only when no rule matches. Always set the default action to a safe fallback — typically forwarding to your main target group.

---

**HANDS-ON — Create the ALB and add path-based routing (12 min)**

**Navigate:** EC2 → **Load Balancers** → **Create load balancer** → select **Application Load Balancer**

---

**Step 1 — Basic configuration**

| Field | Value | Why |
| ----- | ----- | --- |
| Name | `my-web-alb` | Shown in the console and DNS name |
| Scheme | **Internet-facing** | Accepts traffic from the public internet |
| IP address type | **IPv4** | Standard for most workloads |

---

**Step 2 — Network mapping**

| Field | Value | Why |
| ----- | ----- | --- |
| VPC | **Default VPC** | Must match your EC2 instances |
| Availability Zones | Select **at least 2 AZs** with their public subnets | A single AZ = single point of failure |

> Always enable at least 2 AZs. The ALB will not achieve high availability with only one.

---

**Step 3 — Security groups**

1. Click **Create new security group** → name: `alb-sg`
2. Add inbound rule: **HTTP** port `80` from `0.0.0.0/0` *(open to internet)*
3. Save → return to ALB creation and select `alb-sg`

---

**Step 4 — Listeners and routing**

The console pre-creates one HTTP:80 listener.

| Field | Value |
| ----- | ----- |
| Protocol | **HTTP** |
| Port | **80** |
| Default action | **Forward to** → `web-servers-tg` |

Click **Add listener** if you want to add HTTPS:443 now *(or do this in the SSL/TLS section later)*.

---

**Step 5 — Create the ALB**

Click **Create load balancer**

**Wait 2–3 minutes.** State cycles: `provisioning` → `active`

**You should see:** State = **Active** and a DNS name like:
`my-web-alb-123456789.us-east-1.elb.amazonaws.com`

> Paste this DNS name into a browser — you should see your web server's default page. The ALB is now distributing traffic.

---

**Step 6 — Add a path-based routing rule for `/api/*`**

1. Click `my-web-alb` → **Listeners** tab → click the HTTP:80 listener
2. Click **View/edit rules** → **Add rule**
3. **Name:** `api-routing`
4. **Add condition** → **Path** → `/api/*`
5. **Add action** → **Forward to** → `api-servers-tg`
6. **Priority:** `10` *(lower number = evaluated first)*
7. Click **Save**

**Test it:** In a browser, open `http://<your-alb-dns>/api/health` — the request hits `api-servers-tg`. Open `http://<your-alb-dns>/` — the default rule forwards to `web-servers-tg`.

---

### Health Checks

**What it is:** A health check is a periodic probe from the load balancer to each registered target. Only targets in the `healthy` state receive new requests. Health checks are configured per target group and run continuously.

**Health check parameters:**

| Parameter | Detail |
| --------- | ------ |
| **Protocol** | HTTP, HTTPS (ALB); TCP, HTTP, HTTPS (NLB) |
| **Path** | HTTP(S) only — e.g. `/health`, `/status` |
| **Port** | Same as traffic port (default) or a specific override |
| **Interval** | Seconds between checks (5–300; ALB default: 30 s) |
| **Timeout** | Seconds to wait for a response (2–120; must be < Interval) |
| **Healthy threshold** | Consecutive successes before marking healthy (2–10; default 5) |
| **Unhealthy threshold** | Consecutive failures before marking unhealthy (2–10; default 2) |
| **Success codes** | HTTP status codes treated as healthy (default `200`; ranges like `200-299` allowed) |

**Health check state transitions:**

```
   ┌──────────────┐    N failures      ┌────────────┐
   │   healthy    │ ─────────────────► │ unhealthy  │
   │  (in use)    │                    │  (drained) │
   └──────┬───────┘                    └─────┬──────┘
          │                                  │
          │       M successes                │
          └──────────────────────────────────┘
```

**All target states:**

| State | Meaning |
| ----- | ------- |
| `initial` | Target just registered; first check hasn't run yet |
| `healthy` | Passing health checks; receives traffic |
| `unhealthy` | Failing health checks; no new traffic |
| `unused` | Registered but no listener rule points at this target group |
| `draining` | Deregistering; in-flight requests finish but no new ones accepted |
| `unavailable` | Cannot be reached — bad security group or terminated instance |

> **The health-check endpoint must be cheap and dependency-free.** Do not call your database from `/health` — a DB blip will immediately remove all targets and take down the service.

---

**HANDS-ON — Tune health checks and watch a target go unhealthy (10 min)**

**Navigate:** EC2 → **Target Groups** → `web-servers-tg` → **Health checks** tab → **Edit**

---

**Step 1 — Tighten the thresholds for faster failure detection**

| Field | Change to | Why |
| ----- | --------- | --- |
| Healthy threshold | **2** | Mark healthy after only 2 successes instead of 5 — faster recovery |
| Unhealthy threshold | **2** | Mark unhealthy after 2 failures — same as default; keep it |
| Interval | **15 seconds** | Check more frequently to detect failures sooner |
| Timeout | **5 seconds** | Must be less than interval |
| Success codes | `200-299` | Accept any 2xx, not just 200 |

Click **Save changes**

---

**Step 2 — Simulate a failure by stopping the web server**

SSH into one of your EC2 instances and stop the web server:

```bash
# On Amazon Linux 2
sudo systemctl stop httpd

# On Ubuntu
sudo systemctl stop nginx
```

---

**Step 3 — Watch the target go unhealthy in the console**

1. EC2 → **Target Groups** → `web-servers-tg` → **Targets** tab
2. Refresh every 15–30 seconds
3. You will see the stopped instance's **Status** change from `healthy` → `unhealthy`
4. The ALB now sends 100% of traffic to the remaining healthy target

---

**Step 4 — Restore and watch it recover**

```bash
# Restart the web server
sudo systemctl start httpd    # or: sudo systemctl start nginx
```

Refresh the Targets tab — the instance will return to `healthy` after 2 consecutive successful checks (~30 seconds).

> **This is the core value of ELB:** your users experienced no downtime even while one server was down. The ALB silently routed around it.

---

### Sticky Sessions

**What it is:** Sticky sessions (session affinity) route a given client's requests to the same backend target for a defined duration. Use this only when your application stores session state in memory and you cannot move that state to an external store like Redis or DynamoDB.

**Stickiness options on ALB:**

| Type | Cookie name | Duration | Who manages it |
| ---- | ----------- | -------- | -------------- |
| **Duration-based** | `AWSALB` | 1 second – 7 days | ALB itself |
| **Application-based** | Custom (your choice) | Set by your app | Your application |

**Stickiness on NLB (TCP/UDP):**
Uses **source-IP affinity** — the same client IP is routed to the same target. No cookie is used because NLB is Layer 4.

> **Trade-off:** Stickiness breaks even load distribution. If a high-traffic user is pinned to one target, that target becomes a hot spot. Prefer **stateless backends** with an external session store — treat stickiness as a last resort or a migration bridge.

---

**HANDS-ON — Enable sticky sessions and observe the cookie (5 min)**

**Navigate:** EC2 → **Target Groups** → `web-servers-tg` → **Attributes** tab → **Edit**

---

**Step 1 — Enable duration-based stickiness**

| Field | Value |
| ----- | ----- |
| Stickiness type | **Load balancer generated cookie** |
| Stickiness duration | **1 day** (86400 seconds) |

Click **Save changes**

---

**Step 2 — Observe the `AWSALB` cookie in a browser**

1. Open `http://<your-alb-dns>/` in a browser
2. Open DevTools → **Application** tab → **Cookies** → select the ALB domain
3. You will see an `AWSALB` cookie and an `AWSALBCORS` cookie

Refresh the page multiple times — you will always hit the same backend target because the cookie pins you there.

---

**Step 3 — Disable stickiness**

Return to **Target Groups** → `web-servers-tg` → **Attributes** → **Edit** → set **Stickiness** to **Off** → **Save changes**

> Disable stickiness after this exercise. For stateless web apps (most modern apps), stickiness is unnecessary and hurts load distribution.

---

### SSL/TLS Termination

**What it is:** With an HTTPS listener, the load balancer terminates the encrypted connection using an X.509 certificate, then forwards the request (in plaintext or re-encrypted) to the backend. This offloads CPU-intensive TLS processing from your instances and centralises certificate management in one place.

**Certificate sources:**

| Source | Detail |
| ------ | ------ |
| **AWS Certificate Manager (ACM)** | Free public certificates; automatic 60-day-before-expiry renewal; recommended for all public workloads |
| **ACM Private CA** | Internal PKI for private/mTLS use cases |
| **IAM certificate store** | Legacy — upload your own certificate/key pair |

**Listener security policies** (defines which TLS versions and ciphers the LB accepts):

| Policy | Notes |
| ------ | ----- |
| `ELBSecurityPolicy-TLS13-1-2-2021-06` | Modern default — supports TLS 1.2 and 1.3 |
| `ELBSecurityPolicy-TLS13-1-3-2021-06` | TLS 1.3 only — strictest; use if all clients support TLS 1.3 |
| `ELBSecurityPolicy-FS-1-2-Res-2020-10` | Forward-secrecy-only ciphers |
| `ELBSecurityPolicy-2016-08` | Legacy — avoid |

**Two termination modes:**

```
Termination-only:    Client ──HTTPS──► ALB ──HTTP──► Target (in private subnet)
End-to-end encrypt:  Client ──HTTPS──► ALB ──HTTPS──► Target (compliance/PCI/HIPAA)
```

**Multi-certificate listeners (SNI):** An HTTPS listener can serve different certificates for different domains — attach up to 25 ACM certificates per listener using Server Name Indication.

> **ACM certificates are free** for use with ELB, CloudFront, and API Gateway. Always prefer ACM over self-managed certificates — ACM auto-renews 60 days before expiry as long as DNS validation records remain in place.

---

**HANDS-ON — Request an ACM certificate and add HTTPS with HTTP redirect (12 min)**

**Navigate:** AWS Console → search **Certificate Manager** → **Request a certificate**

---

**Step 1 — Request a public certificate**

| Field | Value |
| ----- | ----- |
| Certificate type | **Request a public certificate** |
| Domain names | `yourdomain.com` and `*.yourdomain.com` |
| Validation method | **DNS validation** *(recommended — auto-renews)* |

Click **Request**

---

**Step 2 — Add the DNS validation CNAME record**

1. Click into your new certificate → **Domains** section
2. Click **Create records in Route 53** *(if your domain is in Route 53 — takes ~5 min)*
3. Wait for Status to change from `Pending validation` → `Issued`

*(If your domain is not in Route 53: copy the CNAME name and value, add it manually in your DNS provider, then wait up to 30 minutes.)*

---

**Step 3 — Add an HTTPS listener to the ALB**

**Navigate:** EC2 → **Load Balancers** → `my-web-alb` → **Listeners** tab → **Add listener**

| Field | Value |
| ----- | ----- |
| Protocol | **HTTPS** |
| Port | **443** |
| Default action | **Forward to** → `web-servers-tg` |
| Certificate source | **From ACM** → select your issued certificate |
| Security policy | **ELBSecurityPolicy-TLS13-1-2-2021-06** |

Click **Add**

---

**Step 4 — Force HTTP → HTTPS redirect**

1. Click the **HTTP:80** listener → **Edit**
2. Change Default action: **Redirect** → HTTPS, port `443`, status code `301`
3. Click **Save changes**

**Test:** Open `http://<your-alb-dns>/` — the browser should automatically redirect to `https://` and show a padlock.

> **Why 301 not 302?** A 301 (permanent redirect) lets browsers and crawlers cache the redirect, reducing round trips. Use 302 only during testing when you might revert.

---

### ELB Best Practices

**What it is:** A production-grade checklist of the load balancer configurations that prevent the most common outages, security incidents, and cost surprises.

| # | Best Practice | Why it matters |
| - | ------------- | -------------- |
| 1 | **Enable at least 2 AZs** | Single-AZ ALB = single-AZ outage; always pick subnets in 2+ AZs |
| 2 | **Enable deletion protection** | Prevents accidental deletion of your public endpoint |
| 3 | **Enable access logs to S3** | Free (except S3 storage); essential for debugging 4xx/5xx and DDoS forensics |
| 4 | **Force HTTPS with HTTP → HTTPS redirect** | Never serve plaintext HTTP in production |
| 5 | **Terminate TLS at the LB with ACM** | Offloads CPU from targets; auto-renews at no cost |
| 6 | **Restrict target SG to LB SG only** | Backends must only accept traffic from the ALB, not the internet |
| 7 | **Set a sensible deregistration delay** | 30–120 s for stateless HTTP; up to 300 s for long-lived connections |
| 8 | **Cheap, dependency-free `/health` endpoint** | Do not call the database from `/health` — one DB blip drains every target |
| 9 | **Alarm on 5xx and TargetResponseTime** | Fast signal for backend regressions before users report them |
| 10 | **Use path/host routing instead of many LBs** | One ALB with rules is cheaper and simpler than a fleet of small LBs |

**Key CloudWatch metrics to alarm on:**

| Metric | Load Balancer | What it tells you |
| ------ | ------------- | ----------------- |
| `HTTPCode_Target_5XX_Count` | ALB | Backend is throwing errors |
| `HTTPCode_ELB_5XX_Count` | ALB | LB itself couldn't reach a healthy target |
| `TargetResponseTime` | ALB | Backend latency — alarm on P99 > SLA threshold |
| `UnHealthyHostCount` | ALB / NLB | Number of targets currently failing health checks |
| `RejectedConnectionCount` | ALB | Connections dropped because the LB hit its capacity limit |
| `ActiveFlowCount` | NLB | Live TCP/UDP flows through the LB |

---

**HANDS-ON — Audit your ALB against the production checklist (8 min)**

**Navigate:** EC2 → **Load Balancers** → `my-web-alb`

Check each item:

| # | Where to verify | Expected value |
| - | --------------- | -------------- |
| 1 | **Description** tab → Availability Zones | At least 2 AZs listed |
| 2 | **Attributes** tab → Deletion protection | `Enabled` |
| 3 | **Attributes** tab → Access logs | `Enabled` with an S3 bucket |
| 4 | **Listeners** tab | HTTP:80 listener has Redirect → HTTPS action |
| 5 | **Listeners** tab | HTTPS:443 listener uses an ACM certificate |
| 6 | Target instances' SG → Inbound rules | Port 80 source = `alb-sg` ID, not `0.0.0.0/0` |

---

**Step 1 — Enable deletion protection**

**Navigate:** `my-web-alb` → **Attributes** tab → **Edit**

Toggle **Deletion protection** → **On** → **Save changes**

---

**Step 2 — Enable access logs**

1. Create an S3 bucket first: S3 → **Create bucket** → name `my-alb-access-logs-<your-account-id>` → leave defaults → **Create bucket**
2. Return to `my-web-alb` → **Attributes** → **Edit**
3. Toggle **Access logs** → **On**
4. S3 URI: `s3://my-alb-access-logs-<your-account-id>/prod/my-web-alb`
5. Click **Save changes**

> Access log files appear in S3 within 5 minutes of traffic arriving. Each line contains the request timestamp, client IP, target IP, response code, and latency — invaluable for debugging.

---

**Step 3 — Lock down the target security group**

1. EC2 → **Security Groups** → find the security group attached to your EC2 instances
2. **Inbound rules** → **Edit inbound rules**
3. Change the HTTP:80 source from `0.0.0.0/0` to the security group ID of `alb-sg`
4. **Save rules**

| Source type | Verdict | Risk |
| ----------- | ------- | ---- |
| `alb-sg` security group ID | ✅ Safe | Only the ALB can reach port 80 |
| `0.0.0.0/0` | ❌ Dangerous | Anyone on the internet can bypass the load balancer entirely |

---

### Reference

**Clean up resources (to avoid charges)**

**Step 1 — Delete the ALB**
- EC2 → **Load Balancers** → `my-web-alb` → first **disable deletion protection** (Attributes → Edit) → **Actions** → **Delete load balancer** → confirm

**Step 2 — Delete the target groups**
- EC2 → **Target Groups** → select `web-servers-tg` → **Actions** → **Delete** → confirm
- Repeat for `api-servers-tg`

**Step 3 — Delete the ALB security group**
- EC2 → **Security Groups** → `alb-sg` → **Actions** → **Delete security groups** → confirm

**Step 4 — Delete the ACM certificate (if you created one)**
- Certificate Manager → select your certificate → **Actions** → **Delete** → confirm

**Step 5 — Delete S3 access log bucket**
- S3 → `my-alb-access-logs-<your-account-id>` → **Empty bucket** first → then **Delete bucket**

**Verify:** EC2 → **Load Balancers** — no load balancers listed ✓

---

**Official documentation:**

→ [Elastic Load Balancing — Official AWS Documentation](https://docs.aws.amazon.com/elasticloadbalancing/)

→ [Application Load Balancers User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)

→ [Network Load Balancers User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)

→ [ELB — Listeners for your ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-listeners.html)

→ [ELB — Target Groups for your ALB](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html)

→ [ELB — Health Checks for Target Groups](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/target-group-health-checks.html)

→ [ELB — HTTPS Listeners](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html)

---

## Auto Scaling

**What you will build in this section:**
You will create a self-healing, auto-scaling web server fleet entirely through the AWS Console. By the end you will have a real working system that:
- Keeps 2 servers running at all times and replaces crashed ones automatically
- Adds servers when CPU load is high, removes them when load drops
- Pre-scales before business hours and scales down overnight

**Architecture of what we're building:**

```
          Users
            │
            ▼
  [Application Load Balancer]     ← distributes traffic evenly
            │
     ┌──────┴──────┐
     ▼             ▼
 [Server 1]    [Server 2]         ← Auto Scaling Group manages these
   AZ-a          AZ-b
     ▲             ▲
     └──────┬──────┘
            │
   [Server 3] added automatically  ← ASG spins this up when CPU > 50%
      AZ-a
```

**The five things we'll build — in order:**

```
1. Launch Template  →  2. Auto Scaling Group  →  3. Scaling Policy
                                │
                   4. Scheduled Action + 5. Lifecycle Hook
```

**Prerequisites — check these before starting:**
- [ ] An AWS account with EC2 and CloudWatch access
- [ ] A key pair already created *(EC2 → Key Pairs → Create key pair → download the `.pem` file)*
- [ ] At least 2 subnets in different AZs *(VPC → Subnets — your default VPC has these)*

---

### One Shot Revision

| Step | Topic | What you do |
| ---- | ----- | ----------- |
| 1 | [Auto Scaling Overview](#auto-scaling-overview) | Understand the moving parts before touching the console |
| 2 | [Launch Templates & Launch Configurations](#launch-templates--launch-configurations) | Create the "recipe" that defines what every server looks like |
| 3 | [Auto Scaling Groups (ASG)](#auto-scaling-groups-asg) | Create the fleet manager that uses your recipe — verify 2 servers launch |
| 4 | [Health Checks & Instance Replacement](#health-checks--instance-replacement) | Terminate a server and watch the ASG replace it in real time |
| 5 | [Scaling Policies](#scaling-policies) | Add CPU-based auto-scaling, then simulate load and watch it scale |
| 6 | [Scheduled Actions](#scheduled-actions) | Set the fleet to pre-scale every morning and shrink every night |
| 7 | [Lifecycle Hooks](#lifecycle-hooks) | Pause new servers before they go live so your app is fully ready |
| 8 | [Auto Scaling Best Practices](#auto-scaling-best-practices) | Rules that prevent the most common production mistakes |
| 9 | [Reference](#reference-1) | Clean up + official docs |

---

### Auto Scaling Overview

**Read this first — it maps out every concept before you touch the console.**

Auto Scaling is not one thing — it's a system of five parts that work together. Understanding how they connect makes every console step make sense.

```
┌─────────────────────────────────────────────────────────────┐
│                      Auto Scaling System                     │
│                                                             │
│  ┌──────────────────┐                                       │
│  │  Launch Template │  ← "recipe": what each server looks like
│  └────────┬─────────┘                                       │
│           │ used by                                         │
│           ▼                                                 │
│  ┌──────────────────┐    ┌───────────────┐                  │
│  │ Auto Scaling     │◄───│ Scaling Policy│  ← when to add/remove
│  │ Group (ASG)      │    │ (CPU > 50%)   │                  │
│  │                  │    └───────────────┘                  │
│  │  min=2           │    ┌───────────────┐                  │
│  │  desired=4       │◄───│Scheduled Action│ ← when by time   │
│  │  max=10          │    │ (9am Mon-Fri) │                  │
│  └──────────────────┘    └───────────────┘                  │
│           │                                                 │
│           │ creates/manages                                 │
│           ▼                                                 │
│  [server1] [server2] [server3] ...                          │
│                                                             │
│  Lifecycle Hook: pause server at startup/shutdown for setup │
└─────────────────────────────────────────────────────────────┘
```

**All 7 concepts — plain English:**

| Concept | Simple analogy | What it does |
| ------- | -------------- | ------------ |
| **Launch Template** | A cookie cutter or recipe — every server baked the same way | Stores AMI, instance type, security group, startup script |
| **Auto Scaling Group (ASG)** | A manager who keeps the right number of staff | Owns the fleet; launches/terminates servers to match desired count |
| **Desired / Min / Max** | "I want 4 staff, never below 2, never above 10" | Three numbers that bound the fleet size |
| **Scaling Policy** | A thermostat — turns heat on when cold, off when warm | Watches a CloudWatch metric and changes desired count |
| **Scheduled Action** | An alarm clock for servers | Changes capacity at a fixed time or cron schedule |
| **Lifecycle Hook** | A "hold" button on a phone call | Pauses a server during launch/terminate so you can run a script first |
| **Health Check** | A doctor's checkup, runs every 30 seconds | Detects bad servers and signals ASG to replace them |

**Why use it:**

| Pain without Auto Scaling | How Auto Scaling fixes it |
| ------------------------- | ------------------------- |
| You run 10 servers 24/7 for peak traffic, paying for idle servers at night | Scales in to 2 at night, out to 10 at peak — pay only for what runs |
| A server crashes at 3am — nobody sees it until morning | ASG detects the unhealthy server and replaces it within 2 minutes |
| You manually SSH into each server to configure it differently | Every server uses the same Launch Template — zero configuration drift |
| Traffic spike → your app crashes before you can react | Scaling policy adds servers before the spike kills the app |

**Pricing:**

| What costs money | What is free |
| ---------------- | ------------ |
| The EC2 instances the ASG creates | The Auto Scaling service itself |
| EBS volumes on those instances | Scaling policies |
| CloudWatch alarms that drive policies | Scheduled actions |
| Warm pool servers (EBS cost only, no instance-hours) | Predictive scaling |

---

### Launch Templates & Launch Configurations

**What it is:** A Launch Template is the recipe the ASG follows every time it needs to spin up a new server. Without it every new server could be different — different AMI, different packages, random config drift. With it every server is identical.

> Always use **Launch Templates**. Launch Configurations are the old equivalent — AWS stopped adding features to them.

---

**HANDS-ON — Create a Launch Template (10 min)**

**Navigate:** AWS Console → EC2 → left sidebar → **Launch Templates** → **Create launch template**

---

**Section 1 — Name and description**

| Field | What to type | Why |
| ----- | ------------ | --- |
| Launch template name | `my-web-server-lt` | Used to reference it in the ASG |
| Template version description | `v1 - nginx web server` | Label what this version does |
| Auto Scaling guidance checkbox | ✅ check it | Unlocks ASG-specific options |

---

**Section 2 — Application and OS Images (AMI)**

1. Click **Quick Start**
2. Select **Amazon Linux 2023** → the first result marked "Free tier eligible"
3. Leave the AMI ID as-is — this is the "disk image" every server will boot from

> **What is an AMI?** Think of it as a USB drive with an OS pre-loaded. Every server the ASG creates boots from this same USB drive.

---

**Section 3 — Instance type**

- Select **t2.micro** (free tier eligible — enough for this lab)

> **t2.micro = 1 vCPU, 1 GB RAM.** For production you'd pick something bigger, but this works fine for learning.

---

**Section 4 — Key pair (login)**

- Select your existing key pair from the dropdown
- No key pair yet? → Click **Create new key pair** → name it `my-lab-key` → **Create** → download the `.pem` file now (you can't download it again)

---

**Section 5 — Network settings**

Under **Firewall (security groups)**:
- Select: **Create security group**

| Field | Value |
| ----- | ----- |
| Security group name | `web-server-sg` |
| Description | `Allow HTTP and SSH` |

Add two **inbound rules**:

| Type | Port | Source | Why |
| ---- | ---- | ------ | --- |
| HTTP | 80 | Anywhere (0.0.0.0/0) | Users reach your web server |
| SSH | 22 | My IP | You can log in for debugging |

> Leave subnet blank — the ASG will decide which subnet to use at launch time.

---

**Section 6 — Advanced details → User data**

Scroll all the way down to find the **User data** field. Paste this script:

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello from: $(hostname -f)</h1>" > /var/www/html/index.html
```

> **What this does:** Every time the ASG launches a new server from this template, this script runs automatically on first boot. It installs Apache (web server), starts it, and creates a simple page showing the server's hostname. You'll use this later to prove that the load balancer is distributing across multiple servers.

---

Click **Create launch template**

**You should see:** `Successfully created launch template my-web-server-lt`

---

**Updating the template later — versioning:**

When you need to change the AMI or config, never edit the existing version. Create a new one:

```
v1 (current) — AMI: ami-abc123, nginx
    │
    │  you want to upgrade the AMI
    ▼
v2 (new) — AMI: ami-xyz789, nginx
    │
    │  test in staging → set as default
    ▼
ASG uses v2 for all new launches from now on
Old servers keep running v1 until they are naturally replaced
```

**Console steps to add a new version:**
1. EC2 → Launch Templates → select `my-web-server-lt`
2. Actions → **Modify template (Create new version)**
3. Change only what you need (e.g. AMI ID)
4. Add a version description → **Create template version**
5. To make it default: Actions → **Set default version** → select the new version number

**CLI equivalents (for reference):**

```bash
# Create a new version (e.g. AMI bump) from version 1
aws ec2 create-launch-template-version \
  --launch-template-name my-web-server-lt \
  --source-version 1 \
  --version-description "v2 - new AMI" \
  --launch-template-data '{"ImageId": "ami-0newami9876543210"}'

# Set version 2 as the default
aws ec2 modify-launch-template \
  --launch-template-name my-web-server-lt \
  --default-version 2

# Point the ASG at a specific version
aws autoscaling update-auto-scaling-group \
  --auto-scaling-group-name my-web-asg \
  --launch-template LaunchTemplateName=my-web-server-lt,Version='2'
```

**Key rules to remember:**
- Use `$Latest` in the ASG only if you want every scale-out to automatically pick up new template versions
- Pin to a specific version number (`Version='2'`) when you want explicit control over rollouts
- New AWS features only land on Launch Templates — never migrate back to Launch Configurations

---

### Auto Scaling Groups (ASG)

**What it is:** An ASG is the fleet manager. You hand it a Launch Template and three numbers, and it keeps exactly the right number of healthy servers running at all times — across multiple availability zones, behind a load balancer, automatically.

**The three numbers — a concrete example:**

```
Your e-commerce app scenario:
  min = 2   →  Even at 3am, always keep 2 servers. Below this, scale-in stops.
  desired = 2  →  Start with 2 servers right now.
  max = 5   →  During a flash sale, never spin up more than 5.

         min=2                                  max=5
           │                                      │
           ▼                                      ▼
   ════════●──────────────────────────────────────●════════
                        ▲
                   desired=2
                (ASG converges here)
```

Scaling policies adjust *desired* up or down. The ASG then adds/removes real servers to match it. Min and max are hard limits — no policy can cross them.

---

**HANDS-ON — Create the Auto Scaling Group (15 min)**

**Navigate:** EC2 → left sidebar → **Auto Scaling Groups** → **Create Auto Scaling group**

---

**Page 1 — Choose launch template**

| Field | Value |
| ----- | ----- |
| Auto Scaling group name | `my-web-asg` |
| Launch template | `my-web-server-lt` (the one you just created) |
| Version | `$Latest` |

Click **Next**

---

**Page 2 — Choose instance launch options**

**Network section:**
- VPC: select your **Default VPC**
- Availability Zones and subnets: **select at least 2 subnets in different AZs**
  - e.g. tick `us-east-1a` and `us-east-1b`

> **Why 2 AZs?** Think of AZs as separate buildings in a city. If one building loses power (AZ outage), your app keeps running in the other building. A single-AZ ASG gives you zero protection against this.

Click **Next**

---

**Page 3 — Configure advanced options (Load balancer + Health checks)**

**Load balancing:**
- Select: **Attach to a new load balancer**
- Load balancer type: **Application Load Balancer**
- Load balancer name: `my-web-alb`
- Load balancer scheme: **Internet-facing** ← users need to reach it from the internet
- Availability Zones: the same subnets you chose above

**Listeners and routing:**
- Port: 80 (HTTP)
- Default action: **Create a target group**
  - Target group name: `my-web-tg`

> **What just happened?** You created an ALB in front of your servers. Every new server the ASG creates will be automatically registered into `my-web-tg`, and the ALB will start sending it traffic.

**Health checks section:**
- ✅ Turn on: **Turn on Elastic Load Balancing health checks**
- Health check grace period: `120` seconds

> **Grace period explained:** When a new server boots, it needs ~60-90 seconds to run your startup script and start Apache. If health checks start too early, the server fails before it's ready and gets terminated in a loop. 120 seconds gives it breathing room.

Click **Next**

---

**Page 4 — Configure group size and scaling**

| Field | Value | What it means |
| ----- | ----- | ------------- |
| Desired capacity | `2` | Start with 2 servers |
| Min desired capacity | `2` | Never go below 2 |
| Max desired capacity | `5` | Never go above 5 |

**Automatic scaling:**
- Select: **No scaling policies** — we'll add this in Step 5

Click **Next → Next → Next → Create Auto Scaling group**

---

**Verify it worked — what you should see:**

**Check 1 — Instances launching:**
1. EC2 → **Instances**
2. You should see **2 new instances** with names containing `my-web-asg`
3. Their state will say "Initializing" → wait ~2 minutes → they move to "Running"

**Check 2 — ASG reports InService:**
1. EC2 → Auto Scaling Groups → `my-web-asg` → **Instance management** tab
2. Both instances should show **Health status: Healthy** and **Lifecycle: InService**

**Check 3 — Load balancer is working:**
1. EC2 → **Load Balancers** → `my-web-alb`
2. Copy the **DNS name** (looks like `my-web-alb-123456789.us-east-1.elb.amazonaws.com`)
3. Paste it into your browser
4. You should see: `Hello from: ip-10-0-x-x.ec2.internal`
5. Refresh a few times — the hostname changes as the ALB routes to different servers

> **If you don't see anything:** Wait 3-5 minutes for the instances to fully boot and pass health checks. The ALB shows "unhealthy" targets while instances are still starting.

---

**How the ASG lifecycle works — what happens internally:**

```
Something changes desired capacity:
  ├── CPU metric fires a scaling policy
  ├── 9am scheduled action
  └── you manually change desired in the console
                    │
                    ▼
         ┌──────────────────────┐
         │    Auto Scaling Group │
         │  min=2 desired=2 max=5│
         └──────────┬───────────┘
                    │ launches new server
                    ▼
           [Pending]  ← booting
                    │
           [Pending:Wait]  ← if lifecycle hook is set
                    │
           [InService]  ← joins ELB, receives traffic
                    │
                    │ health check fails
                    ▼
           [Terminating]  ← removed from ELB first (drains)
                    │
           [Terminated]  ← gone, replaced automatically
```

**CLI equivalents (for reference):**

```bash
# Create ASG via CLI
aws autoscaling create-auto-scaling-group \
  --auto-scaling-group-name my-web-asg \
  --launch-template LaunchTemplateName=my-web-server-lt,Version='$Latest' \
  --min-size 2 --max-size 5 --desired-capacity 2 \
  --vpc-zone-identifier "subnet-0abc1234,subnet-0def5678" \
  --target-group-arns arn:aws:elasticloadbalancing:...:targetgroup/my-web-tg/abc \
  --health-check-type ELB \
  --health-check-grace-period 120

# See all ASGs at a glance
aws autoscaling describe-auto-scaling-groups \
  --query 'AutoScalingGroups[].{Name:AutoScalingGroupName,Desired:DesiredCapacity,Min:MinSize,Max:MaxSize}' \
  --output table

# Manually change desired capacity
aws autoscaling set-desired-capacity \
  --auto-scaling-group-name my-web-asg \
  --desired-capacity 4
```

---

### Health Checks & Instance Replacement

**What it is:** The ASG checks every server's health every 30 seconds. The moment a server fails, it is terminated and a brand-new one is launched from the Launch Template. This is the self-healing that makes ASG different from just having EC2 instances.

**Two types of health checks — why both matter:**

| Type | What it actually asks | Catches |
| ---- | --------------------- | ------- |
| **EC2** (always on) | "Is the server's hardware and OS reachable?" | Hardware failure, OS crash |
| **ELB** (you must enable) | "Is the *app* returning healthy responses?" | App crash, 500 errors, hung process |
| **Custom** | You send a manual signal | Your own monitoring logic |

```
EC2 check only (bad):               EC2 + ELB check (correct):
──────────────────                  ──────────────────────────
"Is the server on?" → YES ✓         "Is the server on?" → YES ✓
App crashed → 500 errors            "Does app respond OK?" → NO ✗
EC2 doesn't know → server           ASG marks it Unhealthy
stays in load balancer              → terminates → launches replacement
→ users see errors all day          → users unaffected
```

---

**HANDS-ON — Test Self-Healing (5 min experiment)**

You already enabled ELB health checks when creating the ASG. Now let's prove it works by deliberately killing a server.

**Step 1 — Note the current instance IDs:**
1. EC2 → Auto Scaling Groups → `my-web-asg` → **Instance management** tab
2. Note both instance IDs (e.g. `i-0abc1234` and `i-0def5678`)

**Step 2 — Terminate one instance:**
1. EC2 → **Instances**
2. Select **one** of your ASG instances
3. **Instance state → Terminate instance** → confirm

**Step 3 — Watch the Activity tab:**
1. EC2 → Auto Scaling Groups → `my-web-asg` → **Activity** tab
2. Within 60-90 seconds you should see a new entry appear:

```
Launching a new EC2 instance to replace: i-0abc1234
Status: Successful
Reason: Instance i-0abc1234 was taken out of service in response to
        a user health-check request, changing the instance's health
        status from Healthy to Unhealthy.
```

**Step 4 — Confirm the replacement:**
1. EC2 → **Instances** — a brand-new instance with a different ID is now starting
2. EC2 → Auto Scaling Groups → `my-web-asg` → **Instance management** tab
3. Within ~2 minutes the new instance shows **InService** ✓

> **What you just witnessed:** The ASG noticed the fleet dropped below desired=2, launched a replacement from your Launch Template, waited for it to pass health checks, then registered it with the load balancer. All automatic, all within 2 minutes. This happens 24/7.

---

**How the replacement flow works internally:**

```
1. Health check detects server is Unhealthy
         │
2. Server is deregistered from ALB first
   (existing requests finish — "connection draining")
         │
3. Server is terminated
         │
4. ASG sees: actual count (1) < desired (2)
         │
5. ASG launches a new server from Launch Template
         │
6. New server boots, runs user-data script
         │
7. Grace period (120s) passes
         │
8. ELB health check passes
         │
9. Server joins ALB → back to 2 healthy servers
```

**Adjusting health check settings via CLI:**

```bash
# Switch to ELB health checks (if not done already)
aws autoscaling update-auto-scaling-group \
  --auto-scaling-group-name my-web-asg \
  --health-check-type ELB \
  --health-check-grace-period 180

# Manually mark an instance unhealthy (forces replacement)
aws autoscaling set-instance-health \
  --instance-id i-0abc1234 \
  --health-status Unhealthy

# See health status of all instances in the ASG
aws autoscaling describe-auto-scaling-instances \
  --query 'AutoScalingInstances[].{Id:InstanceId,AZ:AvailabilityZone,Health:HealthStatus,State:LifecycleState}' \
  --output table
```

**Common mistakes:**

| Mistake | What happens | Fix |
| ------- | ------------ | --- |
| Grace period too short (e.g. 30s) | Server fails health check before app starts → endless replace loop | Set grace period ≥ your actual boot time |
| Using EC2 health checks only | Crashed app stays in the load balancer → users get errors | Always enable ELB health checks |
| Health check path returns 500 always | ASG replaces half the fleet constantly | Fix the health check endpoint first |

---

### Scaling Policies

**What it is:** A scaling policy is the rule that decides when to add or remove servers based on a real metric — CPU, request count, memory. Without one, you manually adjust the desired count yourself. With one, it happens automatically in response to actual load.

**Analogy:** A thermostat. You set it to 22°C. If the room gets hotter, AC turns on. If it cools down, AC turns off. You never touch it. Target Tracking Scaling is a thermostat for your server count.

**Four types — pick the right one:**

| Type | How it works | Use when |
| ---- | ------------ | -------- |
| **Target Tracking** | "Keep CPU at 50%" — AWS calculates exactly how many servers to add/remove | Default for most workloads |
| **Step Scaling** | "+1 server at 70% CPU, +2 at 80%, +4 at 90%" — tiered response | You need proportionally bigger reactions to bigger spikes |
| **Simple Scaling** | "+1 server when alarm fires, then wait" | Old/legacy — don't use for new setups |
| **Predictive Scaling** | Uses ML to predict traffic patterns and adds servers *before* the spike | Traffic follows the same daily/weekly pattern |

```
Which policy should I use?
─────────────────────────
Traffic predictable every day/week?
    Yes → Predictive Scaling + Target Tracking together
    No  ↓

Just want "keep metric at X"?
    Yes → Target Tracking  ← use this for 90% of cases
    No  ↓

Need bigger jumps for bigger spikes?
    Yes → Step Scaling
```

---

**HANDS-ON — Add Target Tracking Policy (5 min)**

**Navigate:** EC2 → Auto Scaling Groups → `my-web-asg` → **Automatic scaling** tab → **Create dynamic scaling policy**

| Field | Value | Why |
| ----- | ----- | --- |
| Policy type | **Target tracking scaling** | The thermostat type |
| Scaling policy name | `cpu-target-50` | Descriptive name |
| Metric type | **Average CPU utilization** | What we're tracking |
| Target value | `50` | Keep average CPU at 50% |
| Instance warmup | `60` seconds | Wait 60s before counting a new server in the average |

Click **Create**

**What AWS just did automatically:**
1. EC2 → Auto Scaling Groups → `my-web-asg` → **Automatic scaling** tab — you see the policy listed
2. CloudWatch → **Alarms** — AWS created 2 alarms for you:
   - `TargetTracking-my-web-asg-AlarmHigh-...` → triggers scale-out (adds servers)
   - `TargetTracking-my-web-asg-AlarmLow-...` → triggers scale-in (removes servers)

> AWS manages these alarms for you — don't delete or modify them manually.

---

**HANDS-ON — Trigger the Policy and Watch Scaling (10 min)**

**Step 1 — Find a server's public IP:**
1. EC2 → Instances → click one of your ASG instances
2. Copy the **Public IPv4 address**

**Step 2 — SSH in and generate CPU load:**

```bash
ssh -i my-lab-key.pem ec2-user@<your-public-ip>

# Run 4 background processes that max out the CPU
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
yes > /dev/null &
```

**Step 3 — Watch the alarm turn red:**
1. CloudWatch → **Alarms**
2. Wait 3-5 minutes
3. `TargetTracking-my-web-asg-AlarmHigh-...` changes from OK (green) → **In alarm (red)**

**Step 4 — Watch new servers launch:**
1. EC2 → Auto Scaling Groups → `my-web-asg` → **Activity** tab
2. You'll see entries appear:

```
Launching a new EC2 instance.
Status: Successful
Reason: An alarm triggered a scale-out activity.
        Alarm: TargetTracking-my-web-asg-AlarmHigh-...
```

3. EC2 → Instances — you now have **3, 4, or 5 instances** running

**Step 5 — Stop the load and watch scale-in:**
```bash
# In your SSH session:
killall yes
exit
```

Wait 5-10 minutes → alarm returns to OK → ASG gradually removes the extra servers → back to 2.

> Scale-in is intentionally slower than scale-out. AWS waits to confirm the load is gone before removing servers — prevents thrashing.

---

**Step Scaling — when you need it:**

Use Step Scaling when a small CPU breach should add 1 server, but a large spike should add 4 immediately:

```
CPU 70-80% above target → +1 server
CPU 80-90% above target → +2 servers
CPU 90%+   above target → +4 servers (emergency)
```

**Console:** EC2 → Auto Scaling Groups → Automatic scaling tab → Create dynamic scaling policy → **Step scaling**

**CLI:**

```bash
aws autoscaling put-scaling-policy \
  --auto-scaling-group-name my-web-asg \
  --policy-name cpu-step-out \
  --policy-type StepScaling \
  --adjustment-type ChangeInCapacity \
  --step-adjustments '[
    {"MetricIntervalLowerBound": 0.0,  "MetricIntervalUpperBound": 20.0, "ScalingAdjustment": 1},
    {"MetricIntervalLowerBound": 20.0, "MetricIntervalUpperBound": 40.0, "ScalingAdjustment": 2},
    {"MetricIntervalLowerBound": 40.0,                                   "ScalingAdjustment": 4}
  ]'
```

**Key rules:**
- Use at most **one target-tracking policy per metric** — two policies on the same metric fight each other
- Target tracking disables scale-in automatically during a scale-out event to prevent flapping
- Step scaling requires you to create the CloudWatch alarm yourself; target tracking creates it for you

---

### Scheduled Actions

**What it is:** A scheduled action is an alarm clock for your server fleet. Instead of reacting to traffic after it spikes, you predict it and scale *before* users arrive.

**Why this beats relying on scaling policies alone:**

Scaling policies react *after* the metric threshold is crossed. That means:
1. Traffic spikes at 9am
2. CPU hits 80% → alarm fires → new server launches
3. New server takes 90 seconds to boot
4. **Your users waited 90 seconds on a slow/overloaded site**

Scheduled actions fix this:
1. At 8:50am every weekday: ASG pre-scales to 4 servers
2. 9am traffic arrives → servers are already warm and ready
3. **Zero slowdown for users**

```
Timeline:
──────────────────────────────────────────────────────►
8:50am                 9am              10pm
  │                    │                 │
  │ scheduled          │ users           │ scheduled
  │ action fires       │ arrive          │ action fires
  ▼                    ▼                 ▼
[2→4 servers]    [traffic handled]  [4→2 servers]
                  with no lag        (save money overnight)
```

---

**HANDS-ON — Add Scheduled Actions (5 min)**

**Navigate:** EC2 → Auto Scaling Groups → `my-web-asg` → **Automatic scaling** tab → **Scheduled actions** → **Create scheduled action**

---

**Action 1 — Morning scale-out (weekday business hours)**

| Field | Value |
| ----- | ----- |
| Name | `morning-scale-out` |
| Desired capacity | `4` |
| Min | `4` |
| Max | `5` |
| Recurrence | Custom — choose **Cron** |
| Cron expression | `30 8 * * MON-FRI` |
| Time zone | Your local time zone |

> **Cron `30 8 * * MON-FRI` means:** At 8:30am, every Monday through Friday. The format is `minute hour day month weekday`.

Click **Create**

---

**Action 2 — Nightly scale-in (save money overnight)**

Create another scheduled action:

| Field | Value |
| ----- | ----- |
| Name | `night-scale-in` |
| Desired capacity | `2` |
| Min | `2` |
| Max | `5` |
| Recurrence | Custom — choose **Cron** |
| Cron expression | `0 22 * * *` |
| Time zone | Your local time zone |

> **Cron `0 22 * * *` means:** At 10:00pm, every day.

Click **Create**

---

**Verify it worked:**

EC2 → Auto Scaling Groups → `my-web-asg` → **Automatic scaling** tab → **Scheduled actions** section

You should see both actions listed with their next scheduled run time.

---

**One-time scheduled action — for events like product launches:**

When you know a big traffic event is coming (Black Friday, a marketing email going out), you can pre-scale just once:

**Console:** Create scheduled action → same steps → set a specific **Start time** instead of recurrence

**CLI:**
```bash
# One-time pre-scale before a product launch at 1:30pm UTC
aws autoscaling put-scheduled-update-group-action \
  --auto-scaling-group-name my-web-asg \
  --scheduled-action-name product-launch-warmup \
  --start-time "2026-09-01T13:30:00Z" \
  --min-size 8 --desired-capacity 10 --max-size 20
```

**Cron quick reference:**

```
┌─────── minute (0-59)
│ ┌───── hour (0-23, UTC)
│ │ ┌─── day of month (1-31)
│ │ │ ┌─ month (1-12)
│ │ │ │ ┌ day of week (MON-FRI or 0-6)
│ │ │ │ │
0 9 * * MON-FRI   →  9:00am every weekday
0 22 * * *        →  10:00pm every day
30 8 * * MON-FRI  →  8:30am weekdays
0 0 1 * *         →  midnight on the 1st of every month
```

**Key rules:**
- All times are **UTC** — convert your local time before entering
- Scheduled actions **set** the capacity value, they don't add to it. If desired=4 and the scaling policy already pushed it to 5, the scheduled action sets it to 4 — it won't add 4 on top
- If a scheduled action and a scaling policy both fire at the same moment, the **scheduled action wins**
- Always pair with target tracking so the scaling policy still reacts to unexpected load within the scheduled window

---

### Lifecycle Hooks

**What it is:** By default, the ASG adds a new server to the load balancer the moment the OS boots — even if your app needs another 60 seconds to fully start. Users hit errors during that gap. A lifecycle hook solves this by pausing the server in a "wait" state until you signal it's ready.

```
WITHOUT lifecycle hook:
  OS boots → immediately joins load balancer
               ↑
        app still loading!  →  users get "503 Service Unavailable"

WITH lifecycle hook (launching):
  OS boots → PAUSE (Pending:Wait)
               ↑
        your script runs: install config, warm cache, health-check app
        → signal CONTINUE
                          → joins load balancer
                            app is fully ready → zero errors
```

**Two hook types:**

| Hook | When it fires | Use it for |
| ---- | ------------- | ---------- |
| **Launching hook** | Server booting, before it joins the ELB | Run config, cache warm-up, app readiness check |
| **Terminating hook** | Server shutting down, before it's killed | Drain in-flight requests, flush logs, take snapshot |

**Full lifecycle with hooks:**

```
Scale-out                              Scale-in
─────────                              ────────
[Pending]                              [InService]
     │                                       │
     │  launching hook fires                 │  terminating hook fires
     ▼                                       ▼
[Pending:Wait] ← your script runs    [Terminating:Wait] ← your script drains
     │         → signal CONTINUE           │              → signal CONTINUE
     ▼                                     ▼
[InService] → joins ELB              [Terminated]

If timeout fires without a signal:
  ABANDON → server is terminated (safe for launching)
  CONTINUE → server proceeds anyway (safe for terminating)
```

---

**HANDS-ON — Add a Launching Lifecycle Hook (5 min)**

**Navigate:** EC2 → Auto Scaling Groups → `my-web-asg` → **Instance management** tab → **Lifecycle hooks** section → **Create lifecycle hook**

| Field | Value | Why |
| ----- | ----- | --- |
| Lifecycle hook name | `wait-for-app-ready` | Descriptive |
| Lifecycle transition | **Instance launch** | Fire when a new server starts |
| Heartbeat timeout | `120` | Wait up to 120 seconds for your signal |
| Default result | **ABANDON** | If nothing signals in time, terminate the server — safer than adding a broken one to the LB |

Click **Create lifecycle hook**

**Verify:** The hook appears in the **Lifecycle hooks** section of the Instance management tab.

---

**What happens next time the ASG launches a server:**

1. EC2 → Auto Scaling Groups → `my-web-asg` → **Instance management** tab
2. Force a new launch: increase desired to 3 temporarily
3. You'll see the new instance stuck in **Lifecycle: Pending:Wait** instead of jumping straight to InService
4. After 120 seconds, default result `ABANDON` fires → instance terminates

> In production, your startup script (in user-data) would call `complete-lifecycle-action CONTINUE` when the app is ready. Here we let it timeout to see the behavior.

---

**Making the hook actually work in production:**

Add this to the end of your user-data script so the server signals itself as ready:

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello from: $(hostname -f)</h1>" > /var/www/html/index.html

# Wait for Apache to respond, then signal the lifecycle hook
until curl -s http://localhost/ > /dev/null; do sleep 2; done

# Get instance ID and region from instance metadata
INSTANCE_ID=$(curl -s http://169.254.169.254/latest/meta-data/instance-id)
REGION=$(curl -s http://169.254.169.254/latest/meta-data/placement/region)

# Signal the ASG: "I'm ready, let me into the load balancer"
aws autoscaling complete-lifecycle-action \
  --lifecycle-hook-name wait-for-app-ready \
  --auto-scaling-group-name my-web-asg \
  --lifecycle-action-result CONTINUE \
  --instance-id "$INSTANCE_ID" \
  --region "$REGION"
```

**CLI equivalents:**

```bash
# Add a launching hook (waits for your signal before joining ELB)
aws autoscaling put-lifecycle-hook \
  --lifecycle-hook-name wait-for-app-ready \
  --auto-scaling-group-name my-web-asg \
  --lifecycle-transition autoscaling:EC2_INSTANCE_LAUNCHING \
  --heartbeat-timeout 120 \
  --default-result ABANDON

# Add a terminating hook (waits before the server is killed)
aws autoscaling put-lifecycle-hook \
  --lifecycle-hook-name drain-on-terminate \
  --auto-scaling-group-name my-web-asg \
  --lifecycle-transition autoscaling:EC2_INSTANCE_TERMINATING \
  --heartbeat-timeout 60 \
  --default-result CONTINUE

# Manually signal a hook from your script or Lambda
aws autoscaling complete-lifecycle-action \
  --auto-scaling-group-name my-web-asg \
  --lifecycle-hook-name wait-for-app-ready \
  --instance-id i-0abc1234 \
  --lifecycle-action-result CONTINUE
```

**Key rules:**
- `ABANDON` on a launching hook terminates the server if timeout fires — safe, prevents broken servers from joining the LB
- `CONTINUE` on a terminating hook lets shutdown proceed even if your drain script times out — safe, prevents stuck servers
- Combine terminating hooks with the target group's **deregistration delay** so both the ELB and your script finish draining

---

### Auto Scaling Best Practices

These are the rules that prevent the most common real-world ASG failures. Understand why each one matters — not just what it says.

| Practice | What breaks if you skip it | How to apply it |
| -------- | -------------------------- | --------------- |
| **Always span 2+ AZs** | One AZ outage takes down your entire app | Add subnets from 2+ AZs when creating the ASG |
| **Use Launch Templates, not Configurations** | Can't use Spot, mixed instances, or new AWS features | Always create Launch Templates — never create new Launch Configurations |
| **Enable ELB health checks** | Crashed app stays in the load balancer; users get errors | Enable during ASG creation (Page 3) |
| **Set grace period ≥ real boot time** | Too short → endless terminate/replace loop | Measure how long your app takes to start; add 30s buffer |
| **Default to target tracking policies** | Other policy types are harder to tune and prone to flapping | Target tracking for CPU/requests; only use step scaling for non-linear responses |
| **Protect instances during deployments** | ASG terminates a server mid-deploy, causing partial deployments | Enable scale-in protection before deploying; disable after |
| **Use a warm pool for slow-boot apps** | Scale-out takes 3-5 minutes; users wait during traffic spikes | Add a warm pool of stopped pre-initialized servers |
| **Mix Spot + On-Demand for stateless fleets** | Paying full On-Demand price for servers that could be 70% cheaper | Use mixed instances policy: On-Demand base + Spot for burst |
| **Terminate oldest instance on scale-in** | Fleet never rotates; old servers accumulate config drift | Set termination policy to "OldestInstance" |
| **Test scale-in as carefully as scale-out** | Scale-in terminates the wrong instance; active connections dropped | Run manual scale-in tests before going to production |

---

**HANDS-ON — Monitor your ASG with CloudWatch (5 min)**

**Navigate:** EC2 → Auto Scaling Groups → `my-web-asg` → **Monitoring** tab

The key metric to watch:

```
GroupInServiceInstances  should equal  GroupDesiredCapacity

If GroupInServiceInstances < GroupDesiredCapacity for more than 5 minutes:
  → your health check is failing
  → your grace period is too short
  → your app is crashing on startup
```

**Set up an alarm for when the fleet can't converge:**

1. CloudWatch → **Alarms** → **Create alarm**
2. Select metric: **EC2 Auto Scaling → Group Metrics → GroupInServiceInstances**
3. Filter to your ASG name
4. Condition: **Less than `2`** for 2 consecutive data points (2 minutes)
5. Action: send notification to your email via SNS

**Key CloudWatch metrics:**

| Metric | What it means | Alarm when |
| ------ | ------------- | ---------- |
| `GroupInServiceInstances` | Healthy servers serving traffic | Less than your min |
| `GroupDesiredCapacity` | How many the ASG wants | — |
| `GroupPendingInstances` | Starting up | High for >5 min = slow boot |
| `GroupTerminatingInstances` | Shutting down | High for >5 min = slow drain |
| `GroupMaxSize` | Your ceiling | `InService` equals `Max` = you're out of capacity |

**Enable scale-in protection (protects servers during deploys):**

```bash
# Protect ALL new instances in the ASG
aws autoscaling update-auto-scaling-group \
  --auto-scaling-group-name my-web-asg \
  --new-instances-protected-from-scale-in

# Protect one specific instance during a deploy
aws autoscaling set-instance-protection \
  --auto-scaling-group-name my-web-asg \
  --instance-ids i-0abc1234 \
  --protected-from-scale-in
```

**Create a warm pool (pre-warmed servers ready in seconds):**

```bash
aws autoscaling put-warm-pool \
  --auto-scaling-group-name my-web-asg \
  --min-size 1 \
  --max-group-prepared-capacity 5 \
  --pool-state Stopped \
  --instance-reuse-policy '{"ReuseOnScaleIn": true}'
```

> Warm pool servers are stopped (not terminated) after scale-in, so next time they start in ~30 seconds instead of 3 minutes. You only pay EBS storage cost while they're stopped.

---

### Reference

**HANDS-ON — Clean up (avoid charges!)**

Always delete resources after a lab. Delete in this order — dependents first:

**Step 1 — Delete the Auto Scaling Group** *(this terminates all instances inside it)*
- EC2 → Auto Scaling Groups → `my-web-asg` → Actions → **Delete** → confirm

**Step 2 — Delete the Load Balancer**
- EC2 → Load Balancers → `my-web-alb` → Actions → **Delete** → confirm

**Step 3 — Delete the Target Group**
- EC2 → Target Groups → `my-web-tg` → Actions → **Delete** → confirm

**Step 4 — Delete the Launch Template**
- EC2 → Launch Templates → `my-web-server-lt` → Actions → **Delete template** → confirm

**Step 5 — Delete the Security Group**
- EC2 → Security Groups → `web-server-sg` → Actions → **Delete security groups** → confirm

**Step 6 — Delete CloudWatch Alarms**
- CloudWatch → Alarms → select the `TargetTracking-my-web-asg-...` alarms → **Delete**

**Verify:** EC2 → Instances — all instances show as **Terminated** ✓

---

**Official documentation:**

→ [Amazon EC2 Auto Scaling — Official AWS Documentation](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)

→ [AWS Auto Scaling — Documentation Hub](https://docs.aws.amazon.com/autoscaling/)

---

## RDS Basics

**What you will build in this section:**
You will create a production-like relational database on AWS RDS entirely through the AWS Console. By the end you will have a real working system that:
- Runs a MySQL database with automated backups and point-in-time recovery
- Stays highly available with Multi-AZ automatic failover
- Scales read traffic with a Read Replica in a different Availability Zone

**Architecture of what we're building:**

```
            [EC2 Application]
                   │
          ┌────────┴─────────┐
          ▼                  ▼
   [Primary RDS]      [Read Replica]   ← offloads SELECT queries
     MySQL 8.0          MySQL 8.0
       AZ-a               AZ-b
         │
         │ automatic failover (~60s)
         ▼
   [Standby RDS]            ← takes over if primary fails (Multi-AZ)
       AZ-b
```

**The four things we'll build — in order:**

```
1. RDS Instance  →  2. Multi-AZ Standby  →  3. Read Replica  →  4. Monitoring
```

**Prerequisites — check these before starting:**
- [ ] An AWS account with RDS and VPC access
- [ ] A VPC with at least 2 subnets in different AZs *(your default VPC already has this)*
- [ ] An EC2 instance in the same VPC to test connectivity *(optional but recommended)*

---

### One Shot Revision

| Step | Topic | What you do |
| ---- | ----- | ----------- |
| 1 | [RDS Overview](#rds-overview) | Understand what RDS is and when to use it over a self-managed database |
| 2 | [Database Engines](#database-engines) | Choose the right engine for your workload — MySQL, PostgreSQL, Aurora |
| 3 | [Create an RDS Instance](#create-an-rds-instance) | Spin up a MySQL database through the Console and connect to it from EC2 |
| 4 | [RDS Storage & Backups](#rds-storage--backups) | Enable automated backups and take a manual snapshot, then restore it |
| 5 | [Multi-AZ & High Availability](#multi-az--high-availability) | Enable Multi-AZ and trigger a failover to see automatic recovery |
| 6 | [Read Replicas](#read-replicas) | Create a Read Replica and redirect read queries to a separate endpoint |
| 7 | [RDS Security](#rds-security) | Lock down access with Security Groups, Subnet Groups, and encryption |
| 8 | [Parameter Groups](#parameter-groups) | Tune database engine settings without SSHing into any server |
| 9 | [RDS Monitoring & Performance Insights](#rds-monitoring--performance-insights) | Identify slow queries and resource bottlenecks using built-in tools |
| 10 | [RDS Best Practices](#rds-best-practices) | Production rules that prevent the most common database mistakes |
| 11 | [Aurora RDS](#aurora-rds) | Understand Aurora's architecture and when to choose it over standard RDS |
| 12 | [Reference](#reference-2) | Clean up all resources + official docs |

---

### RDS Overview

**What it is:** Amazon RDS (Relational Database Service) is a managed service that runs relational databases — MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Aurora — on AWS. AWS handles OS patching, backups, replication, and failover so you focus only on your schema and queries.

Use RDS when your application needs a structured, SQL-queryable database with ACID guarantees and you do not want to manage the underlying server, storage, or replication yourself.

---

**HANDS-ON — Explore the RDS Console (3 min)**

**Navigate:** AWS Console → search **RDS** → open **Amazon RDS**

Click through each left-sidebar item:

| Item | What you'll find |
| ---- | ---------------- |
| **Databases** | Lists all your RDS instances — empty for now |
| **Snapshots** | Manual and automated daily backup copies |
| **Parameter groups** | Database engine configuration files |
| **Subnet groups** | Which VPC subnets your databases can live in |
| **Events** | A log of everything RDS has done — failovers, restarts, backups |

> **Key insight:** Every item you see here is something RDS manages for you. On a self-hosted MySQL server, you would do all of this manually — cron jobs for backups, custom replication scripts, manual failover procedures.

---

### Database Engines

**What it is:** RDS supports six database engines. You choose the engine at creation time and cannot change it afterwards. Each engine has an Aurora variant that offers higher performance at a higher price.

| Engine | Best for | Free tier eligible |
| ------ | -------- | ------------------ |
| **MySQL 8.0** | Most web apps, general purpose | ✅ db.t3.micro |
| **PostgreSQL 16** | Complex queries, JSON, extensions | ✅ db.t3.micro |
| **MariaDB 10.11** | MySQL-compatible, fully open source | ✅ db.t3.micro |
| **Oracle** | Enterprise apps with Oracle licensing | ❌ |
| **SQL Server** | .NET apps, Windows ecosystem | ❌ |
| **Aurora MySQL / PostgreSQL** | High-throughput production workloads | ❌ |

> **This lab uses MySQL 8.0** — it is free-tier eligible and everything you learn applies directly to Aurora MySQL in production.

---

**HANDS-ON — Compare engines without creating anything (2 min)**

**Navigate:** RDS → **Create database** (do NOT click Create at the end — this is exploration only)

1. Click each engine radio button and notice how the version options and "Templates" change
2. Click **Aurora** — notice the "cluster" concept and that there is no Free tier template
3. Click **MySQL** — notice the **Free tier** template appears at the top
4. Click **Cancel** — no resources created

---

### Create an RDS Instance

**What it is:** An RDS instance is a single managed database server. You define its engine, instance size, storage, network placement, and credentials. AWS provisions the VM, installs the engine, applies the parameter group, and gives you an endpoint (hostname) to connect to — no SSH or OS access required.

---

**HANDS-ON — Create an Aurora RDS cluster (15 min)**

**Navigate:** RDS → **Databases** → **Create database**

---

**Section 1 — Creation method & engine**

| Field | Select |
| ----- | ------ |
| Creation method | **Standard create** |
| Engine type | **Amazon Aurora** |
| Edition | **Amazon Aurora MySQL-Compatible Edition** |
| Engine version | **Aurora MySQL 3.x (MySQL 8.0 compatible)** — select latest |

---

**Section 2 — Templates**

Select **Dev/Test** — Aurora has no Free Tier template. Dev/Test avoids Multi-AZ and keeps cost low for learning.

> **Note:** Aurora is not free-tier eligible. A `db.t3.medium` instance running for a full month costs roughly $50–$60. Stop or delete the cluster after the lab to avoid charges.

---

**Section 3 — Settings (credentials)**

| Field | Value | Why |
| ----- | ----- | --- |
| DB cluster identifier | `my-aurora-cluster` | Aurora creates a **cluster** (not a single instance) — this names the cluster |
| Master username | `admin` | Root database login |
| Credentials management | **Self managed** | You set and manage the password directly |
| Master password | `MyP@ssword123!` | Write this down — you need it to connect |
| Confirm password | same as above | — |

> **Production note:** Use AWS Secrets Manager to store credentials. Never hard-code passwords in application code or `.env` files.

---

**Section 4 — Instance configuration**

| Field | Value | Why |
| ----- | ----- | --- |
| DB instance class | `db.t3.medium` | Minimum class supported by Aurora — 2 vCPU, 4 GB RAM |
| Multi-AZ deployment | **Don't create an Aurora Replica** | Single writer for this lab; add a reader later for HA |

> **Aurora storage is fully managed:** Unlike standard RDS, you do not set a storage size or type. Aurora's distributed storage layer grows automatically in 10 GB increments up to 128 TiB — no disk-full errors, no pre-provisioning required.

---

**Section 5 — Connectivity (networking)**

| Field | Value | Why |
| ----- | ----- | --- |
| VPC | **Default VPC** | Same VPC your EC2 instances live in |
| DB subnet group | **Create new DB subnet group** | Spans all AZs automatically |
| Public access | **No** | Database must NOT be directly on the internet |
| VPC security group | **Create new** → name: `aurora-sg` | Controls who can reach port 3306 |
| Availability Zone | **No preference** | Aurora picks the optimal AZ |
| Database port | **3306** | MySQL-compatible default |

> **Why no public access?** A database should only be reachable from inside your VPC — from EC2 instances or Lambda functions — never from the public internet.

---

**Section 6 — Additional configuration**

| Field | Value | Why |
| ----- | ----- | --- |
| Initial database name | `myappdb` | Creates this schema on first boot |
| Backup retention period | **7 days** | Automated daily backups kept for a week |
| Enable encryption | ✅ checked (default) | Encrypts data at rest using AWS KMS — cannot be disabled after creation |
| Enable Performance Insights | ✅ checked | Free for 7 days — shows slow queries visually |
| Enable Enhanced Monitoring | ✅ checked → 60 seconds | OS-level metrics (CPU, memory, disk) |

---

Click **Create database**

**Wait 5–10 minutes.** Cluster status cycles: `creating` → `backing-up` → `available`

**You should see:** Two entries under Databases — the **cluster** and one **writer instance** inside it, both showing **Available**.

Aurora gives you **two cluster endpoints** — use these, never the instance endpoint directly:

| Endpoint | Purpose |
| -------- | ------- |
| **Writer endpoint** | Routes all writes to the current primary; auto-updated on failover |
| **Reader endpoint** | Load-balances reads across all Aurora Replicas |

> Copy the **writer endpoint** — it looks like: `my-aurora-cluster.cluster-abc123.us-east-1.rds.amazonaws.com`

---

**Connect to your Aurora cluster from EC2**

First, allow your EC2 to reach port 3306 on the Aurora security group:

1. EC2 → **Security Groups** → `aurora-sg` → **Inbound rules** → **Edit inbound rules**
2. **Add rule:** Type = `MySQL/Aurora`, Port = `3306`, Source = your EC2 security group ID
3. Click **Save rules**

Then SSH into your EC2 and run:

```bash
# Install MySQL client
sudo yum install -y mysql

# Connect to Aurora cluster via the writer endpoint
mysql -h my-aurora-cluster.cluster-abc123.us-east-1.rds.amazonaws.com -u admin -p
# Enter your password when prompted

# Once inside MySQL — verify the database exists
SHOW DATABASES;
USE myappdb;

# Create a test table and insert data
CREATE TABLE users (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(100));
INSERT INTO users (name) VALUES ('Alice'), ('Bob');
SELECT * FROM users;
```

**You should see:** The `users` table with two rows — your Aurora cluster is live.

---

### RDS Storage & Backups

**What it is:** RDS automatically backs up your database every day during a configurable backup window, retaining those backups for 1–35 days. You can also take manual snapshots at any time that persist until you explicitly delete them.

Point-in-time recovery lets you restore to any second within the retention window — not just the daily backup timestamps.

---

**HANDS-ON — Take a manual snapshot and restore it (10 min)**

**Navigate:** RDS → **Databases** → `my-rds-db`

---

**Step 1 — Take a manual snapshot**

1. **Actions** → **Take snapshot**
2. Snapshot name: `my-rds-db-manual-snap-1`
3. Click **Take snapshot**

**Status:** `creating` → `available` *(2–5 minutes)*

> **When to take manual snapshots:** Before any risky migration or schema change. Automated backups cover daily protection — manual snapshots cover "I'm about to do something dangerous" moments.

---

**Step 2 — View the backup window and restore point**

1. RDS → `my-rds-db` → **Maintenance & backups** tab
2. Note **Backup window** *(UTC time when daily backup runs)*
3. Note **Latest restorable time** *(how recent a point-in-time restore can go — typically within 5 minutes of now)*

---

**Step 3 — Restore the snapshot to a new instance (optional)**

1. RDS → **Snapshots** → select `my-rds-db-manual-snap-1`
2. **Actions** → **Restore snapshot**
3. DB instance identifier: `my-rds-db-restored`
4. Instance class: `db.t3.micro`
5. Click **Restore DB instance**

> **Important:** Restoring always creates a **new** RDS instance — it never overwrites the original. Your application must update its connection string to point to the restored instance.

**Clean up:** RDS → `my-rds-db-restored` → **Actions** → **Delete** → skip final snapshot → confirm

---

### Multi-AZ & High Availability

**What it is:** Multi-AZ keeps a synchronous standby copy of your database in a second Availability Zone. If the primary instance fails — hardware fault, AZ outage, planned maintenance — RDS automatically promotes the standby to primary in approximately 60 seconds. Your app reconnects to the same endpoint with no configuration change.

The standby is NOT readable — it exists only for failover. For read scaling, use Read Replicas.

---

**HANDS-ON — Enable Multi-AZ and trigger a failover (10 min)**

**Navigate:** RDS → **Databases** → `my-rds-db` → **Modify**

---

**Step 1 — Enable Multi-AZ**

1. Scroll to **Availability & durability**
2. Select **Create a standby instance (recommended for production usage)**
3. Scroll down → **Continue**
4. Apply when: **Immediately**
5. **Modify DB instance**

**Status:** `modifying` → `available` *(5–10 minutes — the standby is being provisioned)*

> **Cost note:** Multi-AZ doubles your RDS cost since you're running two instances. Enable it here briefly to test, then disable to save lab costs.

---

**Step 2 — Trigger a manual failover**

1. RDS → `my-rds-db` → **Actions** → **Reboot**
2. Check **Reboot With Failover?** ✅
3. Click **Confirm**

**Watch the Events log:** RDS → `my-rds-db` → **Logs & events** tab

You will see:
- `Multi-AZ instance failover started`
- `DB instance restarted`
- `Recovered from a Multi-AZ failover`

> **The endpoint stays the same throughout.** Your application sees a ~60-second connection drop, then reconnects to the promoted standby — same hostname, no DNS change, no config update needed.

---

**Step 3 — Disable Multi-AZ (save costs)**

`my-rds-db` → **Modify** → Availability & durability → **Do not create a standby instance** → Apply immediately → **Modify DB instance**

---

### Read Replicas

**What it is:** A Read Replica is an asynchronous copy of your primary database that serves SELECT queries. Unlike a Multi-AZ standby, a replica IS readable — you point your app's read traffic at the replica's endpoint to reduce load on the primary. Replicas can also be in a different region for disaster recovery.

---

**HANDS-ON — Create and use a Read Replica (8 min)**

**Navigate:** RDS → **Databases** → `my-rds-db`

---

**Step 1 — Create the replica**

1. **Actions** → **Create read replica**
2. DB instance identifier: `my-rds-db-replica`
3. Destination region: same region as primary
4. DB instance class: `db.t3.micro`
5. Public access: **No**
6. Click **Create read replica**

**Wait 5–10 minutes.** Status: `creating` → `available`

---

**Step 2 — Note the separate endpoint**

1. Click `my-rds-db-replica` → **Connectivity & security**
2. Copy the replica endpoint — e.g. `my-rds-db-replica.abc123.us-east-1.rds.amazonaws.com`

> **Read/write splitting pattern:** Your app sends `INSERT`, `UPDATE`, `DELETE` to the primary endpoint and `SELECT` queries to the replica endpoint — this is the standard way to scale a MySQL workload.

---

**Step 3 — Verify replication is working**

From your EC2, write to the primary and read from the replica:

```bash
# Write to primary
mysql -h my-rds-db.abc123.us-east-1.rds.amazonaws.com -u admin -p myappdb \
  -e "INSERT INTO users (name) VALUES ('Charlie');"

# Read from replica (may take 1-2 seconds due to async replication lag)
mysql -h my-rds-db-replica.abc123.us-east-1.rds.amazonaws.com -u admin -p myappdb \
  -e "SELECT * FROM users;"
# Charlie should appear after a short replication delay
```

---

**Step 4 — Clean up the replica**

RDS → `my-rds-db-replica` → **Actions** → **Delete** → skip final snapshot → confirm

---

### RDS Security

**What it is:** RDS security has three layers: network isolation (the VPC and subnets the database lives in), access control (which security groups can reach port 3306), and encryption (data at rest and in transit). Properly configured, your database is unreachable from the internet and encrypted even if someone physically removed the storage media.

---

**HANDS-ON — Audit and harden your RDS security (8 min)**

**Navigate:** RDS → **Databases** → `my-rds-db` → **Connectivity & security** tab

---

**Step 1 — Confirm public access is OFF**

- Verify **Publicly accessible = No**
- If it says Yes: **Modify** → Connectivity → Public access = **No** → Apply immediately

---

**Step 2 — Inspect the DB Subnet Group**

1. Click the subnet group link (e.g. `default-vpc-xxx`)
2. Confirm it spans **at least 2 Availability Zones**

> DB Subnet Groups tell RDS which subnets it can place your database in. Always use private subnets — subnets with no route to an Internet Gateway.

---

**Step 3 — Tighten the security group inbound rules**

1. Click the `rds-sg` security group link
2. **Inbound rules** — confirm port 3306 is open **only** to your EC2 security group ID, not to `0.0.0.0/0`
3. If it says `0.0.0.0/0`: **Edit inbound rules** → change Source to your EC2 security group → **Save rules**

| Source type | Verdict | Risk |
| ----------- | ------- | ---- |
| EC2 security group ID | ✅ Safe | Only your app servers can connect |
| 0.0.0.0/0 | ❌ Dangerous | Anyone on the internet can attempt a connection |
| Your office IP range | ⚠️ Acceptable for dev only | Breaks when IP changes; don't use in prod |

---

**Step 4 — Verify encryption at rest**

- RDS → `my-rds-db` → **Configuration** tab
- Find **Storage encrypted = Yes** and note the **AWS KMS key ARN**

> Encryption at rest is configured at creation time and **cannot be enabled on an existing instance**. The only way to encrypt an unencrypted instance is to take a snapshot, copy it with encryption enabled, then restore from the encrypted snapshot.

---

**Step 5 — Connect with SSL/TLS (enforce encrypted transit)**

```bash
# Download the AWS RDS CA certificate bundle
wget https://truststore.pki.rds.amazonaws.com/global/global-bundle.pem

# Connect with SSL verification enabled
mysql -h my-rds-db.abc123.us-east-1.rds.amazonaws.com \
      -u admin -p \
      --ssl-ca=global-bundle.pem \
      --ssl-mode=VERIFY_IDENTITY

# Inside MySQL — confirm SSL is active
SHOW STATUS LIKE 'Ssl_cipher';
# Output should show something like: AES256-SHA
```

---

### Parameter Groups

**What it is:** A Parameter Group is a named collection of database engine settings — things like `max_connections`, `slow_query_log`, and `innodb_buffer_pool_size`. Instead of SSHing into a server and editing config files, you change values in the Parameter Group and attach it to your RDS instance — no OS access needed.

---

**HANDS-ON — Create a custom Parameter Group and tune engine settings (8 min)**

**Navigate:** RDS → **Parameter groups** → **Create parameter group**

---

**Step 1 — Create a new parameter group**

| Field | Value |
| ----- | ----- |
| Parameter group family | `mysql8.0` |
| Type | **DB Parameter Group** |
| Group name | `my-mysql-params` |
| Description | `Custom MySQL 8.0 parameters for learning` |

Click **Create**

---

**Step 2 — Edit key parameters**

Click `my-mysql-params` → **Edit parameters**. Search for and update:

| Parameter | Set to | Why |
| --------- | ------ | --- |
| `slow_query_log` | `1` | Enable logging of slow queries |
| `long_query_time` | `1` | Log any query taking longer than 1 second |
| `max_connections` | `100` | Cap concurrent connections (default is too high for db.t3.micro) |

Click **Save changes**

> Parameters marked **dynamic** apply immediately. Parameters marked **static** require a database reboot — they show a `pending-reboot` indicator next to the instance after you apply them.

---

**Step 3 — Attach the parameter group to your instance**

1. RDS → `my-rds-db` → **Modify**
2. **Database options** → DB parameter group → select `my-mysql-params`
3. **Continue** → Apply: **Immediately** → **Modify DB instance**

---

**Step 4 — Verify the settings took effect**

```bash
# Connect to MySQL and check
mysql -h <your-endpoint> -u admin -p myappdb

SHOW VARIABLES LIKE 'slow_query_log';
-- Expected: slow_query_log = ON

SHOW VARIABLES LIKE 'long_query_time';
-- Expected: long_query_time = 1.000000

SHOW VARIABLES LIKE 'max_connections';
-- Expected: max_connections = 100
```

---

### RDS Monitoring & Performance Insights

**What it is:** RDS automatically pushes dozens of metrics to CloudWatch — CPU, active connections, read/write IOPS, disk latency. Performance Insights adds a query-level view on top: you see which SQL statements are consuming the most database time, making it fast to identify the slow query behind a CPU spike.

---

**HANDS-ON — Read metrics and identify slow queries (8 min)**

**Navigate:** RDS → **Databases** → `my-rds-db` → **Monitoring** tab

---

**Step 1 — Read the CloudWatch metric graphs**

| Metric | What it tells you | Warning sign |
| ------ | ----------------- | ------------ |
| **CPUUtilization** | Is the DB compute-bound? | Sustained > 80% |
| **DatabaseConnections** | How many apps are connected | Approaching `max_connections` |
| **FreeStorageSpace** | Disk remaining | Below 10% of allocated |
| **ReadIOPS / WriteIOPS** | Disk operations per second | Unexpected spikes |
| **ReadLatency / WriteLatency** | Time per disk operation | Above 20ms |

> **Diagnose bottlenecks:** High CPU + low IOPS = query logic problem (missing index). High IOPS + high latency = disk throughput problem (wrong storage type or size).

---

**Step 2 — Open Performance Insights**

1. Click the **Performance Insights** tab
2. The **DB load** chart shows database activity colored by wait type
3. Below it: **Top SQL** — statements ranked by total database time consumed

| Color in DB load chart | Bottleneck |
| ---------------------- | ---------- |
| `CPU` | Query computation is the problem — check for missing indexes |
| `IO:DataFileRead` | Too much data being read — full table scans |
| `Lock:row lock waits` | Concurrent transactions blocking each other |

Click any SQL statement in **Top SQL** to see its full text and average latency.

---

**Step 3 — Generate test load and watch the metrics**

From your EC2:

```bash
mysql -h <your-rds-endpoint> -u admin -p myappdb <<'EOF'
CREATE TABLE IF NOT EXISTS load_test (
  id INT AUTO_INCREMENT PRIMARY KEY,
  data VARCHAR(255)
);
INSERT INTO load_test (data) SELECT REPEAT('x', 255) FROM information_schema.columns LIMIT 100;
INSERT INTO load_test (data) SELECT data FROM load_test;
INSERT INTO load_test (data) SELECT data FROM load_test;
SELECT COUNT(*) FROM load_test;
SELECT * FROM load_test WHERE data LIKE '%x%';
EOF
```

Switch to the **Monitoring** tab and watch **CPUUtilization** and **WriteIOPS** spike, then return to baseline.

---

**Step 4 — Check Enhanced Monitoring (OS-level metrics)**

1. **Monitoring** tab → scroll down to **OS metrics** section
2. You will see CPU steal, memory used, filesystem usage, and disk I/O at 60-second granularity

> Enhanced Monitoring runs an agent inside the RDS instance that reports OS metrics to CloudWatch Logs — these are more detailed than standard CloudWatch metrics, which only show hypervisor-level data.

---

### RDS Best Practices

**What it is:** A production-grade checklist covering the most common RDS configuration mistakes — missing backups, open security groups, credential exposure, and connection pool mismanagement. Going through this checklist before you deploy prevents 80% of real-world database incidents.

---

**HANDS-ON — Audit your instance against the production checklist (5 min)**

Check each item against `my-rds-db`:

| # | Practice | Where to verify | Why it matters |
| - | -------- | --------------- | -------------- |
| 1 | **Multi-AZ enabled** | Configuration tab → Multi-AZ = Yes | Automatic failover in under 60 seconds |
| 2 | **Automated backups ON** | Maintenance & backups → Retention > 0 days | Recover from accidental DELETE without prod restore |
| 3 | **No public access** | Connectivity → Publicly accessible = No | Database should never be internet-facing |
| 4 | **Encryption at rest ON** | Configuration → Storage encrypted = Yes | Required for SOC 2, PCI-DSS, HIPAA |
| 5 | **Storage autoscaling ON** | Configuration → Max allocated storage > 20 GB | Prevents disk-full outages at 3am |
| 6 | **Security group uses SG source** | Inbound rules reference SG IDs, not `0.0.0.0/0` | SG IDs auto-update; IP ranges go stale |
| 7 | **Performance Insights enabled** | Monitoring → Performance Insights tab is active | Find slow queries before users complain |
| 8 | **Backup window set off-peak** | Maintenance & backups → Backup window | Avoid backup I/O during peak traffic hours |
| 9 | **Parameter group customized** | Configuration → not using `default.mysql8.0` | Default params are too permissive for production |
| 10 | **Failover tested** | Events log shows past failover test | Proves your app handles reconnects gracefully |

---

**Common mistakes and how to fix them:**

| Mistake | What happens | Fix |
| ------- | ------------ | --- |
| Security group allows `0.0.0.0/0` on port 3306 | Database reachable from the entire internet | Restrict source to your app's security group ID |
| No connection pool / too many direct connections | Connection count hits `max_connections`, new connections fail | Use RDS Proxy or a connection pooler (PgBouncer) |
| Never tested a restore | Backup exists but cannot be restored in time during incident | Run a monthly restore drill in staging |
| Using `db.t3.micro` under sustained load | CPU credits deplete, latency spikes 3–5× | Monitor `CPUCreditBalance` — upgrade before credits hit zero |
| Credentials stored in `.env` committed to git | Leaked repo = database breach | Use AWS Secrets Manager + automatic rotation |

---

### Aurora RDS

**What it is:** Amazon Aurora is an AWS-designed relational database engine that is fully compatible with MySQL and PostgreSQL but built on a custom distributed storage layer. It delivers up to 5× the throughput of standard MySQL on RDS and up to 3× that of standard PostgreSQL — at one-tenth the cost of commercial databases — by separating compute from storage and replicating data 6 ways across 3 Availability Zones automatically.

Use Aurora when you need high throughput, sub-30s failover, or global multi-region active-active reads, and you still want a familiar SQL interface.

---

**How Aurora differs from standard RDS:**

| Feature | Standard RDS (MySQL/PostgreSQL) | Amazon Aurora |
| ------- | ------------------------------- | ------------- |
| **Storage** | EBS volume attached to one instance | Distributed, shared cluster volume — all nodes read the same data |
| **Replication** | 1 synchronous standby (Multi-AZ) | 6 copies across 3 AZs, always on |
| **Failover time** | ~60 seconds | < 30 seconds (typically < 10 s) |
| **Read scaling** | Up to 5 Read Replicas | Up to 15 Aurora Replicas, all sharing the same storage |
| **Storage growth** | You provision a fixed size | Automatically grows in 10 GB increments up to 128 TiB |
| **Backtrack** | Not available | Roll back a cluster to any point in the last 72 hours without a restore |
| **Global Database** | Not available | Replicate to up to 5 secondary Regions with < 1 s lag |
| **Serverless v2** | Not available | Instantly scale compute up/down per ACU — pay only for what you use |

---

**Aurora Architecture:**

```
            [Writer Instance]          ← one primary, handles all writes
             /     |      \
      [Reader]  [Reader]  [Reader]     ← up to 15 read replicas, share same storage
             \     |      /
         ┌───────────────────────┐
         │   Aurora Cluster Vol  │     ← 6 copies across 3 AZs, auto-healing
         │  AZ-a  │  AZ-b  │ AZ-c│
         └───────────────────────┘
```

All replicas read from the same shared storage volume — there is no replication lag for reads.

---

**HANDS-ON — Create an Aurora MySQL cluster (10 min)**

**Navigate:** AWS Console → **RDS** → **Create database**

**Step 1 — Choose engine**
- Creation method: **Standard create**
- Engine type: **Amazon Aurora**
- Edition: **Amazon Aurora MySQL-Compatible Edition**
- Version: select the latest **MySQL 8.0-compatible** engine

**Step 2 — Template & cluster settings**
- Template: **Dev/Test** *(to stay in Free Tier range)*
- DB cluster identifier: `my-aurora-cluster`
- Master username: `admin`
- Credentials: **Self managed** → set a strong password

**Step 3 — Instance configuration**
- DB instance class: **db.t3.medium** *(minimum for Aurora)*
- Multi-AZ deployment: **Don't create an Aurora Replica** *(for this lab)*

**Step 4 — Connectivity**
- VPC: your default VPC
- Public access: **No**
- VPC security group: create new → `aurora-sg`
  - Add inbound rule: MySQL/Aurora (3306) from your EC2 security group ID

**Step 5 — Additional configuration**
- Initial database name: `auroradb`
- Backup retention: **7 days**
- Encryption: **Enabled** *(default)*
- Click **Create database**

**Wait ~5 min** for the cluster to become **Available**.

---

**Step 6 — Identify your endpoints**

In the cluster view you will see two endpoints:

| Endpoint | Purpose |
| -------- | ------- |
| **Writer endpoint** | Sends writes to the current primary; auto-updated on failover |
| **Reader endpoint** | Load-balances reads across all Aurora Replicas |

Always connect your application to these cluster endpoints — never to an individual instance endpoint.

**Step 7 — Connect from EC2**
```bash
# SSH into your EC2 instance, then:
mysql -h <writer-endpoint> -u admin -p auroradb
```

Run a quick test:
```sql
CREATE TABLE test (id INT AUTO_INCREMENT PRIMARY KEY, val VARCHAR(50));
INSERT INTO test (val) VALUES ('aurora works');
SELECT * FROM test;
```

---

**Key Aurora-only features to know:**

| Feature | How to enable | When to use |
| ------- | ------------- | ----------- |
| **Aurora Serverless v2** | Instance class → **Serverless** → set min/max ACUs | Dev/test, unpredictable traffic — pay per second |
| **Global Database** | Cluster → **Actions** → **Add Region** | Disaster recovery with < 1 s cross-region replication |
| **Backtrack** | Enable during creation → set window (up to 72 h) | Undo accidental `DROP TABLE` without a full restore |
| **Aurora Replicas** | Cluster → **Add reader** | Scale read traffic; secondary readers auto-promote on failover |
| **Performance Insights** | Monitoring tab | Same as standard RDS — built in at no extra charge for Aurora |

---

**Common mistakes:**

| Mistake | What happens | Fix |
| ------- | ------------ | --- |
| Connecting to instance endpoint instead of cluster endpoint | App connects to old primary after failover | Always use the writer or reader cluster endpoint |
| Choosing `db.t3.micro` for Aurora | Aurora requires at least `db.t3.medium` — creation fails | Use `db.t3.medium` or larger for Aurora clusters |
| Treating Aurora Multi-AZ the same as RDS Multi-AZ | Aurora replication works differently — add Aurora Replicas, not a standby | Add a reader instance; Aurora handles AZ placement automatically |
| Not using the reader endpoint for reads | All traffic hits the writer; reader replicas sit idle | Route `SELECT` queries to the reader endpoint in your connection string |

---

### Reference

**Clean up resources (to avoid charges)**

**Step 1 — Delete the Read Replica (if still running)**
- RDS → `my-rds-db-replica` → **Actions** → **Delete** → skip final snapshot → confirm

**Step 2 — Delete the main RDS instance**
- RDS → `my-rds-db` → **Actions** → **Delete**
- Create final snapshot: **No** *(this is a lab)*
- Type `delete me` to confirm → click **Delete**

**Step 3 — Delete manual snapshots**
- RDS → **Snapshots** → select `my-rds-db-manual-snap-1` → **Actions** → **Delete snapshot**

**Step 4 — Delete the custom parameter group**
- RDS → **Parameter groups** → `my-mysql-params` → **Actions** → **Delete**

**Step 5 — Delete the security group**
- EC2 → **Security Groups** → `rds-sg` → **Actions** → **Delete security groups** → confirm

**Verify:** RDS → **Databases** — no instances listed ✓

---

**Official documentation:**

→ [Amazon RDS — Official AWS Documentation](https://docs.aws.amazon.com/rds/)

→ [RDS User Guide — Getting Started](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.html)

→ [RDS MySQL — Engine Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html)

→ [RDS — Multi-AZ Deployments](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)

→ [RDS — Working with Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)

→ [RDS Performance Insights](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PerfInsights.html)

→ [RDS Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html)

→ [Amazon Aurora — User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html)

→ [Aurora — Comparing Aurora and RDS](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraMySQL.Overview.html)

---

## Useful Tips & Tricks

- _To be filled in._

---

## References

- [AWS Pricing Models — EC2 Pricing](https://aws.amazon.com/ec2/pricing/)
- [AWS Savings Plans — Official Docs](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html)
- [AWS Spot Instances — Official Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html)
- [AWS Dedicated Hosts — Official Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/dedicated-hosts-overview.html)
- [AWS Pricing Calculator](https://calculator.aws/)
- [AWS Cost Explorer — Official Docs](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)
- [AWS Free Tier — Official Page](https://aws.amazon.com/free/)
- [AWS Billing & Cost Management — Free Tier Dashboard](https://console.aws.amazon.com/billing/home#/freetier)
- [AWS Budgets — Official Docs](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)
- [AWS Global Infrastructure — Regions & AZs](https://aws.amazon.com/about-aws/global-infrastructure/)
- [AWS Regional Services List](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)
- [AWS Local Zones — Official Docs](https://docs.aws.amazon.com/local-zones/latest/ug/what-is-aws-local-zones.html)
- [AWS Wavelength — Official Docs](https://docs.aws.amazon.com/wavelength/latest/developerguide/what-is-aws-wavelength.html)
- [AWS Outposts — Official Docs](https://docs.aws.amazon.com/outposts/latest/userguide/what-is-outposts.html)
- [Amazon CloudFront — Edge Locations](https://aws.amazon.com/cloudfront/features/)
- [AWS IAM User Guide — Introduction](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- [AWS IAM — Policy Evaluation Logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)
- [AWS IAM — Security Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [AWS EC2 User Guide — Concepts](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)
- [AWS Lambda Developer Guide — Welcome](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [Elastic Load Balancing — What is Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)
- [Application Load Balancer — User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)
- [Network Load Balancer — User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html)
- [Gateway Load Balancer — User Guide](https://docs.aws.amazon.com/elasticloadbalancing/latest/gateway/introduction.html)
- [ELB — Comparison of Load Balancer Types](https://aws.amazon.com/elasticloadbalancing/features/)
- [AWS Auto Scaling — Documentation Hub](https://docs.aws.amazon.com/autoscaling/)
- [Amazon EC2 Auto Scaling — User Guide](https://docs.aws.amazon.com/autoscaling/ec2/userguide/what-is-amazon-ec2-auto-scaling.html)
- [EC2 Auto Scaling — Launch Templates](https://docs.aws.amazon.com/autoscaling/ec2/userguide/launch-templates.html)
- [EC2 Auto Scaling — Scaling Policies](https://docs.aws.amazon.com/autoscaling/ec2/userguide/scaling-overview.html)
- [EC2 Auto Scaling — Lifecycle Hooks](https://docs.aws.amazon.com/autoscaling/ec2/userguide/lifecycle-hooks.html)
- [EC2 Auto Scaling — Warm Pools](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-warm-pools.html)
- [EC2 Auto Scaling — Predictive Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/ec2-auto-scaling-predictive-scaling.html)
- [Amazon RDS — Official AWS Documentation](https://docs.aws.amazon.com/rds/)
- [RDS User Guide — Getting Started](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.html)
- [RDS MySQL — Engine Documentation](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_MySQL.html)
- [RDS — Multi-AZ Deployments](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html)
- [RDS — Working with Read Replicas](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html)
- [RDS Performance Insights](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PerfInsights.html)
- [RDS Best Practices](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_BestPractices.html)
- [Amazon Aurora — User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html)
- [Aurora — Comparing Aurora and RDS](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.AuroraMySQL.Overview.html)
- [AWS Documentation Home](https://docs.aws.amazon.com/)
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
