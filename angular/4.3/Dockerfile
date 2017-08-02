FROM node:alpine

COPY package.json ./

RUN apk update
RUN apk add git bash

RUN yarn install