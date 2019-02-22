ansible-role-amazon-cloudwatch-agent
======

This role will install the AWS CloudWatch Agent on Ubuntu (64-bit, trusty).
- config and credentials are stored in /root/.aws/
- the process runs as a priviledged user

Variables
------

### aws_cwa_region
(Optional) AWS region.  Defaults to "eu-west-1".
```
aws_cwa_region: "eu-west-1"
```

### aws_cwa_key_access
AWS access key
```
aws_cwa_key_access: (encrypted)ACCESSKEYGOESHERE
```

### aws_cwa_key_secret
AWS secret key
```
aws_cwa_key_secret: (encrypted)SECRETKEYGOESHERE
```

#### It's recommended that you declare `aws_cwa_key_access` and `aws_cwa_key_secret` in either a vault-encypted var file, or as vault-encrypted strings within a var file.



### aws_cwa_namespace
The namespace prefix for the namespace in which your metrics will reside (e.g. 'airtel_tz/host1').
```
aws_cwa_namespace_prefix: "airtel_tz"
```

Example Playbook
------

```
---
- hosts: all
  become: yes
  become_user: root
  roles:
  - ansible-role-amazon-cloudwatch-agent
```


Example Dir Structure
------

```
.
├── group_vars
│   └── all.yml
├── inventory
├── main.yml
└── roles
    └── ansible-role-amazon-cloudwatch-agent
        ├── README.md
        └── tasks
            ├── main.yml
```

Forked from ansible role by [tgam-abarrett][url]

[url]: https://github.com/globeandmail/ansible-role-amazon-cloudwatch-agent
