# Docker

### Connect to PostgreSQL Database running on docker from local Machine.

```
docker run -d -p 5432:5432 --name root -e POSTGRES_PASSWORD=12345 postgres
```

### The above command will install postgres docker image on our machine and then run the database server exposing on port 5432

### Access the db container from our machine. We will create a database inside our PostgreSQL container.

```
docker exec -it root bash
```

### Now we are inside the db container and now can access postgres using

```
psql -U postgres
```

### Once it's inside, we can create a database

```
CREATE DATABASE test;
```

### To connect, we can use any postgres client like (PgAdmin, visual studio code) and conect to the db using

```
  "host": "localhost",
  "user": "postgres",
  "port": 5432,
  "ssl": false,
  "database": "test",
  "password": "12345"
```

