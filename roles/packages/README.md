Packages
=========

Install Cryptography packages needed by ansible to manage private keys, csr, certificates, pkcs12 and keystores / truststores 

Requirements
------------

Package repositories reachable

Role Variables
--------------

```yaml
install_sys_packages: yes
install_tls_packages: yes
install_jdk_packages: yes
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.tls.packages
```

License
-------

MIT

Author Information
------------------

http://fathallah.fr
