poetry run uvicorn app.main:app --host localhost --port 8000 --reload

poetry run pytest --dburl=postgresql://postgres:postgres@localhost:5433/postgres

##  API

api works

![API HEALTHCHECKER OK](./images/api-healthchecker-OK.png)

## Docker

docker compose uses postgres for all and I use my version with PgAdmin - see `docker/docker.compose.yml`.

```
  postgres:  
    container_name: postgres_local  
    image: postgres:16-alpine #postgres:
    environment:
      - POSTGRES_DB=postgres # optional
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
```

tables created in DB

![TABLES CREATED](./images/pgadmin.png)

sql crud works OK - tested with publisher and employee in slq_postgres folder

The following are used in Python CRUD in sql_postgres folder

```
POSTGRES_HOST = "host.docker.internal"
POSTGRES_USER = "postgres"
POSTGRES_PASSWORD = "postgres"
POSTGRES_DB = "postgres"
```

## PyTest

pytest can't connect to DB using this `postgresql://postgres:postgres@localhost:5433/postgres` hard coded.

![PYTEST CANNOT CONNECT TO DB](./images/pytest.png)

