[![Project Supported by CyVerse](https://img.shields.io/badge/Supported%20by-CyVerse-blue.svg)](https://learning.cyverse.org/projects/vice/en/latest/) [![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3246932.svg)](https://doi.org/10.5281/zenodo.3246932) [![license](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://opensource.org/licenses/GPL-3.0)

# jupyterlab-base

Jupyter Lab base Docker container recipe based on Jupyter datascience-notebook for CyVerse VICE. VICE requires additional configuration files to be compatible with our Condor and Kubernetes orchestration.

[![CircleCI](https://circleci.com/gh/cyverse-vice/jupyterlab-base.svg?style=svg)](https://circleci.com/gh/cyverse-vice/jupyterlab-base)[![DockerHub](https://img.shields.io/badge/DockerHub-brightgreen.svg?style=popout&logo=Docker)](https://hub.docker.com/r/cyversevice/jupyterlab-base)


quick launch | tag | size | metrics | build |
------------ | --- | ---- | ------- | ------|
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/jupyterlab-base) | [![Docker Automated build](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/jupyterlab-base) 
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/jupyterlab-base:1.0.5.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base:1.0.5) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base:1.0.5.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base:1.0.5) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/jupyterlab-base) | [![Docker Automated build](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/jupyterlab-base) 
[![VICE](https://img.shields.io/badge/CyVerse-VICE-blue.svg?style=popout&logo=Docker&color=#1488C6)]() | [![TAG](https://images.microbadger.com/badges/version/cyversevice/jupyterlab-base:1.0.9.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base:1.0.9) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base:1.0.5.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base:1.0.9) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/jupyterlab-base) | [![Docker Automated build](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/jupyterlab-base) 

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
docker run -it --rm -v /$HOME:/app --workdir /app -p 8888:8888 -e REDIRECT_URL=http://localhost:8888 cyversevice/jupyterlab-base:latest
```
