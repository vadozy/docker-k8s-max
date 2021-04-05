FROM node:14-alpine3.13

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV MONGODB_USERNAME=vadim
ENV MONGODB_PASSWORD=secret


CMD ["npm", "start"]