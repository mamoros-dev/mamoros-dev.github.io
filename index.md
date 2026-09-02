<img src="./images/Foto_CV_baja.png" alt="Miguel Amorós" width="120" style="float: left; margin-right: 20px; border-radius: 50%;">

# Miguel Amorós Moret

### Cloud Engineer Junior · AWS · Infrastructure as Code

<div style="clear: both;"></div>

Systems technician with 4 years of experience keeping critical infrastructure running in a 24/7 production environment, where any failure had real consequences. Alongside that, I've built a portfolio of cloud projects on AWS on my own initiative — from Infrastructure as Code architectures to a production Kubernetes cluster and a high-availability deployment with tested automatic recovery.

📍 Barcelona · Remote / Hybrid · Available immediately
📧 [miguel14amoros@gmail.com](mailto:miguel14amoros@gmail.com) · 💼 [LinkedIn](https://www.linkedin.com/in/miguel-amoros-moret) · 🐙 [GitHub](https://github.com/mamoros-dev)

---

## 🛠️ Technical Stack

**Cloud & DevOps:** AWS (EC2, VPC, ALB, Auto Scaling, RDS, Lambda, API Gateway, DynamoDB, S3, EKS, IAM, CloudWatch, SSM) · Terraform · Ansible · Docker · Kubernetes · Helm · GitHub Actions (OIDC) · Prometheus · Grafana

**Systems:** Linux · Windows Server · TCP/IP · VPN · Python · Bash

---

## 📌 Projects

### [High Availability Cluster — Zero-Downtime](https://github.com/mamoros-dev/aws-ansible-gitops-ha-v2)
ALB + Auto Scaling Group with zero-downtime deployments (Ansible `serial: 1`). I tested automatic recovery by terminating a live instance: traffic stayed at 100% while the ASG spun up a replacement.
`Terraform` `Ansible` `AWS ALB/ASG` `GitOps`

### [Automation with Terraform + Ansible + GitHub Actions](https://github.com/mamoros-dev/aws-ansible-gitops-pipeline)
Terraform provisions the infrastructure and Ansible configures it via dynamic inventory. Secrets are managed with Ansible Vault and AWS SSM Parameter Store, without exposing credentials in the repository.
`Terraform` `Ansible Vault` `AWS SSM` `CI/CD`

### [WordPress + MySQL on Kubernetes (EKS)](https://github.com/mamoros-dev/aws-eks-wordpress)
Deployed on an EKS cluster with Helm, Ingress, autoscaling (HPA) and monitoring with Prometheus and Grafana, with its own CI/CD pipeline.
`Kubernetes` `Helm` `Prometheus` `Grafana`

### [Three-Tier Web Architecture with Terraform](https://github.com/mamoros-dev/aws-3-tier-terraform)
Migrated a manually deployed architecture to Infrastructure as Code, with a remote S3 backend and DynamoDB state locking.
`Terraform` `AWS VPC/ALB/RDS`

### [Serverless API — URL Shortener](https://github.com/mamoros-dev/aws-serverless-url-shortener)
Event-driven architecture with Lambda, API Gateway and DynamoDB, with no servers to maintain.
`Lambda` `API Gateway` `DynamoDB`

### [Three-Tier Web Architecture (Console)](https://github.com/mamoros-dev/aws-3-tier-web-architecture)
First version, built by hand to properly understand each component before automating anything.
`AWS EC2/VPC/ALB/RDS`

---

## 💼 Experience

**Mediapro (Grupo Mediapro), Barcelona** — IT Support & Sysadmin · March 2022 – May 2026 (4 years)
Part of the IT team (3 people) at an audiovisual post-production facility, as technical lead and directly responsible for servers and systems. I coordinated task distribution across the team during peak workload periods, managed Windows Server infrastructure, high-performance networking, backups and VPN, and provided L1/L2 technical support.

---

## 🎓 Education

- AWS Certified Solutions Architect – Associate (SAA-C03) — exam in preparation
- Higher Vocational Training in Network Systems Administration (CFGS ASIR) — IES Escola del Treball, Barcelona

---

## 📫 Get in Touch

Looking for a Cloud Engineer junior with a solid background in real-world systems? Let's talk.

[📧 Email](mailto:miguel14amoros@gmail.com) · [💼 LinkedIn](https://www.linkedin.com/in/miguel-amoros-moret) · [🐙 GitHub](https://github.com/mamoros-dev)

