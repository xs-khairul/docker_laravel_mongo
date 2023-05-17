# docker_laravel_mongo

```php
docker-compose build app
docker-compose up -d
docker-compose exec app rm -rf vendor composer.lock
docker-compose exec app composer update   
docker-compose exec app php artisan key:generate
docker-compose exec app php artisan migrate
docker-compose exec app composer require laravel/ui 
docker-compose exec app php artisan ui bootstrap --auth    
​​docker-compose exec app php artisan migrate:refresh





docker-compose run --rm npm install
docker-compose run --rm npm run dev
docker rmi id -f   # image
docker rm id -f  # container

#hasib


'mongodb' => [
           'driver' => 'mongodb',
           'host' => env('DB_HOST', '127.0.0.1'),
           'port' => env('DB_PORT', 27017),
           'database' => env('DB_DATABASE', 'homestead'),
           'username' => env('DB_USERNAME', 'homestead'),
           'password' => env('DB_PASSWORD', 'secret'),
           'options' => [
               'appname' => 'homestead',
           ],
       ],


Jenssegers\Mongodb\MongodbServiceProvider::class,
```
