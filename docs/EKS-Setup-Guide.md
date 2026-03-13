# AWS EKS Cluster Configuration, Setup & Application Deployment

This guide explains how to deploy a multi-tier banking application on Amazon EKS using Terraform and Kubernetes.

Region: ap-south-1

---

## Step 1: Install AWS CLI

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install

aws configure

---

## Step 2: Clone Terraform Project

git clone <terraform_repo>

cd Terraform-Code

terraform init

terraform apply --auto-approve

---

## Step 3: Update kubeconfig

aws eks --region ap-south-1 update-kubeconfig --name devopsshack-cluster

---

## Step 4: Install kubectl

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

chmod +x kubectl

sudo mv kubectl /usr/local/bin/

kubectl version --client

---

## Step 5: Install eksctl

curl -LO https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_Linux_amd64.tar.gz

tar -xzf eksctl_Linux_amd64.tar.gz

sudo mv eksctl /usr/local/bin

eksctl version

---

## Step 6: Associate IAM OIDC Provider

eksctl utils associate-iam-oidc-provider \
--region ap-south-1 \
--cluster devopsshack-cluster \
--approve

---

## Step 7: Create IAM Service Account

eksctl create iamserviceaccount \
--region ap-south-1 \
--name ebs-csi-controller-sa \
--namespace kube-system \
--cluster devopsshack-cluster \
--attach-policy-arn arn:aws:iam::aws:policy/service-role/AmazonEBSCSIDriverPolicy \
--approve

---

## Step 8: Deploy AWS EBS CSI Driver

kubectl apply -k \
"github.com/kubernetes-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/ecr/?ref=release-1.11"

---

## Step 9: Deploy Application

kubectl apply -f Manifest-Code/manifest.yaml

---

## Verification

kubectl get nodes

kubectl get serviceaccount ebs-csi-controller-sa -n kube-system

kubectl get pods -n kube-system -l app.kubernetes.io/name=aws-ebs-csi-driver

kubectl get pods
