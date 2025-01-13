# Introduction to Docker

_Based on Aitor Mendivil's work._

- [Introduction to Docker](#introduction-to-docker)
  - [Why Docker?](#why-docker)
  - [Docker Containers](#docker-containers)
  - [Containers Vs Virtual Machines](#containers-vs-virtual-machines)
    - [Docker Pros](#docker-pros)
    - [Docker Cons](#docker-cons)
    - [VM Pros](#vm-pros)
    - [VM Cons](#vm-cons)
  - [Docker Basic Components](#docker-basic-components)
    - [Docker Engine](#docker-engine)
      - [Installation](#installation)
    - [Docker Images](#docker-images)
    - [Docker Hub](#docker-hub)
      - [CHALLENGE 1](#challenge-1)
  - [Using Docker](#using-docker)
    - [Getting Images from the Hub/Registry](#getting-images-from-the-hubregistry)
      - [CHALLENGE 2](#challenge-2)
    - [Running Containers](#running-containers)
    - [Listing Containers](#listing-containers)
      - [CHALLENGE 3](#challenge-3)
  - [Run a static website](#run-a-static-website)
    - [Stopping/killing Containers](#stoppingkilling-containers)
  - [Building Your Own Docker Image](#building-your-own-docker-image)
    - [Step By Step Guide](#step-by-step-guide)
    - [Building it](#building-it)
    - [Running it](#running-it)
      - [CHALLENGE 4](#challenge-4)
    - [Docker Registry](#docker-registry)
      - [CHALLENGE 5](#challenge-5)
  - [Docker Networking](#docker-networking)
    - [CHALLENGE 6](#challenge-6)
  - [Docker Compose](#docker-compose)
    - [CHALLENGE 7](#challenge-7)
    - [CHALLENGE 8](#challenge-8)
    - [CHALLENGE 9](#challenge-9)
  - [Additional Contents](#additional-contents)
    - [Glossary of Terms](#glossary-of-terms)
    - [Dockerfile commands summary](#dockerfile-commands-summary)
    - [Docker CheatSheets](#docker-cheatsheets)

## Why Docker?

- Very Useful, you will realise it later on
- Easy to use
- Major Companies use it
- Companies around us use it, so it is a plus for finding the best job

## Docker Containers

A file system made of layers and a process. It's a package of software that includes everything needed to run it: code, runtime, system tools, system libraries and settings.

## Containers Vs Virtual Machines

There are some benefits to using containers over virtual machines.

### Docker Pros

- Easy to Use
- Lightweight and Powerful
- Fast to deploy
- Easy to share
- Microservice architectures

### Docker Cons

- Only Linux (Not anymore! But works better on Linux)
- Not as good performance (but almost) as a similar on-premise installation

### VM Pros

- Largely adopted (But this is changing)
- Useful for managing DPCs (Deferred Procedure Calls) and IaaS
- Hypervisors are very powerful managing shared hardware resources

### VM Cons

- Slow to update/mantain/deploy
- Not easy share
- More complex (networking)
- Generally, harder

## Docker Basic Components

Now let's see the 3 docker basic components: Docker Engine, Docker Images and DockerHub.

### Docker Engine

Containers are not something invented by docker. But they were the ones to make it easy to use and share them.
The docker helps you to create, run and share containers. It is the main component of docker.

#### Installation

You can find how to install docker [here](https://docs.docker.com/engine/install/)

Once you are done installing Docker, test your Docker installation by running the following command `docker run hello-world`.
You will see the following:

```bash
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
03f4658f8b78: Pull complete
a3ed95caeb02: Pull complete
Digest: sha256:8be990ef2aeb16dbcb9271ddfe2610fa6658d13f6dfb8bc72074cc1ca36966a7
Status: Downloaded newer image for hello-world:latest

Hello from Docker.
This message shows that your installation appears to be working correctly.
...
```

### Docker Images

A Docker Image is a type of container. Docker images have intermediate layers that increase reusability, decrease disk usage, and speed up docker build by allowing each step to be cached. These intermediate layers are not shown by default.

```bash
# To List images:
Usage:  docker images [OPTIONS] [REPOSITORY[:TAG]]
```

### Docker Hub

Dockerhub is the official registry for Docker images. It is a cloud-based repository where you can find and share images. You can also create your own images and share them with the community. You can find the official Docker Hub [here](https://hub.docker.com/).

#### CHALLENGE 1

Find an image that you can use daily (for example Nginx) and get familiar with the Main Page. You don't need the terminal, just browse DockerHub

## Using Docker

### Getting Images from the Hub/Registry

To get started, let's run the following in our terminal:

```bash
docker pull ubuntu:bionic
```

The `pull` command fetches the ubuntu:bionic **image** from the **Docker registry** and saves it in our system. You can use the `docker images` command to see a list of all images on your system.

```bash
$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       bionic    e28a50f651f9   3 weeks ago   63.1MB
```

#### CHALLENGE 2

Get and list the previous image from Challenge 1

### Running Containers

<https://docs.docker.com/engine/reference/commandline/run/>

There are a lot of options for running containers. These are the most common:

```bash
Usage: docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
--help                  Print usage
--env , -e              Set environment variables
--interactive , -i      Keep STDIN open even if not attached
--name                  Assign a name to the container
--publish , -p          Publish a container’s port(s) to the host
--tty , -t              Allocate a pseudo-TTY
--volume , -v           Bind mount a volume
...
```

Great! Let's now run a Docker **container**. To do that you are going to use the `docker run` command.

```bash
$ docker run ubuntu:bionic ls -l
total 64
drwxr-xr-x   2 root root 4096 Dec 15 14:20 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
drwxr-xr-x   5 root root  340 Jan 25 19:46 dev
drwxr-xr-x   1 root root 4096 Jan 25 19:46 etc
drwxr-xr-x   2 root root 4096 Apr 24  2018 home
drwxr-xr-x   8 root root 4096 May 23  2017 lib
drwxr-xr-x   2 root root 4096 Dec 15 14:19 lib64
drwxr-xr-x   2 root root 4096 Dec 15 14:19 media
drwxr-xr-x   2 root root 4096 Dec 15 14:19 mnt
drwxr-xr-x   2 root root 4096 Dec 15 14:19 opt
dr-xr-xr-x 453 root root    0 Jan 25 19:46 proc
drwx------   2 root root 4096 Dec 15 14:20 root
drwxr-xr-x   5 root root 4096 Dec 15 14:20 run
drwxr-xr-x   2 root root 4096 Dec 15 14:20 sbin
drwxr-xr-x   2 root root 4096 Dec 15 14:19 srv
dr-xr-xr-x  13 root root    0 Jan 25 19:46 sys
drwxrwxrwt   2 root root 4096 Dec 15 14:20 tmp
drwxr-xr-x  10 root root 4096 Dec 15 14:19 usr
drwxr-xr-x  11 root root 4096 Dec 15 14:20 var
```

What happened? When you call `run` it is like a shortcut that does several things:

1. The Docker daemon checks local store if the image (bionic in this case) is available locally, and if not, downloads it from Docker Store. (Since we have issued `docker pull ubuntu:bionic` before, the download step is not necessary)
2. The Docker daemon creates the container and then runs a command in that container. The command is the first process that will be executed inside the container.
3. Docker streams the output of the command to the standard output (your shell)

When you run `docker run ubuntu:bionic`, you provided a command (`ls -l`), so Docker started the command specified and you saw the listing. More on commands later.

Let's now try to launch a shell inside our container, in order to interact with it, just as we do with our host computer:

```bash
docker run ubuntu:bionic /bin/sh
```

Wait, nothing happened! Is that a bug? Well, no. These interactive shells will exit after running any scripted commands, unless they are run in an interactive terminal - so for this example to not exit, you need to `docker run -it ubuntu:alpine /bin/sh`.

You are now inside the container shell and you can try out a few commands like `ls -l`, `ps axu`, `top` (to view resources) and others. Exit the container by executing the `exit` command.

### Listing Containers

`docker ps` command shows you all containers that are currently running

```bash
Usage: docker ps [OPTIONS]
--all , -a          Show all containers (default shows just running)
--filter , -f       Filter output based on conditions provided
--format            Pretty-print containers using a Go template
--last , -n -1      Show n last created containers (includes all states)
--latest , -l       Show the latest created container (includes all states)
--no-trunc          Don’t truncate output
--quiet , -q        Only display numeric IDs
--size , -s         Display total file sizes
```

try it:

```bash
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

If you want to see previous ran containers, you can use the option `-a`. Try runnig:

```bash
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
967bf511e52a        ubuntu:bionic             "/bin/sh"                6 minutes ago       Exited (0) 6 minutes ago                               romantic_mayer
7cd8e0cf10f1        ubuntu:bionic             "ls -l"                  13 minutes ago      Exited (0) 13 minutes ago                              flamboyant_lewin
...
```

#### CHALLENGE 3

Find an image that is useful for your daily job in the Docker Hub and try to run it. For example: nginx, alpine, python, java...

## Run a static website

The image that you are going to use is a single-page website that was already created for a Docker 101 course and is available on the Docker Store as [`dockersamples/static-site`](https://store.docker.com/community/images/dockersamples/static-site). You can download and run the image directly in one go using `docker run` as follows.

```bash
docker run -d dockersamples/static-site
```

But we can't access the website yet! The container is executed inside it's own network, so we need ports in our host to access it!

Let's re-run the command with some new flags to publish ports and pass your name to the container to customize the message displayed. We'll use the _-d_ option again to run the container in detached mode.

Stop the container that you have just launched. In order to do this, we need the container ID.

### Stopping/killing Containers

```bash
# Stopping
Usage: docker stop [OPTIONS] CONTAINER [CONTAINER...]
# Killing
Usage: docker kill [OPTIONS] CONTAINER [CONTAINER...]
```

but first we need to get its ID: (First column)

```bash
$ docker ps
CONTAINER ID        IMAGE                  COMMAND                  CREATED             STATUS              PORTS               NAMES
f7e1e504ca3e        dockersamples/static-site   "/bin/sh -c 'cd /usr/"   28 seconds ago      Up 26 seconds       80/tcp, 443/tcp     crazy_galileo
```

And now stop and remove it!

```bash
docker stop f7e1e504ca3e
docker rm   f7e1e504ca3e
```

Let's run it properly exposing the ports!

```bash
docker run --name static-site -d -P dockersamples/static-site
```

In the above command:

- `-d` will create a container with the process detached from our terminal
- `-P` will publish all the exposed container ports to random ports on the Docker host.
- `-e` is how you pass environment variables to the container
- `--name` allows you to specify a container name

with `-P` the ports are assigned automatically. We can check them using:

```bash
$ docker ps
CONTAINER ID        IMAGE                       COMMAND                  CREATED             STATUS              PORTS                                           NAMES
f7e1eb4fc224        dockersamples/static-site   "/bin/sh -c 'cd /usr…"   4 minutes ago       Up 4 minutes        0.0.0.0:32769->80/tcp, 0.0.0.0:32768->443/tcp   static-site
```

or:

```bash
$ docker port static-site
443/tcp -> 0.0.0.0:32772
80/tcp -> 0.0.0.0:32773
```

now try to access <http://localhost:32772> in your web browser. (Replace the port with your own `http://<YOUR_IPADDRESS>:[YOUR_PORT_FOR 80/tcp]`)

you can also specify your own port with `-p` option. Is mandatory to know the exposed ports.

```bash
docker run --name static-site-2 -d -p 8888:80 dockersamples/static-site
```

Let's remove all proof of existence of the previous containers ;)

```bash
docker rm -f static-site
docker rm -f static-site-2
```

Remove all uneeded containers and check your environment is clean:

Run `docker ps` to make sure the containers are gone.

```bash
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

## Building Your Own Docker Image

[Image Building Reference](https://docs.docker.com/engine/reference/builder/)

An important distinction with regard to images is between _base images_ and _child images_.

- **Base images** are images that have no parent images, usually images with an OS like ubuntu, alpine or debian.

- **Child images** are images that build on base images and add additional functionality.

Another key concept is the idea of _official images_ and _user images_. (Both of which can be base images or child images.)

- **Official images** are Docker sanctioned images. Docker, Inc. sponsors a dedicated team that is responsible for reviewing and publishing all Official Repositories content. This team works in collaboration with upstream software maintainers, security experts, and the broader Docker community. These are not prefixed by an organization or user name. In the list of images above, the `python`, `node`, `alpine` and `nginx` images are official (base) images. To find out more about them, check out the [Official Images Documentation](https://docs.docker.com/docker-hub/official_repos/).

- **User images** are images created and shared by users like you. They build on base images and add additional functionality. Typically these are formatted as `user/image-name`. The `user` value in the image name is your Docker Store user or organization name.

### Step By Step Guide

- Create a file called **Dockerfile** in your work directory, and add content to it as described below.

  ```bash
  # Simple Server with Docker

  # 1. Create your work directory
  mkdir -p /home/<username>/dev/simple_server
  cd /home/<username>/dev/simple_server
  # 2. Create a Dockerfile
  touch Dockerfile
  # 3. Edit the Dockerfile with your own commands. Example:
  nano Dockerfile
  ```

- We'll start by specifying our base image, using the `FROM` keyword:

  ```dockerfile
  FROM ubuntu
  ```

- We are going to define ENV vars. can be changed during the container execution (`run` command)

  ```dockerfile
  ENV PORT 8080
  ENV WORKDIR /tmp/server
  ```

- In our work folder, we are going to create an HTML file `index.html`

  ```dockerfile
  <!doctype html>
  <html>
    <head>
      <title>This is my docker website!</title>
    </head>
    <body>
      <p>This is an example paragraph. Anything in the <strong>body</strong> tag will appear on the page, just like this <strong>p</strong> tag and its contents.</p>
    </body>
  </html>
  ```

- We add the command to create a workdir in our Dockerfile:  

  ```dockerfile
  RUN mkdir ${WORKDIR}
  ```

- Now, we can copy the `index.html` from our host computer to the workdir in the container. Check out that workdir is an ENV var that can be changed during container execution.

  ```dockerfile
  COPY index.html ${WORKDIR}
  ```

- We are going to use Python `SimpleHTTPServer` as our server, so we need to install python:

  ```dockerfile
  RUN apt-get install -y python
  ```

- We also have to specify the port number which needs to be exposed. It is our other ENV vart:

  ```dockerfile
  EXPOSE ${PORT}
  ```

- The last step is the command for running the application. Use the [CMD](https://docs.docker.com/engine/reference/builder/#cmd) command to do that:

  ```dockerfile
  CMD cd ${WORKDIR} && python -m SimpleHTTPServer ${PORT}
  ```

### Building it

Now that you have your `Dockerfile`, you can build your image. The `docker build` command creates a docker image from a `Dockerfile`.

The `docker build` command is quite simple - it takes an optional tag name with the `-t` flag, and the location of the directory containing the `Dockerfile` - the `.` indicates the current directory:

```bash
sudo docker build -t simplehttpserver:latest .
```

>**Caution** Don't forget the dot to indicate the directory!

### Running it

The next step in this section is to run the image and see if it actually works!

```bash
sudo docker run -p 80:8080 simplehttpserver:latest
```

#### CHALLENGE 4

Create your own website using Docker.

Following the previous steps and the docs, build your own Docker Image. Don't just copy the commands, try it in another language, or use nginx instead of python

A cool thing about Docker is that you only need a Dockerfile, and your code to recreate your image and run your container anywhere, this makes it perfect to store it in a repo, and much more easy to integrate with CI systems such as Jenkins

### Docker Registry

It's your own local Hub. You can run it using the following commands:

```bash
docker run -d -p 5000:5000 --name registry registry:2
```

```bash
docker pull <my_registry_endpoint>:<your/docker/image/repo>:<version_tag>
```

Docker pulling and pushing example

```bash
docker run -d -p 5000:5000 --name registry registry:2
docker pull ubuntu
docker tag ubuntu localhost:5000/myfirstimage
docker push localhost:5000/myfirstimage
docker pull localhost:5000/myfirstimage
docker stop registry && docker rm -v registry
```

#### CHALLENGE 5

Push your image from Challenge 4 to your local registry

## Docker Networking

- Bridge: All docker has its own IP inside the Docker0 network (type `ifconfig -a` to check it out)
- Host: Containers and Host share the same network (Caution with the ports!)
- None: No network interface

```bash
# try this:
docker network create --driver bridge isolated_nw
docker network inspect isolated_nw
docker network ls


docker run --network=isolated_nw -itd --name=example busybox
```

### CHALLENGE 6

Run two containers in the same bridge network (a custom network made by you) and check if their IPs are in the same range (docker inspect command) Also, check the communication between containers is possible (for example with netcat, telnet or ping)

More info [here](https://devops.datenkollektiv.de/how-to-create-a-bridge-network-with-docker.html)

## Docker Compose

Compose is a tool for defining and running multi-container Docker applications.

[Docker Compose Docs](https://docs.docker.com/compose/overview/)

### CHALLENGE 7

Install Docker Compose! Link [here](https://docs.docker.com/compose/install/)

```bash
$ sudo apt-get update
$ sudo apt-get install docker-compose-plugin
$ docker compose version
Docker Compose version v2.15.1
```

### CHALLENGE 8

Get familiar with Docker and Docker Compose by doing the [Getting started Guide](https://docs.docker.com/compose/gettingstarted/)

### CHALLENGE 9

Create your own Dockerized App (Can be a very simple http API) that depends on a database (MySQL, PostgreSQL, the one you like) if you don't have time you can use something that already exists, for example, Wordpress, then, create the Docker Compose that deploys both containers. You have succesfully created a microservice oriented architecture!

## Additional Contents

### Glossary of Terms

- _Images_ - The file system and configuration of our application which are used to create containers. To find out more about a Docker image, run `docker inspect alpine`. In the demo above, you used the `docker pull` command to download the **ubuntu/zesty** image. When you executed the command `docker run hello-world`, it also did a `docker pull` behind the scenes to download the **hello-world** image.
- _Containers_ - Running instances of Docker images &mdash; containers run the actual applications. A container includes an application and all of its dependencies. It shares the kernel with other containers, and runs as an isolated process in user space on the host OS. You created a container using `docker run` which you did using the alpine image that you downloaded. A list of running containers can be seen using the `docker ps` command.
- _Docker daemon_ - The background service running on the host that manages building, running and distributing Docker containers.
- _Docker client_ - The command line tool that allows the user to interact with the Docker daemon.

### Dockerfile commands summary

Here's a quick summary of the few basic commands we used in our Dockerfile.

- `FROM` starts the Dockerfile. It is a requirement that the Dockerfile must start with the `FROM` command. Images are created in layers, which means you can use another image as the base image for your own. The `FROM` command defines your base layer. As arguments, it takes the name of the image. Optionally, you can add the Docker Cloud username of the maintainer and image version, in the format `username/imagename:version`.

- `RUN` is used to build up the Image you're creating. For each `RUN` command, Docker will run the command then create a new layer of the image. This way you can roll back your image to previous states easily. The syntax for a `RUN` instruction is to place the full text of the shell command after the `RUN` (e.g., `RUN mkdir /user/local/foo`). This will automatically run in a `/bin/sh` shell. You can define a different shell like this: `RUN /bin/bash -c 'mkdir /user/local/foo'`

- `COPY` copies local files into the container.

- `CMD` defines the commands that will run on the Image at start-up. Unlike a `RUN`, this does not create a new layer for the Image, but simply runs the command. There can only be one `CMD` per a Dockerfile/Image. If you need to run multiple commands, the best way to do that is to have the `CMD` run a script. `CMD` requires that you tell it where to run the command, unlike `RUN`. So example `CMD` commands would be:

```dockerfile
  CMD ["python", "./app.py"]

  CMD ["/bin/bash", "echo", "Hello World"]
```

>**Note:** CMD can be overridden by the `docker run` command. For example, if you have a `CMD` that runs a Python script, you can override it by running `docker run <image> python ./app.py` to run a different Python script.

- `EXPOSE` creates a hint for users of an image which ports provide services. It is included in the information which
 can be retrieved via `$ docker inspect <container-id>`.

>**Note:** The `EXPOSE` command does not actually make any ports accessible to the host! Instead, this requires
publishing ports by means of the `-p` flag when using `$ docker run`.  

- `PUSH` pushes your image to Docker Cloud, or alternately to a [private registry](https://docs.docker.com/registry/)

>**Note:** If you want to learn more about Dockerfiles, check out [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/).

### Docker CheatSheets

<http://files.zeroturnaround.com/pdf/zt_docker_cheat_sheet.pdf>

<https://reinvent.awsevents.com/_media/docs/sponsors/gold/Docker-Inc_Commands-Cheat-Sheet.pdf>
