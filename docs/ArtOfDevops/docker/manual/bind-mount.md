# Bind mounts

Bind mounts create a direct link between a host system path and a container, allowing access to files or directories stored anywhere on the host. Since they aren't isolated by Docker, both non-Docker processes on the host and container processes can modify the mounted files simultaneously.

Use bind mounts when you need to be able to access files from both the container and the host.