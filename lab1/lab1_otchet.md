University: Sholom-Aleichem Priamursky State University 

Faculty: FICT

Course: Network-programming 

Year: 2023/2024  
Group: 1701 
Author: Dolmatov Dmitrii Alexeevich  
Lab: Lab1  

# Лабораторная работ №1 "Установка CHR и Ansible, настройка VPN"  
## Описание  
Данная работа предусматривает обучение развертыванию виртуальных машин (VM) и системы контроля конфигураций Ansible а также организации собственных VPN серверов
## Цель работы  
Целью данной работы является развертывание виртуальной машины на базе платформы Microsoft Azure с установленной системой контроля конфигураций Ansible и установка CHR в VirtualBox
### Ход работы  
#### Создание вирутальной машины на сервисе Yandex.Cloud
Была создана виртуальная машина в сервисе Yandex.Cloud. Результат создання машины представлен ниже ![Созданная виртуальная машина](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/yandexVM.png)  

Для подключения к виртуальной машине используется программа PuTTY, в которой был сгенерирован SSH ключ для подключения
![Установка соединения с виртуальной машиной яндекс](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/conectionYandexVM.png) 


Слудющим шагом являлась установка python3 и ansible. 

Python3 в данной виртуальной машине был предустановлен по умолчанию. ![Устаановленный python3](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/InstalPython.png) 

Ansible был установлен с помощью соответсвующих команд. ![Установка Ansible](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/ansibleinstall.png)  


После настройки виртуальной машины в сервисе яндекс, осуществляется настройка виртуальной машины в VirtualBox перед установкой RouterOS/
При создании виртуального роутера используется следующая настройка сети 
![Настройка сети виртуальной машины](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/settingVM1.png) 

Далее был загружен образ виртуальной машины с офциального сайта Mikrotik. После была выполнена установка в VurtualBox. Также для дальнейшей работы был установлен WinBox, который позволяет подключаться к роутеру и управлять им, использую графический интрфейс.
![Виртуальная машина с RouterOS](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/installRouterOS.png) 

После настройки всех машин следует установка OVPN на виртуальную машину яндекс с помощью скрипта
![Устаановленный OVPN на виртуальную машину яндекс](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/InstalOVPN.png) 

В результате установки OVPN в консоли выводится лицензия, секретный ключ для подключения, а также логин и пароль
![Установленный OVPN](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/RunOVPN.png) 

Далее осущствляется создания сетевого интерфейса в RouterOS с помощью WinBox. В процессе создания загружаются в файлы RouterOS сертификат и подключается к нему секретныйй ключ. Дале происходит настройка самого интерфейса
![Настройка сетевого интерфейса в WinBox](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/interfaceFoOVPNClientMT.png) 

В результате создания интерфейса можно проверить подключения локальной виртуальной машины с виртуальной машиной яндекс с помощью команды ping
![Проверка соединения между виртуальными машинами](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/pingRouterOS.png) 
