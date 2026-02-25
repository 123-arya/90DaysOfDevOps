# Task 1: What is Docker?

## What is a container and why do we need them?

Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), can handle more applications and require fewer VMs and Operating systems. Containers isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.

## Containers vs Virtual Machines — what's the real difference?

Containers and virtual machines are very similar resource virtualization technologies. Virtualization is the process in which a system singular resource like RAM, CPU, Disk, or Networking can be ‘virtualized’ and represented as multiple resources. The key differentiator between containers and virtual machines is that virtual machines virtualize an entire machine down to the hardware layers and containers only virtualize software layers above the operating system level.

##  What is the Docker architecture? (daemon, client, images, containers, registry)

Docker daemon - The core "engine" of Docker, running as a persistent background process on the host machine.

Docker Client - The primary interface that users interact with, typically the Command Line Interface (CLI).

Docker Imanges - Read-only templates or blueprints with instructions for creating a Docker container.

Docker Containers - A runnable instance of a Docker image.

Docker Registry -  A centralized storage and distribution location for Docker images.

# Task 2: Install Docker

sudo apt update && sudo apt install docker.io

docker --version

docker run hello-world

# Task 3: Run Real Containers

docker run -itd nginx

docker run -itd ubuntu

docker ps 

docker ps -a

docker stop <container_id>

docker rm <container_id>

# Task 4: Explore

## Run a container in detached mode — what's different?

starts it in the background, freeing up your terminal immediately instead of occupying it with container logs.

## Give a container a custom name

docker run --name [custom name] -d [image name]

## Map a port from the container to your host

docker run --name task -d -p host:container nginx

## Check logs of a running container

docker logs <container_id>

## Run a command inside a running container

docker exec -it <container_id> bash



