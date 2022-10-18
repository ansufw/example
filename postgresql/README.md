# PostgreSQL

## PostgreSQL Command Line

```
psql -U root -c [query];
```
- `-U` is user 
- `-c` is command querry

## Sample Query

| query command | description |
|---------|------------:|
| `SELECT current_database()` | retrieve the current database version  |
| `SELECT version();` | retrieve the current version |
| `CREATE DATABASE db_name;` | create database |
| `CREATE TABLE colors (ColorID int, ColorName char(20));` | create table named 'colors' |
| `INSERT INTO colors VALUES (1, 'red'), (1, 'blue'), (1, 'green');` | insert data to table | 
| `SELECT * FROM pg_database;` | show all database |

short commands

| command | description |
|---------|------------:|
|`\l` | list available databases |
| `\dt` | list available tables |
| `\d table_name` | describe a table |
| `\dn` | list all schemes of the currently connected db |
| `\df` | list available functions in the current db |
| `\dv` | list available view |
| `\du` | list all users and their assign role |
| `\g` | execute the last command again |
| `\?` | know all available psql commands |
| `\h` | get help |
| `\H` | switch the output to the HTML format | 
| `\q` | exit psql shell | 
| `\c db_name` | switch database |

sample usage:

Get list database

```
psql -U [username] -c "\l";
```

Get list database via Docker

```
docker exec -i [container_name] psql -U [username] -c "SELECT * FROM pg_database;"
```

### Creating User

```
CREATE USER username;
```

command above is alias for

```
CREATE ROLE username WITH LOGIN
```


### Backup db

- via docker

```
docker exec -t your-db-container pg_dumpall -c -U postgres > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql
```

### Restore file

- Via Docker

```
cat dump_file.sql | docker exec -i container_name psql -U username

```

- Non Docker

```
`psql dbname < dump_file.sql`
```

