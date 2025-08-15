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
- A configured inventory file (hosts.ini) with reachable hosts

#### hosts.ini (inside inventories/dev):
```
[ubuntu_target]
192.168.56.102 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
```

## 📦 Installation
Clone this repository:
```
git clone https://github.com/Yagna3903/Ansible-devops-toolbox.git
cd Ansible-devops-toolbox
```
#### Install required roles (if not already present):
```
ansible-galaxy install -r requirements.yml
```

## ▶️ Usage
### 1. Test Connectivity
```
ansible-playbook -i inventories/dev/hosts.ini playbooks/ping.yml
```
### 2. Run Full Setup
```
ansible-playbook -i inventories/dev/hosts.ini playbooks/site.yml --ask-become-pass
```

## 📜 Roles Overview
| Role              | Description                                  |
| ----------------- | -------------------------------------------- |
| **firewall**      | Configures `ufw` rules for system security   |
| **nginx**         | Installs and configures the Nginx web server |
| **ssh-hardening** | Implements secure SSH configurations         |
| **users**         | Creates and manages system users             |
| **webapp**        | Deploys and serves a sample web application  |

## 🖼 Example Output
#### Running the full playbook:
<img width="1564" height="1111" alt="image" src="https://github.com/user-attachments/assets/47ad5d69-34f0-4d1e-99ad-f5f5bb8202b2" />

