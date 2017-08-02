FROM node:alpine

WORKDIR /lib/

COPY package.json ./

RUN apk update
RUN apk add git bash

RUN yarn install