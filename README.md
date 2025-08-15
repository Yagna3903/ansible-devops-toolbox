# Ansible DevOps Toolbox

A robust, production-grade Ansible project designed to automate server provisioning, configuration, and application deployment.  
This repository follows a clean, modular structure and uses **Ansible best practices** with separate inventories, roles, and playbooks, making it scalable and maintainable for real-world DevOps workflows.

---

## 📂 Project Structure

```plaintext
Ansible-devops-toolbox/
│
├── ansible.cfg                  # Central Ansible configuration file
├── inventories/                 # Environment-specific inventory files
│   └── dev/
│       └── hosts.ini             # Inventory for the development environment
│
├── playbooks/                    # Main playbooks and variable files
│   ├── group_vars/
│   │   └── ubuntu_target.yml     # Host group variables
│   ├── ping.yml                  # Connectivity test playbook
│   └── site.yml                  # Main execution playbook
│
└── roles/                        # Modular Ansible roles (from Ansible Galaxy)
    ├── firewall                  # Configures and manages firewall rules
    ├── nginx                     # Installs and configures Nginx
    ├── ssh-hardening             # Secures SSH configurations
    ├── users                     # Manages system users and groups
    └── webapp                    # Deploys a sample web application
```
### 🚀 Features

- Modular Role Structure – Easily plug, replace, or reuse roles across environments.
- Environment-Specific Inventories – Supports dev, staging, and production setups.
- Security Best Practices – Includes SSH hardening and firewall rules.
- Automated Web Deployment – Installs Nginx and deploys a basic web application.
- User Management – Creates and configures user accounts with proper permissions.

### 🛠 Prerequisites

- Before running this project, ensure you have:
- Ansible 2.15+
- Python 3.x
- SSH access to target nodes
