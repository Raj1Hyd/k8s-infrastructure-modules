# Phase 1: High-Availability FinTech Activity Ingestion Engine

An enterprise-grade Kubernetes core infrastructure blueprint implementing namespace isolation, service discovery, and ingress-based routing.

---

## 🧱 Architecture Overview

Client Request  
↓  
Ingress (NGINX Controller)  
↓  
ClusterIP Service  
↓  
Deployment  
↓  
Pods (NGINX Container)

---

## 📦 Components

### 1. Namespace (01-namespace.yaml)
- Isolates resources into `fintech-infrastructure`

---

### 2. Deployment (02-deployment.yaml)
- Runs application pods
- Uses label: `component=ingestion-core`
- Ensures scalability and replication
- Replaces original Pod-based design

---

### 3. Service (03-service.yaml)
- ClusterIP service for internal communication
- Exposes port 80 internally
- Routes traffic to pods using labels

---

### 4. Ingress (04-ingress.yaml)
- Exposes application externally
- Host: `fintech.local`
- Uses NGINX Ingress Controller
---
