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
tls_jks_path: '{{ tls_base_path }}/java'
tls_p12_path: '{{ tls_base_path }}/pkcs12'

tls_cert: '{{ tls_certs_path }}/{{ ansible_fqdn }}.cert'
tls_key: '{{ tls_keys_path }}/{{ ansible_fqdn }}.key'
tls_key_encrypted: '{{ tls_keys_path }}/{{ ansible_fqdn }}_encrypted.key'
tls_jks_keystore: '{{ tls_jks_path }}/{{ ansible_fqdn }}.jks'
tls_p12_keystore: '{{ tls_p12_path }}/{{ ansible_fqdn }}.pkcs12'

tls_keys_password: 'default'
tls_jks_password: 'default'
tls_p12_password: 'default'

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
