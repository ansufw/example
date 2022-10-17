# Example of MySQL instance

## Quick Start

clone this folder and run this command

```sh
docker-compose -p mysql -f ./docker-compose.yaml up -d
```

This command above will create an image called `mysql` and run up the container namely `mysqldb`

## Run Shell

to enter the running container shell, run

```sh
docker exec -it mysqldb /bin/sh
```

## MySQL cli

to enter cli mode on the shell of the container, run

```sh
mysql -u root -p
```

and then enter the password

## Guidence

commond syntax

### See all database

```sql
SHOW DATABASES;
```