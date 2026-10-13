# Docker Deployment

## Nginx Container Deployment

For this activity, Docker was used to pull and deploy an Nginx web server. The Nginx container was run in detached mode with port 8080 on the host mapped to port 80 inside the container.

### 1. Pull the Nginx Image

```bash
docker pull nginx
```

This command downloads the official Nginx image from Docker Hub.

### 2. Run the Nginx Container

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command creates and runs an Nginx container in the background and maps host port 8080 to port 80 inside the container.

### 3. Test the Web Server

```bash
curl http://localhost:8080
```

This command sends an HTTP request to the Nginx server through port 8080 and confirms that the server is working by displaying the Nginx welcome page.

## Container Lifecycle

### 4. List Running Containers

```bash
docker ps
```

This command displays the containers that are currently running.

### 5. Stop the Container

```bash
docker stop nginx-server
```

This command stops the running Nginx container without immediately deleting it.

### 6. Verify the Container Is Stopped

```bash
docker ps -a
```

This command displays all containers, including stopped containers, and confirms that `nginx-server` has an `Exited (0)` status.

### 7. Remove the Container

```bash
docker rm nginx-server
```

This command permanently removes the stopped `nginx-server` container.

### 8. Verify the Container Was Removed

```bash
docker ps -a
```

This command confirms that the `nginx-server` container no longer exists.

## Screenshots

* `docker-version.png` — Docker installation and environment verification
* `nginx-running.png` — Successful Nginx deployment and HTTP request
* `container-lifecycle.png` — Container stop, verification, and removal
