# tagspaces-web-docker

### Install docker

#### Windows && Mac
https://docs.docker.com/desktop/

#### Mac OS
`docker-machine start` # Start virtual machine for docker
`docker-machine env`  # It's helps to get environment variables
`eval "$(docker-machine env default)"` # Set environment variables

### Run in project folder
`docker-compose up`

#### Rebuild without cache
`docker-compose build --force-rm --no-cache`

