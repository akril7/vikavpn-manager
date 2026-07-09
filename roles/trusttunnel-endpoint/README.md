# Ansible Role: trusttunnel-endpoint

Deploy and configure TrustTunnel endpoint.

The role:

- installs TrustTunnel binary
- creates endpoint configuration
- configures users authentication
- installs systemd service
- uses certificates from the `certificates` role

## Dependencies

This role requires:

```

dependencies:

* role: certificates

```

## Variables

| Variable | Description | Default |
|---|---|---|
| `trusttunnel.install_dir` | Installation directory | `/opt/trusttunnel` |
| `trusttunnel.port` | Listen port | required |
| `trusttunnel.metrics_port` | Metrics port | `35553` |
| `vpn.users` | List of VPN users | required |
| `certificates.domain` | Server domain name | required |

## Result

Installation directory:

```

/opt/trusttunnel

```

Configuration files:

```

/opt/trusttunnel/credentials.toml
/opt/trusttunnel/hosts.toml
/opt/trusttunnel/vpn.toml

```

Service:

```

trusttunnel.service

```
