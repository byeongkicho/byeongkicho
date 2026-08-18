## Hi, I'm Ki 👋

**Infrastructure Engineer** · growing into **SRE / DevOps**, with an **AIOps** edge · Seoul, Korea

*A social-work → infrastructure career switch. Everything below I've built or operated hands-on — and where something is only code, or only installed, I say so.*

An infra engineer who actually **runs agentic AI in his daily workflow — not just reads about it.** *(Claude Certified Architect – Foundations)*

---

### 🛠 What I do

- 🔧 Hands-on infra & systems ops — HPE/Dell servers, Cisco networking, M365 — for global enterprise clients via a global IT delivery chain. Now automating the repeatable parts.
- ☁️ Cloud / Platform — AWS + EKS provisioned and operated as **Terraform** code, with remote state and **OIDC-authenticated CI** (see ⭐ below)
- 📊 Observability — a custom exporter feeding Grafana Cloud dashboards, alerts, and an **SLO with an error budget** — all managed as code, on a site I actually run
- 🧪 Production automation with DevOps principles — idempotent reconciliation, backoff+jitter retry honoring 429/503, audit logging
- 🤖 Infra × AI — multi-agent (Claude Code) pipelines I run day to day
- 🎓 Social work → IT — I bring an ops-and-people lens to incidents and handoffs, and I learn in public

---

### ⭐ Featured — [smallbiz-cloud-platform](https://github.com/byeongkicho/smallbiz-cloud-platform)

**An AWS EKS platform defined as Terraform code** — VPC / EKS / managed node group / IRSA / RDS — provisioned on my own account, operated, and torn down deliberately for cost control.

- **Remote state** on S3 (versioning · SSE · public-access block) with DynamoDB locking
- **GitHub OIDC** — CI runs `terraform plan` on every PR with **no long-lived AWS keys in the repo**. The trust policy pins `sub` to this repo's `pull_request` and `main` (no wildcards), and the CI role has **no write permissions at all** — not even `s3:PutObject` — so `apply` and state corruption are structurally impossible.
- **Cost forensics from the real bill** — **63% of one month's charges turned out to be EKS extended-support surcharge**, not resource usage. That's money spent on not upgrading, so I pinned the cluster to a standard-support version.
- **A verification table in the README** that separates what was `apply`-verified from what is code-only. Building it flipped two of my own conclusions: a resource *missing from state* that billing proved had run 38 hours, and a component helm reported as `deployed` that had **never actually created anything**. One class of evidence would have gotten both backwards.

> Not in this repo: Karpenter, CloudFront, Container Insights — the README says so explicitly, and ArgoCD / the load balancer controller are marked *installed only*.

---

### 🚀 More projects

| Project | Stack | Proof |
|---|---|---|
| **[Gluten-Free Korea](https://noglutenkorea.com)** | Next.js 15 · Cloudflare · Grafana Cloud | **Live** — 1+ year in production, solo. Custom metrics exporter, dashboard, alerts and SLO, [managed by Terraform](https://github.com/byeongkicho/Gluten-Free_Korea) |
| **[m365-automation-toolkit](https://github.com/byeongkicho/m365-automation-toolkit)** | PowerShell + Graph · idempotent · backoff+jitter (429/503) | 10-user onboarding from ~30 min manual to **under 10 seconds**; intermittent failures (~30%) gone since rollout |
| **[Masters of Ayò](https://github.com/byeongkicho/masters-of-ayo)** | vanilla JS · Canvas · zero runtime deps | Built with a generate→verify multi-agent pipeline (adversarial red-team + invariant test gates) · 92 tests · [play](https://byeongkicho.github.io/masters-of-ayo/) |
| **[Regime Music Societe](https://rmsociete.com)** | React · TypeScript | **Live** — paid client delivery on an ongoing maintenance retainer (Atlanta label) |
| **[Cloud Architecture](https://github.com/byeongkicho/AWS_Architecture001)** | draw.io hybrid diagrams | Design artifact — **not deployed** |

---

### 🎯 Currently

- 📖 Working toward **CKAD**
- 🔜 Next up — a **log axis (Loki)** for the observability stack, and **checkov** static analysis in the Terraform CI

---

### 📌 Open to: **SRE / DevOps / Platform / Cloud / AIOps** — Seoul or Remote

[![LinkedIn](https://img.shields.io/badge/LinkedIn-byeongkicho-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/byeongkicho)
[![Email](https://img.shields.io/badge/byeongkicho%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:byeongkicho@gmail.com)

---

### 📜 Certifications

Claude Certified Architect – Foundations · AWS Solutions Architect Associate · AWS Developer Associate · GCP Associate Cloud Engineer · Oracle OCI Architect Associate · Cisco CCNA · HPE Hybrid Cloud · Azure AZ-900 · Google IT Support — **CKAD in progress**
