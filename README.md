<p align="center"><img src="https://res.cloudinary.com/practicaldev/image/fetch/s--Bb3IWflG--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/016f1249r1njnhhciz9n.png"></p>


# Docker LAMP / Docker
## Docker LAMP with PHP / APACHE / MYSQL


This environment can lift the laravel environments already with npm

## Setup

##### Docker

Set up .env file
> cp .env.example .env

**Important! Change the DB parameters in the .env file before build the containers**
Then, build all containers
> docker-compose build

And customize as needed. Also, configure your /etc/hosts file accordingly:
> 127.0.0.1   [url].local

Finally, start the app
> docker-compose up -d

Install composer
> docker exec -it [app_name] composer install -vvv --prefer-dist

Install npm dependencies
> docker exec -it [app_name] npm install

Import a database into MariaDB container
>  docker exec -i [container_name] mysql -u[user] -p[pass] [MYSQL_DATABASE] < [database.sql]

Change permissions for "storage" and "bootstrap/cache" folders
> docker exec -it [app_name] chmod -R 777 storage
>
> docker exec -it [app_name] chmod -R 777 bootstrap/cache

Access the application from your browser
> http://[url].local:8081/

Have fun!


## License

The Lumen framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)

