University: Sholom-Aleichem Priamursky State University 

Faculty: FICT

Course: Network-programming 

Year: 2023/2024  
Group: 1701 
Author: Dolmatov Dmitrii Alexeevich  
Lab: Lab1  

# Лабораторная работ №2 "Развертывание дополнительного CHR, первый сценарий Ansible"  
## Описание  
В данной лабораторной работе вы на практике ознакомитесь с системой управления конфигурацией Ansible, использующаяся для автоматизации настройки и развертывания программного обеспечения.  
Цель работы. С помощью Ansible настроить несколько сетевых устройств и собрать информацию о них. Правильно собрать файл Inventory.
### Ход работы  
#### Создание создание второго CHR(RouterOS) на своём ПК
Была создана виртуальная машина в сервисе Yandex.Cloud. Результат создання машины представлен ниже ![Созданная виртуальная машина](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/yandexVM.png)  

Для подключения к виртуальной машине используется программа PuTTY, в которой был сгенерирован SSH ключ для подключения
![Установка соединения с виртуальной машиной яндекс](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab1/otchet/conectionYandexVM.png) 


Слудющим шагом являлась установка python3 и ansible. 

