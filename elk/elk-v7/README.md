# ELK Service

source: https://github.com/Einsteinish/Einsteinish-ELK-Stack-with-docker-compose

## How to Use

1. Run `docker compose up`

# Problem

1. error `Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:5000 -> 0.0.0.0:0: listen tcp 0.0.0.0:5000: bind: address already in use`-- solution: change the port
