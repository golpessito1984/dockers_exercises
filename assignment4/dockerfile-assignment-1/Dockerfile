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

CMD [ "/sbin/tini", "--", "node",  "./bin/www"]

# To build
docker image build -t davidruizdelarosa/node_assignment1:latest .

# To run
docker container run --rm -p 80:3000 davidruizdelarosa/node_assignment1:latest

# To push
docker image push davidruizdelarosa/node_assignment1:latest
