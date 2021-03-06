# Docker

## LOGIN

```.bash
# login to container
docker exec -it node-docker.app /bin/bash --login

# login to container and move to target directory
docker exec -it -w /share/fuootus node-docker.app /bin/bash --login
```

## REMOVE

```.bash
# stop active containers
docker ps -q | xargs docker stop
# remove suspended containers
docker ps -aq | xargs docker rm -f
# remove suspended containers and images
docker ps -aq | xargs docker rm -f && docker images -aq | xargs docker rmi -f
# remove suspended containers and images and caches
docker ps -aq | xargs docker rm -f && docker images -aq | xargs docker rmi -f && docker system prune --volumes -f
```

## RUN

```.bash
# run python docker
docker run --rm -v "$(PWD)":/opt/app/src -w /opt/app/src --name python-sample -it python:3.10.2-bullseye /bin/bash --login

# run go docker with volume share
docker run --rm -v "$(PWD)":/go/src -w /go/src --name go-sample -it golang:1.17.6-bullseye /bin/bash

# run JupyterNotebook
docker run --rm -v "$(PWD)":/home/jovyan/work -w /home/jovyan/work -p 8888:8888 --name jupyter jupyter/scipy-notebook

# run node docker
docker run --rm -v "$(PWD)":/opt/app/src -w /opt/app/src --name node-sample -it node:16.13.2-bullseye /bin/bash --login
```

