FROM ubuntu:18.04
CMD nginx -g 'daemon off;'
RUN apt-get update \
	&& apt-get install -y curl \
	&& curl -fsSL https://deb.nodesource.com/setup_8.x | bash - \
	&& apt-get install -y nginx nodejs ca-certificates git \
	&& git clone https://github.com/jbonachera/hello-world.git \
	&& cd hello-world \
	&& npm install \
	&& npm run build \
	&& mkdir -p /var/www/html/ \
	&& cp -R dist/* /var/www/html/ \
	&& cd .. && rm -rf hello-world
RUN apt-get remove -y nodejs git curl \
	&& apt-get clean 
RUN rm -rf .npm/
