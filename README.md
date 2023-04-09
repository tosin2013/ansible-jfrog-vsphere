# Deploy JFrog to vSphere on Fedora CoreOS

[![JFrog CI testing for Fedora](https://github.com/tosin2013/ansible-jfrog-vsphere/actions/workflows/jfrog-ci-test.yml/badge.svg)](https://github.com/tosin2013/ansible-jfrog-vsphere/actions/workflows/jfrog-ci-test.yml)

## Prerequisites

- Install Ansible: `python3 -m pip install ansible`
- Install needed pip modules: `python3 -m pip install -r ./requirements.txt`
- Install needed Ansible Collections: `ansible-galaxy collection install -r ./collections/requirements.yml`

## Copy and Modify the Variables

```bash
cp example.vars.yml vars.yml

nano vars.yml
```

## Deploy JFrog to FCOS VM

```bash
ansible-playbook -e "@vars.yml" 1_bootstrap.yml
```

## Delete FCOS VM from vSphere

```bash
ansible-playbook -e "@vars.yml" 9_destroy.yml
```