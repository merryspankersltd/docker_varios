Original run command:

```sh
docker run \
        --name=datascience-notebook \
        --hostname=c38c36f31434 \
        --user=1000 \
        --mac-address=02:42:ac:11:00:03 \
        --env=PATH=/opt/conda/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
        --env=DEBIAN_FRONTEND=noninteractive \
        --env=CONDA_DIR=/opt/conda \
        --env=SHELL=/bin/bash \
        --env=NB_USER=jovyan \
        --env=NB_UID=1000 \
        --env=NB_GID=100 \
        --env=LC_ALL=en_US.UTF-8 \
        --env=LANG=en_US.UTF-8 \
        --env=LANGUAGE=en_US.UTF-8 \
        --env=HOME=/home/jovyan \
        --env=XDG_CACHE_HOME=/home/jovyan/.cache/ \
        --env=JULIA_DEPOT_PATH=/opt/julia \
        --env=JULIA_PKGDIR=/opt/julia \
        --env=JULIA_VERSION=1.8.2 \
        --workdir=/home/jovyan \
        -p 10000:8888 \
        --restart=unless-stopped \
        --label='maintainer=Jupyter Project <jupyter@googlegroups.com>' \
        --runtime=runc \
        jupyter/datascience-notebook \
        start-notebook.sh
```
Actual command

```bash
sudo docker run \
        --name=datascience-notebook \
        --hostname=c38c36f31434 \
        --user=1000 \
        --mac-address=02:42:ac:11:00:03 \
        --env=PATH=/opt/conda/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
        --env=DEBIAN_FRONTEND=noninteractive \
        --env=CONDA_DIR=/opt/conda \
        --env=SHELL=/bin/bash \
        --user root \
        --env=NB_USER=marc \
        --env=NB_UID=1000 \
        --env=NB_GID=100 \
        --env=CHOWN_HOME=yes \
        --env=LC_ALL=en_US.UTF-8 \
        --env=LANG=en_US.UTF-8 \
        --env=LANGUAGE=en_US.UTF-8 \
        --env=HOME=/home/marc \
        --env=XDG_CACHE_HOME=/home/jovyan/.cache/ \
        --env=JULIA_DEPOT_PATH=/opt/julia \
        --env=JULIA_PKGDIR=/opt/julia \
        --env=JULIA_VERSION=1.8.2 \
        --workdir="/home/${NB_USER}" \
        -v "/mnt/c/Users/marcl/OneDrive - URBALYON/docker/jupyter:/home/${NB_USER}/work" \
        -p 10000:8888 \
        --restart=unless-stopped \
        --label='maintainer=Jupyter Project <jupyter@googlegroups.com>' \
        --runtime=runc \
        jupyter/datascience-notebook \
        start-notebook.sh
```
