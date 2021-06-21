FROM node:14-alpine

LABEL author="Tolfix" maintainer="support@tolfix.com"

RUN apk add --no-cache --update curl ca-certificates openssl git tar bash sqlite fontconfig \
    && adduser --disabled-password --home /home/container container \
    && npm install -g @types/node \
    && npm install -g typescript

USER container
ENV  USER=container HOME=/home/container

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]