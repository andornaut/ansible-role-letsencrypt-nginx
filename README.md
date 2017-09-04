# ansible-role-letsencrypt

Register and renew HTTPS certificates using [Let's Encrypt](https://letsencrypt.org/).

## Variables

```
account_email: info@example.com
acme_directory: https://acme-v01.api.letsencrypt.org/directory
websites:
  - domain: example.com
  - domain: subdomain.example.com
```
