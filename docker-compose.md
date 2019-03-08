# Docker Compose

## What is Docker Compose
* Separate CLI that gets installed along with Docker
* Used to start up multiple Docker containers at the same time, and automatically connect them together with some form of networking.
* Automates some of the long-winded arguments we were passing to 'docker run'

### build with Docker Compose
This looks into current working directory for `docker-compose.yml` file.
`docker-compose build`

### start Docker Compose
This looks into current working directory for `docker-compose.yml` file.
`docker-compose up` 
Options
  * -d: run containers in the background `docker-compose up -d`

### stop all running containers
`docker-compose down`

### build/rebuild container and run
`docker-compose up --build`

### show the status configured in a docker-compose.yml file (run in the same directory as docker-compose.yml file)
`docker-compose ps`
