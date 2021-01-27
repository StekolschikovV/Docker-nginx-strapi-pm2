FROM strapi/base:latest

LABEL authors="Vitaly Stekolschikov <v.a.stekolschikov@gmail.com>" \
      org.label-schema.vendor="Waves Association Site Backend" \
      org.label-schema.name="Waves Association Site Backend Docker Image" \
      org.label-schema.description="Waves Association Site" \
      org.label-schema.url="https://wavesassociation.org" \
      org.label-schema.schema-version="1.0"

RUN yarn global add strapi

RUN mkdir /srv/app && chown 1000:1000 -R /srv/app
RUN apk --no-cache add curl

WORKDIR /srv/app

EXPOSE 1337 3000

COPY . .

RUN yarn

CMD ["strapi", "start"]
