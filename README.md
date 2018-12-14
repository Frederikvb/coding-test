# Solution Local development - Frederik Van Brussel

## Installation
```ShellSession
git clone https://github.com/Frederikvb/coding-test.git
cd coding-test
docker-compose up -d
```
When everything is done, the output of docker ps should be something like this:

```
CONTAINER ID        IMAGE                COMMAND                  CREATED             STATUS              PORTS                                      NAMES
6be22f8152e3        coding-test_apache   "httpd-foreground"       17 seconds ago      Up 12 seconds       0.0.0.0:80->80/tcp, 0.0.0.0:443->443/tcp   apache
9b28ec3d320b        coding-test_client   "npm run start"          17 seconds ago      Up 15 seconds       3000/tcp                                   client
87b3a20daa5f        redis                "docker-entrypoint.s…"   17 seconds ago      Up 15 seconds       0.0.0.0:6379->6379/tcp                     redis
368cee628d1b        coding-test_server   "docker-php-entrypoi…"   17 seconds ago      Up 14 seconds       9000/tcp                                   server
b843f9e929aa        mysql:5.6            "docker-entrypoint.s…"   17 seconds ago      Up 16 seconds       0.0.0.0:3306->3306/tcp                     mysql
```

## Guidelines

- frontend-url: teamleader.localhost

  backend-url: teamleader.localhost/api  

  production-url: prod.teamleader.localhost

  ***note:*** teamleader.localhost should resolve to localhost (127.0.0.1). Edit /etc/hosts when this is not the case.

- Build production for the client:
  ```
    docker exec -it client npm run build
  ```

- run the phpunit tests:
  ```
  docker exec -it server ./vendor/bin/phpunit --configuration phpunit.xml
  ```
  
