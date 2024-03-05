# Ansible playbook: labocbz.deploy_kubernetes_cluster

![Licence Status](https://img.shields.io/badge/licence-MIT-brightgreen)
![CI Status](https://img.shields.io/badge/CI-success-brightgreen)
![Testing Method](https://img.shields.io/badge/Testing%20Method-Ansible%20Molecule-blueviolet)
![Testing Driver](https://img.shields.io/badge/Testing%20Driver-docker-blueviolet)
![Language Status](https://img.shields.io/badge/language-Ansible-red)
![Compagny](https://img.shields.io/badge/Compagny-Labo--CBZ-blue)
![Author](https://img.shields.io/badge/Author-Lord%20Robin%20Crombez-blue)

## Description

![Tag: Ansible](https://img.shields.io/badge/Tech-Ansible-orange)
![Tag: Debian](https://img.shields.io/badge/Tech-Debian-orange)
![Tag: SSL/TLS](https://img.shields.io/badge/Tech-SSL%2FTLS-orange)
![Tag: Docker](https://img.shields.io/badge/Tech-Docker-orange)
![Tag: Kubernetes](https://img.shields.io/badge/Tech-Kubernetes-orange)
![Tag: K3S](https://img.shields.io/badge/Tech-K3S-orange)
![Tag: Kubectl](https://img.shields.io/badge/Tech-Kubectl-orange)
![Tag: Kubeadm](https://img.shields.io/badge/Tech-Kubeadm-orange)
![Tag: Kubelet](https://img.shields.io/badge/Tech-Kubelet-orange)
![Tag: Apache2](https://img.shields.io/badge/Tech-Apache2-orange)

An Ansible playbook to deploy and configure a Kubernetes cluster on your hosts.


This playbook streamlines the installation and configuration of a comprehensive stack consisting of K3S, Docker, and Apache2. You have the flexibility to choose whether to install all components together or separately, depending on your requirements. Additionally, SSL deployment is seamlessly handled by the playbook, although it assumes pre-existing SSL content.

The playbook not only installs Apache as a web front-end server but also leverages the ingress controller and mesh routing capabilities provided by K3S. This setup allows for efficient traffic redirection to controllers and applications within the K3S environment. By utilizing these features, you can easily manage and scale your applications while ensuring high availability and reliability.

Whether you're deploying a simple web application or a complex microservices architecture, this playbook provides a streamlined solution for setting up and managing your infrastructure. With support for SSL deployment and integrated mesh routing, you can confidently deploy your applications while maintaining security and performance.

## Deployment diagramm

## Tests and simulations

### Basics

You have to run multiples tests. *tests with an # are mandatory*

```MARKDOWN
# lint
# syntax
# converge
# idempotence
# verify
side_effect
```

Executing theses test in this order is called a "scenario" and Molecule can handle them.

Molecule use Ansible and pre configured playbook to create containers, prepare them, converge (run the playbook) and verify its execution.
You can manage multiples scenario with multiples tests in order to get a 100% code coverage.

This playbook contains a ./tests folder. In this folder you can use the inventory or the tower folder to create a simualtion of a real inventory and a real AWX / Tower job execution.

### Command reminder

```SHELL
# Check your YAML syntax
yamllint -c ./.yamllint .

# Check your Ansible syntax and code security
ansible-lint --config=./.ansible-lint .

# Execute and test your playbook
molecule lint
molecule create
molecule list
molecule converge
molecule verify
molecule destroy

# Execute all previous task in one single command
molecule test
```

## Installation

To install this playbook, just copy/import this playbook or raw file into your fresh playbook repository or call it with the "include_playbook/import_playbook" module.

## Usage

### Vars

```YAML
# From inventory
---
# all vars from to put/from your inventory
# see tests/inventory/group_var for all groups and vars.
```

```YAML
# From AWX / Tower
---
all vars from to put/from AWX / Tower
```

## Architectural Decisions Records

Here you can put your change to keep a trace of your work and decisions.

### 2024-01-09: First Init

* First init of this playbook with the bootstrap_playbook playbook by Lord Robin Crombez

### 2024-03-02: Fix and CI

* Added support for new CI base
* Edit all vars with __
* Tested and validated on Docker
* temp

### 2024-03-05: New CI, imported K3S

* K3S installed
* Apache2 installed
* Docker installed
* Tested

## Authors

* Lord Robin Crombez

## Sources

* [Ansible playbook documentation](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_playbooks.html)
* [Ansible Molecule documentation](https://molecule.readthedocs.io/)
