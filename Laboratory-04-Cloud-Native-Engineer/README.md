# Laboratory 04 - Cloud-Native Engineer

## Mission Overview

In this laboratory activity, we focused on learning the basic concepts of cloud-native computing and containerization. I compared traditional Virtual Machines (VMs) with containers and learned why containers are considered lightweight and faster to start. I also used the KillerCoda Ubuntu environment to practice Docker commands and deployed an Nginx web server as my first containerized application. Through the activity, I was able to experience how Docker can simplify the process of running and managing applications.

## Objectives

The main objectives of this laboratory activity were to:

* Understand the differences between Virtual Machines and containers.
* Use a Docker-enabled Ubuntu environment through KillerCoda.
* Verify that Docker was installed and running properly.
* Practice basic Docker CLI commands.
* Pull the official Nginx image from Docker Hub.
* Run an Nginx web server inside a Docker container.
* Use port mapping to access the Nginx server.
* Test the containerized web server using `curl`.
* Practice the basic Docker container lifecycle.
* Document the activity and organize the outputs in my GitHub portfolio.

## Docker Commands Executed

### 1. Docker Environment Verification

I first checked the Docker installation and environment using:

```bash
docker --version
docker info
```

The `docker --version` command displayed the installed Docker version, while `docker info` showed details about the Docker server and environment. The KillerCoda environment was running Docker version **29.1.3** on **Ubuntu 24.04.4 LTS**.

### 2. Downloading the Nginx Image

I downloaded the official Nginx image using:

```bash
docker pull nginx
```

This command downloaded the Nginx image that was needed to create the web server container.

### 3. Running the Nginx Container

I created and started the Nginx container using:

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

The container was named `nginx-server` and was run in detached mode. Port `8080` on the host was connected to port `80` inside the container.

### 4. Testing the Nginx Server

I tested the web server using:

```bash
curl http://localhost:8080
```

The command successfully returned the Nginx welcome page, confirming that the containerized web server was running properly.

### 5. Managing the Container Lifecycle

I checked the running container with:

```bash
docker ps
```

I then stopped the Nginx container:

```bash
docker stop nginx-server
```

To check the stopped container, I used:

```bash
docker ps -a
```

Finally, I removed the container:

```bash
docker rm nginx-server
```

I used `docker ps -a` again to confirm that the container had been completely removed.

## Skills Learned

I learned how to check a Docker environment, download a Docker image, create and run a container, connect ports, and manage a container. I also learned how to use curl to test a web server and how to organize my laboratory files and screenshots in GitHub.

## Challenges Encountered

One of the challenges I encountered was understanding how the Docker port mapping `-p 8080:80` works. I initially needed to understand why port 8080 was used on the host while Nginx uses port 80 inside the container. After running the container and using `curl http://localhost:8080`, I was able to see that the host port was forwarding requests to the Nginx service inside the container.

The following screenshots serve as evidence of the Docker operations completed during this laboratory activity:

* `docker-version.png` - Docker installation and environment verification
* `nginx-running.png` - Successful Nginx container deployment and `curl` test
* `container-lifecycle.png` - Container listing, stopping, and removal
