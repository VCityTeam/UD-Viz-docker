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
RUN git clone https://github.com/VCityTeam/UD-Viz.git
WORKDIR UD-Viz
RUN npm install
RUN npm run build

######### Install SimpleServer (an ExpressJS based...simple server)
WORKDIR /
RUN git clone https://github.com/VCityTeam/UD-SimpleServer
WORKDIR UD-SimpleServer
RUN git checkout cors-issues
RUN npm install

EXPOSE 80
CMD [ "node", "./index.js", "../UD-Viz", "80" ]
