# Kubernetes Infrastructure Modules

A production-ready collection of modular, highly available Kubernetes infrastructure blueprints designed for enterprise workload isolation, decoupled logging streams, and secure ingress routing traffic topologies.

---

## 🏗️ Phase 1 Module: High-Availability FinTech Activity Ingestion Engine

This module demonstrates a complete, isolated data ingestion architecture designed to handle high-throughput activity logs with zero single points of failure.


### 🛠️ Architectural Components & Implemented Design Patterns

1. **Strict Boundary Isolation (`01-namespace.yaml`)**
   - Implements hard administrative partitions utilizing dedicated custom Namespaces (`fintech-infrastructure`) to ensure multi-tenant security and blast-radius containment.

2. **Scalable Declarative Workloads (`02-ingestion-pod.yaml`)**
   - Deploys highly available, self-healing application layers managed via `apps/v1.Deployment` structures. 
   - Utilizes custom match-labels (`component: ingestion-core`) for dynamic scheduling and controller targeting.

3. **Deterministic Local Network Primitives (`03-service.yaml`)**
   - Engineers stable internal load-balancing endpoints using `NodePort` service primitives.
   - Binds host-level ports explicitly to `32090` to expose microservices safely to localized monitoring tools.

4. **Production-Grade Ingress Topology (`04-ingress.yaml`)**
   - Implements Layer 7 application routing utilizing an **NGINX Ingress Controller** framework.
   - Maps external host-header routing (`fintech-local`) natively onto internal cluster endpoints on Port 80, separating traffic management from application business logic.

---

## 📂 Repository Layout
```text
.
├── README.md                   # Main portfolio documentation & architectural briefs
└── core-architecture/          # Phase 1 Production Module Manifests
    ├── 01-namespace.yaml       # Isolation Layer
    ├── 02-ingestion-pod.yaml   # Workload Layer
    ├── 03-service.yaml         # Internal Routing Layer
    └── 04-ingress.yaml         # Layer 7 Gateway Ingress Layer
