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
Создание создание второго CHR(RouterOS) на своём ПК
Создание второй CHR виртуальнйо машины осущствляется дублированием первой и сбросом её настроек. Далее проводятся аналогичные действия , описанные в лабороторной работе №1, а именно загружаются файлы сертификата и секретного ключа, создаётся новый сетевой интеерфейс. После проделанных процедур проверяем наличие соединения сервера в яндекс облаке с локальными CHR машинами  ![Созданная виртуальная машина](https://github.com/ErdmanAA/2023_2024-network_programming-1701-erdman_a_a/blob/main/lab2/otchet/chekingConnection.png)  

Для использования возможностей Ansible в первую очередь необходимо создадать файл "hosts" для инвентаризации. В этом файле  укажем списки наших роутеров CHR, их IP-адреса, а также логины и пароли для доступа.
'''
[chrs]
chr_1 ansible_host=172.27.240.20 rid=10.10.10.1
chr_2 ansible_host=172.27.240.21 rid=10.10.10.2

[chrs:vars]
ansible_connection=ansible.netcommon.network_cli
ansible_network_os=community.routeros.routeros
ansible_user=admin
ansible_ssh_pass=123
