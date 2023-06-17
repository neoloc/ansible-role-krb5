krb5 Role
=========

This role will install and configure the krb5 tools and krb5.conf file.

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-neoloc.sssdad-blue.svg)](https://galaxy.ansible.com/neoloc/ansible-role-sssdad/)


Requirements
------------

None

Role Variables
--------------

refer to default/main.yml file.

```yaml
krb5_configure: true
krb5_packages:
  - krb5-config
  - krb5-locales
  - krb5-user

krb5_kdc_timesync: 1
krb5_ccache_type: 4
krb5_forwardable: true
krb5_proxiable: true

krb5_default_realm: somedomain.tld
krb5_realms:
  somedomain.tld:
    kdc:
      - kdc01.somedomain.tld
      - kdc02.somedomain.tld
    admin_server: admin.somedomain.tld
    default_domain: somedomain.tld
    # master_kdc: kdc01.somedomain.local

kdc_domain_realms:
  somedomain.tld:
    - .somedomain.tld
    - somedomain.tld

krb5_default_tkt_enctypes:
  - aes256-cts-hmac-sha1-96
  - aes128-cts-hmac-sha1-96
  - rc4-hmac
krb5_default_tgs_enctypes:
  - aes256-cts-hmac-sha1-96
  - aes128-cts-hmac-sha1-96
  - rc4-hmac
krb5_permitted_enctypes:
  - aes256-cts-hmac-sha1-96
  - aes128-cts-hmac-sha1-96
  - rc4-hmac
```


Example Playbook
----------------

    - hosts: all
      roles:
         - neoloc.krb5

License
-------

See license.md

Author Information
------------------

[![Github](https://img.shields.io/badge/Github-neoloc-blue.svg)](https://github.com/neoloc)
