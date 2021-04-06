$ docker network create goals-network
$ docker volume create mongo_data

-- Start Mongo Container before startint the app container:

$ docker container run -d --name mongodb --rm --network goals-network -v mongo_data:/data/db -e MONGO_INITDB_ROOT_USERNAME=vadim -e MONGO_INITDB_ROOT_PASSWORD=secret mongo:4.4.4-bionic

-- Start backend api

$ docker build -t backend-api .
-- $ docker container run --name backend-api --rm -d -p 80:80 --network goals-network backend-api:latest
$ docker container run --name backend-api --rm -d -p 80:80 --network goals-network -v $(pwd):/app -v logs:/app/logs -v /app/node_modules backend-api:latest

-- Frontend

$ docker build -t frontend .
-- $ docker container run --name frontend --rm -d -it -p 3000:3000 frontend:latest
$ docker container run --name frontend --rm -d -i -p 3000:3000 -v $(pwd)/src:/app/src frontend:latest


-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
-- Section 06 puts all this into docker-compose.yml
-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --

$ docker-compose up -d
-- $ docker-compose up -d --build
$ docker-compose down
-- $ docker-compose down -v