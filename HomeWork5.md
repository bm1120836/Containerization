
## Задание 1:
## 1) создать docker compose файл, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД
## 2) запустить docker compose файл
## 3) по итогу на БД контейнере должно быть 2 реплики, на админере должна быть 1 реплика. Всего должно 
## получиться 3 контейнера
## 4) выводы зафиксировать

### Создание docker-compose.yaml

version: "3.9"

services:

db:
   image: mysql:latest
   restart: always
   environment:
        MYSQL_ROOT_PASSWORD: 1

wordpress:
   image: wordpress:latest
   ports:
   - "8000:81"
   restart: always

### Запустить развертывание контейнеров из yaml-файла

docker-compose up -d

### Посмотреть что получилось

docker-compose ps -a