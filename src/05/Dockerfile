FROM debian
ARG USERNAME=pizza

COPY ./nginx.conf /ect/nginx/nginx.conf
COPY ./server.c /home/$USERNAME/server.c
COPY ./start.sh /home/$USERNAME/start.sh

WORKDIR /home/$USERNAME

RUN useradd -m $USERNAME ; \
    apt-get update ; \
    apt-get install -y gcc spawn-fcgi libfcgi-dev ; \
    rm -rf /var/lib/apt/lists/*

USER $USERNAME

ENTRYPOINT ["sh", "./start.sh"]
