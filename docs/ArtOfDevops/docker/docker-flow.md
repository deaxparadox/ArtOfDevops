# Docker flow

The Docker flow starts with a command in the client (CLI) pulling an image using the `docker pull` subcommand. The docker engine checks if the image is locally at the host or not. If it is not, the engine will pull it from the repository. Then it runs it and crafts a container from the image using the `docker run` subcommand.