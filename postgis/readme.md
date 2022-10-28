run from windows terminal (using windows notation for host bind folder)

```/bin/bash
docker run \
  --name postgis \
  -p 5432:5432 \
  --restart unless-stopped \
  -e POSTGRES_PASSWORD=postgres \
  -e PGDATA=/var/lib/postgresql/data \
  -v "c:\Users\some_user\OneDrive - some_company\docker_binds\postgres\pgdata:/var/lib/postgresql/data" \
  -d postgis/postgis
```

