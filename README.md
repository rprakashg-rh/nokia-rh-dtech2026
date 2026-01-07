# nokia-rh-dtech2026
All artifacts used for nokia demo for dtech 2026

## Pre-Requisistes


## Building ISO


## Configuring the host for deploying and running realtime workloads
Steps to prepare and configure the host for running realtime workload like ABB SSC600SW is automation using ansible. Execute the ansible playbook

```sh
ansible-playbook -i inventory --vault-password-file <(echo "$VAULT_SECRET") configure_system.yml -e @vars/nokia.yml
```

## Deploy SSC600 VM


```sh
ansible-playbook -i inventory deploy_ssc600_vm.yml -e @vars/nokia.yml
```
