FROM node:10-alpine

LABEL maintainer="ryan.salles@gmail.com"

RUN apk add --no-cache \
  ca-certificates \
  curl \
  git \
  openssh \
  vim

WORKDIR /var/www/html

RUN yarn global add @angular/cli --dev \
  && yarn \
  && yarn cache clean \
  && ng config -g cli.packageManager yarn

CMD ng serve --host 0.0.0.0