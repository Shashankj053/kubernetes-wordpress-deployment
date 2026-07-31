# 🚀 Kubernetes WordPress Deployment

![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.33-326CE5?logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![WordPress](https://img.shields.io/badge/WordPress-21759B?logo=wordpress&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?logo=linux&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green)

A **production-inspired Kubernetes project** demonstrating the deployment of a **WordPress** application with a **MySQL backend** using Kubernetes best practices.

This project showcases production-style Kubernetes concepts including Deployments, Services, Persistent Storage, ConfigMaps, Secrets, Resource Management, and Ingress while deploying a complete stateful web application.

---

# 📌 Project Status

✅ Completed

This project demonstrates a fully functional Kubernetes deployment of WordPress with persistent storage and production-inspired Kubernetes resources.

---

# 📚 Table of Contents

- [Project Overview](#-project-overview)
- [Architecture](#-architecture)
- [Features](#-features)
- [Technology Stack](#-technology-stack)
- [Prerequisites](#-prerequisites)
- [Project Structure](#-project-structure)
- [Kubernetes Resources Used](#-kubernetes-resources-used)
- [How It Works](#-how-it-works)
- [Deployment](#-deployment)
- [Screenshots](#-screenshots)
- [Skills Demonstrated](#-skills-demonstrated)
- [Learning Outcomes](#-learning-outcomes)
- [Troubleshooting](#-troubleshooting)
- [Future Improvements](#-future-improvements)
- [Author](#-author)
- [License](#-license)

---

# 📖 Project Overview

This project demonstrates how to deploy a **stateful WordPress application** on Kubernetes using declarative YAML manifests.

The application consists of:

- WordPress frontend
- MySQL backend
- Kubernetes Deployments
- Kubernetes Services
- ConfigMaps
- Secrets
- Persistent Volumes
- Persistent Volume Claims
- NFS Storage
- Resource Requests & Limits
- Ingress Manifest

The objective of this project is to simulate a production-style Kubernetes deployment while following Kubernetes best practices.

---

# 🏗 Architecture

<p align="center">
    <img src="screenshots/architecture.png" width="100%">
</p>

---

# ✨ Features

- Deploy WordPress on Kubernetes
- MySQL backend deployment
- Persistent Storage using NFS
- Persistent Volume Claims (PVC)
- ConfigMaps for application configuration
- Kubernetes Secrets for sensitive credentials
- Resource Requests & Limits
- ClusterIP Service
- NodePort Service
- Ingress Manifest
- Production-style Kubernetes manifests

---

# 🛠 Technology Stack

- Kubernetes
- Docker
- WordPress
- MySQL
- Linux
- YAML
- NFS

---

# 📋 Prerequisites

Before deploying this project, ensure you have:

- Kubernetes Cluster
- kubectl installed
- Docker images accessible
- NFS Server configured
- Persistent Volumes created (or StorageClass available)

---

# 📁 Project Structure

```text
kubernetes-wordpress-deployment
│
├── yamls/
│   ├── mysql-config.yaml
│   ├── mysql-deployment.yaml
│   ├── mysql-pv.yaml
│   ├── mysql-pvc.yaml
│   ├── mysql-secret.yaml
│   ├── mysql-service.yaml
│   ├── wordpress-config.yaml
│   ├── wordpress-deployment.yaml
│   ├── wordpress-ingress.yaml
│   ├── wordpress-pv.yaml
│   ├── wordpress-pvc.yaml
│   └── wordpress-service.yaml
│
├── screenshots/
│   ├── architecture.png
│   ├── kubectl-get-pods.png
│   ├── kubectl-get-services.png
│   ├── kubectl-get-pv.png
│   ├── kubectl-get-pvc.png
│   ├── wordpress-dashboard.png
│   └── wordpress-site.png
│
├── LICENSE
├── .gitignore
└── README.md
```

---

# ☸ Kubernetes Resources Used

| Resource | Purpose |
|-----------|---------|
| Deployment | Manages WordPress and MySQL Pods |
| Pod | Runs application containers |
| ClusterIP Service | Internal communication with MySQL |
| NodePort Service | Exposes WordPress externally |
| ConfigMap | Stores application configuration |
| Secret | Stores sensitive credentials |
| Persistent Volume | Provides persistent storage |
| Persistent Volume Claim | Requests storage for Pods |
| Ingress | HTTP routing configuration |

---

# ⚙️ How It Works

1. Users access the application through the NodePort Service.
2. Kubernetes forwards traffic to the WordPress Pod.
3. WordPress communicates with MySQL using the ClusterIP Service.
4. Database credentials are securely stored in Kubernetes Secrets.
5. Application configuration is managed through ConfigMaps.
6. Persistent data is stored on NFS-backed Persistent Volumes.
7. Deployments ensure Pods remain available if failures occur.

---

# 🚀 Deployment

## Clone the Repository

```bash
git clone https://github.com/ShashankJ053/kubernetes-wordpress-deployment.git
```

Move into the project directory.

```bash
cd kubernetes-wordpress-deployment
```

Deploy all Kubernetes resources.

```bash
kubectl apply -f yamls/
```

Verify the Pods.

```bash
kubectl get pods
```

Verify the Services.

```bash
kubectl get svc
```

Verify Persistent Volumes.

```bash
kubectl get pv
```

Verify Persistent Volume Claims.

```bash
kubectl get pvc
```

---

# 📸 Screenshots

## Kubernetes Pods

Running WordPress and MySQL Pods.

![Pods](screenshots/kubectl-get-pods.png)

---

## Kubernetes Services

NodePort and ClusterIP Services.

![Services](screenshots/kubectl-get-services.png)

---

## Persistent Volumes

Persistent Volumes configured for WordPress and MySQL.

![PV](screenshots/kubectl-get-pv.png)

---

## Persistent Volume Claims

Persistent Volume Claims successfully bound.

![PVC](screenshots/kubectl-get-pvc.png)

---

## WordPress Dashboard

Successful WordPress installation.

![Dashboard](screenshots/wordpress-dashboard.png)

---

## Running Website

WordPress application running successfully.

![Website](screenshots/wordpress-site.png)

---

# 🎯 Skills Demonstrated

- Kubernetes
- Docker
- Linux Administration
- WordPress Deployment
- MySQL Deployment
- Kubernetes Networking
- Persistent Storage
- NFS
- ConfigMaps
- Secrets
- YAML
- Resource Management
- Kubernetes Troubleshooting

---

# 📚 Learning Outcomes

Through this project I gained hands-on experience with:

- Kubernetes Deployments
- Services
- ConfigMaps
- Secrets
- Persistent Volumes
- Persistent Volume Claims
- NFS Storage
- Kubernetes Networking
- YAML Manifest Design
- Stateful Application Deployment
- Kubernetes Troubleshooting
- Production-style Kubernetes Architecture

---

# 🔧 Troubleshooting

During development, the following issues were identified and resolved:

- Persistent Volumes remained in the **Released** state after deleting Persistent Volume Claims.
- WordPress displayed **"Error establishing a database connection"** because stale MySQL data remained on the NFS volume.
- Health probes initially returned HTTP 500 responses during WordPress startup.
- NFS-backed Persistent Volumes required cleanup before reinitializing the database.
- Pods remained in the **Pending** state until Persistent Volumes were recreated and rebound successfully.

These issues provided valuable experience troubleshooting Kubernetes storage, deployments, and application initialization.

---

# 🚀 Future Improvements

- Helm Charts
- Kubernetes StatefulSets
- Horizontal Pod Autoscaler (HPA)
- GitHub Actions CI/CD
- ArgoCD
- Kustomize
- Prometheus Monitoring
- Grafana Dashboards
- TLS with NGINX Ingress Controller
- cert-manager
- Velero Backup & Restore
- ExternalDNS

---

# 👨‍💻 Author

**Shashank Jain**

Bachelor of Computer Applications (Cloud Computing)

Aspiring DevOps Engineer

- GitHub: https://github.com/ShashankJ053
- LinkedIn: https://www.linkedin.com/in/your-linkedin-profile/

---

# 📄 License

This project is licensed under the **MIT License**.

See the [LICENSE](LICENSE) file for details.

---

⭐ If you found this project useful, consider giving it a **Star** on GitHub.
