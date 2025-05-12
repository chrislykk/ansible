# Ansible Training Project

This is a personal Ansible training repository designed to practice infrastructure automation concepts using Ansible playbooks, roles, and host-specific variables.

## 📦 Project Structure

ansible/
├── site.yml # Main playbook entry point
├── inventory # Inventory file listing target hosts
├── roles/ # Modular Ansible roles
├── host_vars/ # Host-specific variable definitions
└── README.md # Project documentation


## 🚀 Getting Started

### Prerequisites

- Ansible installed on your control node (host running the playbook)
- SSH access to the target machines
- Python installed on managed nodes (usually pre-installed)

### Running the Playbook

To execute the main playbook:

```bash
ansible-playbook -i inventory site.yml
```

🧱 Roles
Each role encapsulates related tasks, handlers, and variables for specific functions. Example:

base: baseline setup for all nodes

web_servers: installs and configures web services

db_servers: installs and configures MariaDB database services

file_servers: installs and configures samba services

📄 Host Variables
The host_vars/ directory defines per-host configurations. These override defaults and can be used to tailor deployments to specific machines.




---
