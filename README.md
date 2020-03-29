# ansible-role-letsencrypt-nginx

An [Ansible](https://www.ansible.com/) role that provisions [NGINX HTTP server](https://www.nginx.com) 
on Ubuntu and manages auto-renewal of HTTPS certificates using
[Let's Encrypt](https://letsencrypt.org/).

## Requirements

* [Ansible](https://www.ansible.com/) >= 2.8.0

## Variables

See [default values](./defaults/main.yml).

### Example configuration

Be sure to set `letsencryptnginx_acme_directory_url` for production use.

```
letsencryptnginx_account_email: info@example.com
# Production URL
letsencryptnginx_acme_directory_url: https://acme-v02.api.letsencrypt.org/directory
letsencryptnginx_websites:
  - domain: example.com
  - domain: subdomain.example.com
```
