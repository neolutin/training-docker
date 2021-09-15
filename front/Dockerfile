FROM node:8.4 AS build
RUN git clone https://github.com/jbonachera/hello-world.git
WORKDIR hello-world
RUN npm install && npm run build
RUN sed -i 's/hello-container/hello-container neolutin/' dist/index.html
FROM nginx AS runtime
RUN mkdir -p /var/www/html/
COPY --from=build hello-world/dist/* /usr/share/nginx/html/
# RUN cp -R dist/* /var/www/html/ 
CMD nginx -g 'daemon off;'
