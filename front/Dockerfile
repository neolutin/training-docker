FROM node:8.4
RUN apt-get update \
	&& apt-get install -y nginx
RUN git clone https://github.com/jbonachera/hello-world.git
WORKDIR hello-world
RUN npm install && npm run build
RUN mkdir -p /var/www/html/
# COPY --from=runtime dist/* /var/www/html/
RUN sed -i 's/hello-container/hello-container neolutin/' dist/index.html
RUN cp -R dist/* /var/www/html/ 
CMD nginx -g 'daemon off;'
