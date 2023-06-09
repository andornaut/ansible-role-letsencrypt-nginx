# ansible-role-letsencrypt-nginx

An [Ansible](https://www.ansible.com/) role that provisions [NGINX HTTP server](https://www.nginx.com)
on Ubuntu and manages auto-renewal of HTTPS certificates using
[Let's Encrypt](https://letsencrypt.org/).

## Requirements

* [Ansible](https://www.ansible.com/) >= 2.9.0
* community.crypto collection: `ansible-galaxy collection install community.crypto`

## Variables

See [default values](./defaults/main.yml).

### Example configuration

Be sure to set `letsencryptnginx_acme_directory_url` for production use.

```
letsencryptnginx_account_email: info@example.com

# Production URL
letsencryptnginx_acme_directory_url: https://acme-v02.api.letsencrypt.org/directory

letsencryptnginx_websites:
  # Return 404
  - domain: subdomain.example.com
    use_snakeoil_certificate: true

  - domain: example.com
    repo: https://github.com/andornaut/example.com.git

  - domain: httpbasic.example.com
    http_basic_authentication:
      allowed_networks:
        - 192.168.0.0/16
      credentials:
        - username: hello
          password: world
    locations:
      - src: /nas
        dest: /media/nas

  - domain: proxy.example.com
    cloudflare_api_token: token
    cloudflare_api_zone: example.com
    csr_commonName: *.example.com
    proxy_port: 8123
    proxy_redirect_http: False
    proxy_remove_authorization_header: False
    websocket_path: /api/websocket
```
