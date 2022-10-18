# Example of MySQL instance

[docker hub](https://hub.docker.com/_/mysql)

version 5.7

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
=======
# Add another instance

- Delete all files and folders in `datadb`
- You may want to delete previous instance. Use `docker-compose -p mysql -f ./docker-compose.yaml down -v`. (source: [stackoverflow](https://stackoverflow.com/questions/59838692/mysql-root-password-is-set-but-getting-access-denied-for-user-rootlocalhost) ) 

# Syntax

references:
- [create user](https://dev.mysql.com/doc/refman/5.6/en/create-user.html)
- [drop user](https://dev.mysql.com/doc/refman/5.6/en/drop-user.html)
- [grant](https://dev.mysql.com/doc/refman/8.0/en/grant.html)
- [show grant](https://dev.mysql.com/doc/refman/8.0/en/show-grants.html)

## Mysql CLI

```
mysql -u root -p
```

## User

### Show all users

```
SELECT user FROM mysql.userl
```

### Show all users field

```
DESC mysql.user
```

### Grant User

```
grant all on widget.* to 'ansuf'@'%' identified by 'secret';
```
notes:
- widget is the name of database
- ansuf is the user name
- '%' is all host
- 'secret' is the user password

### Create User 

```
CREATE USER 'nilu'@'172.17.0.1' IDENTIFIED BY 'password';
```

### Grant Privileges

```
GRANT ALL PRIVILEGES ON *.* TO 'nilu'@'172.17.0.1' WITH GRANT OPTION;
```

### Flush Previlege

```
flush privileges;
```