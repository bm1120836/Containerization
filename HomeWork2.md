
Контейнеризация

ДЗ по семинару № 2.
студент: Горбунов Владимир Федорович.

Задание:
1) запустить контейнер с ubuntu, используя механизм LXC
2) ограничить контейнер 256 Мб ОЗУ и проверить, что ограничение работает
Задание по желанию ..
4)'' добавить автозапуск контейнеру, перезагрузить ОС и убедиться, что контейнер действительно запустился самостоятельно
5) ''при создании указать файл, куда записывать логи
6) ''после перезагрузки проанализировать логи


sudo apt update

sudo apt install lxc-utils

sudo apt-get install lxc-templates

lxc storage list

lxc-create -n test123 -t ubuntu

sudo apt-get update

sudo apt-get install lxc

sudo lxc-checkconfig

lxc-start -n test123

lxc-attach -n teat123

free -m

nano /var/lib/lxc/test123/config

lxc.cgroup2.memory.max = 256M

lxc.start.auto  =  1
