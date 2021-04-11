FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

# ENV MONGODB_USERNAME=xxxx
# ENV MONGODB_PASSWORD=xxxx

CMD ["npm", "start"]