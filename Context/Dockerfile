FROM dhi.io/node:24-alpine-dev AS build-stage

LABEL maintainer=VCityTeam
LABEL source.repo=https://github.com/VCityTeam/UD-Viz-docker

# Verify and install dependencies
RUN node --version
RUN apk add git
RUN git --version

######### Install UD-Viz
ARG checkoutName=master
WORKDIR /usr/src/
RUN git clone https://github.com/VCityTeam/UD-Viz.git
WORKDIR /usr/src/UD-Viz
RUN git checkout $checkoutName
RUN npm install

EXPOSE 8000
CMD [ "npm", "run", "start" ]
