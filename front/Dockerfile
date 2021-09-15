FROM ubuntu:18.04
RUN apt-get update \
	&& apt-get install -y curl \
	&& curl -fsSL https://deb.nodesource.com/setup_8.x | bash - \
	&& apt-get install -y nginx nodejs ca-certificates git
RUN git clone https://github.com/jbonachera/hello-world.git
WORKDIR hello-world
RUN npm install && npm run build
RUN mkdir -p /var/www/html/
RUN cp -R dist/* /var/www/html/ 
CMD nginx -g 'daemon off;'
