# SQLite docker

```
This SQLite docker repository consists of a SQLite Dockerfile image to run SQLite as a self-host with docker-compose script to run SQLite in a compose environment, as well as a docker run wrapper script based on my project 'easydock' runner script that uses docker run to manage instead of docker-compose (if the docker-compose file doesnt work for you).

The primary SQLite build in this repository is, at the moment, from the SQLite image Dockerfile provided, instructions to startup the SQLite container using docker run individually is provided below.
```

## Setup

### Pre-Requisites
+ Add user to 'docker' group

### Dependencies
+ docker
+ docker-compose

## Documentation
### Synopsis/Syntax

#### easydock docker run wrapper
```console
easydock {options} <arguments>
```

### Parameters
+ -b | --build  : Build the local Dockerfile specified
+ -e | --exec   : Execute a shell command inside the container
+ -u | --up     : aka "Up", Build the local Dockerfile required AND startup/run a container using the specified image and flags
+ -d | --down   : aka "Down", Stop a running container and remove after stopping 
+ -p | --view-processes : View current docker container processes (using docker container ps)
+ -r | --run    : docker run command to startup the container using the specified image and flags (using docker run)
+ -R | --remove : Remove the specified docker container after its stopped (using docker container rm)
+ -s | --start  : Start a stopped container
+ -S | --stop   : Stop a running container

### Usage

#### Dockerfile image build
- Building docker image
    ```console
    docker build . -t [image-name]
    ```

#### Docker exec
- Enter container shell
    ```console
    docker exec -it [container-name] /bin/bash
    ```

#### Docker run
- Startup using Dockerfile image
    ```console
    docker run -dit -v "host-system-path:/db:permission" --name "container-name" [image-name] [commands]
    ```

#### docker-compose
- Starting up the docker-compose with local Dockerfile image
    ```console
    docker-compose up -d --build [container-name]
    ```

- Tear down docker-compose
    ```console
    docker-compose down
    ```

- Stop a running docker-compose environment
    ```console
    docker-compose stop [container-name]
    ```

- Start a stopped docker-compose environment
    ```console
    docker-compose start [container-name]
    ```

- Running SQLite command in container with docker-compose and entrypoint
    ```console
    docker-compose run sqlite [command]
    ```

## Wiki

