# Install

1. Первым шагом установить laravel с помощью команды `composer create-poject laravel/laravel <project_name>`.  
2. Копировать папку `docker` и  файл `docker-compose.yaml` в новосозданный проект laravel. 

## Ошибки

### Ошибка - `UnexpectedValueException` - `The stream or file "/var/www/storage/logs/laravel.log" could not be opened`

Для исправления этой ошибки необходимо дать права для папок `storage` и `bootstrap/cache`.  
С помощью команды `sudo chmod -R 777 storage && sudo chmod -R 777 bootstrap/cache`.  
Команду писать в корне проектаю

### Ошибка - `No application encryption key has been specified.`

Входим в контейнер php с помощью команды `docker exec -it <container_name> bash`.
Прописываем команду `php artisan key:generate`

# Using

Use the command `docker-compose up -d` to start the containers.  
Use the command `docker-compose down` to stop the containers.