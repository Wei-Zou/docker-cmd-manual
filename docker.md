# Docker common commands

### List running containers
`docker ps`

### Build docker image
`docker build -t TAG_NAME .`

### run docker image (essentially `docker create` and `docker start`)
`docker run TAG_NAME`
Options:
  * -d: run container in the background: `docker run -d IMAGE`

### stop a running container
`docker stop CONTAINER_ID`

# Docker restart policy
  * "no" (default): Never attempt to restart containers
  * always: If container stops for any reason always attempt to restart containers
  * on-failure: Only restart if the container stops with an error code
    Cases where on-failure is used: cron job, when finished successfully, don't want to restart; only restart on failure
  * unless-stopped: Always restart unless we (developers) forcibly stop it
