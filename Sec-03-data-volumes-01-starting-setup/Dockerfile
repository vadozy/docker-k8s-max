FROM node:14-alpine3.13

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

ARG DEFAULT_PORT=80
ENV PORT $DEFAULT_PORT
EXPOSE $PORT

VOLUME ["/app/feedback"]

# CMD [ "node", "server.js" ]
CMD [ "npm", "start" ]