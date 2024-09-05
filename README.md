# Hazelcast Flow Docker Compose Files

This repository provides docker-compose files that enable you to run a local instance of the Hazelcast Flow. There are a variety of docker-compose files, each utilizing a different set of dependencies.

## Prerequisites

To use these files, you must first have the following installed:

- [Docker](https://docs.docker.com/engine/installation/)
- [docker-compose](https://docs.docker.com/compose/install/)

## How to use

The following steps will run a local instance of the Hazelcast Flow using the default configuration file (`docker-compose.yml`):

1. Clone this repository.
2. Change directory into the root of the project.
3.  Set up the Hazelcast License
```bash
cp .env.example .env
```

> **⚠️ Important**
> You must create the file .env and populate it with the license information:
>   - MC_LICENSE contains the Hazelcast license

4. Run the `docker-compose up` command.

```bash
git clone https://github.com/hazelcast/hazelcast-flow-docker-compose.git
cd  docker-compose
docker-compose up
```

### Other configuration files

The default configuration file (`docker-compose.yml`) uses a PostgreSQL database, and exposes the Hazelcast Flow on port 9021.
The other configuration files in the repo spin up instances of the Hazelcast Flow using different dependencies.

```bash
docker-compose -f docker-compose-idp.yml up
```

Here is a list of available files and the dependencies they use.

| File                                           | Description                                                       |
|------------------------------------------------|-------------------------------------------------------------------|
| docker-compose.yml                             | Flow, Postgres and Management Center (default)                    |
| docker-compose-idp.yml                         | Default + OIDC configured                                         |
| docker-compose-idp-local-sec-preconfigured.yml | Default + OIDC configured + local security provider preconfigured |
| docker-compose-ext-hazelcast.yml               | Default + external hazelcast installation                         |
| docker-compose-prometheus.yml                  | Default + Prometheus setup                                        |

Some exposed endpoints:
- http://localhost:9021 - Hazelcast Flow UI
- http://localhost:8080 - Management Center UI
- http://localhost:9090 - Prometheus UI
