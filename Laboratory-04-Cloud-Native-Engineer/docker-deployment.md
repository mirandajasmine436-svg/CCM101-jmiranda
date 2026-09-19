# 🐳 Docker Deployment

## 🚀 Nginx Container Deployment

### Pull the Nginx Image

```bash
docker pull nginx
```

This command downloads the official Nginx image from Docker Hub.

### Run the Nginx Container

```bash
docker run -d --name nginx-server -p 8080:80 nginx
```

This command runs the Nginx container in detached mode and maps port 8080 on the host to port 80 inside the container.

### Test the Nginx Web Server

```bash
curl http://localhost:8080
```

This command sends an HTTP request to the Nginx web server and displays its HTML response in the terminal.

## 🔄 Container Lifecycle

### 1. List Running Containers

```bash
docker ps
```

This command lists all Docker containers that are currently running.

### 2. Stop the Running Container

```bash
docker stop nginx-server
```

This command stops the running Nginx container without removing it.

### 3. Verify the Container is Stopped

```bash
docker ps
```

This command verifies that the Nginx container is no longer running.

### 4. Remove the Container

```bash
docker rm nginx-server
```

This command permanently removes the stopped Nginx container from Docker.
