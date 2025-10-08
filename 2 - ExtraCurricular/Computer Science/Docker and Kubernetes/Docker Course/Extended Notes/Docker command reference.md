 07-10-2025 04:04

Tags: [[Docker]] [[Note]]
# **Docker command reference**

- `docker pull <image>`: Download image from registry.
- `docker images`: List downloaded images.
- `docker run <image>`: Create and start a container.
- `docker ps`: List running containers.
- `docker ps -a`: List all containers (including stopped).
- `docker stop <container>` / `docker start <container>`: Stop/start container.
- `docker rm <container>`: Remove container.
- `docker rmi <image>`: Remove image.
- `docker logs <container>`: Show logs of a container.
- `docker exec -it <container> <command>`: Run a command inside a container.
- `docker-compose up`: Start all services in Compose file.
- `docker-compose down`: Stop and remove services.
- `docker-compose logs`: View logs from Compose services.
- `docker-compose exec <service> <command>`: Run command in a Compose service.

References: [[Docker Course Notes]]