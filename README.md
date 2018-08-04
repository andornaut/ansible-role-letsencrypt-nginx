# ansible-role-letsencrypt-nginx

An [Ansible](https://www.ansible.com/) role that provisions [NGINX HTTP server](https://www.nginx.com) 
on Ubuntu and manages auto-renewal of HTTPS certificates using
[Let's Encrypt](https://letsencrypt.org/).

## Variables

See [default values](./defaults/main.yml).

### Example configuration

```
letsencryptnginx_account_email: info@example.com
letsencryptnginx_acme_directory_url: https://acme-v01.api.letsencrypt.org/directory
letsencryptnginx_websites:
  - domain: example.com
  - domain: subdomain.example.com
```
