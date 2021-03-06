Truststores
=========

Manage PKCS12 and Java Truststores

Requirements
------------

Private key exists

Role Variables
--------------

```yaml
tls_base_path: /etc/tls/default

tls_cacerts_path: '{{ tls_base_path }}/cacerts'
tls_keys_path: '{{ tls_base_path }}/keys'
tls_jks_path: '{{ tls_base_path }}/java'

tls_cacert: '{{ tls_cacerts_path }}/{{ ansible_fqdn }}.ca'
tls_key: '{{ tls_keys_path }}/{{ ansible_fqdn }}.key'

tls_key_encrypted: '{{ tls_keys_path }}/{{ ansible_fqdn }}_encrypted.key'
tls_jks_truststore: '{{ tls_jks_path }}/{{ ansible_fqdn }}-truststore.jks'

tls_key_password: 'default'
tls_jks_truststore_password: 'default'

tls_truststore_owner: root
tls_truststore_group: root
```

Example Playbook
----------------

```yaml
- hosts: localhost
  connection: local
  roles:
  - role: klusters.tls.truststores
```

License
-------

MIT

Author Information
------------------

http://fathallah.fr
