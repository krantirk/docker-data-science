# docker-data-science

Set up an automated data science environment using Docker

Any changes to the Dockerfile will be automatically built in Docker Hub, so just pull the container:

`docker pull krantirk/docker-data-science`

Then you can either run the container interactively:

1. linux: `docker run -it -v ~/GitProjects:/root/GitProjects --network=host -i krantirk/docker-data-science`
2. MacOS or Windows: `docker run -it -v ~/GitProjects:/root/GitProjects -p 8888:8888 -i krantirk/docker-data-science`

Or run the container in a detached mode so that you can use Jupyter Notebooks but still use bash

1. linux:
```
docker run -d --name data-science -v ~/GitProjects:/root/GitProjects --network=host -i krantirk/docker-data-science
docker exec -it data-science bash
```
2. MacOS or Windows:
```
docker run -d --name data-science -v ~/GitProjects:/root/GitProjects -p 8888:8888 -i krantirk/docker-data-science
docker exec -it data-science bash
```

To use Jupyter Lab on your host machine, just navigate to `localhost:8888` and enter the token `data-science`.
