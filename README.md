# Docker LAMP / Docker
## Docker LAMP with PHP / APACHE / MYSQL

###### 1 - Clonar el repositorio 
###### 2 - Copiar el archivo .env.example a .env y reemplazar por la información necesaria.
###### 3 - Ejecutar docker-compose build
###### 4 - Arrancar docker-compose up -d
###### 5 - Asignar permisos docker exec -it apache_app chmod -R 777 bootstrap/cache && docker exec -it apache_app chmod -R 777 storage