FROM node:12
MAINTAINER TagSpaces

RUN apt-get update
RUN apt-get install -y gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget
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
