# Gatling is a highly capable load testing tool.
#
# Documentation: https://gatling.io/docs/3.2/
# Cheat sheet: https://gatling.io/docs/3.2/cheat-sheet/

FROM openjdk:21-jdk-slim

MAINTAINER Nadezhda Ryabtsova <nadezhdaryabtsova@gmail.com>

# docker scout recommendations
#RUN apt-get update && \
#    apt-get install -y --no-install-recommends openssl libtasn1 libretls zlib && \
#    rm -rf /var/lib/apt/lists/*

# working directory for gatling
WORKDIR /opt/

# gating version
ENV GATLING_VERSION 3.11.1

# create directory for gatling install
RUN mkdir -p gatling

# install gatling
RUN apt-get update && \
    apt-get install -y --no-install-recommends wget bash libc6 unzip && \
    mkdir -p /tmp/downloads && \
    wget -q -O /tmp/downloads/gatling-$GATLING_VERSION.zip \
    https://repo1.maven.org/maven2/io/gatling/highcharts/gatling-charts-highcharts-bundle/$GATLING_VERSION/gatling-charts-highcharts-bundle-$GATLING_VERSION.zip && \
    mkdir -p /tmp/archive && cd /tmp/archive && \
    unzip /tmp/downloads/gatling-$GATLING_VERSION.zip && \
    mv /tmp/archive/gatling-charts-highcharts-bundle-$GATLING_VERSION/* /opt/gatling/ && \
    rm -rf /tmp/* && \
    rm -rf /var/lib/apt/lists/*

# change context to gatling directory
WORKDIR  /opt/gatling

# set directories below to be mountable from host
VOLUME ["/opt/gatling/conf", "/opt/gatling/results", "/opt/gatling/user-files"]

# set environment variables
ENV PATH /opt/gatling/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV GATLING_HOME /opt/gatling

ENTRYPOINT ["gatling.sh"]
