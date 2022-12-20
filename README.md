# Docker-nginx-mailine 📦
A custom docker image with added modules to run Nginx server.

# Featury bits & pieces 🪡

Based on the [nginx-alpine-slim](https://hub.docker.com/_/nginx) official docker image.

Added modules such as:

- [ngx_brotli](https://github.com/google/ngx_brotli)
- [ngx_fancyindex](https://github.com/aperezdc/ngx-fancyindex)
- [ngx_http_auth_pam_module](https://github.com/sto/ngx_http_auth_pam_module)

# Docker Compose configuration:
>This is an example config
```
version: "3"

services:
  doh-server:
    image: snowy68/nginx-mailine:latest
    container_name: nginx
    restart: unless-stopped
    ports:
      - "80:80/tcp"
    volumes:
      - './nginx:/etc/nginx'
      - '/etc/passwd:/etc/passwd:ro'
```
# TODO
- [ ] Support for arm64