## Создать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД (compose)

Создаем папку для текущего задания

mkdir compose/

Переходим в нее 

cd compose/

Создаем файл с расширением yaml

nano docker-compose.yaml

Заполняем файл

~~~
version:'3.9'
services:
  db:
    image:mariadb:10.10.2
    restart:always
    environment:
      MYSQL_ROOT_PASSWORD:12345
  adminer:
    image:adminer:4.8.1
    restart:always
    ports:
      -6080:8080
~~~

version:'3.9' - Версия

db и adminer - Сервисы

image:mariadb:10.10.2 и image:adminer:4.8.1 - Образы

restsrt:always - Политика перезагрузки

environment - Флаг -e

porsts - Флаг -p

Создаем контейнеры

docker compose up

Проверяем запущенные контейнеры 

docker ps -a
