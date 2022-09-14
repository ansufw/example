# Example of MySQL instance

To start, clone this folder and run this command

```sh
docker-compose -p mysql -f ./docker-compose.yaml up -d
```

This command above will create an image called `mysql` and run up the container namely `mysqldb`

# Add another instance

- Delete all files and folders in `datadb`
- You may want to delete previous instance. Use `docker-compose -p mysql -f ./docker-compose.yaml down -v`. (source: [stackoverflow](https://stackoverflow.com/questions/59838692/mysql-root-password-is-set-but-getting-access-denied-for-user-rootlocalhost) ) 
