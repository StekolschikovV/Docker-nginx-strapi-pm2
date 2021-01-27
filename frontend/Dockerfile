FROM keymetrics/pm2:latest-alpine

LABEL authors="Vitaly Stekolschikov <v.a.stekolschikov@gmail.com>" \
      org.label-schema.vendor="Waves Association Site Frontend" \
      org.label-schema.name="Waves Association Site Frontend Docker Image" \
      org.label-schema.description="Waves Association Site" \
      org.label-schema.url="https://wavesassociation.org" \
      org.label-schema.schema-version="1.0"

ENV NPM_CONFIG_LOGLEVEL error

WORKDIR /usr/src/app

RUN apk update && apk upgrade && apk add --no-cache bash git openssh
RUN apk --no-cache add curl

COPY . .

RUN yarn install
RUN yarn build:ssr

EXPOSE 3000 1337

CMD [ "pm2-runtime", "start", "pm2.json" ]
