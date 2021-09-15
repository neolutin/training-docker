FROM node:8.4 AS build
RUN mkdir hello-world
COPY . hello-world
WORKDIR hello-world
RUN npm install && npm run build

FROM nginx:alpine AS runtime
COPY --from=build hello-world/dist/ /usr/share/nginx/html/
