# ftp-web-stack
A simple docker compose stack that declares both an web and a ftp service. 

This stack uses Docker images that are based on Alpine Linux making them small as possible.
The default config will share the **/var/www/html** folder on the host with the ngnix container and also with the ftp service, hence making any content uploaded to the ftp service also available over http becuse the nginx service will expose that same folder.
Please notice the **USERS** and **ADDRESS** environment variables on the ftp service:

USERS=john.doe|12345678|/var/www/html

ADDRESS=ftp.example.com 

More info, please see [delfer-alpine](https://github.com/delfer/docker-alpine-ftp-server) docs.

## Usage:
```
git clone https://github.com/raonigabriel/ftp-web-stack.git
cd ftp-web-stack
docker-compose up -d
```

## Reference:
https://hub.docker.com/_/nginx

https://hub.docker.com/r/delfer/alpine-ftp-server
