# Docker

# Postgres

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

# Mongodb

### Connect to Mongodb running on docker from local Machine.

```
docker run -d -p 27017:27017 -v ~/dataMongo:/data/db mongo
```

### We need to enter the interactive shell using the below command

```
docker exec -it container-id bash

```

### And then type 

```Mongo``` in the bash 

### The next is to create/use the database

```
use testdb
```

### And to create user and password, execute the below command

```
db.createUser({
  user: 'root',
  pwd: '12345',
  roles: [{ role: 'readWrite', db:'cool_db'}]
})
```
