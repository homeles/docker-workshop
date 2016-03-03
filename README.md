# Docker Workshop at HPE
This repository contains the instrucctions to run the voting-app using docker-compose.

## Prerequisites
* Docker installed

## Instructions

 1 - Install docker-compose
```
  sudo su
  curl -L https://github.com/docker/compose/releases/download/1.6.2/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
  chmod +x /usr/local/bin/docker-compose
```
 2 - Get voting-app repository from GitHub
```
  git clone https://github.com/homeles/example-voting-app.git
```
*Note: If you have issues downloading the repository go to help section below.*

 3 - Execute command docker compose and check your application. 
```bash
  cd example-voting-app
  docker-compose up
```
*Note: If you have issues downloading the images go to help section below.*
 
 4 - Validate the application is up and running. Go to your browser...

  * Voting app [http://localhost:5000]
  * Results app [http://localhost:5001]

**WELL DONE!!!**

## Help & Troubleshooting

##### Git clone command is failing

* Get the repository from the USB and extract the content.
```
  tar -xvf example-voting-app.tar
```

##### Docker compose up is failing 

If the image download process is failing then execute the following

* Download the images from the USB and extract the content.
```
  tar -xvf images-voting-app.tar
```
* Load the docker images from the USB in case you cannot download the connect directly from DockerHub
```
  docker load < examplevotingapp_result-app.tar
  docker load < examplevotingapp_voting-app.tar
  docker load < examplevotingapp_worker.tar
  docker load < postgres.tar
  docker load < redis.tar
```
* Now Execute again docker compose inside the example-voting-app repository
```
  docker-compose up
```
