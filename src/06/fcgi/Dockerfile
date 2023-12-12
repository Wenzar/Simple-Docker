FROM ubuntu/nginx
ARG USERNAME=nginx

WORKDIR /home/

COPY server.c /home/
COPY start.sh /home/

RUN apt-get update ; \
    apt-get install -y gcc libfcgi-dev spawn-fcgi ; \
    gcc server.c -lfcgi ; \
    rm -rf /var/lib/apt/lists ; \
    mkdir -p /var/run/nginx ; \
    touch /var/run/nginx.pid ; \
    chown -R $USERNAME:$USERNAME /var/run/nginx.pid ;\
    chown -R $USERNAME:$USERNAME /var/run/nginx /var/lib/nginx /etc/nginx /var/log/nginx

USER $USERNAME

CMD ["sh", "/home/start.sh"]


