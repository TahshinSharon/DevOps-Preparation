<h1 align="center">Cloud Engineering Learning Notes</h1>

<p align="center">
  A personal collection of Cloud Engineering services, concepts,<br>
  and notes gathered while learning.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white" alt="AWS">
  <img src="https://img.shields.io/badge/IAM-DD344C?style=for-the-badge&logo=amazonaws&logoColor=white" alt="IAM">
  <img src="https://img.shields.io/badge/EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white" alt="EC2">
  <img src="https://img.shields.io/badge/Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white" alt="Cloud">
  <img src="https://img.shields.io/badge/DevOps-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="DevOps">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Sections-3-blue?style=flat-square" alt="Sections">
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
- [IAM — Identity and Access Management](#iam--identity-and-access-management)
  - [One Shot Revision](#one-shot-revision)
  - [IAM Overview](#iam-overview)
  - [IAM Users & Groups](#iam-users--groups)
  - [IAM Roles](#iam-roles)
  - [IAM Policies](#iam-policies)
  - [IAM Best Practices](#iam-best-practices)
- [Elastic Compute Cloud](#elastic-compute-cloud)
  - [One Shot Revision](#one-shot-revision-1)
  - [EC2 Overview](#ec2-overview)
- [AWS Lambda](#aws-lambda)
  - [One Shot Revision](#one-shot-revision-2)
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
