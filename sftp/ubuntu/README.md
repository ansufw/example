# Intro

This container I use for sftp server

# How To Use

## Create folder volume

go to this ubuntu folder and make a dir called volume `mkdir volume` if there is no directory available yet.

## Initialize Container

```sh
docker-compose -p smartfren -f ./docker-compose.yaml up -d
```

The command will do the following:
1. flag `-p` give the name of project by `smartfren`
2. flag `-f`, following with the location of docker-compose file, locate the file of docker-compose
3. command `docker-compose up -d`, with detach flag, means starting the containers in the background and leaves them running ([source](https://docs.docker.com/engine/reference/commandline/compose_up/)).



## Connect to SSH

```sh
ssh root@localhost -p 3022
```

## Connect to SFTP

```sh
sftp -oPort=3022 root@localhost
```
