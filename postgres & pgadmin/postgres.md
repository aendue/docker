## Postgres und pgadmin

postgres default admin user = postgres

```zsh
sudo docker run -d --name postgres -p 5432:5432  -e POSTGRES_PASSWORD=12345 -e PGDATA=/var/lib/postgresql/data/pgdata -v /mnt/data1/docker_data/pgdata:/var/lib/postgresql/data postgres

sudo docker run --name pgadmin4 -p 80:80 -e 'PGADMIN_DEFAULT_EMAIL=andy@grundt.de' -e 'PGADMIN_DEFAULT_PASSWORD=12345' -d dpage/pgadmin4
```