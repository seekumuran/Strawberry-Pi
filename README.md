# Strawberry-Pi

> A hands-on systems engineering project exploring how Raspberry Pi hardware, Linux, containers, networking, and service orchestration relate to modern cloud and enterprise infrastructure.

**Status:** Draft. Implementation details are pending verification against the repository.

---

## Table of Contents

- [Overview](#overview)
- [Engineering Objectives](#engineering-objectives)
- [Architecture](#architecture)
- [Requirements](#requirements)
- [Installation and Setup](#installation-and-setup)
- [Configuration](#configuration)
- [Networking and Services](#networking-and-services)
- [Data Persistence](#data-persistence)
- [Monitoring and Troubleshooting](#monitoring-and-troubleshooting)
- [Security Considerations](#security-considerations)
- [Enterprise and Cloud Technology Landscape](#enterprise-and-cloud-technology-landscape)
- [Enterprise Technology Roles and Industry Landscape](#enterprise-technology-roles-and-industry-landscape)
- [Design Decisions and Trade-offs](#design-decisions-and-trade-offs)
- [Testing and Validation](#testing-and-validation)
- [Limitations and Known Gaps](#limitations-and-known-gaps)
- [Roadmap](#roadmap)
- [Learning Outcomes](#learning-outcomes)
- [Contributing](#contributing)
- [License and Acknowledgments](#license-and-acknowledgments)

---

## Overview

Strawberry-Pi uses a Raspberry Pi as a constrained, low-cost host for experimenting with the building blocks of modern infrastructure: Linux system administration, containerized services, service-to-service networking, persistent storage, and operational tooling. The emphasis is on understanding trade-offs (resource limits, isolation, recovery, and maintainability) rather than on building a production platform.

## Engineering Objectives

- Understand infrastructure design under tight CPU, memory, storage, and power constraints.
- Practice service isolation and repeatable deployment.
- Examine networking and communication between services, including API boundaries.
- Explore configuration and secrets handling.
- Consider persistence, backup, and data-handling concerns.
- Build monitoring, health-check, and recovery habits.
- Relate local experiments to the concepts used in public cloud and enterprise environments.

## Architecture

`TODO: verify.` The actual service topology, container runtime, and network layout must be taken from the repository before this section is written. A diagram will be added only after that verification.

## Requirements

- **Hardware:** Raspberry Pi model and storage media `TODO: verify`
- **OS:** Raspberry Pi OS / Linux distribution and version `TODO: verify`
- **Software:** Docker / Compose version, language runtimes, and other dependencies `TODO: verify`

## Installation and Setup

`TODO: verify.` Setup commands, Compose file names, and required steps must be copied from the repository. No commands are listed here because none have been verified.

## Configuration

`TODO: verify.` List the actual environment-variable names from the repository's configuration or `.env.example`. Do not document secret values.

## Networking and Services

`TODO: verify.` Service names, ports, and endpoints must come from the Compose or service definitions. No ports are listed here.

## Data Persistence

`TODO: verify.` Document the actual volumes, bind mounts, and database files.

## Monitoring and Troubleshooting

`TODO: verify.` Document only health checks, logs, and tools that exist in the repository.

## Security Considerations

General principles that apply to this kind of project:

- Keep credentials out of version control and out of images.
- Apply least privilege to containers and host access.
- Limit exposed ports and restrict network reachability.
- Keep the base OS and container images updated.

`TODO: verify` which of these are actually implemented.

## Enterprise and Cloud Technology Landscape

This section is conceptual. None of the products below are installed, integrated, or simulated by this project unless the repository shows otherwise.

### Amazon Web Services (AWS)

- **EC2** provides virtual compute. A Raspberry Pi host is a rough analogy for a single virtual machine, without the elasticity or managed scaling.
- **S3** provides object storage. Local volumes can illustrate the storage-interface concept, but not durability or regional replication.
- **VPC** provides network isolation. Docker networks and host firewall rules teach related ideas at a smaller scale.
- **IAM** governs identity and access. Local Unix users and container permissions are a basic analogue for least privilege.
- **CloudWatch** provides monitoring and logs. Local logging and health checks illustrate the same goals.

Learning about these services is different from simulating them locally, and both differ from integrating with the real service. This project does none of the third one unless verified.

### SAP

SAP S/4HANA is an ERP suite covering finance, procurement, inventory, and supply chain. SAP Business Technology Platform (BTP) provides integration and extension services. Infrastructure and service architecture can support such applications, but this project does not install, connect to, or emulate SAP software.

### Oracle

- **OCI** is Oracle's cloud infrastructure platform.
- **Fusion Cloud Applications** and **E-Business Suite (EBS)** are enterprise application suites.
- **Supply Chain Management (SCM)** areas include Procurement, Inventory, Order Management, and Planning.
- **Enterprise Performance Management (EPM)** areas include Financial Consolidation and Close (FCC), Planning, Account Reconciliation (ARC), Profitability and Cost Management (PCM), and Enterprise Data Management (EDM).
- **Oracle Analytics Cloud (OAC)** and **Business Intelligence (BI)** cover analytics.
- **Oracle Data Integrator (ODI)** covers data integration.

These are distinct layers: infrastructure, databases, integration tooling, analytics, and business applications. None are running locally or connected to this project.

### Workday

Workday provides Human Capital Management (HCM) and related applications. Its functional concepts include worker data, business processes, and reporting. Its technical concepts include integrations and data integration. This project does not connect to Workday.

### Microsoft Azure

Azure offers comparable concepts for comparative study: virtual machines and storage, virtual networks, Entra ID for identity, Azure Monitor for observability, container services, and hybrid-cloud connectivity. These are learning references only.

### Broader Technologies

`TODO: verify` each item below against the repository before listing it as implemented: Linux, Docker, reverse proxies, persistent volumes, CI/CD, and observability tools.

## Enterprise Technology Roles and Industry Landscape

The following role categories and experience bands are supplied as market context from a reference provided for this README. They are not independently verified salary or employment statistics, and they do not indicate that Strawberry-Pi provides this experience or qualifies its developer for senior enterprise roles. Vendor functional and technical expertise requires separate study and hands-on practice.

| Role / Technology | Experience Band |
|---|---|
| Workday HCM Functional | 9–15 years |
| Workday Technical | 2–5, 5–10, 9–15 years |
| Oracle Cloud/Fusion/EBS SCM | 1–2, 2–3 years |
| Oracle Cloud/Fusion SCM — Procurement, Inventory, Order Management | 5–15 years |
| Oracle Cloud SCM Order Management | 5–10 years |
| Oracle Planning Cloud | 5–10 years |
| Oracle App/EBS/Fusion Technical | 2–5, 5–8 years |
| Oracle Analytics Cloud / BI | 2–5, 5–10 years |
| Oracle Data Integrator | 5–10 years |
| Oracle EPM — FCC, Planning, ARC, PCM, EDM | 2–5, 5–10 years |
| Oracle EBS Finance | 2–5 years |
| Oracle Fusion Finance | 2–5 years |

The project can help build infrastructure intuition relevant to these environments. Platform-specific expertise is a separate effort.

## Design Decisions and Trade-offs

`TODO: verify and document.` Record the actual choices made in the repository (for example, why Compose was chosen, how state is stored, and what was deliberately left out) along with their costs.

## Testing and Validation

`TODO: verify.` List only tests or checks that exist in the repository.

## Limitations and Known Gaps

- Not a production system and not a cloud provider.
- Single-host, resource-constrained deployment `TODO: verify`.
- No vendor integrations are implemented.

## Roadmap

Planned items are not commitments. `TODO: confirm` with the maintainer.

## Learning Outcomes

- Linux and container operations on constrained hardware.
- Service design, networking, and persistence trade-offs.
- Mapping local infrastructure concepts to cloud and enterprise equivalents.

## Contributing

`TODO: add contribution guidelines if the maintainer wants them.`

## License and Acknowledgments

`TODO: add license.` No license has been verified, so none is claimed here. Third-party components should be credited once the dependency list is confirmed.

Product names and trademarks belong to their respective owners. This project is not affiliated with or endorsed by AWS, SAP, Oracle, Workday, or Microsoft.
