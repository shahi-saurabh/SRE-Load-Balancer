# Architecture

## High-Level Design

This document provides a detailed overview of the architecture for the SRE-Load-Balancer project.

## Development Approach

### What We Are Building

The SRE-Load-Balancer project aims to deliver a scalable, reliable, and observable load balancing solution tailored for SRE teams managing modern distributed applications. The system will support dynamic traffic distribution, health checks, security, automation, and monitoring integrations.

### How We Will Develop

1. **Requirements Gathering:**
  - Identify key use cases for SREs, such as zero-downtime deployments, automated failover, and traffic analytics.
  - Define functional and non-functional requirements (scalability, reliability, security, observability).

2. **Technology Selection:**
  - Choose a programming language (Go, Python, or Node.js) for the core load balancer logic.
  - Use cloud-native tools (Azure VMSS, NGINX/IIS, cloud-init, CLI/PowerShell) for infrastructure automation.
  - Integrate with monitoring solutions (Prometheus, Grafana) for metrics and alerting.

3. **System Design:**
  - Design modular components: traffic manager, health checker, configuration manager, metrics exporter, and security handler.
  - Define APIs and configuration formats (YAML/JSON).
  - Plan for extensibility to support additional algorithms and cloud providers.

4. **Implementation:**
  - Develop the load balancer core logic and supporting modules.
  - Automate infrastructure provisioning using scripts and templates.
  - Implement health checks, failover logic, and metrics endpoints.

5. **Testing & Validation:**
  - Write unit and integration tests for all components.
  - Simulate real-world traffic and failure scenarios.
  - Validate security controls and monitoring integrations.

6. **Documentation & Deployment:**
  - Document architecture, configuration, and operational procedures.
  - Provide deployment guides for cloud and on-premise environments.
  - Enable CI/CD pipelines for automated testing and deployment.

7. **Continuous Improvement:**
  - Gather feedback from SREs and users.
  - Iterate on features, performance, and reliability based on real-world usage.

This approach ensures the project is robust, maintainable, and aligned with industry best practices for SRE and load balancing.

### Flow Diagram

User → Basic Load Balancer → VMSS (NGINX/IIS Instances)

- **User:** Initiates requests to the application.
- **Basic Load Balancer:** Distributes incoming traffic across multiple VMSS instances running NGINX or IIS.
- **VMSS (Virtual Machine Scale Set):** Hosts multiple instances of web servers (NGINX/IIS) for scalability and reliability.

### Networking Components

- **VNet (Virtual Network):** Provides network isolation and segmentation.
- **Subnet:** Logical subdivision within the VNet for organizing resources.
- **NSG (Network Security Group):** Controls inbound and outbound traffic. 
  - Allow HTTP (port 80) for web traffic.
  - Optionally allow SSH (port 22) for management.

### Automation

- **CLI & PowerShell:** Used for provisioning and managing resources.
- **cloud-init scripts:** Automate server configuration and application deployment.

---

# Security Considerations

- Restrict SSH (22) access to your IP only.
- Use NSGs to limit inbound traffic to required ports.
- For production environments:
  - Prefer Standard Load Balancer for advanced features and reliability.
  - Enable diagnostics and configure monitoring for visibility and alerting.

---

# Troubleshooting

- **VMSS not reachable:**
  - Check NSG rules and Load Balancer probe configuration.
- **NGINX/IIS not running:**
  - Verify cloud-init or custom script execution on VMSS instances.
- **Azure CLI errors:**
  - Ensure Azure CLI is updated (`az upgrade`).

---

For more details on each component and best practices, refer to additional documentation in this folder.
