## Pull Postgres docker image
```bash
docker pull postgres:<version>
```

## Run the Docker container
```bash
docker run
--name <container-name> \
-e POSTGRES_PASSWORD=<password> \
-e POSTGRES_USER=<username> \
-p <port-on-host>:<container-port> \
-v postgres_data:/var/lib/postgresql/data \
-d postgres
```

- `POSTGRES_USER` – Specifies a user with superuser privileges and a database with the same name. Postgres uses the default user when this is empty.
- `POSTGRES_DB` – Specifies a name for your database or defaults to the `POSTGRES_USER` value when left blank. 
- `POSTGRES_INITDB_ARGS` – Sends arguments to `postgres_initdb` and adds functionality
- `POSTGRES_INITDB_WALDIR` – Defines a specific directory for the Postgres transaction log. A transaction is an operation and usually describes a change to your database. 
- `POSTGRES_HOST_AUTH_METHOD` – Controls the `auth-method` for `host` connections to `all` databases, users, and addresses
- `PGDATA` – Defines another default location or subdirectory for database files

## Connect to the Postgres container via terminal
```bash
docker exec -it <container-name> psql -U <username>
```

From there you can create a new database, as you shouldn't really touch the default postgres database which is used to store information about the Postgres instance itself.

## Create tables from a SQL dump file
```bash
docker exec
-i <container-name> psql \
-U <username> \
-d <database-name> < ./<path-to-the-dump-file>.sql
```