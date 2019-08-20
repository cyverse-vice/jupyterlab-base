# jupyterlab-base
Jupyter Lab base Docker container recipe based on [Jupyter datascience-notebook](https://hub.docker.com/r/jupyter/datascience-notebook) for [CyVerse VICE](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/index.html). VICE requires additional configuration files to be compatible with our Condor and Kubernetes orchestration. 

[![CircleCI](https://circleci.com/gh/cyverse-vice/jupyterlab-base.svg?style=svg)](https://circleci.com/gh/cyverse-vice/jupyterlab-base) [![license](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://opensource.org/licenses/GPL-3.0)  [![Project Supported by CyVerse](https://img.shields.io/badge/Supported%20by-CyVerse-blue.svg)](https://www.cyverse.org)  [![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3246932.svg)](https://doi.org/10.5281/zenodo.3246932)

image | tag | size | metrics | build | status |  
----- | --- | ---- | ------- | ------|--------|
[![DockerHub](https://img.shields.io/badge/DockerHub-brightgreen.svg?style=popout&logo=Docker)](https://hub.docker.com/r/cyversevice/jupyterlab-base) | [![](https://images.microbadger.com/badges/version/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base "latest") |  [![](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base "latest") | [![](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base)  |  [![](https://img.shields.io/docker/cloud/automated/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base/builds) | [![](https://img.shields.io/docker/build/cyversevice/jupyterlab-base.svg)](https://cloud.docker.com/u/cyversevice/repository/docker/cyversevice/jupyterlab-base)

image | tag | size | metrics | build |
----- | ----| ---- | ------- | ------|
<a href="https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=19f6a94b-71b6-4034-a7a5-40f7bea0b85b&app-id=75773c76-8ee1-11e9-907f-008cfa5ae621" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | [![](https://images.microbadger.com/badges/version/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base "latest") | [![](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base) | [![](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base/latest.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base)  |  [![](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base)|
tba | [![](https://images.microbadger.com/badges/version/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base:1.0.5 "1.0.5") | [![](https://images.microbadger.com/badges/image/cyversevice/jupyterlab-base.svg)](https://microbadger.com/images/cyversevice/jupyterlab-base) | [![](https://img.shields.io/docker/pulls/cyversevice/jupyterlab-base/1.0.5.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base)  |  [![](https://img.shields.io/docker/automated/cyversevice/jupyterlab-base.svg)](https://hub.docker.com/r/cyversevice/jupyterlab-base)


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
