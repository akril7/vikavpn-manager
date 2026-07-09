# Ansible Role: Bootstrap Server

Ansible role for initial server bootstrap and basic hardening.

The role performs:

- root password configuration
- creation of SSH user
- SSH public key installation for root
- SSH daemon configuration
- enabling BBR


## Role Variables

The role expects two main variable groups:

- `bootstrap`
- `bootstrap_secret`

Example:

```yaml
bootstrap:
  ssh:
    user: user
    port: 2222
    authorized_keys:
      - ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIxxxxxxxx user@example

bootstrap_secret:
  root_password_hash: "$6$xxxxxxxxxxxxxxxx"
  ssh_user_password_hash: "$6$xxxxxxxxxxxxxxxx"
