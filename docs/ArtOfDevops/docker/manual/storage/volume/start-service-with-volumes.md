# Use a volume with Docker Compose

The following example shows a single Docker Compose service with a volume:

```Dockerfile
services:
  frontend:
    image: node:lts
    volumes:
      - myapp:/home/node/app
volumes:
  myapp:
```

Start container(s) with docker compose to to create a volume:

```bash
$ docker compose up
```

Docker reuses a the same volume when you run the command subsequently.

To attach the a external container created using command `docker volume create`:

```Dockerfile
services:
  frontend:
    image: node:lts
    volumes:
      - myapp:/home/node/app
volumes:
  myapp:
    external: true
```


### Start a service with volumes

When you start a service and define a volume, each service container uses it own local volume. None of the containers canshare this data if you use the `local` volume driver. However, some volume drivers do not support shared storage.

The following example starts an `nginx` sevice with four replicas, each of which uses a local volumes called `myvol2`.

```bash
docker service create -d \
  --replicas=4 \
  --name devtest-service \
  --mount source=myvol2,target=/app \
  nginx:latest
```

Use `docker service ps devtest-service` to verify that the service is running:

```bash
docker service ps devtest-service

ID                  NAME                IMAGE               NODE                DESIRED STATE       CURRENT STATE            ERROR               PORTS
4d7oz1j85wwn        devtest-service.1   nginx:latest        moby                Running             Running 14 seconds ago
```

you can remove the service to stop the running tasks:

```bash
docker service rm devtest-service
```

Removing the service doesn't remove any volumes created by the service.

### Populate a volume using a container

If you start a container which creates a new volume, and the container has files or directories in the driectory to be mounted such as `/app/`, Docker copies the directory's content into the volume. The container then mounts and uses the volume, and other containers which use the volume also have access to the prepopulated content.

The following example starts an `nginx` container and populates the new volume `nginx-vol` with the contents of the container's `/usr/share/nginx/html` directory. This is where Nginx stores its default HTML content.

The `--mount` and `-v` examples have the same end result.

- `--mount`

```bash
docker run -d \
  --name=nginxtest \
  --mount source=nginx-vol,destination=/usr/share/nginx/html \
  nginx:latest
```

- `-v`

```bash
docker run -d \
  --name=nginxtest \
  -v nginx-vol:/usr/share/nginx/html \
  nginx:latest
```

----------

After running either of these examples, run the following commands to clean up the containers and volumes. Note volume removal is a separate step.

```bash
$ docker container stop nginxtest
```

```bash
$ docker container rm nginxtest
```

```bash
docker volume rm nginx-vol
```