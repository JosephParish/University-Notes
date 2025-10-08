 07-10-2025 04:03

Tags: [[Docker]] [[Note]]
# **Persistent storage in Docker**

- Containers are ephemeral; data inside is lost when they stop. 
- Use **named volumes** or **bind mounts** to persist data beyond container lifecycle.
- Named volumes are managed by Docker and stored in Docker’s storage area.
- Bind mounts link a directory on the host machine to the container.
- Volumes ensure data consistency for databases or stateful apps.
- Compose files can declare volumes for easy reuse.

References: [[Docker Course Notes]]