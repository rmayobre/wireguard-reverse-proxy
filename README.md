# Wireguard Reverse Proxy
An Nginx reverse proxy behind a Wireguard client connection. This comes with [Nginx Proxy Manager](https://github.com/jc21/nginx-proxy-manager) as an Web UI for managing proxy connections.

## Installation
Before installing, make sure you have [docker-compose](https://docs.docker.com/compose/install/) installed to your machine. 

Change the credentials for the Nginx Database. Go to the `docker-compose.yml` and edit the environment section.

### Web App - snippet
```yaml
DB_MYSQL_USER: "nginx"  # Change to match db
DB_MYSQL_PASSWORD: "CHANGE_ME" # Change to match db
DB_MYSQL_NAME: "nginx" # Change to match db
```

### Database - snippet
```yaml
MYSQL_ROOT_PASSWORD: 'CHANGE_ME' # Change to be secure
MYSQL_DATABASE: 'nginx' # Change to be secure; must match app
MYSQL_USER: 'nginx' # Change to be secure; must match app
MYSQL_PASSWORD: 'CHANGE_ME' # Change to be secure; must match app
```

Get a Wireguard peer configuration file from your Wireguard server. Rename it "`wg0.conf`" and place it in the `/wireguard/` directory.


Run docker compose in the same directory as `docker-compose.yml`
```sh
docker-compose up -d
```

## References
- [Nginx Proxy Manager GitHub](https://github.com/jc21/nginx-proxy-manager)
- [Linuxserver Wireguard docs](https://docs.linuxserver.io/images/docker-wireguard)
- [Linuxserver Wireguard GitHub](https://github.com/linuxserver/docker-wireguard)