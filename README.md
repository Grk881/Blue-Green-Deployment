# Blue-Green Deployment with Kubernetes + GitHub Actions

## ✅ Overview

This repository demonstrates a simple blue-green deployment setup using Kubernetes (Minikube) and GitHub Actions.

## 🚀 Steps to Deploy

### 1. Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/blue-green-k8s-cicd.git
cd blue-green-k8s-cicd
```

### 2. Apply Blue Deployment

```bash
kubectl apply -f blue/
```

### 3. Switch to Green Deployment

Update `service.yaml` selector version from `blue` to `green`, then:

```bash
kubectl apply -f green/
kubectl apply -f blue/service.yaml
```

### 4. Access Service

```bash
minikube service myapp-service --url
```

## 📁 Repo Structure

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml
├── blue/
│   ├── deployment.yaml
│   └── service.yaml
├── green/
│   └── deployment.yaml
└── README.md
```
