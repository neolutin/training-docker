FROM horgix/cactus-builder AS build
COPY . /src
WORKDIR /src
RUN npm install && npm run build

FROM nginx:alpine AS runtime
COPY --from=build src/dist/ /usr/share/nginx/html/
