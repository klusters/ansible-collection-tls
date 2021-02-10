Encrypt private keys
=========

Add passphrase to existing private keys

Requirements
------------

Private key exists

Role Variables
--------------

```yaml
tls_base_path: /etc/tls/default
tls_keys_path: '{{ tls_base_path }}/keys'
tls_key_password: 'default'
tls_key: '{{ tls_keys_path }}/{{ ansible_fqdn }}.key'
tls_key_encrypted: '{{ tls_keys_path }}/{{ ansible_fqdn }}_encrypted.key'
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.tls.encrypt_private_keys
```

License
-------

MIT

Author Information
------------------

http://fathallah.fr
