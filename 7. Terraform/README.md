<h1 align="center">Terraform Learning Notes</h1>

<p align="center">
  A personal collection of Terraform commands, concepts,<br>
  and notes gathered while learning Infrastructure as Code.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform">
  <img src="https://img.shields.io/badge/HCL-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="HCL">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS">
  <img src="https://img.shields.io/badge/DevOps-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="DevOps">
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
  <a href="../6. Kubernetes/README.md"><b>Kubernetes Notes</b></a>
</p>

---

## Table of Contents

- [Introduction](#introduction)
- [Terraform Commands](#terraform-commands)
- [Terraform Fundamentals](#terraform-fundamentals)
  - [One Shot Revision](#one-shot-revision)
  - [What is Terraform?](#what-is-terraform)
  - [Terraform vs Other IaC Tools](#terraform-vs-other-iac-tools)
  - [How Terraform Works](#how-terraform-works)
  - [HCL Basics](#hcl-basics)
- [Terraform Basics](#terraform-basics)
  - [One Shot Revision](#one-shot-revision-1)
  - [Install Terraform](#install-terraform)
  - [Terraform Workflow](#terraform-workflow)
  - [Providers](#providers)
  - [Resources](#resources)
  - [Variables and Outputs](#variables-and-outputs)
  - [Terraform State](#terraform-state)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction

Brief notes about Terraform — the open-source Infrastructure as Code tool by HashiCorp that lets you define and provision infrastructure using a declarative configuration language.

- **Focus:** Writing, planning, and applying infrastructure configurations with Terraform.
- **Scope:** Providers → Resources → Variables → Outputs → State → Modules → Workspaces.
- **Goal:** Build strong Terraform fundamentals for DevOps interview prep and day-to-day IaC workflows.

**Learn from the official source:**

→ [Terraform Documentation](https://developer.hashicorp.com/terraform/docs)

---

## Terraform Commands

Terraform's primary CLI is `terraform` — it lets you initialize, plan, apply, and destroy infrastructure. Every command follows the pattern `terraform <subcommand> [options]`. Common subcommands: `init`, `plan`, `apply`, `destroy`, `validate`, `fmt`, `show`, `state`.

For the full list of commands and flags, see the **[Terraform CLI Reference →](https://developer.hashicorp.com/terraform/cli/commands)**

---

## Terraform Fundamentals

Before writing any `.tf` file, it helps to build a clear mental picture of what Terraform is, why it exists, and how its core pieces fit together. This section is the "story" behind every command in the rest of the notes.

### One Shot Revision

| Topic | Short Description |
| ----- | ----------------- |
| [What is Terraform?](#what-is-terraform) | Open-source IaC tool that provisions infrastructure declaratively |
| [Terraform vs Other IaC Tools](#terraform-vs-other-iac-tools) | Terraform is cloud-agnostic; CloudFormation is AWS-only; Ansible is config mgmt |
| [How Terraform Works](#how-terraform-works) | Write HCL → Plan changes → Apply changes → State tracks reality |
| [HCL Basics](#hcl-basics) | HashiCorp Configuration Language — blocks, arguments, expressions, and types |

### What is Terraform?

**In one sentence:** Terraform is an open-source Infrastructure as Code tool that lets you define cloud and on-prem resources in human-readable configuration files and manage their full lifecycle.

Without an IaC tool, provisioning infrastructure means clicking through cloud consoles, running ad-hoc CLI commands, or writing fragile shell scripts — all of which are hard to version, review, and repeat. Terraform solves this by declaring the **desired state** of your infrastructure in `.tf` files and reconciling the current state to match.

**Problem → Solution Flow:**

```
Without Terraform:
  New Environment → Manual console clicks → Error-prone, slow
  Config Drift → Unknown differences between envs → Debugging pain
  Team Collaboration → No audit trail → "Who changed what?"

With Terraform:
  New Environment → terraform apply → Infrastructure in minutes
         ↓
  Config Drift → terraform plan → Shows exact diff before any change
         ↓
  Team Collaboration → Git history + state file → Full audit trail
         ↓
  Destroy When Done → terraform destroy → Zero leftover costs
```

**Why it matters for DevOps:**

- **Declarative** — describe what you want, not how to build it. Terraform figures out the order and method.
- **Cloud-agnostic** — one tool for AWS, Azure, GCP, Kubernetes, Datadog, GitHub, and hundreds more via providers.
- **State management** — Terraform tracks what it has built in a state file, enabling safe incremental changes.
- **Plan before apply** — `terraform plan` shows a diff of changes before anything is touched in production.
- **Idempotent** — running `apply` twice with the same config produces the same result; no duplicate resources.

**Name origin:** "Terraform" is a science-fiction term meaning to reshape a planet's environment — fitting for reshaping cloud infrastructure.

---

### Terraform vs Other IaC Tools

Terraform is not the only IaC tool. Understanding where it fits helps you pick the right tool for the job.

**Tool Comparison:**

```
┌─────────────────────────────────────────────────────────────────┐
│                     IaC Tool Landscape                          │
├─────────────────┬───────────────┬───────────────┬──────────────┤
│   Terraform     │ CloudFormation│    Ansible    │    Pulumi    │
│  (HashiCorp)    │    (AWS)      │  (Red Hat)    │   (Pulumi)   │
├─────────────────┼───────────────┼───────────────┼──────────────┤
│ Cloud-agnostic  │ AWS-only      │ Cloud-agnostic│ Cloud-agnostic│
│ Declarative     │ Declarative   │ Procedural    │ Imperative   │
│ HCL language    │ JSON/YAML     │ YAML playbooks│ Python/TS/Go │
│ State file      │ Stack drift   │ No state file │ State file   │
│ Infrastructure  │ Infrastructure│ Config mgmt + │ Infrastructure│
│ provisioning    │ provisioning  │ orchestration │ provisioning  │
└─────────────────┴───────────────┴───────────────┴──────────────┘
```

| Aspect | Terraform | CloudFormation | Ansible |
| ------ | --------- | -------------- | ------- |
| **Scope** | Multi-cloud infrastructure | AWS infrastructure only | Configuration management + infrastructure |
| **Language** | HCL (HashiCorp Config Language) | JSON or YAML | YAML playbooks |
| **Style** | Declarative | Declarative | Procedural |
| **State** | State file (local or remote) | AWS manages stack state | Stateless (checks live system) |
| **Best for** | Provisioning cloud resources across any provider | AWS-native teams who want deep AWS integration | Configuring software on existing servers |
| **Learning curve** | Moderate | Moderate | Low |

**Mental model:** Use Terraform to spin up the cloud resources (VPCs, EC2, RDS); use Ansible to configure the software on top (install Nginx, deploy app). They complement each other.

---

### How Terraform Works

Terraform's core loop is: **Write → Plan → Apply → (repeat) → Destroy**.

**The Terraform Workflow:**

```
┌──────────────────────────────────────────────────────────────┐
│                    Terraform Workflow                        │
│                                                              │
│   1. WRITE                                                   │
│      .tf files define desired state                          │
│      (providers, resources, variables, outputs)              │
│             │                                                │
│             ▼                                                │
│   2. INIT  (terraform init)                                  │
│      Downloads provider plugins                              │
│      Sets up backend for state storage                       │
│             │                                                │
│             ▼                                                │
│   3. PLAN  (terraform plan)                                  │
│      Reads current state file                                │
│      Calls provider APIs to check real infrastructure        │
│      Shows diff: what will be created / changed / destroyed  │
│             │                                                │
│             ▼                                                │
│   4. APPLY (terraform apply)                                 │
│      Executes the plan                                       │
│      Calls cloud APIs to make changes                        │
│      Updates state file to reflect new reality               │
│             │                                                │
│             ▼                                                │
│   5. DESTROY (terraform destroy)  ← when done               │
│      Removes all managed resources                           │
│      Clears state file                                       │
└──────────────────────────────────────────────────────────────┘
```

**Three-Way Reconciliation:**

Terraform always compares three things before making a change:

```
┌──────────────┐     ┌──────────────┐     ┌──────────────────┐
│  .tf config  │     │  State file  │     │  Real cloud infra │
│ (desired)    │ vs  │ (last known) │ vs  │  (actual)         │
└──────────────┘     └──────────────┘     └──────────────────┘
        │                   │                      │
        └───────────────────┴──────────────────────┘
                            │
                     terraform plan
                     (shows the diff)
                            │
                     terraform apply
                     (closes the gap)
```

---

### HCL Basics

HCL (**H**ashiCorp **C**onfiguration **L**anguage) is the language Terraform configuration is written in. It is designed to be both human-readable and machine-parseable.

**File structure:**

```
project/
├── main.tf           ← resource definitions
├── variables.tf      ← input variable declarations
├── outputs.tf        ← output value declarations
├── provider.tf       ← provider configuration
├── terraform.tfvars  ← variable values (not committed)
└── .terraform/       ← downloaded plugins (git-ignored)
```

**Block syntax:**

Every HCL construct is a **block**:

```hcl
<block_type> "<type_label>" "<name_label>" {
  argument = value
}
```

**The four most important block types:**

```hcl
# 1. terraform block — backend and version constraints
terraform {
  required_version = ">= 1.5.0"
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

# 2. provider block — configure a cloud provider
provider "aws" {
  region = "us-east-1"
}

# 3. resource block — declare an infrastructure object
resource "aws_instance" "web_server" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}

# 4. output block — expose values after apply
output "instance_ip" {
  value = aws_instance.web_server.public_ip
}
```

**HCL data types:**

| Type | Example |
| ---- | ------- |
| `string` | `"us-east-1"` |
| `number` | `3`, `1.5` |
| `bool` | `true`, `false` |
| `list` | `["a", "b", "c"]` |
| `map` | `{ key = "value" }` |
| `object` | `{ name = string, age = number }` |

**References and expressions:**

```hcl
# Reference another resource's attribute
subnet_id = aws_subnet.main.id

# Use a variable
instance_type = var.instance_type

# String interpolation
name = "server-${var.environment}"

# Conditional expression
instance_type = var.environment == "prod" ? "t3.large" : "t3.micro"
```

---

## Terraform Basics

Hands-on foundation — from installing Terraform to managing your first resource. Every concept from the Fundamentals section becomes concrete here.

### One Shot Revision

| Topic | Short Description |
| ----- | ----------------- |
| [Install Terraform](#install-terraform) | Install the Terraform CLI on macOS, Linux, or Windows |
| [Terraform Workflow](#terraform-workflow) | `init` → `plan` → `apply` → `destroy` — the core four commands |
| [Providers](#providers) | Plugins that talk to cloud APIs; must be declared and initialized |
| [Resources](#resources) | The building blocks of infrastructure — EC2, S3, VPC, and more |
| [Variables and Outputs](#variables-and-outputs) | Pass values in with variables; expose values out with outputs |
| [Terraform State](#terraform-state) | How Terraform tracks what it has built — local vs remote state |

### Install Terraform

**Install Terraform CLI:**

```
┌─────────────────────────────────────┐
│  Choose Your Platform               │
├─────────────────────────────────────┤
│                                     │
├─ macOS (Homebrew)                   │
│  └─ brew tap hashicorp/tap          │
│     └─ brew install hashicorp/tap/terraform │
│                                     │
├─ Linux (apt)                        │
│  └─ Add HashiCorp GPG key & repo    │
│     └─ apt-get install terraform    │
│                                     │
├─ Any OS (binary download)           │
│  └─ Download zip from releases page │
│     └─ Unzip and move to PATH       │
│                                     │
└─────────────────────────────────────┘
```

**macOS:**

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

**Linux (Ubuntu/Debian):**

```bash
wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
  https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
  sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update && sudo apt install terraform
```

**Verify installation:**

```bash
terraform version
# Terraform v1.x.x
# on linux_amd64
```

---

### Terraform Workflow

The four core commands make up every Terraform operation.

**Core Workflow Flow:**

```
Write .tf files
      │
      ▼
terraform init
  ├─ Downloads provider plugins into .terraform/
  ├─ Sets up backend (where state is stored)
  └─ Run once per project, or when providers change
      │
      ▼
terraform plan
  ├─ Reads .tf files + state file
  ├─ Calls provider APIs to check current reality
  ├─ Prints what will be (+) created, (~) changed, (-) destroyed
  └─ Safe to run anytime — makes NO changes
      │
      ▼
terraform apply
  ├─ Shows plan output, asks for confirmation
  ├─ Creates/updates/destroys resources via provider APIs
  └─ Updates state file to reflect new reality
      │
      ▼
terraform destroy   ← when you want to tear everything down
  ├─ Shows destruction plan, asks for confirmation
  └─ Deletes all resources managed by this config
```

**`terraform init`**

Prepares the working directory. Must be the first command you run.

```bash
terraform init
```

**`terraform validate`**

Checks your `.tf` files for syntax errors without contacting any APIs.

```bash
terraform validate
# Success! The configuration is valid.
```

**`terraform fmt`**

Formats `.tf` files to the canonical style. Run before committing.

```bash
terraform fmt           # format files in the current directory
terraform fmt -recursive  # format all subdirectories too
```

**`terraform plan`**

Shows a preview of changes. Use the `-out` flag to save the plan for a later apply.

```bash
terraform plan
terraform plan -out=tfplan        # save plan to a file
terraform plan -var="env=prod"    # override a variable
```

**Reading plan output:**

```
+ resource "aws_instance" "web_server"    ← will be CREATED
~ resource "aws_security_group" "main"    ← will be UPDATED in-place
- resource "aws_s3_bucket" "old"          ← will be DESTROYED
-/+ resource "aws_instance" "db"          ← will be DESTROYED then re-created
```

**`terraform apply`**

Executes the plan. Use `-auto-approve` only in CI/CD pipelines.

```bash
terraform apply                   # interactive — shows plan, asks for yes/no
terraform apply tfplan             # apply a saved plan (no confirmation needed)
terraform apply -auto-approve      # skip confirmation (use with care)
terraform apply -var="env=prod"    # pass a variable
```

**`terraform destroy`**

Destroys all infrastructure managed by the current configuration.

```bash
terraform destroy                  # interactive — shows destruction plan, asks for yes/no
terraform destroy -auto-approve    # skip confirmation
terraform destroy -target=aws_instance.web_server   # destroy a specific resource only
```

---

### Providers

Providers are plugins that give Terraform the ability to interact with specific APIs — AWS, Azure, GCP, GitHub, Kubernetes, and hundreds more.

**Provider Architecture:**

```
Your .tf config
      │
      ▼
Terraform Core
      │
      │  provider "aws" { ... }
      ▼
┌─────────────────┐
│  AWS Provider   │  ← downloaded during terraform init
│  (plugin)       │
└────────┬────────┘
         │  API calls (AWS SDK)
         ▼
   AWS Cloud APIs
   (EC2, S3, RDS, VPC, ...)
```

**Declaring a provider:**

```hcl
# provider.tf

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"   # registry.terraform.io/hashicorp/aws
      version = "~> 5.0"          # any 5.x version
    }
  }
}

provider "aws" {
  region = "us-east-1"
}
```

**Provider authentication (AWS):**

Terraform uses the same credential chain as the AWS CLI:

```bash
# Option 1: environment variables (recommended for CI/CD)
export AWS_ACCESS_KEY_ID="AKIAIOSFODNN7EXAMPLE"
export AWS_SECRET_ACCESS_KEY="wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"

# Option 2: AWS CLI config (~/.aws/credentials) — works automatically
aws configure

# Option 3: IAM role (best for EC2/ECS/Lambda — no keys needed)
# Terraform picks up the instance/task role automatically
```

**Multiple providers (e.g., multi-region):**

```hcl
provider "aws" {
  region = "us-east-1"
  alias  = "us_east"
}

provider "aws" {
  region = "eu-west-1"
  alias  = "eu_west"
}

resource "aws_instance" "us_server" {
  provider      = aws.us_east
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
```

---

### Resources

Resources are the most important building block in Terraform. Each resource block describes one infrastructure object.

**Resource Block Anatomy:**

```hcl
resource "<provider>_<type>" "<local_name>" {
  # arguments configure the resource
  argument = value
}
```

```
resource "aws_instance" "web_server" {
    │           │             │
    │           │             └── local name — used to reference this resource
    │           └────────────── resource type — aws_instance from the AWS provider
    └────────────────────────── "resource" keyword
```

**Common AWS resources:**

```hcl
# EC2 instance
resource "aws_instance" "web_server" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  tags = {
    Name        = "web-server"
    Environment = "dev"
  }
}

# S3 bucket
resource "aws_s3_bucket" "assets" {
  bucket = "my-assets-bucket-2024"

  tags = {
    Environment = "dev"
  }
}

# VPC
resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true

  tags = {
    Name = "main-vpc"
  }
}

# Security group
resource "aws_security_group" "web" {
  name   = "web-sg"
  vpc_id = aws_vpc.main.id    # reference to another resource

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

**Resource references (implicit dependencies):**

When one resource references another, Terraform automatically creates a dependency and applies them in the correct order:

```hcl
resource "aws_subnet" "main" {
  vpc_id     = aws_vpc.main.id       # depends on aws_vpc.main
  cidr_block = "10.0.1.0/24"
}

resource "aws_instance" "web" {
  subnet_id = aws_subnet.main.id     # depends on aws_subnet.main
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}

# Terraform builds: vpc → subnet → instance (correct order)
```

**Explicit dependency (`depends_on`):**

Use when the dependency isn't expressed through attribute references:

```hcl
resource "aws_instance" "app" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  depends_on = [aws_iam_role_policy.app_policy]
}
```

---

### Variables and Outputs

Variables parameterize your configuration; outputs expose values after apply.

**Variables:**

```hcl
# variables.tf

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}

variable "environment" {
  description = "Deployment environment"
  type        = string
  # no default — must be provided
}

variable "allowed_cidrs" {
  description = "List of CIDRs allowed to access the instance"
  type        = list(string)
  default     = ["10.0.0.0/8"]
}
```

**Providing variable values:**

```bash
# 1. terraform.tfvars file (auto-loaded)
environment   = "dev"
instance_type = "t3.micro"

# 2. Command-line flag
terraform apply -var="environment=prod"

# 3. Environment variable (TF_VAR_ prefix)
export TF_VAR_environment=prod
terraform apply

# 4. Interactive prompt — if no value is provided, Terraform asks
```

**Using variables in config:**

```hcl
# main.tf

resource "aws_instance" "app" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = var.instance_type     # reference with var.<name>

  tags = {
    Environment = var.environment
  }
}
```

**Outputs:**

Outputs expose values after `apply` — useful for consuming values in scripts or passing them between Terraform modules.

```hcl
# outputs.tf

output "instance_public_ip" {
  description = "Public IP of the web server"
  value       = aws_instance.app.public_ip
}

output "instance_id" {
  description = "EC2 instance ID"
  value       = aws_instance.app.id
}

output "s3_bucket_name" {
  description = "Name of the S3 bucket"
  value       = aws_s3_bucket.assets.id
  sensitive   = false
}

# Mark sensitive outputs — Terraform won't print them in plain text
output "db_password" {
  value     = random_password.db.result
  sensitive = true
}
```

**Viewing outputs:**

```bash
terraform output                        # show all outputs
terraform output instance_public_ip     # show a specific output
terraform output -json                  # output in JSON (useful for scripting)
```

---

### Terraform State

The state file (`terraform.tfstate`) is Terraform's record of what infrastructure it has built. It maps your `.tf` configuration to the real resources in the cloud.

**Why state matters:**

```
.tf config            State file            Real Cloud
(desired)        ←→  (last known)  ←→      (actual)

terraform plan reads all three and shows the diff.
terraform apply closes the gap and updates the state.
```

**State file basics:**

```bash
terraform show                    # human-readable view of current state
terraform state list              # list all resources in state
terraform state show aws_instance.web_server   # show state for one resource
```

**State file location:**

By default, the state file is stored locally as `terraform.tfstate`. This works for solo projects but is dangerous for teams (no locking, no sharing).

**Remote state (recommended for teams):**

Store state in S3 + DynamoDB for locking:

```hcl
# backend.tf

terraform {
  backend "s3" {
    bucket         = "my-terraform-state-bucket"
    key            = "project/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "terraform-locks"     # for state locking
    encrypt        = true
  }
}
```

**State operations:**

```bash
# Move a resource to a new address (after renaming in config)
terraform state mv aws_instance.old_name aws_instance.new_name

# Remove a resource from state without destroying it
# (use when you want Terraform to stop managing something)
terraform state rm aws_instance.web_server

# Import existing infrastructure into state
# (use when you have resources that were created outside Terraform)
terraform import aws_instance.web_server i-1234567890abcdef0
```

**Important notes:**

- **Never edit the state file manually** — use `terraform state` commands.
- **Always use remote state** when working in a team — prevents concurrent apply conflicts.
- **State contains secrets** — store it encrypted and restrict access (IAM policies on S3).
- **Back up state** — enable versioning on the S3 bucket used for state storage.

---

## Conclusion

Terraform is the industry-standard tool for provisioning infrastructure across any cloud provider using a declarative, version-controlled workflow. This section covers the mental model needed before writing a single `.tf` file.

**The Complete Terraform Story:**

```
┌──────────────────────────────────────────────────────────────┐
│  Developer / DevOps Engineer                                 │
│  terraform apply                                             │
└─────────────────┬────────────────────────────────────────────┘
                  │
                  ▼
        ┌─────────────────────┐
        │  Terraform Core     │
        ├─────────────────────┤
        │  Reads .tf files    │
        │  Compares state     │
        │  Builds dep graph   │
        │  Calls providers    │
        └──────────┬──────────┘
                   │
        ┌──────────┴───────────────────┐
        │                              │
        ▼                              ▼
┌───────────────┐              ┌───────────────┐
│  AWS Provider │              │  Azure/GCP/   │
│  ├─ EC2       │              │  Other        │
│  ├─ S3        │              │  Providers    │
│  ├─ VPC       │              └───────────────┘
│  ├─ RDS       │
│  └─ IAM       │
└───────┬───────┘
        │  API calls
        ▼
  Real Cloud Resources
  (Created / Updated / Destroyed)
        │
        ▼
  State File Updated
  (terraform.tfstate)
```

**Key takeaways so far:**

- Terraform declares **desired state** in `.tf` files and continuously reconciles the cloud to match it.
- The `init → plan → apply` workflow ensures changes are **reviewed before they happen**.
- **Providers** are the bridge between Terraform and cloud APIs — each provider covers one platform.
- **Resources** are the building blocks; **variables** parameterize them; **outputs** expose their values.
- **State** is Terraform's memory — keep it safe, remote, and encrypted.

More sections (Modules, Workspaces, Data Sources, Locals, Dynamic Blocks, Provisioners, Terraform Cloud) will be added here as they are completed.

---

## References

- [Terraform Documentation](https://developer.hashicorp.com/terraform/docs)
- [Terraform CLI Commands](https://developer.hashicorp.com/terraform/cli/commands)
- [Terraform Registry](https://registry.terraform.io/)
- [AWS Provider Docs](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
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
