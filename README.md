# ansible-docs

My hands-on experience with Ansible (all videos available on my YouTube channel for this playbook).

Automation for Everything, Everyone, Everywhere.

## What is Ansible

Ansible is an open source configuration management, provisioning, application deployment, security, and orchestration tool.

## Install Ansible

See the [official installation guide](https://docs.ansible.com/projects/ansible/latest/installation_guide/installation_distros.html).

You need Python 2.7 or Python 3.

```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

You can also install via pip, yum (needs epel-release), dnf, etc.

## Why Ansible?

Simple, agentless (uses SSH, or WinRM for Windows), flexible, efficient, fast, reliable, and repeatable.

You never touch a server manually — every change is defined in a playbook and applied automatically.

Point Ansible at a new server and it's ready — no manual setup, updates, or patching required.

Think about it: how would you install one package across 1500 VMs by hand? With Ansible, it's a single command.

## Ansible Architecture

- **Inventory**: the file listing the machines Ansible manages (default `/etc/ansible/hosts`). Each entry is a **host** (a DNS name or IP), and hosts can be organized into **groups** so you can target them together.
- **Host**: a single target machine, identified by DNS name or IP address.
- **Group**: a named set of hosts, e.g. all your web servers:
  ```
  [webservers]
  server-1
  server-2
  ```
- **Group of groups**: a group that contains other groups, using `:children`, e.g. one "servers" group covering both web and db servers:
  ```
  [servers:children]
  webservers
  dbservers
  ```
