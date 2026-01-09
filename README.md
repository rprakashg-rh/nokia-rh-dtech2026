# nokia-rh-dtech2026
All artifacts used for nokia demo for dtech 2026

## Pre-Requisistes
Provision an image builder host

Install [vpac](https://github.com/rprakashg/vpac) ansible collection by running command below

```sh
ansible-galaxy collection install  git+https://github.com/rprakashg/vpac.git,main
```

Create an ansible inventory file and add snippet below, replace with specific parameters 

```yaml
---
all:
  hosts:
    imagebuilder:
      ansible_host: "<replace>"
      ansible_port: 22
      ansible_user: "<replace>"
      ansible_ssh_private_key_file: "<replace>"
```

Configure the Image Builder host by running ansible playbook below

```sh
ansible-playbook -i inventory setup_imagebuilder.yml
```

## Building ISO
Create a customized RHEL 9.7 ISO to provision host machine.
 

## Configuring the host for deploying and running realtime workloads
Steps to prepare and configure the host for running realtime workload like ABB SSC600SW is automation using ansible. Execute the ansible playbook

```sh
ansible-playbook -i inventory --vault-password-file <(echo "$VAULT_SECRET") configure_system.yml -e @vars/nokia.yml
```

## Deploy SSC600 VM
Run ansible playbook to deploy SSC600 virtual machine on KVM

```sh
ansible-playbook -i inventory deploy_ssc600_vm.yml -e @vars/nokia.yml
```
