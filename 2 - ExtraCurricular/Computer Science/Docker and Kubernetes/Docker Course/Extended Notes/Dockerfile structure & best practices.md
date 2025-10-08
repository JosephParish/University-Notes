 07-10-2025 04:03

Tags: [[Docker]] [[Note]]
# **Dockerfile structure & best practices**

- Dockerfile defines the steps to build a Docker image.
- Common directives: `FROM`, `WORKDIR`, `COPY`, `RUN`, `EXPOSE`, `CMD`, `ENTRYPOINT`.
- Keep Dockerfiles small and efficient by minimizing layers and combining commands where possible.
- Use `.dockerignore` to exclude unnecessary files and reduce image size.
- Prefer multi-stage builds to separate build environment from final image, improving security and size.
- Avoid hardcoding secrets or credentials inside Dockerfiles.

References: [[Docker Course Notes]]