# Docker Storage

By default all files created inside a container are stored on a writable container layer that sits on top of the read-only, immutable image layers.

Data written to the container layer doesn't persist when the container is destroyed.This means that it can be difficult to get the data out of the container if another process needs it.

The writable layer is unique per container. You can't easily extract the data from the writable layer to the host, or to another container.

### Stroage mount options

Docker supports the following storage mounts for storing data outside of the writable layer of the container:

- [Volume mounts](volume/README.md)
- [Bind mounts](bind-mount/README.md)
- [tmpfs mounts](tmpfs/README.md)
- [Named pipes](named-pipes/README.md)

Data is exposed as either a directory or an individual file in the container's filesystem.
