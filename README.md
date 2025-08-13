# ntw-diplom
# ДИПЛОМНАЯ РАБОТА
[по курсу «Сетевой инженер»](https://github.com/netology-code/ntw-diplom/blob/main/README.md)

Выполнил:
Олин Александр.

Задание:
Нужно настроить отказоустойчивую, безопасную, масштабируемую сеть и запустить на ней пользовательские сервисы.

# 1 Соберите топологию сети в Cisco Packet tracer. Модели сетевого оборудования:

<img width="1281" height="723" alt="shema" src="https://github.com/user-attachments/assets/1198599a-b81b-4720-8aca-3958f2ad700b" />
Топология сети построена, для удобства тестирования добавлены пара телефонов и принтер в филиале.


# 2 Заполните таблицу распределения подсетей и адресов (по примеру коммутатора "internet").

[Таблица с адресами сети](https://github.com/Targitay99/ntw-diplom/blob/main/Files/ip-address-table1.xlsx)

# 3 Настройте на коммутаторах доступа порты для подключения пользовательских устройств и аплинки. Также на пользовательских портах коммутатора следует настроить:

port-security на 3 адреса,\
dhcp-snooping,\
portfast,\
RSTP.

<img width="382" height="368" alt="3" src="https://github.com/user-attachments/assets/6ec205ef-14b4-46a4-bad3-a739f7468352" />

# 4 Настройте на коммутаторах ядра:

vlan,\
LAG,\
RSTP,\
SVI,\
dhcp-relay\
HSRP для всех vlan.

[core1](https://github.com/Targitay99/ntw-diplom/blob/main/config/core1.txt)
[core2](https://github.com/Targitay99/ntw-diplom/blob/main/config/core2.txt)

