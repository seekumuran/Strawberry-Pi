# Cloud Supply Chain Management

Infrastructure as Code (IaC) configuration and container orchestration for an enterprise-grade **Cloud Supply Chain Management Platform**.

---

## Overview

This repository defines the infrastructure and service deployments for the Cloud Supply Chain Management system. The platform manages logistics workflows, inventory integration, document management, and automated supply chain pipelines across a multi-node infrastructure.

* **Provisioning & Automation:** Infrastructure is dynamically provisioned across physical nodes using [Terraform](https://www.google.com/search?q=terraform/) with base VM images created using [Packer](https://www.google.com/search?q=packer/).
* **Deployment & Orchestration:** Services are containerized via [Docker Compose](https://www.google.com/search?q=docker/) with ongoing migration plans to a lightweight [Kubernetes (K3s)](https://www.google.com/search?q=kubernetes/) cluster for microservices management.
* **Configuration & Secrets:** [Ansible](https://www.google.com/search?q=ansible/) playbooks manage system configurations and pull sensitive environment variables directly from [HashiCorp Vault](https://www.google.com/search?q=external/).

---

## Infrastructure & Core Stack

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

## Repository Structure

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

## Hardware & Node Allocation

### Physical Hardware Architecture

| Host Node | OS / Platform | Role in Supply Chain Infrastructure |
| --- | --- | --- |
| **Linux Server** | Linux (Ubuntu Server / Debian) | Primary Compute Node (Virtualization & Core Microservices Host) |
| **Windows Node 1** | Windows | Logistics Workstation & Monitoring Client |
| **Windows Node 2** | Windows | Warehouse Inventory Management & ERP Integration Node |
| **Windows Node 3** | Windows | Administrative & Supply Chain Analytics Host |
| **Raspberry Pi** | Raspberry Pi OS / Linux | Edge Gateway / Warehouse IoT Collector & K3s Edge Node |

### Service & VM Deployment

* **Primary Linux Host:** Runs core docker stacks, application databases, and primary Kubernetes master components.
* **Raspberry Pi Node:** Lightweight K3s agent node for edge telemetry, barcode scanner triggers, and local device management.
* **Windows Cluster Hosts:** Integrated via Tailscale/Headscale subnet routers for administrative controls and database sync.
