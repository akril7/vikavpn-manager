# Ansible Role: sudoku-endpoint

Deploy and configure Sudoku proxy endpoint.

The role:

- installs Sudoku binary
- creates server configuration
- installs systemd service
- enables and starts Sudoku service

## Variables

| Variable | Description | Default |
|---|---|---|
| `sudoku.install_dir` | Installation directory | `/opt/sudoku` |
| `sudoku.transport` | Transport protocol | required |
| `sudoku.port` | Listen port | required |
| `sudoku.fallback_port` | Fallback service port | required |
| `sudoku.public_key` | Public key for endpoint | required |

## Result

Installation directory:

```
/opt/sudoku
```

Configuration:

```
/opt/sudoku/server.json
```

Service:

```
sudoku.service
```
