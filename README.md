# VPN Server Ansible Deployment

Ansible project for automated deployment and configuration of a personal VPN server.

The project installs and configures:

- server bootstrap and SSH hardening
- SSL certificates deployment
- Nginx file server
- Sudoku proxy endpoint
- Mita VPN service
- TrustTunnel endpoint
- Mihomo client configurations

## Features

- Full server provisioning with Ansible
- Multiple VPN protocols behind a single server
- Automatic TLS certificate deployment
- User-based VPN configuration generation
- Nginx-based subscription/file delivery
- Systemd service management
- Secrets support through Ansible Vault

## Project Structure

```

.
├── inventories/
│   ├── hosts.ini
│   └── group_vars/
│       ├── bootstrap/
│       └── vpn_servers/
│
├── roles/
│   ├── bootstrap/
│   ├── certificates/
│   ├── fakesite/
│   ├── fileserver/
│   ├── mihomo/
│   ├── mita/
│   ├── sudoku/
│   └── trusttunnel/
│
├── files/
    └── certs/

```

## Roles

| Role | Description |
|---|---|
| `bootstrap` | Initial server setup, SSH configuration, BBR tuning |
| `certificates` | Deploy SSL certificates and private keys |
| `fakesite` | Configure HTTPS landing page |
| `fileserver` | Configure Nginx file/subscription server |
| `sudoku` | Deploy Sudoku proxy endpoint |
| `mita` | Deploy Mita VPN service |
| `trusttunnel` | Deploy TrustTunnel endpoint |
| `mihomo` | Generate Mihomo client configurations |

## Dependencies

Role dependencies:

```

fakesite
└── certificates

fileserver
└── certificates

trusttunnel
└── certificates

mihomo
└── fileserver

```

## Inventory

Example:

```

inventories/
├── hosts.ini
└── group_vars/
├──── bootstrap/
│   ├─ bootstrap.yml
│   └─ secret.yml
│
└──── vpn_servers/
├───── vpn.yml
└───── users.yml

```

Example hosts:

```

[bootstrap]
server1 ansible_host=203.0.113.10

[vpn_servers]
server1 ansible_host=203.0.113.10

```

## Variables

### Server configuration

See:

```

groups_vars/vpn_secrets/vpn.yml

```

### Users

VPN users are defined in:

```

group_vars/vpn_servers/users.yml

```

## Certificates

Certificates are stored locally:

```

files/
└── certs/
└──── vpn.example.com/
├────── cert.pem
└────── key.pem

```

They are deployed by the `certificates` role.

Private keys should never be committed to Git.

## Deployment

Run deployment:

```

ansible-playbook -i inventories/hosts.ini site.yml

```

## Services

After deployment the following services are configured:

| Service | Description |
|---|---|
| `nginx` | HTTPS file server |
| `sudoku` | Sudoku proxy endpoint |
| `mita` | Mita VPN service |
| `trusttunnel` | TrustTunnel endpoint |

## Generated Files

Mihomo configurations:

```

/opt/fileserver/<user.uuid>.yaml

```

Certificates:

```

/etc/ssl/<domain>/

```

Mita configuration:

```

/etc/mita/mita.json

```

TrustTunnel configuration:

```

/opt/trusttunnel/

```

Sudoku configuration:

```

/opt/sudoku/server.json

```

## Example Client Configuration URL

Mihomo subscriptions are available through:

```

https://vpn.example.com/sub/<user.uuid>

```

