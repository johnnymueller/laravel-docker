## Laravel API Using Docker

Based on the tutorial here: https://www.toptal.com/laravel/restful-laravel-api-tutorial, with a handful of bug fixes and all running in Docker containers instead of using Laravel's `php artisan serve`.

## Installation

Log in to DB and create user:
```
docker exec -it [NAME_OF_MYSQL_CONTAINER] bash;
mysql -uroot -psecret;

CREATE USER 'homestead'@'%' IDENTIFIED BY 'secret';
GRANT ALL PRIVILEGES ON * . * TO 'homestead'@'%';
```

Install, migrate, seed, and spin up Docker:

1. `composer install`
2. `php artisan migrate`
3. `php artisan db:seed`
4. `docker-compose up -d`

API is served at `localhost:8080`. Postman helps and make sure to send the following headers:
`Accept: application/json`
`Content-Type: application/json`
