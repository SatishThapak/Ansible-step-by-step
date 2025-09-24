# 🚀 Ansible Overview

Ansible provides open-source automation that reduces complexity and runs everywhere. Using Ansible lets you automate virtually any task.

---

## ✅ Common Use Cases

1. Eliminate repetition and simplify workflows  
2. Manage and maintain system configuration  
3. Continuously deploy complex software  
4. Perform zero-downtime rolling updates  

---

## 📜 How It Works

Ansible uses simple, human-readable scripts called **playbooks** to automate tasks.  
You declare the desired state of a local or remote system in your playbook, and Ansible ensures the system remains in that state.

---

## 🧠 Core Principles of Ansible

### 1. Agent-less Architecture
- No need to install additional software across your infrastructure.
- Uses SSH for communication.

### 2. Simplicity
- Playbooks use straightforward YAML syntax.
- Code reads like documentation.
- Decentralized access using existing OS credentials.

### 3. Scalability and Flexibility
- Modular design supports:
  - Multiple operating systems
  - Cloud platforms
  - Network devices

### 4. Idempotence and Predictability
- Ensures consistent system state.
- Re-running playbooks doesn’t cause unintended changes.


---

## 🔑 Key Concepts

- **Inventory**: Lists target hosts (static or dynamic).
- **Playbooks**: YAML files defining tasks and configurations.
- **Tasks**: Individual actions executed on hosts.
- **Modules**: Built-in tools for system operations (e.g., file, package, service).
- **Roles**: Structured, reusable playbook components (tasks, vars, handlers).

---

## 🛠️ Installation of Ansible

### Install via APT
```bash
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible

## Configure Inventory

sudo nano /etc/ansible/hosts
ansible-inventory --list -y

[servers]
server1 ansible_host=<Public IP>
server2 ansible_host=<Public IP>
server3 ansible_host=<Public IP>

[all:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/<file>


## ⚡ Ad-Hoc Commands vs Modules

Ad-Hoc Commands
ansible all -a "df -h" -u ubuntu
ansible servers -a "uptime" -u ubuntu

Modules
ansible all -m ping -u ubuntu
