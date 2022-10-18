# Set Dockerfile

Create Docker File

```Dockerfile
FROM ubuntu:latest

RUN mkdir -p /var/run/sshd

RUN apt update && \
    apt install -y openjdk-8-jdk && \
    apt install -y openssh-server

RUN useradd -rm -d /home/remote_user -s /bin/bash remote_user && \
    echo remote_user:password1234 | chpasswd

RUN mkdir /home/remote_user/.ssh && \
    chmod 777 /home/remote_user/.ssh

COPY id_rsa.pub /home/remote_user/.ssh/authorized_keys

RUN chown remote_user:remote_user -R /home/remote_user/.ssh && \
    chmod 600 /home/remote_user/.ssh/authorized_keys

CMD ["/usr/sbin/sshd", "-D"]

    
```

# Generate pair of SSH key

```sh
ssh-keygen -t rsa -m PEM -f id_rsa
```

# Create docker-compose 

```yaml
version: '3.8'
services:
  sftp:
    container_name: sftp-ubuntu
    build: .
    image: ubuntu_sftp_server
    ports:
      - "3011:22"
    volumes:
      - ./vol:/home/remote_user
```

# Connect to server

1. Using password

```
ssh remote_user@localhost -p 3011
```

2. Using ssh key

```
ssh -i id_rsa remote_user@localhost -p 3011
```

