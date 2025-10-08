 06-10-2025 02:50

Tags: [[Docker]]  [[Note]]
# **Docker Course Notes**

## Overview

1. What is Docker? – Introduction to Docker and containerization

2. Containers vs Images – Difference between images (templates) and running containers

3. Basic Docker Commands – Common CLI commands to manage images and containers

4. Dockerfile & Building Images – Instructions to build custom images

5. Docker Compose – Defining and managing multi-container applications

6. Persistent Storage & Volumes – Handling data persistence beyond container lifecycles

7. Pushing to a Registry – Sharing images via Docker Hub or private registries

8. Best Practices – Tips for efficient and secure Docker usage

9. Quick Docker Command Summary – Handy commands for daily use
## What is Docker?

- **Docker**: Open-source platform that enables developers to create, deploy, and run applications inside lightweight, portable containers. These containers package an application and its dependencies, ensuring consistent behaviour across different environments.
- Solves problems like: 
	- Isolation of applications
	- Portability (same container runs anywhere)
	- Simplified dependencies / dev environments
	- Efficient resource usage
## Containers vs Images

- **Image**: A read-only template; file system + settings
- **Container**: A running instance of an image
- Images are versioned; containers are ephemeral
- Use Docker Hub or private registry to store images

Extra: [[Containers vs VMs]]
## Basic Docker Commands

- `docker pull <image>` — download an image
- `docker images` — list local images
- `docker run <image>` — run a container
    - `-d` for detached mode
    - `-p hostPort:containerPort` for port mapping
    - `--name` to name container
- `docker ps` — list running containers
- `docker ps -a` — list all containers (including stopped)
- `docker stop <container>` / `docker start <container>`
- `docker rm <container>` — remove container
- `docker rmi <image>` — remove image

## Dockerfile & Building Images

**Dockerfile Directives:**
- `FROM` — base image
- `WORKDIR` — working directory inside container
- `COPY` / `ADD` — copy files into image
- `RUN` — run commands during build
- `EXPOSE` — declare ports
- `CMD` / `ENTRYPOINT` — default container start command

**Build and Tag**
- `docker build -t my-image:tag .`
- `docker tag my-image myrepo/my-image:tag`

Extra: [[Dockerfile structure & best practices]]

## Docker Compose

**Why use it:** Define multi-container apps with one YAML file.

**Sample `docker-compose.yml`:**
```yaml
version: '3'  
services:  
 app:  
  build: .  
  ports:  
   - "3000:3000"  
 db:  
  image: postgres  
  volumes:  
   - db-data:/var/lib/postgresql/data

volumes:  
 db-data:
```

**Key Commands:**
- `docker-compose up`
- `docker-compose up -d`
- `docker-compose down`
- `docker-compose logs`
- `docker-compose exec <service> <command>`

Extra: [[Docker Compose cheatsheet]]

## Persistent Storage & Volumes

- Containers are **ephemeral**
- Use **named volumes** or **bind mounts** to persist data

**Compose Volume Example:**
```yaml
volumes:  
 db-data:
```
Mount into a container:
- `volumes: - db-data:/path/in/container`

Extra: [[Persistent storage in Docker]]

## Pushing to a Registry

- Authenticate: `docker login`
- Tag: `docker tag image repo/image:tag`
- Push: `docker push repo/image:tag`

Used in CI/CD pipelines and cloud deployment.

Extra: [[Deploying containers to cloud or registry workflow]]

## Best Practices

- Keep Dockerfile small and optimized
- Use `.dockerignore` to reduce image size
- Avoid hardcoding secrets
- Use volumes for writable data
- Prefer multi-stage builds for production
- Use lightweight base images (e.g. Alpine)

## Quick Docker Command Summary

docker pull nginx:latest  
docker run -d -p 8080:80 --name web nginx  
docker ps  
docker logs web  
docker exec -it web /bin/sh  
docker stop web  
docker rm web  
docker rmi nginx:latest

docker build -t myapp:1.0 .  
docker tag myapp:1.0 myrepo/myapp:1.0  
docker push myrepo/myapp:1.0

docker-compose up -d  
docker-compose down  
docker-compose logs  
docker-compose exec app sh

Extra: [[Docker command reference]]

## ## Related Notes

- [[Dockerfile structure & best practices]]
- [[Docker Compose cheatsheet]]
- [[Persistent storage in Docker]]
- [[Containers vs VMs]]
- [[Deploying containers to cloud or registry workflow]]
- [[Docker command reference]]

References: https://www.youtube.com/watch?v=3c-iBn73dDE&t=3999s