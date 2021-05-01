-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
-- -- --  Launching containers manually:  -- -- --
-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --

-- 1
$ cd auth-api
$ docker build -t vadozy/auth-api:1 .
$ docker container run -d --rm -p 80:80 --name auth_name vadozy/auth-api:1

-- 2
$ cd users-api
$ docker build -t vadozy/users-api:1 .
$ docker container run -d --rm -p 8080:8080 --link auth_name:auth vadozy/users-api:1

-- 3
$ cd tasks-api
$ docker build -t vadozy/tasks-api:1 .
$ docker container run -d --rm -p 8000:8000 --link auth_name:auth -e "TASKS_FOLDER=tasks" vadozy/tasks-api:1

-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --

