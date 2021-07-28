FROM node:16-alpine

# Some extra deps. For example graphicsmagick for a npm module like gm
RUN apk add --update graphicsmagick

# Create a work directory
WORKDIR /home/node/app

COPY package.json yarn.lock ./

RUN yarn install --production

COPY . .

CMD ["node", "index.js"]