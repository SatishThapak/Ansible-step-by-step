## Create a Role Structure
Roles help you organize tasks, variables, templates, and handlers. You can create a role manually or use Ansible’s built-in command.

ansible-galaxy init nginx

This creates a directory structure like:

nginx/
├── defaults/
│   └── main.yml
├── files/
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
├── tests/
│   └── inventory
│   └── test.yml
├── vars/
│   └── main.yml


## 📝 Example: nginx/tasks/main.yml

- name: Install nginx
  apt:
    name: nginx
    state: present

- name: Start nginx
  service:
    name: nginx
    state: started
    enabled: yes


## 📜 Use the Role in a Playbook

- name: Configure web servers
  hosts: webservers
  become: yes
  roles:
    - nginx


