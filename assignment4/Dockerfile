# Create image from node:alpine
FROM node:6-alpine

#Install tini
RUN apk add --update tini \
    && mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json .

RUN npm install \
    && npm cache clean --force

COPY . .

# Expose 3000 port into container
EXPOSE 3000

#/sbin/tini -- node ./bin/www

CMD [ "/sbin/tini", "--", "node", "/usr/src/app/app.js" ]