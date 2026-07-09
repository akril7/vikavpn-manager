# Ansible Role: fakesite

Deploy a simple Nginx HTTPS site with a static `index.html`.

The role:

- installs Nginx
- deploys a static page
- configures HTTPS virtual host
- uses certificates from the `certificates` role

## Dependencies

This role requires:

```
dependencies:

* role: certificates
```

## Variables

| Variable        | Description                | Default                    |
| --------------- | -------------------------- | -------------------------- |
| `fakesite.path` | Path to website index file | `/var/www/html/index.html` |
| `fakesite.port` | HTTPS listen port          | `443`                      |

