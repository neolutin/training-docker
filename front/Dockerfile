FROM node:8.4-alpine AS build
RUN mkdir hello-world
COPY package.json package-lock.json hello-world/
WORKDIR hello-world
RUN npm install
COPY ./ ./
RUN npm run build
FROM nginx:alpine AS runtime
COPY --from=build hello-world/dist/ /usr/share/nginx/html/
