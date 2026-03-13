<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:161b27,100:1f6feb&height=200&section=header&text=Sarthak%20Singh&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Cloud%20%26%20DevOps%20Engineer&descAlignY=57&descSize=20&descColor=58A6FF" width="100%"/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=18&pause=1200&color=58A6FF&center=true&vCenter=true&width=700&lines=VM+Infrastructure+%E2%86%92+Kubernetes+%E2%86%92+Production+CI%2FCD;AWS+%7C+Kubernetes+%7C+Terraform+%7C+Helm+%7C+Jenkins;Built+from+Scratch.+Not+from+Tutorials.;2nd+Year+BTech+%E2%86%92+Production-Grade+EKS+Deployments;Depth+over+Breadth.+Internals+over+Interfaces." alt="Typing SVG" />

<br/><br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarthak-singh-a0aa62322)
[![GitHub followers](https://img.shields.io/github/followers/Sarthakx67?style=for-the-badge&color=58A6FF&labelColor=0d1117&logo=github&label=Follow)](https://github.com/Sarthakx67)
[![Profile Views](https://komarev.com/ghpvc/?username=Sarthakx67&style=for-the-badge&color=1f6feb&label=PROFILE+VIEWS)](https://github.com/Sarthakx67)

</div>

---

## `$ whoami`

```yaml
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│   name:        Sarthak Singh                                     │
│   role:        Cloud & DevOps Engineering Student                │
│   degree:      BTech Computer Engineering  —  2nd Year           │
│   location:    India                                             │
│                                                                  │
│   philosophy: >                                                  │
│     "I don't want to know how to use the tools.                  │
│      I want to know what happens when they fail."                │
│                                                                  │
│   journey:     VM Infrastructure → Kubernetes → Production CI/CD │
│   goal:        Cloud / DevOps Architect. Systems-focused.        │
│   status:      Open to DevOps / Cloud Engineering Internship     │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

---

## 🗺️ My Engineering Journey

> Everything below was built in sequence. Each project taught me something the previous one couldn't.

```
PHASE 1 — Learn infrastructure the hard way
    RoboShop on EC2 + ALB  →  15 Terraform modules, VMs, ASGs, security groups

PHASE 2 — Build reusable, modular IaC
    Terraform VPC Module  →  Reusable across projects, dual testing/prod mode

PHASE 3 — Move to container orchestration
    Kubernetes Lab  →  Every resource type, every concept, hands-on manifests

PHASE 4 — Production Kubernetes
    Retail Store on EKS  →  Helm umbrella charts, IRSA, HPA, StatefulSets, observability

PHASE 5 — Automate everything
    Jenkins Shared Library  →  One pipeline to rule all microservices, all languages
```

---

## 🏗️ Projects

---

### 🔴 RoboShop — VM-Based Multi-Environment AWS Infrastructure

<!-- ⚠️  Replace YOUR-ROBOSHOP-REPO-NAME below with your actual repo name -->
[![Repo](https://img.shields.io/badge/RoboShop-Infra-Standard-181717?style=flat-square&logo=github)](https://github.com/Sarthakx67/RoboShop-Infra-Standard.git)
[![Terraform VPC Module](https://img.shields.io/badge/Module-Terraform--AWS--VPC--Advanced-7B42BC?style=flat-square&logo=terraform)](https://github.com/Sarthakx67/Terraform-AWS-VPC-Advanced)
[![Security Group Module](https://img.shields.io/badge/Module-RoboShop--Security--Group--Module-7B42BC?style=flat-square&logo=terraform)](https://github.com/Sarthakx67/RoboShop-Security-Group-Module)
[![Ansible Roles](https://img.shields.io/badge/Ansible-RoboShop--Ansible--Roles-EE0000?style=flat-square&logo=ansible)](https://github.com/Sarthakx67/RoboShop-Ansible-Roles-tf)
[![Shell Scripts](https://img.shields.io/badge/Scripts-RoboShop--Shell--Scripts-4EAA25?style=flat-square&logo=gnu-bash)](https://github.com/Sarthakx67/RoboShop-Shell-Script-For-Alma-Linux)

> **The foundation.** Before touching Kubernetes, I built the entire platform the hard way — EC2, ALBs, ASGs, Ansible — across DEV and PROD using 15 separate Terraform modules. This is where I learned why infrastructure needs to be code, not clicks.

<table>
<tr><td width="50%" valign="top">

**Infrastructure (15 Terraform Modules)**
- Custom VPC module across 2 AZs — public, private, database subnets
- **13 security groups** — least-privilege rules, service-to-service on exact ports, VPN-only SSH
- Remote S3 backend + DynamoDB state locking across all modules
- SSM Parameter Store for cross-module data passing — zero hardcoded values

**Compute & Deployment**
- **AMI baking pipeline** — EC2 → Ansible configure → stop → bake AMI → delete → Launch Template → ASG
- Auto Scaling Groups with 50% CPU target tracking policy
- Internal ALB with host-header routing to each microservice
- External ALB + Route53 on custom domain `stallions.space`

</td><td width="50%" valign="top">

**Databases & Services**
- MongoDB, Redis, MySQL, RabbitMQ — each isolated in database subnet
- Separate security group per database — only the correct service can reach it
- DNS records per service via Route53

**Configuration Management**
- Ansible via **ansible-pull model** — instances pull their own config at boot
- No push model, no manual SSH, no configuration drift

**CI Pipeline (Catalogue Service)**
- Jenkins pipeline — version detection from `package.json`, npm build
- SonarQube code quality scan, SAST security scan
- Nexus artifact publish, downstream CD trigger with version parameter
- *Built for catalogue as proof of concept — full multi-service CI/CD in Retail Store below*

</td></tr>
</table>

**Stack:** `Terraform` `Ansible` `Jenkins` `AWS EC2/ALB/ASG/Route53/SSM` `AlmaLinux`

---

### 🔵 Terraform AWS VPC Module — Reusable Infrastructure Building Block

[![Repo](https://img.shields.io/badge/GitHub-Terraform--AWS--VPC--Advanced-181717?style=flat-square&logo=github)](https://github.com/Sarthakx67/Terraform-AWS-VPC-Advanced)

> **Extracted the VPC into its own reusable module** after building RoboShop. This module is what the RoboShop infrastructure and Retail Store both pull from. It taught me the difference between writing Terraform and writing *good* Terraform.

<table>
<tr><td width="50%" valign="top">

**What Makes It Actually Reusable**
- **Dual-mode design** — testing mode uses IGW for all subnets (zero cost), production mode uses NAT Gateway. Switch with a variable
- **Region-agnostic** — uses `data "aws_availability_zones"` + `slice()` to pick 2 AZs in any region automatically
- **Input validation** — `validation` block enforces exactly 2 CIDR blocks per subnet tier, fails with a clear error before touching AWS

</td><td width="50%" valign="top">

**Technical Depth**
- `count` + `count.index` for creating 2 subnets from one resource block
- VPC Peering — conditional via ternary, adds routes to all 4 route tables automatically
- DB Subnet Group created automatically for RDS multi-AZ
- `merge()` for layered tagging — common tags + resource-specific tags
- NAT Gateway commented out by default — `$0/month for dev`, uncomment for production

</td></tr>
</table>

**Stack:** `Terraform` `AWS VPC/Subnets/IGW/NAT/Route Tables/VPC Peering`

---

### ⚪ Kubernetes Manifests Lab — Full Resource Coverage

<!-- ⚠️  Replace YOUR-K8S-REPO-NAME below with your actual repo name -->
[![Repo](https://img.shields.io/badge/K8-resources-181717?style=flat-square&logo=github)](https://github.com/Sarthakx67/K8-resources.git)

> **Before deploying on EKS, I built every Kubernetes resource type manually** — not to follow a tutorial, but to understand what I was actually deploying. Every manifest includes comments explaining *why* the resource is designed that way, not just what it does.

<details>
<summary><b>Full coverage — click to expand</b></summary>

<br/>

| Category | Resources Covered |
|---|---|
| **Workloads** | Pod, Multi-container Pod, Deployment, ReplicaSet, StatefulSet, DaemonSet |
| **Config & Secrets** | ConfigMap (key-ref + envFrom), Secrets (individual + bulk), Labels, Annotations |
| **Networking** | ClusterIP, NodePort, LoadBalancer — named ports, targetPort by name |
| **Storage** | emptyDir (Nginx + Filebeat sidecar), HostPath (Fluentd DaemonSet), EBS Static PV/PVC, EBS Dynamic StorageClass, EFS Static PV/PVC, EFS Dynamic with Access Points |
| **Scaling** | Resource requests/limits, HPA with CPU utilization target |
| **Patterns** | Sidecar logging (Nginx + Filebeat sharing emptyDir), Node-level log collection (Fluentd DaemonSet + hostPath) |

</details>

**What I documented that most people skip:** Why `ReadWriteMany` should be EFS not EBS. Why `WaitForFirstConsumer` prevents cross-AZ attachment failures. Why a headless service is required for StatefulSets. Why `targetPort` by name beats targetPort by number.

**Stack:** `Kubernetes` `AWS EBS CSI` `AWS EFS CSI` `Filebeat` `Fluentd`

---

### 🟢 AWS Retail Store — EKS Production Deployment

[![Repo](https://img.shields.io/badge/GitHub-retail--store--aws--deployment-181717?style=flat-square&logo=github)](https://github.com/Sarthakx67/retail-store-aws-deployment)
<!-- ⚠️  Replace YOUR-SHARED-LIBRARY-REPO below with your actual Jenkins shared library repo name -->
[![Shared Library](https://img.shields.io/badge/Jenkins-Shared--Library-D24939?style=flat-square&logo=jenkins)](https://github.com/Sarthakx67/YOUR-SHARED-LIBRARY-REPO)

> **The flagship project.** Everything learned building RoboShop on VMs, rebuilt properly on Kubernetes — with full observability, zero static credentials, and a CI/CD pipeline that handles every microservice in every language from a single shared library.

<table>
<tr><td width="50%" valign="top">

**Helm Architecture**
- **Umbrella chart with 10 subcharts** — cart, catalog, checkout, orders, ui, mysql, postgresql, rabbitmq, redis, dynamodb
- Environment-specific values files — dev uses local DynamoDB + static creds, prod uses AWS DynamoDB + IRSA
- `_helpers.tpl` for health probe templates — defined once, used across all services
- StorageClass defined inside the chart — self-contained, no cluster pre-setup needed

**Security — IRSA Fully Implemented**
- OIDC provider enabled on EKS cluster
- Trust policy with exact `system:serviceaccount` condition — scoped to one service account
- IAM policy scoped to specific DynamoDB table ARN — not account-wide
- ServiceAccount annotated with `eks.amazonaws.com/role-arn`
- **Zero static AWS credentials anywhere in the cluster**
- Verified by checking `AWS_ROLE_ARN` + `AWS_WEB_IDENTITY_TOKEN_FILE` in pod env

</td><td width="50%" valign="top">

**Kubernetes Architecture**
- StatefulSets with EBS dynamic provisioning for MySQL and PostgreSQL
- `volumeClaimTemplates` — each replica gets its own EBS volume, not a shared PVC
- HPA on all 5 application services at 70% CPU target
- Health probes (startup + liveness + readiness) — **reduced deploy time 12 min → 1.5 min**
- EBS CSI driver + gp3 StorageClass with `WaitForFirstConsumer`

**CI/CD — Jenkins Shared Library**
- `detectVersion()` — reads `pom.xml` for Java, `main.go` for Go, `package.json` for Node
- `dockerBuildPush()` — builds image, pushes to DockerHub with version tag
- `deployK8s()` — helm upgrade with environment-specific values file
- One shared library handles all 5 services across 3 languages

**Observability**
- Prometheus kube-prometheus-stack with ServiceMonitor per service
- Grafana dashboards — 5xx error rate, CPU, JVM memory, requests/second
- Health endpoints: `/actuator/health/liveness`, `/actuator/health/readiness`, `/health`, `/metrics`

</td></tr>
</table>

**Stack:** `AWS EKS` `Helm` `Jenkins Shared Library` `IRSA` `Prometheus` `Grafana` `EBS CSI` `Docker` `Terraform`

---

### 🟢 Shell Scripts Arsenal — Production Bash Automation

[![Repo](https://img.shields.io/badge/Shell--Script-181717?style=flat-square&logo=github)](https://github.com/Sarthakx67/shell-script.git)

> Not toy scripts. Built with the same patterns used in production — structured logging, exit code validation, root checks, and the `VALIDATE()` function pattern across every script.

```bash
VALIDATE(){
    if [ $1 -ne 0 ]; then
        echo -e "$R $2 ... FAILURE $N" && exit 1
    else
        echo -e "$G $2 ... SUCCESS $N"
    fi
}
```

**Scripts built:** Automated system info reporter (continuous loop + file output) · Disk usage monitor with threshold alerting · Bulk package installer with dependency checking · Log rotation with `find -mtime` · Automated Git push with directory validation · Connectivity checker · Root user validation

**Stack:** `Bash` `Linux` `Systemd` `Git`

---

## 🛠️ Full Tech Stack

<div align="center">

| Layer | Technologies |
|---|---|
| ☁️ **Cloud** | ![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazon-aws&logoColor=white) EKS · VPC · IAM · ALB · ASG · EC2 · EBS · EFS · DynamoDB · Route53 · SSM · S3 |
| 🐳 **Containers** | ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Helm](https://img.shields.io/badge/Helm-0F1689?style=flat-square&logo=helm&logoColor=white) Umbrella Charts · IRSA · StatefulSets · HPA |
| 🏗️ **IaC** | ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white) Reusable Modules · Remote State · SSM Integration · Dual-mode VPC |
| ⚙️ **Config Mgmt** | ![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white) ansible-pull · Roles · Zero push model |
| 🔄 **CI/CD** | ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white) Shared Libraries · Nexus · SonarQube · Multi-language version detection |
| 📊 **Observability** | ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white) ServiceMonitors · Custom Dashboards · PromQL |
| 🐧 **OS & Scripting** | ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white) AlmaLinux · Ubuntu |
| 💻 **Languages** | ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) Go · Node.js · Python (reading/debugging) |
| 🔁 **VCS** | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) |

</div>

---

## 📊 GitHub Stats

<div align="center">

<img width="49%" src="https://github-readme-stats.vercel.app/api?username=Sarthakx67&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58A6FF&icon_color=1f6feb&text_color=c9d1d9&count_private=true&include_all_commits=true" />
<img width="49%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sarthakx67&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58A6FF&text_color=c9d1d9&langs_count=8" />

<br/>

<img width="65%" src="https://github-readme-streak-stats.herokuapp.com?user=Sarthakx67&theme=tokyonight&hide_border=true&background=0d1117&ring=58A6FF&fire=FF6B6B&currStreakLabel=58A6FF" />

</div>

---

## 📌 Honest Status

```
PRODUCTION-READY ───────────────────────────────────────────────────────

  ✅  Multi-env VM infrastructure — 15 Terraform modules, full AWS stack
  ✅  Reusable Terraform VPC module — dual mode, region-agnostic, validated
  ✅  EKS production deployment — Helm umbrella, 10 subcharts, multi-env values
  ✅  IRSA — full OIDC chain, scoped IAM, zero static credentials
  ✅  Jenkins shared library — multi-language, multi-service, single codebase
  ✅  StatefulSets + EBS dynamic provisioning — MySQL and PostgreSQL
  ✅  HPA + health probes — 12 min → 1.5 min deployment time
  ✅  Prometheus + Grafana — ServiceMonitors, custom dashboards

ACTIVELY LEARNING ──────────────────────────────────────────────────────

  🔄  Linux internals — cgroups, namespaces, process model, OOM killer
  🔄  Networking — TCP, DNS resolution chain, k8s packet path through CNI
  🔄  PromQL + AlertManager — from dashboards to actual SLOs and alert rules

NEXT BUILDS ────────────────────────────────────────────────────────────

  ⏳  External Secrets Operator — replace plaintext passwords with ESO + IRSA
  ⏳  NetworkPolicies — pod-level security mirroring existing SG rules
  ⏳  ArgoCD — pull-based deployment replacing Jenkins CD
  ⏳  Terraform CI — tflint + checkov + GitHub Actions on every PR
  ⏳  Trivy image scanning in Jenkins pipeline
```

---

## 💡 Why My Work Is Different

Most students who "know Kubernetes" have run `kubectl apply` on a tutorial manifest. Here is what I have actually done differently.

**On IRSA:** I did not copy-paste a blog post. I enabled the OIDC provider, wrote the trust policy with the service account condition, scoped the IAM policy to a specific table ARN, annotated the ServiceAccount, and verified it by exec-ing into the pod and checking `env | grep AWS`. I know it works because I know why it works.

**On the VPC module:** I wrote a module that other modules consume. It has input validation, dual deployment modes, and is region-agnostic. When I call it from RoboShop and call it again from a new project, I do not copy-paste Terraform — I reference the same tested module.

**On the Jenkins shared library:** I did not write a Jenkinsfile per service. I wrote three reusable Groovy functions that handle version detection for Maven, Go, and Node — then one pipeline definition that every service calls. When the deployment process changes, I change it once.

**On health probes:** I did not add them because a tutorial said to. I added them, measured the deploy time, watched it drop from 12 minutes to 1.5 minutes, and understood why. The startup probe is what made the difference — Kubernetes was killing pods before they finished connecting to databases.

---

<div align="center">

<br/>

*2nd Year BTech · Building production infrastructure · Seeking DevOps Internship*

<br/>

[![LinkedIn](https://img.shields.io/badge/Let's_Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarthak-singh-a0aa62322)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1f6feb,100:0d1117&height=100&section=footer" width="100%"/>

</div>
