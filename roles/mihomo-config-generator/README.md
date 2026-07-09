# Ansible Role: mihomo

Generate Mihomo client configurations for VPN users and publish them through the file server.

The role:

- generates individual Mihomo configs for each VPN user
- configures proxies, DNS, proxy groups and routing rules
- stores generated configs in the `fileserver` directory

## Dependencies

This role requires:

```

dependencies:

* role: fileserver

```

## Variables

| Variable | Description | Default |
|---|---|---|
| `vpn.users` | List of VPN users | required |
| `fileserver.dir` | Directory for generated configs | from `fileserver` role |
| `certificates.domain` | Server domain name | required |
| `sudoku.port` | Sudoku proxy port | required |
| `mita.port_range` | Mieru port range | required |
| `mita.protocol` | Mieru transport protocol | required |
| `trusttunnel.port` | TrustTunnel port | required |


## Result

Configuration files are generated for each user:

```
{{ fileserver.dir }}/<user.uuid>.yaml
```

Example:

```
/opt/fileserver/550e8400-e29b-41d4-a716-446655440000.yaml
```

