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

### 1. Namespace
- Isolates resources into `fintech-infrastructure`

### 2. Deployment
- Runs application pods
- Uses label: `component=ingestion-core`
- Ensures scalability and replication

### 3. Service
- ClusterIP service for internal communication
- Exposes port 80 internally

### 4. Ingress
- Exposes application externally
- Host: `fintech.local`
- Uses NGINX Ingress Controller

---
