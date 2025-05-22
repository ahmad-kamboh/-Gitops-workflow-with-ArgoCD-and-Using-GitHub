
# GitOps Workflow with ArgoCD and GitHub

This guide walks you through setting up a GitOps workflow using **ArgoCD**, **GitHub**, and **Minikube**. By the end, you’ll have a working Kubernetes environment managed via GitHub and deployed automatically with ArgoCD.

---
![WhatsApp Image 2025-05-21 at 23 34 16_f84ec5cd](https://github.com/user-attachments/assets/5f9e2738-57a6-40f3-9613-dec77b8a99eb)

## ⚙️ System Requirements

- Ubuntu (or similar Linux distro)
- Internet connection
- User with `sudo` privileges

---
![WhatsApp Image 2025-05-21 at 23 34 14_a242cb8e](https://github.com/user-attachments/assets/6e1ad706-f7ff-410d-925c-147c9cc71ea8)
## 🔄 Update System

```bash
sudo apt-get update && sudo apt-get upgrade -y
Create GitOps workflow with ArgoCD and Using GitHub:

Ensure the system is updated before starting:
sudo apt-get update && sudo apt-get upgrade -y

Step 1: Install Git:
sudo apt-get install git -y

Verify installation:
git --version

Step 2: Install Docker:

Uninstall any old Docker versions:
sudo apt-get remove docker docker-engine docker.io containerd runc

Install Docker prerequisites:
sudo apt-get install ca-certificates curl gnupg -y

Add Docker’s official GPG key:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

Set up the stable repository:
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Install Docker:
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

Start Docker and enable it to start on boot:
sudo systemctl start docker
sudo systemctl enable docker

Allow non-root user to run Docker:
sudo usermod -aG docker $USER
---

Verify Docker:
docker --version


Step 3: Install Minikube:
Download Minikube binary:
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

Install Minikube:
sudo install minikube-linux-amd64 /usr/local/bin/minikube

Verify Minikube installation:
minikube version

Step 4: Install kubectl:
Download the latest kubectl binary:
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

Install kubectl:
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

Verify kubectl installation:
kubectl version --client

Step 5: Install Helm:
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

Verify Helm installation:
helm version

![WhatsApp Image 2025-05-21 at 23 34 14_a242cb8e](https://github.com/user-attachments/assets/6e1ad706-f7ff-410d-925c-147c9cc71ea8)

Step 6: Install ArgoCD CLI:
Download ArgoCD CLI binary:
curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64

Install ArgoCD CLI:
sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd

Verify ArgoCD installation:
argocd version --client

If you face errors with Minikube permissions:

Add user to Docker group:
sudo usermod -aG docker $USER

Apply group change:
newgrp docker

![WhatsApp Image 2025-05-21 at 23 34 16_fd692ea9](https://github.com/user-attachments/assets/5e08689e-4864-4545-8851-c605a8222902)

Check Docker:
docker ps

Restart Minikube with Docker driver:
minikube start --driver=docker

For full workflow example and GitHub Actions integration, refer to:
https://www.fosstechnix.com/gitops-workflow-with-argocd-and-github-actions/

📞 Contact Information

| **Method** | **Details**                  |
|------------|------------------------------|
| Email      | ahmadtahir4235@gmail.com     |
| Phone      | +92 3000511136               |
| LinkedIn   | https://linkedin.com/in/m-ahmadtahir |
