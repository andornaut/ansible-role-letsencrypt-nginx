# ansible-role-letsencrypt

An [Ansible](https://www.ansible.com/) role that can be used to register and renew HTTPS certificates using
[Let's Encrypt](https://letsencrypt.org/).

## Variables

See [default values](./defaults/main.yml).

### Example configuration

```
account_email: info@example.com
acme_directory: https://acme-v01.api.letsencrypt.org/directory
websites:
  - domain: example.com
  - domain: subdomain.example.com
```
