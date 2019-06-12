# jupyterlab-base
Jupyter Lab base Docker container recipe based on [Jupyter datascience-notebook](https://hub.docker.com/r/jupyter/datascience-notebook) for [CyVerse VICE](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/index.html). VICE requires additional configuration files to be compatible with our Condor and Kubernetes orchestration. 

[![Project Supported by CyVerse](https://img.shields.io/badge/Supported%20by-CyVerse-blue.svg)](https://www.cyverse.org) [![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)

image            | description                               | size   | metrics | build status 
---------------- | ----------------------------------------- | ------ | ------- | --------------
[![DockerHub](https://img.shields.io/badge/DockerHub-brightgreen.svg?style=popout&logo=Docker)](https://hub.docker.com/r/cyversevice/jupyterlab-base) | Jupyter Lab Base latest | [![](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base) | [![](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/tswetnam/emsi-rstudio)  |  [![](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base/builds)
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]()| VICE RStudio R v3.5.0 w/ geospatial depends | [![](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base) | [![](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base)  |  [![](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-basebuilds)

# Instructions

## Run Docker locally or on a Virtual Machine

To run the RStudio container, you must first pull them from DockerHub, or activate a [CyVerse Account](https://user.cyverse.org/services/mine).

A Docker container for running RStudio is hosted on DockerHub.

```
docker pull cyversevice/jupyterlab-base:latest
```

```
docker run -it --rm -d cyversevice/jupyterlab-base:latest
```

The default username is `jovyan`

## Run Docker container in CyVerse VICE

Unless you plan on making changes to this container, you should just use the existing launch button above. 

###### Developer notes

To test the container locally:

```
docker run -it --rm -v /$HOME:/app --workdir /app -p 8888:80 -e REDIRECT_URL=http://localhost:8888 cyversevice/jupyterlab-base:latest
```
