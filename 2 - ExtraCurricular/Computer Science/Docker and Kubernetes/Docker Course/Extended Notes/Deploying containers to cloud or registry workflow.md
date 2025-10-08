 07-10-2025 04:03

Tags: [[Docker]] [[Note]]
# **Deploying containers to cloud or registry workflow**

- Authenticate with a container registry (`docker login`).
- Build and tag images appropriately (`docker build`, `docker tag`).
- Push images to registry (`docker push`) for sharing and deployment.
- Pull images on target environments (`docker pull`).
- Use CI/CD pipelines to automate build, test, and deploy workflows.
- Popular registries: Docker Hub, AWS ECR, Google Container Registry, Azure Container Registry.
- Orchestrate deployments with Kubernetes, Docker Swarm, or other platforms.

References: [[Docker Course Notes]]