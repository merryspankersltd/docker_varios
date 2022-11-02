run command (windows terminal)

```sh
docker run  `
         -d `
         --name datascience-notebook `
         --user root `
         --env NB_USER=foo `
         --env NB_UID=1000 `
         --env NB_GID=100 `
         --env CHOWN_HOME=yes `
         --env HOME=/home/foo `
         --workdir "/home/foo/work" `
         -v "c:\Users\foo\OneDrive - ACME\docker_binds\jupyter\work:/home/foo/work" `
         -v "C:\Users\foo\OneDrive - ACME\data:/home/foo/data" `
         -p 10000:8888 `
         --restart unless-stopped `
jupyter/notebook-datascience
```
