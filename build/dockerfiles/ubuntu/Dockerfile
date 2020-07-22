FROM ubuntu:focal
MAINTAINER Jeff Genovy <29107334+jefgen@users.noreply.github.com>
LABEL com.github.microsoft.icu="ubuntu-focal"

# Update installed software in the container
RUN apt-get -q -y update && apt-get -q -y upgrade

# Install necessary build tools
RUN apt-get -q -y install build-essential git python zip

# Remove icu-dev in case it was somehow already installed.
RUN apt-get -q -y remove libicu-dev

# When we run the docker container we will mount the source repo here
VOLUME /src

# The output from make install will go here
VOLUME /dist

# Do the actual build in tmp
RUN mkdir /tmp/build
WORKDIR /tmp/build
