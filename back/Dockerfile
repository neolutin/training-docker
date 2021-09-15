FROM node:8.4-alpine AS build
RUN mkdir hello-world
WORKDIR hello-world
COPY package.json package-lock.json server.js ./
RUN npm install --production 

CMD node ./server.js
