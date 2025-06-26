# Multi-Distro Webstack Ansible

A flexible, distro-agnostic Ansible playbook for deploying a basic web stack (Apache, PHP, MariaDB) across multiple Linux distributions. Designed for tinkerers, sysadmins, and anyone who wants to automate web server provisioning without being locked into a single OS family.

## ✨ Features

- Supports Debian/Ubuntu and RedHat/CentOS-based systems
- Installs and configures Apache, PHP, and MariaDB
- Uses `include_vars` and conditional logic to handle distro-specific differences
- Modular role structure for easy customization and reuse
- Minimal dependencies, maximum portability

## 📁 Directory Structure

```
multi-distro-webstack-ansible/
├── group_vars/
│   └── all.yml
├── host_vars/
│   └── yourhost.yml
├── inventory/
│   └── hosts.ini
├── roles/
│   ├── apache/
│   ├── mariadb/
│   └── php/
├── site.yml
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Ansible 2.10+
- SSH access to target hosts
- Sudo privileges on remote machines

### Inventory Setup

Edit `inventory/hosts.ini`:

```ini
[webservers]
debian1 ansible_host=192.168.1.10 ansible_user=youruser
centos1 ansible_host=192.168.1.11 ansible_user=youruser
```

### Run the Playbook

```bash
ansible-playbook -i inventory/hosts.ini site.yml
```

## 🧠 How It Works

Each role uses `include_vars` to load OS-specific variables:

```yaml
- name: Load OS-specific vars
  include_vars: "{{ ansible_os_family }}.yml"
```

This allows you to define package names, service names, and config paths per distro in `vars/`.

## 🛠️ Customization

Want to swap Apache for Nginx? Add a new role and update `site.yml`. Need to support Arch or Alpine? Just drop in a new vars file and you're good to go.

## 📜 License

MIT — use it, fork it, break it, fix it.

---

Built with 🧠 and a bit of bash history. Contributions welcome.

