#### University: [ITMO University](https://itmo.ru/ru/)
#### Faculty: [FTMI](https://ftmi.itmo.ru/)
#### Course: [Cloud platforms as the basis of technology entrepreneurship]
#### Year: 2024/2025
#### Group: U4225
#### Author: Kovalev Taras Andreevich
#### Lab: Lab1
#### Date of create: 6.11.2024
#### Date of finished: -

## Описание
Это первая лабораторная работа "Обзор Google Cloud и исследование основных сервисов."

## Цель работы
Ознакомиться с основными возможностями и преимуществами облачной платформы Google Cloud.

## Ход работы

### Вам необходимо заполнить гугл форму, приложив свою Gmail почту, чтобы вам выдали доступы к Google Cloud.
Сделано

### Зашел во вкладку IAM. Мной был создан service account с ролью Storage Admin. Использовал Storage admin, чтобы получить полный контроль над сегментами, управляемыми папками и объектами.
<img width="1024" alt="image" src="https://github.com/user-attachments/assets/898d277e-5667-4c42-8532-72498bfe1f4c">

### Создал Compute Engine с Machine type e2-micro в режиме Spot.
<img width="1130" alt="image" src="https://github.com/user-attachments/assets/23bedc94-eba0-4945-aaab-403cd813562f">

### С помощью утилиты gsutils был найден бакет lab1-bucket-itmo. Я скопировал 3 файла в локальную папку на VM с помощью команды ls -lah и отобразил что эти файлы хранятся у меня на VM.
<img width="919" alt="Снимок экрана 2024-11-06 в 14 28 11" src="https://github.com/user-attachments/assets/79afba41-bf50-43b1-a2df-e32ffa6892d9">

### Поменял права доступа для Service account со Storage Admin на Compute Viewer, попробовал повторить пункт с копированием данных. На этот раз вышла ошибка AccessDeniedExeption: 403
<img width="1703" alt="Снимок экрана 2024-11-06 в 14 35 05" src="https://github.com/user-attachments/assets/3c9e23f0-c5ec-465f-88f3-8fdb461ee6cc">

После удалил VM, удалил service account.

## Выводы: 
Роль Storage Admin даёт полный доступ к контейнерам, папкам и объектам в облачном хранилище, а роль Compute Viewer предоставляет права только для чтения, позволяя получать и просматривать информацию обо всех ресурсах Compute Engine, таких как экземпляры, диски и настройки. Однако эта роль не даёт доступа к данным, хранящимся на дисках, образах и снимках, а только к метаданным.
