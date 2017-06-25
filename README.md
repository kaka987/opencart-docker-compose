# Introduction

Deploy opencart-lnmp(Linux, Nginx, MySQL, PHP5) using docker.

ubuntu 	16.04
docker  17.04.0-ce
docker-compose 1.13.0

cd /opt/
git clone https://github.com/kaka987/opencart-docker-compose.git
cd opencart-docker-compose
docker-compose up -d

-> You need to check permission of some folders. or chmod -R 777 .

## Lnmp from https://github.com/micooz/docker-lnmp

I want to share my ideas and designs about Web-Deploying using Docker with you.

### Architecture

![architecture][1]  

The whole app is divided into three Containers:

1. Nginx is running in `Nginx` Container, which handles requests and makes responses.
2. PHP or PHP-FPM is put in `PHP-FPM` Container, it retrieves php scripts from host, interprets, executes then responses to Nginx. If necessary, it will connect to `MySQL` as well.
3. MySQL lies in `MySQL` Container, 

Our app scripts are located on host, you can edit files directly without rebuilding/restarting whole images/containers.

### Build and Run

At first, you should have had [Docker](https://docs.docker.com) and [Docker Compose](https://docs.docker.com/compose) installed.

Without building images one by one, you can make use of `docker-compose` and simply issue:

    $ sudo docker-compose up

For more operations to containers, please refer to:

    $ sudo docker-compose --help

Check out your https://\<docker-host\> and have fun :beer:

### Contributors

Micooz <micooz@hotmail.com>

sndnvaps <sndnvaps@gmail.com>

### License

MIT

  [1]: architecture.png
