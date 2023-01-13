FROM ubuntu:focal

LABEL maintainer "VCityTeam"
LABEL source.repo "https://github.com/VCityTeam/UD-Viz-docker"

# Install system dependencies
RUN apt-get update

# Node version 16 is required. For its installation (on focal) refer to e.g.
#  https://computingforgeeks.com/install-node-js-14-on-ubuntu-debian-linux/
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash -
RUN apt-get install -y nodejs
RUN node --version
RUN npm --version
RUN apt-get install -y git
RUN git --version

######### Install UD-Viz
ARG checkoutName=master
RUN git clone https://github.com/VCityTeam/UD-Viz.git
WORKDIR UD-Viz
RUN git checkout $checkoutName
RUN npm install



EXPOSE 8000
CMD [ "npm", "run", "host" ]
