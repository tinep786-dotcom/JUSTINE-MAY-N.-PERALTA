
Checkpoint 6 - Technical Documentation
Docker Compose Guide: Nextcloud + MariaDB
The Compose File
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
What does the services: block do?
The services: block defines every container that makes up the application. Each entry under it (database and app) is one service, with its own image, environment variables, and port settings. Docker Compose reads this block and creates, networks, and starts all the containers together. It also puts them on a shared default network automatically.

How did the Nextcloud container find the database?
The MYSQL_HOST=database variable tells Nextcloud which host to connect to. Compose creates a private network for the stack and registers each service name as a DNS hostname on it. The name database therefore resolves to the MariaDB container's IP address, so no IP address has to be hardcoded.

The MYSQL_USER, MYSQL_PASSWORD, and MYSQL_DATABASE values are identical in both services so that Nextcloud logs in with the account MariaDB created.

docker run vs docker-compose up -d
docker run	docker-compose up -d
Scope	Starts one container	Starts every service in the file
Configuration	Long command with flags (-p, -e, --name)	Stored in a reusable YAML file
Networking	Must be created and linked manually	Created automatically
Repeatability	Easy to mistype or forget flags	Same result every time; can be version-controlled
Cleanup	Stop and remove each container separately	docker-compose down removes the whole stack
The -d flag runs the containers in the background (detached mode).
