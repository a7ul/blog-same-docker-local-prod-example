# base image contains the dependencies and no application code
FROM node:16-alpine as base  

RUN apk add --update graphicsmagick

# prod image inherits from base and adds application code
FROM base as prod 

WORKDIR /home/node/app
COPY package.json yarn.lock ./
RUN yarn install --production
COPY . .

CMD ["node", "index.js"]
