# Docker

## LOGIN

```bash
# login to container
docker exec -it node-docker.app /bin/bash --login

# login to container and move to target directory
docker exec -it -w /share/fuootus node-docker.app /bin/bash --login
```

## REMOVE

```bash
# remove containers and images
docker ps -aq | xargs docker rm && docker images -aq | xargs docker rmi
```
