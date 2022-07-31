# Intro

This container I use for sftp server

# How To Use

## Create folder volume

go to this ubuntu folder and make a dir called volume `mkdir volume` if there is no directory available yet.

## Initialize Container

```sh
docker-compose -p sftp -f ./docker-compose.yaml up -d
```


## Connect to SSH

```sh
ssh root@localhost -p 3022
```

## Connect to SFTP

```sh
sftp -oPort=3022 root@localhost
```