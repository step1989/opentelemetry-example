FROM node:14.15.5-alpine3.13
EXPOSE 4000
EXPOSE 9465

RUN mkdir /app && chown -R node:node /app

USER node

COPY package.json package-lock.json /app/
RUN cd /app && npm ci

WORKDIR /app

COPY --chown=node:node . /app

RUN npm run build

CMD [ "npm", "run" ,"start:prod" ]
