# Docker under macOS

c.f.

 * [General](./docker.md) information
 * Use Docker for [Android CI](./docker.andorid.md)

We use [Docker for Mac](https://docs.docker.com/docker-for-mac/), older Mac's may need [Docker Toolbox](https://www.docker.com/products/docker-toolbox), but that's not discussed further here.

Unfortunatly there are some issues with the Docker VM ineracting with the `adb` Android emulator VM.

docker
> ps
> information
> version
> images

# `boot2docker`
 
Located here - `/usr/local/share/boot2docker`
 
# `docker-machine`
 
is the OS-X VM used to run Docker. A nice command would be `docker-machine inspect default` or `docker-machine start`. The default machine is called `default`.
  
If the network has broken things (as mine often does) then a quick `docker-machine restart` & `docker-machine env` / `eval $(docker-machine env)` may help.
 
Read the [docs](https://docs.docker.com/engine/installation/mac/) for more details.
 
```
docker run gliderlabs/alpine echo Hello Rik
 
Run 'Docket Quickstart Terminal', then `eval $(docker-machine env)`

docker-machine start
docker-machine inspect default
docker-machine restart

docker images
docker images
docker run rikwatson/docker-whale
docker run cellofellow/ffmpeg
docker ps
docker run hello-world
docker run -it ubuntu bash
```

```
service docker[.io] status
```



```
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
c04b14da8d14: Pull complete
Digest: sha256:0256e8a36e2070f7bf2d0b0763dbabdd67798512411de4cdcf9431a1feb60fd9
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker Hub account:
 https://hub.docker.com

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/
```