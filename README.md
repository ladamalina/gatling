Docker image for [Gatling](https://gatling.io/) load testing tool

## Base Docker Image

[openjdk:17-jdk-alpine](https://hub.docker.com/_/openjdk)

## Docker Tags

* `3.10.5`, `latest` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.10.5/Dockerfile))
* `3.10.4` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.10.4/Dockerfile))
* `3.10.3` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.10.3/Dockerfile))
* `3.9.5` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.9.5/Dockerfile))
* `3.9.4` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.9.4/Dockerfile))
* `3.9.3` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.9.3/Dockerfile))
* `3.9.2` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.9.2/Dockerfile))
* `3.9.1` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.9.1/Dockerfile))
* `3.9.0` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.9.0/Dockerfile))
* `3.8.4` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.8.4/Dockerfile))
* `3.8.3` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.8.3/Dockerfile))
* `3.8.2` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.8.2/Dockerfile))
* `3.8.1` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.8.1/Dockerfile))
* `3.7.6` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.7.6/Dockerfile))
* `3.6.1` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.6.1/Dockerfile))
* `3.2.1` ([Dockerfile](https://github.com/ladamalina/gatling/blob/master/3.2.1/Dockerfile))

## Installation

* Install [Docker](https://www.docker.com/)

* Get automated build from public registry:

```bash
# Latest version:
docker pull ladamalina/gatling:latest

# All versions:
docker pull ladamalina/gatling

# Specific version:
docker pull ladamalina/gatling:3.10.4
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
