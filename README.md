docker-compose build
docker-compose up -d
docker exec -it apache_app chmod -R 777 bootstrap/cache
docker exec -it apache_app chmod -R 777 storage