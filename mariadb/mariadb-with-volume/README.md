```yaml
version: '3.8'
 
services:
  db:
    image: mariadb:10
    container_name: mariadb
    environment:
      - MARIADB_MYSQL_LOCALHOST_USER=1
      - MARIADB_MYSQL_LOCALHOST_GRANTS="RELOAD, PROCESS, LOCK TABLES, BINLOG MONITOR"
      - MARIADB_ROOT_PASSWORD=my-secret-pw
    ports:
      - "3808:3306"
    volumes:
      - ./mariadb:/var/run/mysqld
      - ./datadb:/var/lib/mysql
```

# Environment Var

## Mandatory

One of this list should be present

- `MARIADB_ROOT_PASSWORD`
- `MARIADB_ROOT_PASSWORD_HASH`, the hast can be generated with `SELECT PASSWORD('thepassword')`
- `MARIADB_RANDOM_ROOT_PASSWORD`, set `yes` to generate a random initial password for the root user. The generated root password will be printed to stdout (GENERATED ROOT PASSWORD: .....).
- `MARIADB_ALLOW_EMPTY_ROOT_PASSWORD`, set `yes` to allow the container to be started with a blank password for the root user.
