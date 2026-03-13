<!-- SETUP INSTRUCTIONS (delete this block after reading)
=======================================================
1. Create a new repository named exactly: Sarthakx67
2. Make it PUBLIC
3. Add a README.md file
4. Paste everything BELOW this comment block into that file
5. Commit and push — GitHub auto-displays it on your profile
======================================================= -->

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=180&section=header&text=Sarthak%20Singh&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=36&desc=Cloud%20%26%20DevOps%20Engineer&descAlignY=55&descSize=18" width="100%"/>

</div>

---

<div align="center">

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&pause=1000&color=58A6FF&center=true&vCenter=true&width=600&lines=Building+Production+Infrastructure+%F0%9F%9A%80;AWS+%7C+Kubernetes+%7C+Terraform+%7C+Jenkins;From+Zero+to+EKS+in+2nd+Year+of+College;Depth+Over+Breadth.+Always.)](https://git.io/typing-svg)

</div>

---

## 👤 About Me

```yaml
name: Sarthak Singh
role: Cloud & DevOps Engineering Student
location: India
education: BTech Computer Engineering — 2nd Year
goal: High-level Cloud/DevOps Architect (systems-focused, not tool-only)

currently_working_on:
  - Deepening Kubernetes internals understanding
  - Learning Linux internals + networking fundamentals
  - Secrets management with External Secrets Operator

seeking: DevOps / Cloud Engineering Internship
```

---

## 🏗️ What I've Built

### 🔴 RoboShop — Multi-Environment AWS Infrastructure + CI/CD

> Full production-style e-commerce microservices platform across DEV and PROD on AWS

- **Terraform modules** — VPC, subnets, 13 security groups with least-privilege rules, EKS, ASG
- **AMI baking pipeline** — EC2 → Ansible configure → stop → bake AMI → Launch Template → ASG
- **Jenkins CI/CD** — build, Nexus artifact publish, downstream deploy trigger, manual approval gate
- **Ansible ansible-pull** — zero-touch configuration management, no push model
- **SSM Parameter Store** — cross-module data sharing without hardcoded values
- **Internal ALB** — host-header based routing to microservices

---

### 🔵 Retail Store — AWS EKS Production Deployment

> Cloud-native microservices platform on EKS with GitOps-ready CI/CD and full observability

- **Helm umbrella chart** — 10 subcharts (cart, catalog, checkout, orders, ui, mysql, postgresql, rabbitmq, redis, dynamodb)
- **IRSA fully implemented** — zero static credentials, pods use IAM roles via OIDC for DynamoDB access
- **StatefulSets + EBS** — persistent storage for MySQL and PostgreSQL via dynamic EBS provisioning
- **HPA on all services** — auto-scaling at 70% CPU utilization target
- **Health probes** — startup + liveness + readiness reduced deployment time **12 min → 1.5 min**
- **Jenkins shared library** — `detectVersion` / `dockerBuildPush` / `deployK8s` across all microservices
- **Prometheus + Grafana** — ServiceMonitors, custom dashboards, 5xx tracking, CPU and JVM memory

---

### 🟢 Shell Scripts Arsenal

> Production-grade bash automation for system administration

- Automated system info reporter with continuous loop and structured file output
- Disk usage monitor with threshold alerting and color-coded output
- Package installer with `VALIDATE()` function pattern, root validation, exit code handling
- Log cleanup with `find -mtime` for automated rotation
- Automated Git push with directory validation and error handling

---

## 🛠️ Tech Stack

<div align="center">

### Cloud & Infrastructure
![AWS](https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white)

### Containers & Orchestration
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

### CI/CD & Automation
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

### Observability
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

### Languages & Scripting
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### Operating Systems
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=Sarthakx67&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true"/>
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Sarthakx67&layout=compact&langs_count=8&theme=tokyonight&hide_border=true"/>

</div>

<div align="center">

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=Sarthakx67&theme=tokyonight&hide_border=true)](https://git.io/streak-stats)

</div>

---

## 🏆 GitHub Trophies

<div align="center">

[![trophy](https://github-profile-trophy.vercel.app/?username=Sarthakx67&theme=tokyonight&no-frame=true&row=1&column=7)](https://github.com/ryo-ma/github-profile-trophy)

</div>

---

## 📌 Currently Learning

```
✅ IRSA + External Secrets Operator — secrets management without plaintext passwords
🔄 Linux internals — cgroups, namespaces, process model, networking stack
🔄 PromQL + AlertManager — moving from "observability installed" to "observability operational"
⏳ NetworkPolicies — pod-level security to match infrastructure-level security groups
⏳ ArgoCD / GitOps — pull-based deployment model
```

---

## 🤝 Connect

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sarthak-singh-a0aa62322)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Sarthakx67)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your-email@gmail.com)

</div>

---

<div align="center">

> *"I don't want to know how to use the tools. I want to know what happens when they fail."*

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%"/>

</div>
