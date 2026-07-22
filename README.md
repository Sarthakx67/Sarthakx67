<div align="center">

<!-- Header - uses demolab which is stable and maintained -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&pause=99999&color=FFFFFF&center=true&vCenter=true&width=500&height=70&lines=Sarthak+Singh" alt="Sarthak Singh" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=18&pause=1200&color=58A6FF&center=true&vCenter=true&width=700&lines=VM+Infrastructure+%E2%86%92+Kubernetes+%E2%86%92+Production+CI%2FCD;CKA+%7C+AWS+%7C+Kubernetes+%7C+Terraform+%7C+Helm+%7C+Jenkins;Hands-on+projects+built+from+first+principles.;BTech+Student+%E2%86%92+Production-Grade+EKS+Deployments;Depth+over+Breadth.+Internals+over+Interfaces." alt="Typing SVG" />

<br/><br/>

[![CKA](https://img.shields.io/badge/Certified%20Kubernetes%20Administrator-CKA-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)](https://www.credly.com/org/the-linux-foundation/badge/certified-kubernetes-administrator-cka)

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarthak-singh-a0aa62322)
[![GitHub followers](https://img.shields.io/github/followers/Sarthakx67?style=for-the-badge&color=58A6FF&labelColor=0d1117&logo=github&label=Follow)](https://github.com/Sarthakx67)
[![Profile Views](https://komarev.com/ghpvc/?username=Sarthakx67&style=for-the-badge&color=1f6feb&label=PROFILE+VIEWS)](https://github.com/Sarthakx67)

</div>

<br/>

[![Portfolio](https://img.shields.io/badge/Portfolio-sarthakx67.github.io-58A6FF?style=for-the-badge&logo=githubpages&logoColor=white)](https://sarthakx67.github.io/)

*Personal portfolio featuring DevOps projects, certifications, technical skills, and achievements.*

---

## `$ whoami`

```yaml
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│   name:        Sarthak Singh                                     │
│   role:        Cloud & DevOps Engineer | Certified Kubernetes    │
│                 Administrator (CKA)                              │
│   degree:      BTech Computer Engineering                        │
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

## 📜 Certifications

- ✅ Certified Kubernetes Administrator (CKA)
- 📖 AWS Certified Solutions Architect – Associate (In Progress)

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

### 🟢 AWS Retail Store — EKS Production Deployment

<div align="center">

| Repository | Description |
|---|---|
| [**📁 retail-store-aws-deployment**](https://github.com/Sarthakx67/retail-store-aws-deployment) | Main EKS deployment — Helm umbrella charts, IRSA, observability |
| [**🔄 retail-store-Jenkins-shared-library**](https://github.com/Sarthakx67/retail-store-Jenkins-shared-library) | Jenkins shared library — multi-language CI/CD for all services |

</div>

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

### 🔴 RoboShop — VM-Based Multi-Environment AWS Infrastructure

<div align="center">

| Repository | Description |
|---|---|
| [**📁 RoboShop-Infra-Standard**](https://github.com/Sarthakx67/RoboShop-Infra-Standard) | Main infrastructure — Terraform modules, Jenkins CI/CD |
| [**🐚 Roboshop-Dev-Prod-Infra-CICD-Deployment**](https://github.com/Sarthakx67/Roboshop-Dev-Prod-infra-cicd-Deployment.git) | Infra CICD Deployment |
| [**📦 Terraform-AWS-VPC-Advanced**](https://github.com/Sarthakx67/Terraform-AWS-VPC-Advanced) | Reusable VPC module consumed by this project |
| [**🛡️ RoboShop-Security-Group-Module**](https://github.com/Sarthakx67/RoboShop-Security-Group-Module) | Reusable security group module |
| [**⚙️ RoboShop-Ansible-Roles-tf**](https://github.com/Sarthakx67/RoboShop-Ansible-Roles-tf) | Ansible roles for configuration management |
| [**🐚 RoboShop-Shell-Script-For-Alma-Linux**](https://github.com/Sarthakx67/RoboShop-Shell-Script-For-Alma-Linux) | Bootstrap shell scripts |

</div>

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

  ✅  Certified Kubernetes Administrator (CKA)
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

*BTech Student · Certified Kubernetes Administrator (CKA) · Seeking DevOps / Cloud Engineering Internship*

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sarthak_Singh-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarthak-singh-a0aa62322)

[![Email](https://img.shields.io/badge/sarthaksingh6700@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sarthaksingh6700@gmail.com)

</div>
