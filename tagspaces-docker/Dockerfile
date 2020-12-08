FROM node:12-alpine
MAINTAINER TagSpaces

RUN apk --no-cache update
RUN apk --no-cache add libx11 alsa-lib-dev libstdc++6 ca-certificates xdg-utils git
WORKDIR /usr/src/apps
# Clone the tagspaces files into the docker container
RUN git clone https://github.com/tagspaces/tagspaces
WORKDIR /usr/src/apps/tagspaces
RUN yarn install \
 && yarn install-ext \
 && yarn version-meta \
 && yarn build-web \
 && yarn prepare-web

EXPOSE 8000
CMD [ "node", "scripts/webserver.js" ]
