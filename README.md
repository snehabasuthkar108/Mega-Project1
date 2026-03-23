# Multi-Tier Banking Application Deployment on AWS EKS

## Project Overview
This project demonstrates a production-style DevOps architecture where a multi-tier banking application is deployed on Amazon EKS using Terraform, Docker, and Kubernetes.

The project covers infrastructure provisioning, containerization, Kubernetes deployment, persistent storage integration, and IAM OIDC configuration.

---

## Architecture Diagram
![Architecture](docs/architecture.png)

---

## Tech Stack
- AWS EKS
- Terraform
- Kubernetes
- Docker
- GitHub
- IAM OIDC
- AWS EBS CSI Driver

---

## Project Structure
```
application/              Bank application source code
terraform/                Infrastructure provisioning for EKS
kubernetes-manifests/     Kubernetes deployment manifests
docs/                     Documentation and architecture diagrams
```

---

## Deployment Workflow
1. Provision AWS infrastructure using Terraform
2. Configure kubectl using AWS CLI
3. Associate IAM OIDC provider
4. Install AWS EBS CSI Driver
5. Build Docker image
6. Deploy application to EKS using Kubernetes manifests
7. Configure Ingress for external access

---

## Features
- Infrastructure as Code using Terraform
- Containerized application deployment
- Kubernetes orchestration using Amazon EKS
- Persistent storage using AWS EBS
- IAM Role for Service Accounts (IRSA)
- Horizontal Pod Autoscaler
- Ingress Controller

---

## Future Enhancements
- Jenkins CI/CD Pipeline
- Prometheus & Grafana Monitoring
- GitOps using ArgoCD
- Blue-Green Deployment
- Helm Charts

---

## Author
Sneha Basuthkar
Senior Cloud Engineer | AWS | Kubernetes | Terraform | Docker
