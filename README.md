# Docker Workshop at HPE
This repository contains the instrucctions to run the voting-app using docker-compose.

## Prerequisites
* Docker installed

## Instructions

Install docker-compose
```sh
  sudo su
  curl -L https://github.com/docker/compose/releases/download/1.6.2/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
  chmod +x /usr/local/bin/docker-compose
```
Get voting-app repository from GitHub
```bash
  git clone https://github.com/homeles/example-voting-app.git
```
or download it from the USB and extract the content.
```shell
  tar -xvf foldername.tar
```
Load the docker images from the USB in case you cannot download the connect directly from DockerHub
```sh
  docker load < examplevotingapp_result-app.tar
  docker load < examplevotingapp_voting-app.tar
  docker load < examplevotingapp_worker.tar
  docker load < postgres.tar
  docker load < redis.tar
```
Execute command docker compose and check your application. 
```bash
  docker-compose up
```
Validate the application is up and running. Go to your browser...
  * http://localhost:5000 - voting app
  * http://localhost:5001 - results app
