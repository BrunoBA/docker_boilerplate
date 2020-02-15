FROM node:12.14.1-alpine3.9 

RUN apk update \
  && apk add --no-cache git \
  && apk add --update alpine-sdk \
  && apk del alpine-sdk \
  && rm -rf /tmp/* /var/cache/apk/* *.tar.gz ~/.npm \
  && npm cache clean --force \
  && npm install -g @vue/cli \
  && npm install -g @angular/cli \
  && yarn cache clean \
  && sed -i -e "s/bin\/ash/bin\/sh/" /etc/passwd

WORKDIR /app/home

RUN npm install

EXPOSE 3000
EXPOSE 4200