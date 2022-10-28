run command (windows terminal)

```sh
docker run  \
        --name datascience-notebook \
        --user root \
        --env=NB_USER=some_user \
        --env=NB_UID=1000 \
        --env=NB_GID=100 \
        --env=CHOWN_HOME=yes \
        --env=HOME=/home/${NB_USER} \
        --workdir="/home/${NB_USER}/work" \
        -v "c:\Users\some_user\OneDrive - ACME\docker_binds\jupyter\work:/home/${NB_USER}/work" \
        -p 10000:8888 \
        --restart=unless-stopped \
jupyter/datascience-notebook
```
