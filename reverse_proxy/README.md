# Ansible role for ingress only reverse proxy

See repository root for license information.

This Ansible role automates the deployment of an nginx reverse proxy,
configured to proxy traffic to GitHub. This allows us to define some
rules to prevent data egress via git push, while still supporting
clone, pull and fetch etc.

We chose not to use Squid for this as HTTPS traffic through a proxy
server uses direct TCP connect. We want to avoid this as it could open
up other security holes, e.g. by potentially allowing connectivity via
SSH, which would be harder to filter.

There are plans to integrate this with ClamAV for real-time scanning
of repo blobs.

## Usage

From within an Ansible playbook, the role can be utilised like so:

```
---

- hosts: all
  roles:
    - role: hic.reverse_proxy
```

## Molecule tests

From within the role directory, a series of tests can be run against
the role. This requires docker to be installed and configured.

```
molecule converge
molecule verify
molecule destroy
```

