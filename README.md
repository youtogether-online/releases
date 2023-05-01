# Releases
Workflow for deploy and local development

## Setup local instance
1. Install `docker`
2. Clone this repo with `git clone git@github.com:youtogether-online/releases.git`
3. `cd releases`
4. Copy `.env.sample` to `.env`, you can use `cp .env.sample .env`
5. [Generate tls certs](#Generate-tls-certs)
6. Start services with `docker-compose up -d`

Your local instance will be available on https://youtogether.localhost

### Generate tls certs
1. Install `mkcert` with your preferred way, for example with [brew](https://brew.sh/): `brew install mkcert`.
2. Run `mkcert -install`
3. Run `sh scripts/create-cert.sh`