# Environment Var

## Mandatory

One of this list should be present

- `MARIADB_ROOT_PASSWORD`
- `MARIADB_ROOT_PASSWORD_HASH`, the hast can be generated with `SELECT PASSWORD('thepassword')`
- `MARIADB_RANDOM_ROOT_PASSWORD`, set `yes` to generate a random initial password for the root user. The generated root password will be printed to stdout (GENERATED ROOT PASSWORD: .....).
- `MARIADB_ALLOW_EMPTY_ROOT_PASSWORD`, set `yes` to allow the container to be started with a blank password for the root user.
