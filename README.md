# Postgresql n PgAdmin - docker compose


## Requirements:
* Docker and Docker Compose

## Getting Started
* Clone or download this repository

* Create docker volume for postgres
  ```yml
  docker volume create --name postgres-data -d local
  ```
* Create docker volume for dpage/pgadmin4
  ```yml
  docker volume create --name pgadmin4-data -d local
  ```
* Create docker network
  ```yml
  docker network create --driver bridge postgres-net
  ```
* From your project directory, start up your application by running `docker-compose up -d`

* When you are done, run this command `docker-compose down` in repo's directory to shut the postgres and pgAdmin server down.

## Environments
This Compose file contains the following environment variables:

* `POSTGRES_USER` is **postgres** (default)
* `POSTGRES_PASSWORD` is **Abcd1234**
* `POSTGRES_PORT` is **5432**
* `PGADMIN_PORT` is **80**
* `PGADMIN_DEFAULT_EMAIL` is **hihihi@mail.com**
* `PGADMIN_DEFAULT_PASSWORD` is **Abcd1234**

## Access to postgres: 
* `localhost:5432`
* **Username:** postgres
* **Password:** Abcd1234

## Access to PgAdmin: 
* **URL:** `http://localhost:80`
* **Username:** hihihi@mail.com
* **Password:** Abcd1234

## Add a new server in PgAdmin: (Object menu -> Create -> Server...)
* **Host name/address** `my_postgres` (container_name or IPAddress of postgres's container)
* **Port** `5432`
* **Username** as `POSTGRES_USER`, by default: `postgres`
* **Password** as `POSTGRES_PASSWORD`, `Abcd1234`