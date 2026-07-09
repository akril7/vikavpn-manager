# Ansible Role: fileserver

Deploy a simple Nginx-based file server with HTTPS support.

The role:

- installs and enables Nginx
- configures HTTPS virtual host
- creates storage directory
- serves files through a configurable URL prefix
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
| `fileserver.name` | Server page title | `File Server` |
| `fileserver.prefix` | URL prefix for files | `files` |
| `fileserver.dir` | Directory with files | `/opt/fileserver` |
| `fileserver.port` | HTTPS listen port | `443` |


## Result

Files are available at:

```
https://example.com/files/<filename>
```
