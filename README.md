# Releases
Workflow for deploy and local development

### Setup local instance
1. Install `docker`
2. Clone this repo with `git clone git@github.com:youtogether-online/releases.git`
3. `cd releases`
4. Copy `.env.sample` to `.env`, you can use `cp .env.sample .env`
5. [Generate tls certs](#Generate-tls-certs)
6. Start services with `docker-compose up --profile <profile-name> -d`

Docker profiles:
1. Default - profile with real backend, redis, postgres and frontend
2. Mock - profile with mocked backend and frontend 

Your local instance will be available on:<br>
Frontend: https://youtogether.localhost<br>
Traefik dashboard: https://traefik.youtogether.localhost<br>
Backend: https://youtogether.localhost/api <br>

### Generate tls certs
1. Install `mkcert` with your preferred way. [Brew](https://brew.sh) - `brew install mkcert`, [Cholocatey](https://chocolatey.org/install) - `choco install mkcert`
2. Run `mkcert -install`
3. Run `sh scripts/create-cert.sh`

### Environment variables
| Name              | Description                                                                                                                                                                                              |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| POSTGRES_USERNAME | Postgres username                                                                                                                                                                                        |
| POSTGRES_HOST     | Postgres host. If you use default name for postgres service (postgres), you can use localhost. If you want to rename this service you should use service name in this variable, such as database service |
| POSTGRES_DB       | Postgres database                                                                                                                                                                                        |
| POSTGRES_PASSWORD | Postgres password                                                                                                                                                                                        |
| DOMAIN_NAME       | Domain for local server. If you want to add custom domain, you should update ./scripts/create-cert.sh with your domain                                                                                   |

