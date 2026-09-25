 CFG Mock Bank - Hybrid Identity & Access Management (IAM) Infrastructure
A multi-tier security infrastructure deployment modeling enterprise directory architectures, identity lifecycles, and access governance patterns for a regional financial institution.

##  Phase 1 Architecture: Environment Provisioning & Directory Design
Completed: Friday, September 25, 2026

### 1. On-Premises Core Infrastructure (Hypervisor Tier)
* **Hypervisor Orchestration:** Configured a local virtual server instance utilizing Oracle VirtualBox, allocating virtual hardware assets to optimize host system throughput (4GB RAM, 2 CPU Cores).
* **Minimal OS Architecture Deployment:** Successfully provisioned a headless, minimized deployment of Ubuntu Server 24.04 LTS to reduce local storage footprints to a 25GB static boundary.
* **Network Interface Configuration:** Mapped virtual switching interfaces utilizing automated host DHCP parameters to secure localized internal IP boundaries (`10.0.2.15/24`) while preserving open network transport capabilities for upcoming schema installations.
* **Administrative Governance:** Established foundational encrypted master root identities (`jhawkins`) and authorized secure administrative boundary loops via OpenSSH server bindings.

### 2. Cloud Identity Control Plane (Application Tier)
* **Tenant Provisioning:** Deployed a permanent Enterprise-grade Okta Developer Infrastructure Workspace mapped under authorized institutional domain footprints (`@students.towson.edu`).
* **The "Joiner" Lifecycle Phase:** Architected the foundational user directory registry backend, executing identity onboarding workflows to enroll mock banking profiles (`Othenial Kipalu`).
* **Lifecycle State Auditing:** Initiated policy verification sweeps to transition user entries into managed operational states, simulating password expiration constraints and administrative account lock governance.

---

## Upcoming Project Milestones (Saturday & Sunday)
* **Access Control Mapping:** Engineering attribute-based and role-based access control security groups (`SG-Branch-Operations`) to enforce the Principle of Least Privilege.
* **Single Sign-On (SSO) Integration:** Deployed and federated a mock SaaS application integration utilizing the Okta Integration Network to handle unified authentication workflows.
