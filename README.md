# Releases
Workflow for deploy and local development

### Setup local instance
1. Install `docker`
2. Clone this repo with `git clone git@github.com:youtogether-online/releases.git`
3. `cd releases`
4. Copy `.env.sample` to `.env`, you can use `cp .env.sample .env`
5. [Generate tls certs](#Generate-tls-certs)
6. Start services with `docker-compose up -d`

Your local instance will be available on:
Frontend: https://youtogether.localhost
Traefik dashboard: https://traefik.youtogether.localhost
Backend: https://youtogether.localhost/api

### Generate tls certs
1. Install `mkcert` with your preferred way, for example with [brew](https://brew.sh/): `brew install mkcert`.
2. Run `mkcert -install`
3. Run `sh scripts/create-cert.sh`

### Environment variables
| Name              | Description                                                                                                                                                                                              |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| POSTGRES_USERNAME | Postgres username                                                                                                                                                                                        |
| POSTGRES_HOST     | Postgres host. If you use default name for postgres service (postgres), you can use localhost. If you want to rename this service you should use service name in this variable, such as database service |
| POSTGRES_DB       | Postgres database                                                                                                                                                                                        |
| POSTGRES_PASSWORD | Postgres password                                                                                                                                                                                        |
| DOMAIN_NAME       | Domain for local server. If you want to add custom domain, you should update ./scripts/create-cert.sh with your domain                                                                                   |

