# Multi-Tier Banking Application Deployment on AWS EKS

This project demonstrates a production-style DevOps architecture where a multi-tier banking application is deployed on Amazon EKS using Terraform and Kubernetes.

---

## Tech Stack 

AWS EKS  
Terraform  
Kubernetes  
Docker  
GitHub  
CI/CD (planned)

---

## Project Structure

Manifest-Code/

Kubernetes deployment manifests

Terraform-Code/

Infrastructure provisioning for EKS

application/

Bank application source code

docs/

Cluster setup documentation

---

## Deployment Flow

1. Provision infrastructure using Terraform
2. Configure kubectl using AWS CLI
3. Associate IAM OIDC provider
4. Deploy EBS CSI Driver
5. Deploy application using Kubernetes manifests

---

## Key Features

Infrastructure as Code using Terraform

Containerized application deployment

Kubernetes orchestration using EKS

Persistent storage using AWS EBS CSI Driver

Secure IAM integration with OIDC

---

## Future Improvements

Add Jenkins CI/CD pipeline

Add monitoring with Prometheus and Grafana

Add Horizontal Pod Autoscaler

Implement GitOps using ArgoCD
