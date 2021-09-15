FROM nginx
RUN apt-get update \
	&& apt-get install -y curl \
	&& curl -fsSL https://deb.nodesource.com/setup_8.x | bash - \
	&& apt-get install -y nodejs ca-certificates git
RUN apt-get install -y npm
RUN git clone https://github.com/jbonachera/hello-world.git
WORKDIR hello-world
RUN npm install && npm run build
RUN sed -i 's/hello-container/hello-container neolutin/' dist/index.html
RUN cp -R dist/* /usr/share/nginx/html/
