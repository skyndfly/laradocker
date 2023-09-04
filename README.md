# Установка

1. Первым шагом установить laravel с помощью команды `composer create-poject laravel/laravel <project_name>`; 
2. Копировать папку `docker` и  файл `docker-compose.yaml` в новосозданный проект laravel;
3. Проверить совпадение данных подключеения к БД в файлах `docker-compose.yaml` и `.env` (`DB_PORT`, `DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`);
4. В файле `.env` для переменной `DB_CONNECTION` указать значением `container_name`(у меня называется `mysql`), а для перменной `DB_HOST` имя образа?имя контейнера у меня `db`.

## Ошибки

### Ошибка - `UnexpectedValueException` - `The stream or file "/var/www/storage/logs/laravel.log" could not be opened`

Для исправления этой ошибки необходимо дать права для папок `storage` и `bootstrap/cache`.  
С помощью команды `sudo chmod -R 777 storage && sudo chmod -R 777 bootstrap/cache`.  
Команду писать в корне проектаю

### Ошибка - `No application encryption key has been specified.`

Входим в контейнер php с помощью команды `docker exec -it <container_name> bash`.
Прописываем команду `php artisan key:generate`

# Использование

Использывать команду `docker-compose up -d` чтобы запустить контейнеры.  
Использывать команду  `docker-compose down` чтобы остановить контейнеры.