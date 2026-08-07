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
  <img src="https://img.shields.io/badge/EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white" alt="EC2">
  <img src="https://img.shields.io/badge/Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white" alt="Cloud">
  <img src="https://img.shields.io/badge/DevOps-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="DevOps">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-6-blue?style=flat-square" alt="Sections">
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
- [AWS Global Infrastructure](#aws-global-infrastructure)
  - [One Shot Revision](#one-shot-revision)
  - [Regions](#regions)
  - [Availability Zones](#availability-zones)
  - [Edge Locations & Points of Presence](#edge-locations--points-of-presence)
  - [Local Zones & Wavelength Zones](#local-zones--wavelength-zones)
  - [AWS Outposts](#aws-outposts)
  - [How to Choose a Region](#how-to-choose-a-region)
- [AWS Free Tier](#aws-free-tier)
  - [One Shot Revision](#one-shot-revision-1)
  - [Free Tier Types](#free-tier-types)
  - [Key Services in the Free Tier](#key-services-in-the-free-tier)
  - [Monitoring Free Tier Usage](#monitoring-free-tier-usage)
  - [Avoiding Unexpected Charges](#avoiding-unexpected-charges)
- [AWS Pricing Models](#aws-pricing-models)
  - [One Shot Revision](#one-shot-revision-2)
  - [On-Demand](#on-demand)
  - [Reserved Instances & Savings Plans](#reserved-instances--savings-plans)
  - [Spot Instances](#spot-instances)
  - [Dedicated Hosts & Dedicated Instances](#dedicated-hosts--dedicated-instances)
  - [Pricing Calculators & Cost Tools](#pricing-calculators--cost-tools)
- [IAM — Identity and Access Management](#iam--identity-and-access-management)
  - [One Shot Revision](#one-shot-revision-3)
  - [IAM Overview](#iam-overview)
  - [IAM Users & Groups](#iam-users--groups)
  - [IAM Roles](#iam-roles)
  - [IAM Policies](#iam-policies)
  - [IAM Best Practices](#iam-best-practices)
- [Elastic Compute Cloud](#elastic-compute-cloud)
  - [One Shot Revision](#one-shot-revision-4)
  - [EC2 Overview](#ec2-overview)
- [AWS Lambda](#aws-lambda)
  - [One Shot Revision](#one-shot-revision-5)
  - [Lambda Overview](#lambda-overview)
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

## Elastic Compute Cloud

Amazon EC2 (Elastic Compute Cloud) provides resizable virtual servers — called **instances** — in the AWS cloud. It's the foundational compute service for most AWS workloads, letting you launch, configure, scale, and terminate machines on demand without owning physical hardware.

### One Shot Revision

| Topic                                 | Short Description                                                       |
| ------------------------------------- | ----------------------------------------------------------------------- |
| [EC2 Overview](#ec2-overview)         | Core EC2 concepts — instances, AMIs, instance types, key pairs, regions |

### EC2 Overview

**Description:** A primer on the building blocks of EC2 — what an instance is, how AMIs and instance types fit together, and how regions, availability zones, security groups, and key pairs shape an EC2 deployment.

**Learn from the official source:**

→ [AWS EC2 Concepts — Official AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html)

**Notes:**

- _To be filled in after reading the official documentation._

---

## AWS Lambda

AWS Lambda is a **serverless compute service** that runs your code in response to events — HTTP requests, queue messages, file uploads, schedules, and more — without you provisioning or managing servers. You upload a function, Lambda handles the runtime, scaling, and availability, and you pay only for the compute time actually consumed.

### One Shot Revision

| Topic                                 | Short Description                                                       |
| ------------------------------------- | ----------------------------------------------------------------------- |
| [Lambda Overview](#lambda-overview)   | Core Lambda concepts — functions, event sources, runtimes, triggers, execution model |

### Lambda Overview

**Description:** A primer on the building blocks of AWS Lambda — what a function is, how event sources and triggers invoke it, supported runtimes, execution environment, concurrency, and how Lambda fits into serverless architectures.

**Learn from the official source:**

→ [AWS Lambda — Official AWS Documentation](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)

**Notes:**

- _To be filled in after reading the official documentation._

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
