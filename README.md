# Installation

Clone the repo https://github.com/ddevadat/sb-rc-learning-path.git

```
git clone https://github.com/ddevadat/sb-rc-learning-path.git
cd sb-rc-learning-path
```

Create db and minio data folders
```
mkdir -p db-data minio/data

```

Start services
```
alias dc='docker-compose'
dc up -d
```

Disable SSL for keycloak realm ( for demo purpose )

```
Login to the postgres db
select ssl_required from REALM where id = 'master';
update REALM set ssl_required='NONE' where id = 'master'

Restart Keycloak
docker compose up -d --force-recreate --no-deps keycloak

```

