# 🐳 Docker Compose Technical Guide

## 1. What does the `services:` block do?
The `services:` block is the core of a Docker Compose file. It defines the individual "building blocks" or containers that make up your application. In our file, we defined two services: `database` (which runs MariaDB) and `app` (which runs Nextcloud). Compose reads this block to know exactly which images to pull, what ports to expose, and what environment variables to set for each container.

## 2. How did the Nextcloud app container know how to find the database container?
Docker Compose automatically creates a private network for all the services defined in the file. When we set the environment variable `MYSQL_HOST=database` inside the `app` service, we are telling Nextcloud to look for a host named "database". Because Docker Compose registers the service names as hostnames on that private network, the Nextcloud container can seamlessly resolve `database` to the correct internal IP address of the MariaDB container. 

## 3. `docker run` vs. `docker-compose up -d`
- **`docker run`** (used in Mission 4) is used to start a single container. You have to manually type out all the flags (ports, environment variables, volumes) every single time you want to run it. 
- **`docker-compose up -d`** is used to deploy an entire multi-container application. It reads the `docker-compose.yml` file and automatically builds the network, pulls the images, and starts all containers in the correct order with just one command. It is much more efficient, reproducible, and less prone to human error.
