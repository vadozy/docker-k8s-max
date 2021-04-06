$ docker build -t node-util .

-- run container node but generate the package.json file here:
$ docker run -it -v $(pwd):/app node-util npm init -y

-- docker-compose
$ docker-compose run --rm node npm init -y