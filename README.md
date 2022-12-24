# One Click Stacks
Stacks prontas pra você implantar na sua VPS com poucos cliques.

Faça o deploy de mais de 1+ open-source apps com um unico comando no docker.

## Features

- [x] Compatibilidade com Traefik
- [x] Compatibilidade com Portainer
- [x] No need to manage configuration files
- [x] Distributed storage compatibility (GlusterFS, Ceph, NFS) with the env `VOLUME_PATH=/mnt/storage_mountpoint/`

## Preparando tudo


### 1. Deploy Docker
```bash
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
```bash
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

[Documentação Docker](https://docs.docker.com/engine/install/ubuntu/)

### 2. Deploy Portainer
```bash
```

### 3. Deploy traefik
```bash
docker swarm init
docker network create --driver=overlay traefik-net
docker stack deploy -c stacks/traefik.yml traefik
```
### 4. Check your HTTP and HTTPS ports
curl https://ipv4.am.i.mullvad.net/port/80
curl https://ipv4.am.i.mullvad.net/port/443

### 5. Deploy a stack
DOMAIN=<mydomain.com> docker stack deploy -c <stack.yml> <name>

### Example
DOMAIN=ghost.example.com docker stack deploy -c stacks/ghost.yml ghost


## Support me

I'd love to work on this project, but my time on this earth is limited, support my work to give me more time!

Please support me with a one-time or a monthly donation and help me continue my activities.

[![Github sponsor](https://img.shields.io/badge/github-Support%20my%20work-lightgrey?style=social&logo=github)](https://github.com/sponsors/johackim/)
[![ko-fi](https://img.shields.io/badge/ko--fi-Support%20my%20work-lightgrey?style=social&logo=ko-fi)](https://ko-fi.com/johackim)
[![Buy me a coffee](https://img.shields.io/badge/Buy%20me%20a%20coffee-Support%20my%20work-lightgrey?style=social&logo=buy%20me%20a%20coffee&logoColor=%23FFDD00)](https://www.buymeacoffee.com/johackim)
[![liberapay](https://img.shields.io/badge/liberapay-Support%20my%20work-lightgrey?style=social&logo=liberapay&logoColor=%23F6C915)](https://liberapay.com/johackim/donate)
[![Github](https://img.shields.io/github/followers/johackim?label=Follow%20me&style=social)](https://github.com/johackim)
[![Mastodon](https://img.shields.io/mastodon/follow/1631?domain=https%3A%2F%2Fmastodon.ethibox.fr&style=social)](https://mastodon.ethibox.fr/@johackim)
[![Twitter](https://img.shields.io/twitter/follow/_johackim?style=social)](https://twitter.com/_johackim)
