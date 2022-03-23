# What is this?

The code suppliment to the F21SM Docker Masterclass.
Contains a number of important Docker commands, many of which I will have used during the lecture.
Also contains important code that I might have used during the lectures, and the tutorial exercises.

# Docker Command Reference

```bash
# pull an container image onto your machine
docker pull <IAMGE_NAME[:TAG}>

# learn more about the image
docker image inpsect <IMAGE>

# run a container on your machine
docker container run -it --rm \
                        [--name <NAME>] \                     # image name?
			[-v <LOCAL_DIR>:<DOCKER_DIR>] \       # mount a local dir?
			[-d] \                                # run in background?
			[-w <DOCKER_WORK_DIR>] \              # change workind dir in container?
			[-p <LOCAL_PORT>:<DOCKER_PORT>] \     # forward a port into the container?
			[--env VAR1=val1 --env VAR2=val2 ...] # set env variables?
			[--env-file env.list]                 # list of key-val pairs for env variables?
			[--network=<NETWORK_NAME>]            # attach container to a network?
			<IMAGE_NAME> [COMMAND]                # name of the image and command to run

# find running containers on your system
docker ps

# find all containers on your system, even if they're not running
docker ps -a

# start a stopped container
docker start <CONTAINER>

# attach to a running container, IE, assume the main process
# once you control-C, you will most likely stop the container
docker attach <CONTAINER>

# execute a command within the context of a container (does not tamper with the main process)
# if you're just trying to nip into a container to debug it this is probably what you want
docker container attach [-it] <CONTAINER> <COMMAND>

# stop a running container (will also remove container if it was created with the --rm flag)
docker stop <CONTAINER>

# remove (delete) a container
docker rm <CONTAINER>

# force kill a stubborn container that wont stop. nasty, try to avoid this if you can.
docker rm <RUNNING_CONTAINER> -f

# use Dockerfile in current dir to build a container with the name NAME:TAG
docker build . [-t <NAME[:TAG]>]

# list docker volumes on your host VM / machine
docker volume ls

# create a docker volume with a specific name using the (default) local driver
docker volume create -d local --name <VOLUME_NAME>

# remove a docker volume
docker volume rm

# list docker network interfaces on your computer
docker network ls

# inspect the network
docker network inspect <NETWORK_NAME>

# attach a running container to the network
docker network connect <NETWORK_NAME> <CONTAINER_NAME>
```
