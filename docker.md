# Docker:

- [ref: https://training.play-with-docker.com/ops-s1-hello/]

- **VM vs Docker**
    - The VM is a **hardware abstraction**: it takes physical CPUs and RAM from a host, and divides and shares it across several smaller virtual machines. There is an OS and application running inside the VM, but the virtualization software usually has no real knowledge of that.
    - A container is an **application abstraction**: the focus is really on the OS and the application, and not so much the hardware abstraction. Many customers actually use both VMs and containers today in their environments and, in fact, may run containers inside of VMs.

## First Alpine Linux Containers
### 1. Running your first container:
$ `docker container run hello-world`

## 1.1 Docker Images:
$ `docker image pull alpine`
$ `docker image ls`

$ `docker container run alpine ls -l`
$ `docker container run alpine echo "hello from alpine"`
$ `docker container run alpine /bin/sh`
$ `docker container run -it alpine /bin/sh`

$ `docker container ls`
$ `docker container ls -a`

$ `docker container run --help`
$ `docker container start <container ID>`
$ `docker container exec <container ID> ls`

## 1.3 Terminology
In the last section, you saw a lot of Docker-specific jargon which might be confusing to some. So before you go further, let’s clarify some terminology that is used frequently in the Docker ecosystem.

- **Images** - The file system and configuration of our application which are used to create containers. To find out more about a Docker image, run docker image inspect alpine. In the demo above, you used the docker image pull command to download the alpine image. When you executed the command `docker container run hello-world`, it also did a docker image pull behind the scenes to download the hello-world image.
- **Containers** - Running instances of Docker images — containers run the actual applications. A container includes an application and all of its dependencies. It shares the kernel with other containers, and runs as an isolated process in user space on the host OS. You created a container using docker run which you did using the alpine image that you downloaded. A list of running containers can be seen using the docker container ls command.
- **Docker daemon** - The background service running on the host that manages building, running and distributing Docker containers.
- **Docker client** - The command line tool that allows the user to interact with the Docker daemon.
- **Docker Store** - Store is, among other things, a registry of Docker images. You can think of the registry as a directory of all available Docker images. You’ll be using this later in this tutorial.

---

## Doing More With Docker Images
We will start with the simplest form of image creation, in which we simply commit one of our container instances as an image. Then we will explore a much more powerful and useful method for creating images: the Dockerfile.

### Image creation from a container
$ `docker container run -it ubuntu bash`
$ `apt-get update`
$ `apt-get install -y figlet`
$ `figlet "hello docker"`
$ `exit`

- To start, we need to get the ID of this container using the ls command (do not forget the -a option as the non running container are not returned by the ls command).
$ `docker container ls -a`

- Before we create our own image, we might want to inspect all the changes we made. Try typing the command:
$ `docker container diff <container ID>`

- Now, to create an image we need to “commit” this container. Commit creates an image locally on the system running the Docker engine. Run the following command, using the container ID you retrieved, in order to commit the container and create an image out of it.
$ `docker container commit CONTAINER_ID`
$ `docker image tag <IMAGE_ID> ourfiglet`
$ `docker image ls`

- Now we will run a container based on the newly created ourfiglet image:
$ `docker container run ourfiglet figlet hello`

---

## Docker Compose
Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a **YAML file** to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

**Using Compose is basically a three-step process:**
1. Define your app’s environment with a Dockerfile so it can be reproduced anywhere.
2. Define the services that make up your app in docker-compose.yml so they can be run together in an isolated environment.
3. Run `docker-compose up` and Compose starts and runs your entire app.

**Compose has commands for managing the whole lifecycle of your application:**
- Start, stop, and rebuild services
- View the status of running services
- Stream the log output of running services
- Run a one-off command on a service