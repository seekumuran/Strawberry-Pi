# Cloud Supply Chain Management

Infrastructure as Code (IaC) configuration and container orchestration for an enterprise-grade **Cloud Supply Chain Management Platform**.

---

## 📖 Overview

This repository defines the infrastructure and service deployments for the Cloud Supply Chain Management system. The platform manages logistics workflows, inventory integration, document management, and automated supply chain pipelines across a multi-node infrastructure.

* **Provisioning & Automation:** Infrastructure is dynamically provisioned on hypervisors using [Terraform](https://www.google.com/search?q=terraform/) with base VM images created using [Packer](https://www.google.com/search?q=packer/).
* **Deployment & Orchestration:** Services are containerized via [Docker Compose](https://www.google.com/search?q=docker/) with ongoing migration plans to a lightweight [Kubernetes (K3s)](https://www.google.com/search?q=kubernetes/) cluster for microservices management.
* **Configuration & Secrets:** [Ansible](https://www.google.com/search?q=ansible/) playbooks manage system configurations and pull sensitive environment variables directly from [HashiCorp Vault](https://www.google.com/search?q=external/).

---

## 🛠 Infrastructure & Core Stack

### Infrastructure & Tools

* **[Terraform](https://www.google.com/search?q=terraform/)** – Cloud and virtualization resource provisioning.
* **[Packer](https://www.google.com/search?q=packer/)** – Immutable VM image creation for supply chain nodes.
* **[Ansible](https://www.google.com/search?q=ansible/)** – Configuration management and automated playbooks.
* **[Docker](https://www.google.com/search?q=docker/)** – Microservice container execution.
* **[Kubernetes (K3s)](https://www.google.com/search?q=kubernetes/)** – Container orchestration platform for microservices.
* **[Vault](https://www.google.com/search?q=external/)** – Secure management of credentials, API keys, and environment variables.

### Supply Chain Platform Services

| Category | Core Service | Function in Supply Chain |
| --- | --- | --- |
| **API & Traffic Routing** | [Traefik](https://www.google.com/search?q=docker/) | Ingress controller & secure reverse proxy for API endpoints |
| **Workflow Automation** | [n8n](https://www.google.com/search?q=docker/) | Supply chain event triggers, order processing & notifications |
| **Document Management** | [Paperless-ngx](https://www.google.com/search?q=docker/) | Invoices, shipping labels, compliance & PO storage |
| **Identity & Security** | [Vaultwarden](https://www.google.com/search?q=docker/) | Credentials management for integration services |
| **Object Storage** | [MinIO](https://www.google.com/search?q=docker/) | S3-compatible cloud storage for logs, backups, and media |
| **Networking & VPN** | [Headscale](https://www.google.com/search?q=external/) | Secure, private interconnectivity between edge nodes & warehouses |
| **System Backups** | [Borgmatic](https://www.google.com/search?q=docker/) | Automated disaster recovery for relational data and state |

---

## 📁 Repository Structure

```text
.
├── .config/       # Pipeline and tool configurations
├── ansible/       # Configuration playbooks & Vault retrieval tasks
├── docker/        # Docker Compose stacks for core supply chain microservices
├── external/      # Management configuration for isolated infrastructure services
├── kubernetes/    # Manifests for K3s container orchestration migration
├── packer/        # VM image templates
└── terraform/     # Infrastructure provisioning code

```

---

## 🖥️ Hardware & Node Allocation

### Physical Infrastructure

| Host | CPU | Threads | RAM | Storage | Role |
| --- | --- | --- | --- | --- | --- |
| **Vyria** | AMD Ryzen 5 5600X | 12 | 16 GB | 480 GB NVMe | Primary Application Server |
| **Alpha** | Intel i5-6200U | 4 | 8 GB | 128 GB SATA SSD | K3s Worker / Edge Node |
| **Beta** | Intel i5-7300U | 4 | 8 GB | 256 GB SATA SSD | K3s Worker / Auxiliary Services |

### Virtual Machine Deployment

* **Vyria VM:** 4 Cores / 8 GB RAM / 260 GB Storage – Core supply chain services & database backends
* **Kubernetes Node 1:** 2 Cores / 2 GB RAM / 10 GB Storage – Primary K3s cluster node
* **Kubernetes Node 2:** 2 Cores / 2 GB RAM / 10 GB Storage – Secondary K3s cluster node
* **Kubernetes Node 3:** 2 Cores / 2 GB RAM / 10 GB Storage – Edge service cluster node

---

## 📌 Roadmap & To-Do

* [x] Initial infrastructure definition and README documentation
* [x] Establish basic observability and monitoring stacks
* [ ] Implement Proxmox metrics integration for resource monitoring
* [ ] Automate Terraform and Packer secret fetching directly from Vault
* [ ] Build end-to-end CI/CD pipelines for deployment updates
* [ ] Complete full service migration from Docker Compose to K3s
