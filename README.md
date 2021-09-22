# Ansible Collection - klusters.tls
[Inspired by ericsysmin.system](https://galaxy.ansible.com/ericsysmin/system)

Ansible collection that holds roles, that can be used to configure TLS on Linux system. 

## Roles

| Role      | Build Status                                                                                                                                                                                                                                                        | Documentation                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
|  encrypt_private_keys   | ![klusters.tls.encrypt_private_keys](https://github.com/klusters/ansible-collection-tls/workflows/klusters.tls.encrypt_private_keys/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-tls/tree/master/roles/encrypt_private_keys)    |
|  keystores   | ![klusters.tls.keystores](https://github.com/klusters/ansible-collection-tls/workflows/klusters.tls.keystores/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-tls/tree/master/roles/keystores)    |
|  truststores   | ![klusters.tls.truststores](https://github.com/klusters/ansible-collection-tls/workflows/klusters.tls.truststores/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-tls/tree/master/roles/truststores)    |
|  packages   | ![klusters.tls.packages](https://github.com/klusters/ansible-collection-tls/workflows/klusters.tls.packages/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-tls/tree/master/roles/packages)    |

## Usage

You can find specific to each role within the "Documentation" link for each role. However, most should be in this format:

Install this ansible collection :
```bash
ansible-galaxy collection install klusters.tls
```

Write a playbook file *playbook_name.yml* :

```yaml
---
- hosts: localhost

  tasks:
    - include_role:
        name: klusters.tls.<role_name>
```

Run *playbook_name.yml* :
```bash
ansible-playbook playbook_name.yml
```

## Looping support
See [ansible-tls-klusters](https://github.com/klusters/ansible-tls-klusters) project

Take a look at inventories/``**``/group_vars to see variables related to this collection 

Take a look at playbooks/``**``/keystores.yml to see executions related to this collection

## Testing

Testing is done through GitHub Actions, and can be tested locally as well.

To be able to test locally:
- install docker
- install dependencies

For example, on MacOS:
```bash
brew cask install docker

open /Applications/Docker.app

pip install --upgrade --upgrade-strategy eager -r molecule/common/python_requirements.txt
```

Each role can be launched locally using the following command:

```bash
export MOLECULE_DISTRO=<DISTRO> # Tested with centos:7, centos:8, ubuntu:18.04, ubuntu:20.04

molecule test -s <SCENARIO> # ls molecule 
```