FROM node:8.4 AS build
RUN git clone https://github.com/jbonachera/hello-world.git
WORKDIR hello-world
RUN npm install --production 
ENV REDIS_HOST=172.17.0.3
CMD node ./server.js
