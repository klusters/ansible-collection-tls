# Ansible Collection - klusters.tls
[Inspired by ericsysmin.tls](https://galaxy.ansible.com/ericsysmin/system)

Ansible collection that holds roles, that can be used to configure TLS on Linux system. 

## Roles

| Role      | Build Status                                                                                                                                                                                                                                                        | Documentation                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
|  encrypt_private_keys   | ![klusters.tls.encrypt_private_keys](https://github.com/klusters/ansible-collection-tls/workflows/klusters.tls.encrypt_private_keys/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-tls/tree/master/roles/encrypt_private_keys)    |
|  keystores   | ![klusters.tls.keystores](https://github.com/klusters/ansible-collection-tls/workflows/klusters.tls.keystores/badge.svg)          | [Documentation](https://github.com/klusters/ansible-collection-tls/tree/master/roles/keystores)    |

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

## Testing

Testing is done through GitHub Actions, and can be tested locally as well.

To be able to test locally:
- install docker 
- install [nektos/act](https://github.com/nektos/act)
- download the huge docker image (18GB) : [nektos/act-environments-ubuntu:18.04](https://hub.docker.com/r/nektos/act-environments-ubuntu/tags)

For example, on MacOS:
```bash
brew cask install docker

brew install act

open /Applications/Docker.app
docker pull nektos/act-environments-ubuntu:18.04
```

Each workflow pertains to a single role, and can be launched locally using the following command:

```bash
act -W .github/workflows/<WORKFLOW_FILE_TO_RUN> \
-P ubuntu-latest=nektos/act-environments-ubuntu:18.04
```