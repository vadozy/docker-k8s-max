$ docker network create my_network

-- Start Mongo Container before startint the app container:

$ docker container run -d --name mongodb --rm --network my_network mongo:4.4.4-bionic

-- Start web app

$ docker container run --name favorites --rm -p 80:3000 --network my_network favorites-node:latest