
## Задание 1:
1) запустить контейнер с ubuntu, используя механизм LXC
2) ограничить контейнер 256 Мб ОЗУ и проверить, что ограничение работает
3)* добавить автозапуск контейнеру, перезагрузить ОС и убедиться, что контейнер действительно запустился самостоятельно
4)* при создании указать файл, куда записывать логи
5)* после перезагрузки проанализировать логи

## Задание 2*: настроить автоматическую маршрутизацию между контейнерами. Адреса можно взять: 10.0.12.0/24 и 10.0.13.0/24.

## Задание со звездочкой - повышенной сложности, это нужно учесть при выполнении (но сделать его необходимо).

### sudo apt update

### sudo apt install lxc-utils

### sudo apt-get install lxc-templates

### snap install lxd

### lxc storage list

### lxc-create -n test123 -t ubuntu

### sudo apt-get update

### sudo apt-get install lxc

### sudo lxc-checkconfig

### lxc-start -n test123

### lxc-attach -n teat123

### free -m

### nano /var/lib/lxc/test123/config

### lxc.cgroup2.memory.max = 256M

### lxc.start.auto  =  1

