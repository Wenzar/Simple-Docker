FROM nginx:latest
USER root

WORKDIR /home/

COPY /nginx.conf /etc/nginx/

RUN apt-get update && apt-get install -y \
    gcc \
    libfcgi-dev \
    spawn-fcgi && rm -rf /var/lib/apt/lists ; \
    touch /var/run/nginx.pid ; \
    chown -R nginx:nginx /var/run/nginx.pid ;





