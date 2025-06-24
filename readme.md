# Azure DevOps CI/CD for Microservices Voting App 🗳️🚀

This project demonstrates a complete **CI/CD pipeline implementation on Azure DevOps** for a containerized microservices application — originally from [dockersamples/example-voting-app](https://github.com/dockersamples/example-voting-app).

It showcases how to automate the build, test, and deployment of a multi-service architecture using **Azure DevOps**, **AKS**, and **Helm**, following cloud-native best practices.

---

## 🔧 Tech Stack & Architecture

- **CI/CD Tool**: Azure DevOps Pipelines (Multi-stage YAML)
- **Orchestration**: Azure Kubernetes Service (AKS)
- **Containerization**: Docker
- **Container Registry**: Azure Container Registry (ACR)
- **Infrastructure**: Azure Virtual Machine - free tier, for self-hosted Agent Pool
- **Languages Used**: Python, .NET, Node.js
- **Database/Queue**: Redis, PostgreSQL

---

## 🧠 What’s Included?

| Component          | Description |
|-------------------|-------------|
| `azure-pipelines.yml` | CI/CD pipeline for building, testing, and deploying services |
| `manifests/` | Kubernetes deployment files for all services |
| `App Code and health check/` |Code and health check files |
| `scripts/` | Helper scripts for AKS provisioning, image builds, etc.. |

---

## 📌 Key Features

- ✅ Multi-stage CI/CD pipeline using **Azure Pipelines YAML**
- ✅ Image build & push to **Azure Container Registry (ACR)**
- ✅ Deploy to **Azure Kubernetes Service (AKS)** with scaling via **VMSS**
- ✅ Secrets & service connection management via Azure DevOps
- ✅ Rollback-friendly & environment-specific deployments

---

## ⚙️ Setup Instructions

> Prerequisites: Azure Subscription, Azure CLI, Docker, Azure DevOps Project

1. **Clone the repository**  
   ```bash
   git clone https://github.com/dockersamples/example-voting-app


## 🚀 Getting Started: Azure Resource Setup

Follow these steps to deploy the full CI/CD workflow to your Azure environment.

### 🧱 Step 1: Provision Azure Resources

- ✅ Create an **Azure Kubernetes Service (AKS)** cluster with custom **self-hosted agent node pools**
- ✅ Set up an **Azure Container Registry (ACR)** to store Docker images
- ✅ Configure required **Service Connections** in Azure DevOps (Azure Resource Manager & Container Registry)

### 🗂️ Step 2: Import & Configure in Azure DevOps

1. **Import this repository** into your Azure DevOps Repos
2. Navigate to **Pipelines > New Pipeline**
3. Use existing YAML definitions:
   - `azure-pipelines-vote.yml`
   - `azure-pipelines-worker.yml`
   - `azure-pipelines-result.yml`
4. Upload setup **scripts** and define necessary **pipeline secrets/variables**
   - Example: ACR login

### 🔄 Step 3: Run the Pipelines

Running the pipelines will:
- 🔧 Build Docker images for each microservice
- 📦 Push the images to ACR
- 🚀 Deploy services to AKS via script trigger ArgoCD sync

---

## 📂 Folder Structure

```bash
.
├── azure-pipelines-vote.yml     # CI/CD pipeline for voting frontend
├── azure-pipelines-worker.yml   # CI/CD pipeline for worker service
├── azure-pipelines-result.yml   # CI/CD pipeline for result UI
├── OTHER_REPOS_FROM_GIT_CLONE/  # repo clone from [dockersamples/example-voting-app](https://github.com/dockersamples/example-voting-app).
├── scripts/                     # Setup scripts (e.g., for ArgoCD and creating a secret guide)
└── README.md                    # This file


