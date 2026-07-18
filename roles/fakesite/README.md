# Ansible Role: fakesite

Deploy a simple Nginx HTTPS site with a static `index.html`.

The role:

- installs Nginx
- deploys a static page
- can use certificates from the `certificates` role for https

## Dependencies

Optional:

```
* role: certificates
```

## Variables

| Variable        | Description                | Default                    |
| --------------- | -------------------------- | -------------------------- |
| `fakesite.path` | Path to website index file | `/var/www/html/index.html` |
| `fakesite.port` | listen port                | required                   |

