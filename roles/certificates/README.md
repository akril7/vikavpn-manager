# Ansible Role: certificates

Deploy SSL/TLS certificates and private keys to remote hosts.


## Variables

| Variable                  | Description                   | Default    |
| ------------------------- | ----------------------------- | ---------- |
| `certificates.domain`     | Certificate domain name       | required   |
| `certificates.remote_dir` | Remote certificates directory | `/etc/ssl` |
| `certificates.local_dir`  | Local certificates directory  | `certs`    |
| `certificates.cert_file`  | Certificate filename          | `cert.pem` |
| `certificates.key_file`   | Private key filename          | `key.pem`  |


## Expected local structure

certs/
└── example.com/
    ├── cert.pem
    └── key.pem


## Result

Files will be copied to:

/etc/ssl/example.com/
├── cert.pem
└── key.pem
