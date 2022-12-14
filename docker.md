# Docker useful CLI

* show all container
```Shell
docker ps -a
```
* list images
```Shell
docker image ls 
```
* start container
```Shell
docker run -it <image>
```
```-it``` instructs Docker to allocate a pseudo-TTY connected to the container’s stdin<br />
```--rm```		Automatically remove the container when it exits<br />
```-w /path/to/dir/``` set working directory<br />
```-v /path/local:/path/container``` mount host dir to container dir<br />
```-p 80(host port):80(container port)``` bounding ports<br />
```--name <name>``` gives name to container<br />
```--gpus all``` enable gpu for container<br />
* start/turnoff exist container
```Shell
docker start <container>
docker stop <container>
```

* get to bash of container
```Shell
docker exec -ti <container> bash

docker exec -ti <container> <commend>
```
use container's id or name

* commit change of container to image
```Shell
docker commit <containerId> <newImageId>
```

* stop and remove container
```Shell
docker stop <containerId>
docker rm <containerId>

// remove all
docker ps -aq | xargs docker stop | xargs docker rm
```

* image backup
```Shell
docker save <image> -o <filename>.tar

docker load  -i <filename>.tar
```

* container backup
```Shell
// store
docker export "container" > "filename".tar
// recover
docker import - "container" < "filename".tar
```

----

# Docker file
```Shell
FROM <base_image>
MAINTAINER
RUN
CMD
VOLUME
USER
WORKDIR <>
HEALTHCHECH
ARG
EXPOSE
ENV
ADD
COPY
ENTRYPOINT
```

