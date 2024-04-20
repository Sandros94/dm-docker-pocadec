# POCADEC Stack
Pocadec stands for: **PO**rtainer **CAD**dy lets**E**n**C**rypt

(ikr? 🙄)

Start the stack via `docker stack deploy -c pocadec.yml pocadec`


## About this read me
This is going to be a nice readme and basic doco for the deployment of this stack on a docker swarm, with FAQ regarding some workaround and caveats.


## Create required networks

```bash
docker network create -d overlay agent_network
docker network create -d overlay --attachable caddy-public
```

## http cache
Firstly build the custom image using `caddy.dockerfile`, then set it in the main `swarm-pocadec.yml` and uncomment the last two caddy labels.

```bash
docker build -t cdp-custom:2.7.4-alpine . -f caddy.dockerfile --build-arg="CADDY_VERSION=2.7.4"
```

## caddy-dns
In the event of requiring a [dns resolver](https://github.com/caddy-dns) for using wildcards, a custom Caddy image build is required with the following structure added.
```dockerfile
build  --with github.com/caddy-dns/REPOSITORY_NAME
```

## check current caddyfile.autosave
```bash
docker exec $(docker ps -qf "name=^pocadec_caddy") sh -c "cat /config/caddy/Caddyfile.autosave"
```

## ENV List
ACME_USER_EMAIL  
DNS_PROVIDER
DNS_API_PROVIDER
DNS_API_KEY  
HOSTNAME  
WILDCARD_MAIN_DOMAIN  
WILDCARD_SANS_DOMAIN  
TRAEFIK_DOMAIN  
TRAEFIK_BASICAUTH_USERS  
PORTAINER_DOMAIN  
EDGE_DOMAIN  


## To-Do
- [ ] doco
- [ ] env variables definition
- [ ] caveats
- [ ] FAQ