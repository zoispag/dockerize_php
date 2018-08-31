# Docker for PHP

### Docker opinionated ready-to-use containers for PHP apps

Contains:
- nginx
- php-fpm (php 7.2)
- mysql 5.6
- mailcatcher
- composer
- node.js
- php extensions: mysql & sqlite3

Env variables:
- Set APP_PORT to access the app from `localhost:MYSQL_PORT`
- Set MYSQL_PORT to access the sql database with SequelPro with `host = localhost` and `port = MYSQL_PORT`

Setup:
- Put your PHP app inside the `workspace` dir
- Execute `docker-compose build` from the `deployment` dir
- Once finished, run `docker-compose up -d` to start the containers
- First time run will take longer (some images will have to download)

Useful aliases:
```
dup='docker-compose up -d'
ddown='docker-compose down'
dps='docker-compose ps'
drr='ddown && dup'
dphp='docker exec -it php-server /bin/bash'
```