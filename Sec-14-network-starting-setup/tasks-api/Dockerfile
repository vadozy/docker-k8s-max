FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 8000

ENV AUTH_HOSTNAME="auth"

CMD [ "node", "tasks-app.js" ]
