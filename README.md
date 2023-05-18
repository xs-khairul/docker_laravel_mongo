# docker_laravel_mongo

## laravel and mongo connection =>

    1. setup mongo db config in config=>database.php  
    2. set default db to mongodb  and set env file 
    3. need to add package Jenssegers Mongodb
    4. add Jenssegers\Mongodb service provider in config=>app.php file 


    5. use all eluquent model or other classes from Jenssegers\Mongodb by changing in model 

    ex:: 
    // use Illuminate\Foundation\Auth\User as Authenticatable; change to =>
       use Jenssegers\Mongodb\Auth\User as Authenticatable;
    // use Illuminate\Database\Eloquent\Model; change to =>
       use Jenssegers\Mongodb\E`loquent\Model;
```php
#hasib

## mongodb config for config=>dtabase.php
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

## Jenssegers service provider 
Jenssegers\Mongodb\MongodbServiceProvider::class,
```


## laravel mongo dockerize 

1. initialize dockerfile with basics OS with php installed image 
2. we need some extensions and debuger curl etc See the Docker file 
3. docker-composer file initialize all environment thats gona need for the project 
(such as web server , db server etc) 
 

 ## we need some comands thats build initial image than run  the container all are listed below 
 ## how we run composer command php command etc 
 

```php
### needned comand of docker listed below :
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


```
NB resources ::: 

https://www.digitalocean.com/community/tutorials/how-to-install-and-set-up-laravel-with-docker-compose-on-ubuntu-22-04
https://betterprogramming.pub/dockerize-laravel-vite-react-application-in-your-development-environment-a118aea4a02d