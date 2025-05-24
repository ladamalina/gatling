Docker image for [Gatling](https://gatling.io/) load testing tool

## Base Docker Image

[amazoncorretto:22-alpine-jdk](https://hub.docker.com/_/amazoncorretto)

## Supported tags and respective `Dockerfile` links

* [`latest`](https://github.com/ladamalina/gatling/blob/master/3.14.0/Dockerfile)
* [`3.14.0`](https://github.com/ladamalina/gatling/blob/master/3.14.0/Dockerfile)
* [`3.13.5`](https://github.com/ladamalina/gatling/blob/master/3.13.5/Dockerfile), [`3.13.4`](https://github.com/ladamalina/gatling/blob/master/3.13.4/Dockerfile), [`3.13.3`](https://github.com/ladamalina/gatling/blob/master/3.13.3/Dockerfile), [`3.13.1`](https://github.com/ladamalina/gatling/blob/master/3.13.1/Dockerfile)
* [`3.12.0`](https://github.com/ladamalina/gatling/blob/master/3.12.0/Dockerfile)
* [`3.11.5`](https://github.com/ladamalina/gatling/blob/master/3.11.5/Dockerfile), [`3.11.4`](https://github.com/ladamalina/gatling/blob/master/3.11.4/Dockerfile), [`3.11.3`](https://github.com/ladamalina/gatling/blob/master/3.11.3/Dockerfile), [`3.11.2`](https://github.com/ladamalina/gatling/blob/master/3.11.2/Dockerfile), [`3.11.1`](https://github.com/ladamalina/gatling/blob/master/3.11.1/Dockerfile), [`3.11.1-jdk19`](https://github.com/ladamalina/gatling/blob/master/3.11.1-jdk19/Dockerfile), [`3.11.1-jdk21`](https://github.com/ladamalina/gatling/blob/master/3.11.1-jdk21/Dockerfile), [`3.11.1-jdk22`](https://github.com/ladamalina/gatling/blob/master/3.11.1-jdk22/Dockerfile), [`3.11.1-jdk23`](https://github.com/ladamalina/gatling/blob/master/3.11.1-jdk23/Dockerfile)
* [`3.10.5`](https://github.com/ladamalina/gatling/blob/master/3.10.5/Dockerfile), [`3.10.4`](https://github.com/ladamalina/gatling/blob/master/3.10.4/Dockerfile), [`3.10.3`](https://github.com/ladamalina/gatling/blob/master/3.10.3/Dockerfile), [`3.10.2`](https://github.com/ladamalina/gatling/blob/master/3.10.2/Dockerfile), [`3.10.1`](https://github.com/ladamalina/gatling/blob/master/3.10.1/Dockerfile), [`3.10.0`](https://github.com/ladamalina/gatling/blob/master/3.10.0/Dockerfile)
* [`3.9.5`](https://github.com/ladamalina/gatling/blob/master/3.9.5/Dockerfile), [`3.9.4`](https://github.com/ladamalina/gatling/blob/master/3.9.4/Dockerfile), [`3.9.3`](https://github.com/ladamalina/gatling/blob/master/3.9.3/Dockerfile), [`3.9.2`](https://github.com/ladamalina/gatling/blob/master/3.9.2/Dockerfile), [`3.9.1`](https://github.com/ladamalina/gatling/blob/master/3.9.1/Dockerfile), [`3.9.0`](https://github.com/ladamalina/gatling/blob/master/3.9.0/Dockerfile)
* [`3.8.4`](https://github.com/ladamalina/gatling/blob/master/3.8.4/Dockerfile), [`3.8.3`](https://github.com/ladamalina/gatling/blob/master/3.8.3/Dockerfile), [`3.8.2`](https://github.com/ladamalina/gatling/blob/master/3.8.2/Dockerfile), [`3.8.1`](https://github.com/ladamalina/gatling/blob/master/3.8.1/Dockerfile), [`3.8.0`](https://github.com/ladamalina/gatling/blob/master/3.8.0/Dockerfile)
* [`3.7.6`](https://github.com/ladamalina/gatling/blob/master/3.7.6/Dockerfile)
* [`3.6.1`](https://github.com/ladamalina/gatling/blob/master/3.6.1/Dockerfile)
* [`3.2.1`](https://github.com/ladamalina/gatling/blob/master/3.2.1/Dockerfile)

## Installation

* Install [Docker](https://www.docker.com/)

* Get automated build from public registry:

```bash
# Latest version:
docker pull ladamalina/gatling:latest

# All versions:
docker pull ladamalina/gatling

# Specific version:
docker pull ladamalina/gatling:3.13.5
```

* [Alternatively] Build an image from Dockerfile:

```bash
docker build -t="ladamalina/gatling" github.com/ladamalina/gatling
````

## Usage

Use image to run container

```bash
docker run -it --rm ladamalina/gatling
```

Mount configuration and simulation files from the host machine and run gatling in interactive mode

```bash
docker run -it --rm \
    -v $(pwd)/conf:/opt/gatling/conf \
    -v $(pwd)/user-files/resources:/opt/gatling/user-files/resources \
    -v $(pwd)/user-files/simulations:/opt/gatling/user-files/simulations \
    -v $(pwd)/user-files/lib:/opt/gatling/user-files/lib \
    -v $(pwd)/results:/opt/gatling/results \
    ladamalina/gatling
```

Use the `-e` switch to use JAVA_OPTS to pass parameters to gatling tests

```bash
docker run -e JAVA_OPTS="-Dusers=10" -it --rm ladamalina/gatling
```
