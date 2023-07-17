FROM node:19.0.0-alpine3.16
RUN mkdir client

WORKDIR /client
COPY package.json /client/
COPY package-lock.json /client/

COPY . /client/

RUN chmod +x /client/

RUN npm install --production


CMD [ "npm", "start" ]