# POTREC Stack
Potrec stands for: **PO**rtainer **TR**aefik lets**E**n**C**rypt

(ikr? 🙄)

Start the stack via `docker stack deploy -c potrec.yml potrec`

## Metrics
Traefik metrics are enabled by default but need [this stack](github.com/digitoolmedia/dm-docker-metrics) to be used.

## About this read me
This is going to be a nice readme and basic doco for the deployment of this stack on a docker swarm, with FAQ regarding some workaround and caveats.


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