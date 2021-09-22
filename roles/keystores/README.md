Keystores
=========

Manage PKCS12 and Java Keystores

Requirements
------------

Private key exists

Role Variables
--------------

```yaml
tls_base_path: /etc/tls/default

tls_certs_path: '{{ tls_base_path }}/certs'
tls_keys_path: '{{ tls_base_path }}/keys'
tls_keystore_path: '{{ tls_base_path }}/java'

tls_cert: '{{ tls_certs_path }}/{{ ansible_fqdn }}.cert'
tls_key_encrypted: '{{ tls_keys_path }}/{{ ansible_fqdn }}_encrypted.key'

tls_keystore_type: jks
tls_keystore: '{{ tls_keystore_path }}/{{ ansible_fqdn }}.jks'
tls_keystore_alias: '{{ ansible_fqdn }}'

tls_key_password: 'default'
tls_keystore_password: 'default'

tls_keystore_owner: root
tls_keystore_group: root
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.tls.keystores
```

License
-------

MIT

Author Information
------------------

http://fathallah.fr
