#                                                        DOCKER

## What is docker ?
Docker is a platform and set of tools designed to make it easier to create, deploy, and run applications using containers. Containers are lightweight, portable, and self-sufficient units that can encapsulate an application and its dependencies. Docker provides a standardized way to package, distribute, and manage these containers, making it simpler to develop, deploy, and scale applications across different environments.

## Key components of Docker include:
>Docker Engine: The core software responsible for building and running containers. It includes a daemon process, REST API, and a command-line interface (CLI) that allows users to interact with Docker.

>Docker Image: A lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and system tools.

>Container: An instance of a Docker image that runs in isolation on a host system. Containers share the host OS kernel but have their own file system, process space, and network interfaces.

>Dockerfile: A text file that contains instructions for building a Docker image. It defines the base image, sets up the environment, and specifies how to install and configure software within the image.

>Docker Hub: A cloud-based registry service provided by Docker, where users can find and share Docker images. It allows for easy distribution of pre-built images.

>Docker simplifies the deployment process by eliminating the "it works on my machine" problem, as containers ensure consistency across development, testing, and production environments. It has gained widespread popularity in the software development and IT communities due to its flexibility, efficiency, and ease of use

# Why docker is used ?
There are several reasons why Docker has gained popularity or Why docker is used:

  1.Consistency: Docker ensures that applications run consistently across different environments, such as development, testing, and production. This eliminates the "it works on my machine" problem and makes it easier to troubleshoot and debug issues.

  2.Portability: Docker containers are self-contained units that can be easily moved between different hosts or cloud environments. This makes it easier to deploy applications across different infrastructures without worrying about compatibility issues.

  3.Scalability: Docker allows you to scale applications horizontally by running multiple instances of a container across a cluster of machines. This makes it easier to handle increased traffic or workload by simply adding more containers.

  4.Efficiency: Docker containers are lightweight and share the host system's operating system kernel. This means that containers have a minimal overhead compared to traditional virtual machines, resulting in better resource utilization and faster startup times.

  5.Isolation: Docker provides a level of isolation between containers, ensuring that applications running in different containers do not interfere with each other. This enhances security and makes it easier to manage dependencies and versioning.

# How Does Docker Work?
At the core of Docker is the Docker engine, which is responsible for building and running containers. The Docker engine uses a client-server architecture, where the Docker client communicates with the Docker daemon (server) to perform various operations.

Docker images serve as the building blocks for containers. An image is a read-only template that contains the application's code, runtime environment, system tools, and libraries. Images are created from a set of instructions called Dockerfiles, which define the steps to build the image.

Containers, on the other hand, are lightweight and portable instances of images. They can be started, stopped, and moved between different environments without any changes to the underlying application. Each container runs in isolation, with its own filesystem, network, and process space.

Docker packages, provisions and runs containers. Container technology is available through the operating system: A container packages the application service or function with all of the libraries, configuration files, dependencies and other necessary parts and parameters to operate. Each container shares the services of one underlying OS. Docker images contain all the dependencies needed to execute code inside a container, so containers that move between Docker environments with the same OS work with no changes




# DOCKER COMMAND 

##Build an Image from a Dockerfile
```
docker build -t <image_name>
```
##Build an Image from a Dockerfile without the cache
```
docker build -t <image_name> .
```

##List local images
```
docker images
```
##Delete an Image
```
docker rmi <image_name>
```

##Login into Docker
```
docker login -u <username>
```
##Publish an image to Docker Hub
```
docker push <username>/<image_name>
```
##Search Hub for an image
```
docker search <image_name>
```
##Pull an image from a Docker Hub
```
docker pull <image_name>
```

##Create and run a container from an image, with a custom name:
```
docker run --name <container_name> <image_name>
```
##Run a container with and publish a container’s port(s) to the host.
```
docker run -p <host_port>:<container_port> <image_name>
```
##Run a container in the background
```
docker run -d <image_name>
```
##Start or stop an existing container:
```
docker start|stop <container_name> (or <container-id>)
```
##Remove a stopped container:
```
docker rm <container_name>
```
##Open a shell inside a running container:
```
docker exec -it <container_name> bash
```
##Fetch and follow the logs of a container:
```
docker logs -f <container_name>
```
##To inspect a running container:
```
docker inspect <container_name> (or <container_id>)
```
##To list currently running containers:
```
docker ps
```
##List all docker containers (running and stopped):
```
docker ps --all
```
##Start the docker daemon
```
docker -d
```
##Get help with Docker. Can also use –help on all subcommands
```
docker --help
```
##Display system-wide information
```
docker info
```
