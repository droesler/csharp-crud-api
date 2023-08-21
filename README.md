# csharp-crud-api

Asp.net EntityFrameworkCore backend running postgresql db.

The vue 3 frontend for this project is at:  [https://github.com/droesler/user_list_vue_frontend](https://github.com/droesler/user_list_vue_frontend)

Code based on: [https://dev.to/francescoxx/c-c-sharp-crud-rest-api-using-net-7-aspnet-entity-framework-postgres-docker-and-docker-compose-493a](https://dev.to/francescoxx/c-c-sharp-crud-rest-api-using-net-7-aspnet-entity-framework-postgres-docker-and-docker-compose-493a)

## Project Setup

Run the Postgres container:
```sh
docker compose up -d db
```
Create the initial table in the database:
```sh
docker exec -it db psql -U postgres

CREATE TABLE "users" (
  "id" SERIAL PRIMARY KEY,
  "name" VARCHAR(50) NOT NULL,
  "email" VARCHAR(255) NOT NULL
);
```

Build the docker image:
```sh
docker compose build
```
Run the app container:
```sh
docker compose up csharp_app
```
