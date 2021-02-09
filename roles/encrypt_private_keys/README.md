Encrypt private keys
=========

Add passphrase to existing private keys

Requirements
------------

Private key exists

Role Variables
--------------

```yaml
tls_base_path: /etc/tls
tls_keys_path: '{{ tls_base_path }}/keys'
tls_keys_password: 'default'
tls_key: "{{ tls_keys_path }}/{{ ansible_fqdn }}.key"
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
