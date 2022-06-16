# Ansible role for default-deny Squid Proxy

See repository root for license information.

This Ansible role automates the deployment of a squid proxy server
configured to deny all traffic by default. Allowed domains are
specified manually. This is useful for providing access from secure
environments to specific endpoints via an HTTP proxy server.

## Usage

From within an Ansible playbook, the role can be utilised like so:

```
---

- hosts: all
  roles:
    - role: hic.squid
      vars:
        allowed_domains:
          - example.com
```

## Molecule tests

From within the role directory, a series of tests can be run against
the role. This requires docker to be installed and configured.

```
molecule converge
molecule verify
molecule destroy
```

