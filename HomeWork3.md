
## Задание:
1) запустить контейнер с БД, отличной от mariaDB, используя инструкции на сайте: https://hub.docker.com/
2) добавить в контейнер hostname такой же, как hostname системы через переменную
3) заполнить БД данными через консоль
4) запустить phpmyadmin (в контейнере) и через веб проверить, что все введенные данные доступны.

### 1. Запустить контейнеры с mysql и phpmyadmin (поскольку их нет, то система автоматически их найдет и загрузит), уствановив правила проброса порто для соединеня c хостом.

docker pull mysql

docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:8.0.31

docker run --name myphp -d --link some-mysql:db -p 8081:80 phpmyadmin/phpmyadmin

### 2. Убедиться, что контейнеры запустились.

docker ps -a

### 3. Заупстить mysql.

docker exec -it some-mysql mysql -uroot -p

### 4. Посмотреть имеющиеся базы данных.

SHOW DATABASES;

### 5. Создать новую БД.

CREATE DATABASE my_database;

### 6. Зайти в нее.

use my_database;

### 7. Создать в ней таблицу.

mysql> CREATE TABLE Products -> ( -> Id INT AUTO_INCREMENT PRIMARY KEY, -> ProductName VARCHAR(30) NOT NULL, -> Manufacturer VARCHAR(20) NOT NULL, -> ProductCount INT DEFAULT 0, -> Price DECIMAL NOT NULL -> ); 

### 8. Вставить в нее данные.

INSERT Products(ProductName, Manufacturer, ProductCount, Price) VALUES ('iPhone X', 'Apple');