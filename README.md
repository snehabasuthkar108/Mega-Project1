
# Multi-Tier Banking Application Deployment on AWS EKS

## Project Overview

This project demonstrates a production-style DevOps architecture where a multi-tier banking application is deployed on Amazon EKS using Terraform, Docker, and Kubernetes.

The project covers infrastructure provisioning, containerization, Kubernetes deployment, persistent storage integration, and IAM OIDC configuration.

---

## Architecture Diagram

![Architecture](docs/Architecture.png)

---

## Tech Stack

* AWS EKS
* Terraform
* Kubernetes
* Docker
* GitHub
* IAM OIDC
* AWS EBS CSI Driver

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
6. Push Docker image to DockerHub
7. Deploy application to EKS using Kubernetes manifests
8. Expose application using Kubernetes Service

---

## Features Implemented

* Infrastructure as Code using Terraform
* Amazon EKS cluster provisioning
* Containerized application deployment using Docker
* Kubernetes deployments and services
* Persistent storage using AWS EBS CSI Driver
* IAM Role for Service Accounts (IRSA)
* Multi-tier application deployment (BankApp + MySQL)

---

## Future Enhancements

* Jenkins CI/CD Pipeline
* Ingress Controller
* Horizontal Pod Autoscaler (HPA)
* Prometheus & Grafana Monitoring
* GitOps using ArgoCD
* Helm Charts
* Blue-Green Deployment
* Email Notifications for Pipeline

---

## Author

Sneha Basuthkar
Senior Cloud Engineer | AWS | Kubernetes | Terraform | Docker
