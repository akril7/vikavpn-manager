# Ansible Role: mita

Install and configure Mita VPN service.

The role:

- installs Mita package
- creates service configuration
- configures users and port bindings
- enables and starts the Mita service


## Variables

| Variable | Description | Default |
|---|---|---|
| `mita.port_range` | Port range for Mita connections | required |
| `mita.protocol` | Transport protocol | required |
| `vpn.users` | List of VPN users | required |


## Result

Configuration file:

```
/etc/mita/mita.json

```

Service:

```
mita.service

```

