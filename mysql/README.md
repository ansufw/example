# Example of MySQL instance

To start, clone this folder and run this command

```sh
docker-compose -p mysql -f ./docker-compose.yaml up -d
```

This command above will create an image called `mysql` and run up the container namely `mysqldb`

# Add another instance

- Delete all files and folders in `datadb`
- You may want to delete previous instance. Use `docker-compose -p mysql -f ./docker-compose.yaml down -v`. (source: [stackoverflow](https://stackoverflow.com/questions/59838692/mysql-root-password-is-set-but-getting-access-denied-for-user-rootlocalhost) ) 

# Syntax

references:
- https://www.hostinger.com/tutorials/mysql/how-create-mysql-user-and-grant-permissions-command-line

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

### Create new user

```
CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'password'
```

### Grant user

```
GRANT ALL PRIVILEGES ON * . * TO 'new_user'@'localhost';
```
