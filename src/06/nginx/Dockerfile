FROM nginx
ARG USERNAME=pizza

COPY ./nginx.conf /ect/nginx/nginx.conf

WORKDIR /home/$USERNAME

RUN useradd -m $USERNAME ; \
    rm -rf /var/lib/apt/lists/*

USER $USERNAME

ENTRYPOINT ["sh", "./start.sh"]