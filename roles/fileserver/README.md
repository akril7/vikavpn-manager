# Ansible Role: fileserver

Deploy a simple Nginx-based file server with HTTPS support.

The role:

- installs and enables Nginx
- creates storage directory
- serves files through a configurable URL prefix
- can use certificates from the `certificates` role for https

## Dependencies

Optional:
```
* role: certificates
```


## Variables

| Variable | Description | Default |
|---|---|---|
| `fileserver.name` | Server page title | `File Server` |
| `fileserver.prefix` | URL prefix for files | `files` |
| `fileserver.dir` | Directory with files | `/opt/fileserver` |
| `fileserver.port` | listen port | required |


## Result

Files are available at:

```
https://example.com/files/<filename>
```
