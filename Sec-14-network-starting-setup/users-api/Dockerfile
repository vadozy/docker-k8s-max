FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8080

ENV AUTH_HOSTNAME="auth"

CMD [ "node", "users-app.js" ]
