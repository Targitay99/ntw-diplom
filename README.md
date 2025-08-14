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

Настройки сделаны:
[core1](https://github.com/Targitay99/ntw-diplom/blob/main/config/core1.txt)
[core2](https://github.com/Targitay99/ntw-diplom/blob/main/config/core2.txt)

<img width="530" height="348" alt="4_1" src="https://github.com/user-attachments/assets/f98f3fb0-3d5e-493e-a746-b5990620dc0c" />
<img width="531" height="214" alt="4_2" src="https://github.com/user-attachments/assets/8114495f-0899-4cad-9632-b79e71136cce" />

RSTP и LAG работают.

# 5 Настройте сервисы для распределения сетевых настроек для пользовательских устройств. Так как сервер находится в отдельной сети, на SVI настраивается helper. По окончанию настроек dhcp-сервер должен раздать настройки PC, телефонам и принтерам, с любого хоста ЦО должен быть доступен любой другой хост.

Настройки сделаны:
[core1](https://github.com/Targitay99/ntw-diplom/blob/main/config/core1.txt)
[core2](https://github.com/Targitay99/ntw-diplom/blob/main/config/core2.txt)

# 6 Настройте сервис БЛВС. Точки доступа должны подключаться к контроллеру, который сообщит им настройки по capwap. Подключите ноутбук к ТД, проверьте связность сети.

<img width="801" height="478" alt="5_1" src="https://github.com/user-attachments/assets/7027d35f-f7f9-4336-b88c-207a480b2b0b" />
<img width="907" height="440" alt="5_2" src="https://github.com/user-attachments/assets/68eed59d-7a7e-493c-b681-2a13c9170711" />
<img width="785" height="361" alt="5_3" src="https://github.com/user-attachments/assets/9400399e-a6ac-4734-9a35-3ce3623c3cde" />

Настройки выполненны. Ноутбук в основном офисе не подключается к сети после запуска системы. Лечится выключением и включением питания точки доступа. Почему так происходит не разобрался. 

# 7 На коммутаторах ядра запустите протокол маршрутизации ospf. Он должен анонсировать все внутренние сети в зоне 1.

Настройки сделаны:
[core1](https://github.com/Targitay99/ntw-diplom/blob/main/config/core1.txt)
[core2](https://github.com/Targitay99/ntw-diplom/blob/main/config/core2.txt)

На каждом межсетевом экране настройте адресацию и три зоны: inside, outside, DMZ.

# 8 Правила фильтрации:\

из inside доступ свободный во все зоны\
из outside в inside и DMZ доступ разрешен для траффика от приватных адресов\
из DMZ разрешен доступ только в outside на публичные адреса.

Настройки сделаны:\
[ASA1](https://github.com/Targitay99/ntw-diplom/blob/main/config/ASA1.txt)\
[ASA2](https://github.com/Targitay99/ntw-diplom/blob/main/config/ASA2.txt).

# 9 На Cisco ASA настройте протокол ospf. МСЭ должен принимать и анонсировать все сети в зоне 1.
Настройте web-сервер, подключенный в DMZ зону одной из ASA.

Настройки сделаны:\
[ASA1](https://github.com/Targitay99/ntw-diplom/blob/main/config/ASA1.txt)\
[ASA2](https://github.com/Targitay99/ntw-diplom/blob/main/config/ASA2.txt).

На этом шаге проверьте:

все ли сети получены

<img width="632" height="494" alt="9_1" src="https://github.com/user-attachments/assets/88c5f5b9-7d10-4807-8e28-8dac36f9910a" />

все ли сети анонсируются на коммутаторы ядра

<img width="545" height="398" alt="9_2" src="https://github.com/user-attachments/assets/e2082634-6049-4aa4-b82d-05f0139e2140" />

есть ли доступ к web-серверу и с него

<img width="564" height="127" alt="9_3" src="https://github.com/user-attachments/assets/1cbcf9be-a14c-4a16-86bd-5c775de60678" />

# 10 Настройте пограничные маршрутизаторы. Настройте адресацию и проверьте сетевую связность внутри ЛВС и доступность шлюза провайдера.

Настройки сделаны:\
[border1]()\
[border2]().










