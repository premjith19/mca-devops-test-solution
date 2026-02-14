<div align="center">

# 🚀 MCA DevOps Test Solution

### *Modern Cloud-Native DevOps Pipeline with GitOps & Progressive Delivery*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=flat&logo=kubernetes&logoColor=white)](https://kubernetes.io/)
[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat&logo=docker&logoColor=white)](https://www.docker.com/)
[![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=flat&logo=jenkins&logoColor=white)](https://www.jenkins.io/)
[![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=flat&logo=argo&logoColor=white)](https://argo-cd.readthedocs.io/)

<img src="https://raw.githubusercontent.com/kubernetes/kubernetes/master/logo/logo.png" width="100" alt="Kubernetes"/> &nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/docker-library/docs/c350af05d3fac7b5c3f6327ac82fe4d990d8729c/docker/logo.png" width="100" alt="Docker"/> &nbsp;&nbsp;
<img src="https://helm.sh/img/helm.svg" width="100" alt="Helm"/>

---

### 📊 **Complete DevOps Pipeline** | 🔒 **Security-First** | 🎯 **GitOps Native** | ⚡ **Progressive Delivery**

</div>


---

## 🎯 Overview

A **production-ready DevOps solution** demonstrating enterprise-grade practices for containerization, orchestration, continuous integration/deployment, and automated security scanning. This project implements a complete GitOps workflow using cutting-edge cloud-native tools.

---

## 🛠️ Tech Stack

<table>
<tr>
<td width="50%" valign="top">

### 🐳 Container & Orchestration

| Tool | Purpose | Version |
|------|---------|---------|
| ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) | **Containerization** | Latest |
| ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white) | **Orchestration** | 1.32+ |
| ![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white) | **Package Manager** | 3.x |

</td>
<td width="50%" valign="top">

### 🔄 CI/CD & GitOps

| Tool | Purpose | Version |
|------|---------|---------|
| ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white) | **CI Server** | LTS |
| ![ArgoCD](https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white) | **GitOps CD** | 2.x |
| ![Argo](https://img.shields.io/badge/Argo_Rollouts-EF7B4D?style=for-the-badge&logo=argo&logoColor=white) | **Progressive Delivery** | Latest |

</td>
</tr>
<tr>
<td colspan="2" valign="top">

### 🔒 Security & Quality

| Tool | Purpose | Key Features |
|------|---------|--------------|
| ![Trivy](https://img.shields.io/badge/Trivy-1904DA?style=for-the-badge&logo=aqua&logoColor=white) | **Vulnerability Scanner** | CVE Detection, IaC Scanning, Secret Detection |
| ![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=for-the-badge&logo=sonarqube&logoColor=white) | **Code Quality** | Static Analysis, Security Hotspots, Code Coverage |

</td>
</tr>
</table>

---

## ✨ Features

<table>
<tr>
<td width="33%">

### 🎯 **GitOps Native**
- ✅ Infrastructure as Code
- ✅ Declarative configuration
- ✅ Git as single source of truth
- ✅ Automated sync & reconciliation

</td>
<td width="33%">

### 🔒 **Security First**
- ✅ Container vulnerability scanning
- ✅ Code quality gates
- ✅ Secret management
- ✅ Policy enforcement

</td>
<td width="33%">

### 🚀 **Progressive Delivery**
- ✅ Canary deployments
- ✅ Blue-green deployments
- ✅ Automated rollbacks
- ✅ Traffic splitting

</td>
</tr>
</table>

---

## 📋 Prerequisites

> 💡 **Pro Tip:** Use a package manager like `brew` (macOS), `apt` (Ubuntu), or `choco` (Windows) for easier installation!

### 🔧 Required Tools

<details open>
<summary><b>Click to expand installation commands</b></summary>

```bash
# 🐳 Docker
# Visit: https://docs.docker.com/get-docker/
docker --version

# ☸️ Kubectl
# macOS
brew install kubectl
# Linux
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# ⎈ Helm
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash

# 🔍 Trivy
# macOS
brew install trivy
# Linux
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
echo "deb https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main" | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt-get update && sudo apt-get install trivy

# 🎯 ArgoCD CLI
brew install argocd
# Or download from: https://github.com/argoproj/argo-cd/releases
```

</details>

### 📦 Infrastructure Requirements

| Component | Requirement | Notes |
|-----------|-------------|-------|
| **Kubernetes Cluster** | v1.32+ | Minikube, Kind, EKS, GKE, AKS |
| **Jenkins** | LTS version | With Docker & Kubernetes plugins |
| **Container Registry** | Any | Docker Hub, ECR, GCR, Harbor |
| **Git Repository** | Public/Private | GitHub, GitLab, Bitbucket |

---

## 🚀 Quick Start

### 1️⃣ Clone & Setup

```bash
# Clone the repository
git clone <repository-url>
cd mca-devops-test

# Verify all prerequisites
./scripts/verify-prerequisites.sh
```

### 2️⃣ Deploy Infrastructure

```bash
# Create namespaces
kubectl create namespace argocd
kubectl create namespace argo-rollouts
kubectl create namespace app

# Install ArgoCD
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Install Argo Rollouts
kubectl apply -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml

# Wait for pods to be ready
kubectl wait --for=condition=ready pod -l app.kubernetes.io/name=argocd-server -n argocd --timeout=300s
```

### 3️⃣ Access ArgoCD UI

```bash
# Get initial admin password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

# Port forward to access UI
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Open browser: https://localhost:8080
# Username: admin
# Password: <from previous command>
```

### 4️⃣ Deploy Application

```bash
# Apply ArgoCD application
kubectl apply -f argocd/application.yaml

# Watch deployment
kubectl get applications -n argocd -w
```


---

## 🔄 CI/CD Pipeline

### 🔨 Jenkins Pipeline Flow

```
graph TB
    Start([🎬 Webhook Trigger]) --> Checkout[📥 Git Checkout]
    Checkout --> Build[🔨 Build Application]
    Build --> Test[🧪 Unit Tests]
    Test --> Sonar{📊 SonarQube<br/>Quality Gate}
    Sonar -->|✅ Pass| DockerBuild[🐳 Build Image]
    Sonar -->|❌ Fail| Fail([❌ Pipeline Failed])
    DockerBuild --> TrivyScan{🔍 Trivy Scan}
    TrivyScan -->|✅ No Critical| Push[📤 Push to Registry]
    TrivyScan -->|❌ Vulnerabilities| Fail
    Push --> Docker Image Push[📝 Docker Hub / ECR]
    ArgoCD Deploy  --> Success([✅ Deployment Initiated])
```

### 📊 Pipeline Stages Breakdown

| Stage | Tool | Duration | Description |
|-------|------|----------|-------------|
| **1. Checkout** | Git | ~5s | Clone source code from repository |
| **2. Build** | Maven | ~2m | Compile application and run tests |
| **3. SonarQube** | SonarQube | ~1m | Static code analysis & quality gates |
| **4. Trivy FS Scan** | Trivy | ~30s | Scans the project source code and dependencies |
| **5. Docker Build** | Docker | ~3m | Create optimized container image |
| **6. Trivy Image Scan** | Trivy | ~30s | Scan Docker image for vulnerabilities & secrets |
| **6. Trivy Secret Scan** | Trivy | ~30s | Scans the source code for hardcoded secrets such as passwords, API keys, and tokens. |
| **7. Push Image** | Docker | ~1m | Push to container registry |
| **9. Deployment via ArgoCD** | ArgoCD | ~2m | Deploy to Kubernetes cluster |
| **9. Clean WS After build** | ArgoCD | ~2s | Clean WS After build |



---

## 🔐 Security & Quality

### 🔍 Trivy Security Scanning

<table>
<tr>
<td width="50%">

#### 🎯 **Scan Capabilities**
- ✅ OS package vulnerabilities (CVE)
- ✅ Application dependencies
- ✅ IaC misconfigurations
- ✅ Secret detection
- ✅ License compliance

</td>
</tr>
</table>

### 📊 SonarQube Code Quality

<table>
<tr>
<td width="50%">

#### 📈 **Quality Metrics**
| Metric | Threshold |
|--------|-----------|
| Code Coverage | < 80% |
| Duplications | > 3% |
| Maintainability | A Rating |
| Reliability | A Rating |
| Security | A Rating |

</td>
<td width="50%">

#### 🚦 **Quality Gates**
- ✅ No new bugs
- ✅ No new vulnerabilities
- ✅ No new code smells
- ✅ Coverage on new code < 80%
- ✅ Security hotspots reviewed

</td>
</tr>
</table>

---

## 🎨 Deployment Strategies

### 🚀 Argo Rollouts Strategies

<table>
<tr>
<td width="50%">

#### 🔵🟢 **Blue-Green Deployment**

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Rollout
metadata:
  name: backend
spec:
  strategy:
    blueGreen:
      activeService: backend
      previewService: backend-preview
      autoPromotionEnabled: false

```

**Benefits:**
- ✅ Zero-downtime deployments
- ✅ Instant rollback capability
- ✅ Full traffic switch
- ✅ Easy testing in production

</td>
<td width="50%">

#### 🐤 **Canary Deployment**

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Rollout
metadata:
  name: backend
spec:
  strategy:
    canary:
      stableService: backend
      canaryService: backend-canary
      steps:
      - setWeight: 20
      - pause: {duration: 30}
      - setWeight: 50
      - pause: {duration: 30}
      - setWeight: 100

```

**Benefits:**
- ✅ Gradual traffic shifting
- ✅ Risk mitigation
- ✅ A/B testing capability
- ✅ Automated promotion

</td>
</tr>
</table>



Made by DevOps Engineers

**Happy Deploying! 🚀**

</div>
