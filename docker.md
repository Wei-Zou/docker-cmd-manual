# Docker common commands

### List running containers
`docker ps`

### Build docker image
`docker build -t TAG_NAME .`

### Build on a dev Dockerfile.dev
`docker build -f Dockerfile.dev .`

### run docker image (essentially `docker create` and `docker start`)
`docker run TAG_NAME|IMAGE_ID`
Options:
  * -d: run container in the background: `docker run -d IMAGE`
  * -p: `-p LOCAL_PORT:CONTAINER_PORT` port mapping from LOCAL_PORT in local machine to CONTAINER_PORT inside Docker container.
  * -v: setting up Docker volume:
    ** `docker run -v /app/node_modules -v $PWD:/app IMAGE_ID`
    *** the first `-v` tells container not to do the mapping for `/app/node_modules`
    *** the second `-v` maps `$PWD` of local machine to `/app` inside the container

### run docker image and pass in command to run
`docker run TAG_NAME|IMAGE_ID {COMMAND}`

### execute command in a running container with id CONTAINER_ID
`docker exec -it CONTAINER_ID COMMAND_TO_RUN`

### forward input from terminal directly to a specific container; it only attaches to the primary process of the container (like `npm run start`)
`docker attach CONTAINER_ID`

### stop a running container
`docker stop CONTAINER_ID`

# Docker restart policy
  * "no" (default): Never attempt to restart containers
  * always: If container stops for any reason always attempt to restart containers
  * on-failure: Only restart if the container stops with an error code
    Cases where on-failure is used: cron job, when finished successfully, don't want to restart; only restart on failure
  * unless-stopped: Always restart unless we (developers) forcibly stop it
