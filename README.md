# 2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-kovalev_t_a
## University: [ITMO University](https://itmo.ru/ru/) 
## Faculty: [FTMI](https://fict.itmo.ru) 
## Course: [Cloud platforms as the basis of technology entrepreneurship] 
## Year: 2024/2025 
## Group: U4125 
## Author: Kovalev Taras Andreevich 
## Lab: Lab2 
## Date of create: 5.11.2024 
## Date of finished: -


## Описание

Это вторая лабораторная работа "Исследование Cloud Run"

## Цель работы

Ознакомиться с работой Cloud Run - это управляемая вычислительная платформа, которая позволяет запускать контейнеры (изолированная среда для приложения) непосредственно поверх масштабируемой инфраструктуры Google.

## Ход работы

1. Я создал Cloud Run из представленного сервиса с минимальным количеством ресурсов.

Первая версия изначально была на порту 8080 - cтандартный порт для веб-сервисов.

Был сделан deploy образа:
<img width="947" alt="Снимок экрана 2024-11-05 в 20 04 03" src="https://github.com/user-attachments/assets/4b795922-f451-4e16-ac57-ac5d569d8136">

2. Были проанализированы логи:
<img width="1138" alt="image" src="https://github.com/user-attachments/assets/8dd059ca-3b9a-4892-bc6d-f228cad60abe">

В логах можно увидеть, что служба Cloud Run с именем "tkovalev-lab2" была успешно создана в регионе "us-central1" пользователем "yaterressi2020@gmail.com " с помощью Google Cloud Console. Далее можно по логам можно увидеть, что служба Cloud Run «tkovalev-lab2» принимает запросы на порту 8080, а также можно увидеть информацию об успешно принятых HTTP GET-запросах.

3. Были проанализованы метрики:
Среди метрик представлены следующие: количество запросов, задержка запросов, количество экзмепляров контейнера, оплачиваемое время экземпляра контейнера, загрузка ЦП контейнера, использование памяти котнейнера, количество отправленных и полученных байтов, максимальное количество одновременных запросов и задержка запуска контейнера.
<img width="1670" alt="Снимок экрана 2024-11-05 в 20 02 11" src="https://github.com/user-attachments/assets/3b3935bb-39ed-4ab8-9467-17c530383576">
<img width="1677" alt="Снимок экрана 2024-11-05 в 20 02 32" src="https://github.com/user-attachments/assets/ca507c4a-e28b-489a-8b98-b5a16cc76ea6">
<img width="1677" alt="Снимок экрана 2024-11-05 в 20 02 57" src="https://github.com/user-attachments/assets/e517b1fa-7e21-4a88-b412-e8387535b34d">

Активность на отображаемых графиках метрик происходила за счет того, что я обращалась к странице с информацией о запуске образа контейнера (см.выше).

4. Далее был создан еще один образ контейнера на порту 8090 - альтернативный порт для веб-сервисов
<img width="811" alt="image" src="https://github.com/user-attachments/assets/1b3f2b36-0567-4d0f-ad6a-ed2ea1ce0c32">

Были снова проанализированы логи:
<img width="1114" alt="Снимок экрана 2024-11-05 в 20 05 20" src="https://github.com/user-attachments/assets/a8ab8c52-df7a-44c0-9c2b-fc03e8d72c99">
В логах можно отметить, что обновился сервис Cloud Run "tkovalev-lab2" в регионе "us-central1", служба Cloud Run «tkovalev-lab2» принимает запросы на порту 8090 и также можно увидеть информацию об успешно принятых HTTP GET-запросах.
<img width="1120" alt="Снимок экрана 2024-11-05 в 20 06 40" src="https://github.com/user-attachments/assets/60fcebf8-e2ab-4770-ae5a-067d7a6e3c51">

Были проанализированы метрики:
<img width="1687" alt="Снимок экрана 2024-11-05 в 20 12 37" src="https://github.com/user-attachments/assets/a22b24b1-3a47-49f5-8208-b1ef5c37fddb">
<img width="1704" alt="Снимок экрана 2024-11-05 в 20 14 13" src="https://github.com/user-attachments/assets/9d810676-f6ed-403b-86dd-3e9249a88f7b">
<img width="1696" alt="Снимок экрана 2024-11-05 в 20 14 21" src="https://github.com/user-attachments/assets/940ee99b-1c21-4dd7-bad8-f83c8e6c6069">

5. Были протестированы переключения трафика между версиями:
   <img width="986" alt="Снимок экрана 2024-11-05 в 20 15 37" src="https://github.com/user-attachments/assets/f433012c-1261-4856-85c8-b40d79029224">
Лог, показывающий распределение трафика
<img width="1648" alt="Снимок экрана 2024-11-05 в 20 19 13" src="https://github.com/user-attachments/assets/481e005c-c384-4acd-8d2e-1788875e14a6">




