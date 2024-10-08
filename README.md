
Дипломный проект!

Backend-приложение: телеграмм бот "Валютообменник".

Цель дипломного проекта:
Создание и настройка телеграмм бота, который взаимодействует с backend-приложением"Валютообменник".

Подготовка:

1) Основной компьютер, на котором будет установлен интерпретатор Python: Pycharm версии 2024.2.0.1;
2) Виртуальная машина, на которой будет установлена, с помощью образа диска, ОС Rocky Linux (версия 8 и выше);
3) Токен для телеграмм бота, созданный с помощью Fatherbot в самом приложении Telegram.

Этап 1. Настройка сервиса на VM ОС Rocky Linux (версия 8 и выше) и запуск redis, MariaDB и uvicorn.

Установить в командной строке, версию Python 3.10 или более новую версию.
Создать c помощью команды nano или vim следующие файлы:
1) api_exchange_redis.py 
редактировать файл с помощью команды nano и перенести туда данные с файла api_exchange_redis.py из репозитория;
2) exchange_redis.conf
редактировать файл с помощью команды nano и перенести туда данные с файла exchange_redis.conf из репозитория.

Также необходимо установить на VM, с помощью doker, следующие контейнеры:
1) redis;
2) mariadb;
3) FastAPI

Вводим в командную строку "doker ps -a" и запускаем с помощью doker следующих контейнеров:
1) redis (команда: doker start "name redis");
2) mariadb (команда: doker start "name mariadb");
3) запускаем uvicorn (/usr/local/bin/uvicorn api_exchange_redis:app --host 0.0.0.0 --port 8080)


Этап 2. Запускаем backend-приложением"Валютообменник" в интерпретаторе Pycharm на основном компьютере. 

1) Копируем код репозитория Graduation_project_PlankinIS и создаем новый проект в интерпретаторе Pycharm;
2) Во всех файлах меняем ip адрес на адрес сервиса установленного на виртуальной машине;
3) Запускаем файл get_currency_rate.py (получение данных из ЦБ и занесение их в БД);
4) Устанавливаем в файле Telegrambot.py токен bot;
5) Запускаем файл Telegrambot.py


Этап 3. Запускаем созданный телеграмм бота в Telegram.

1) Вводим команду /start
2) вводим данные.

Если условия установки соблюдены, программа функционирует в штатном режиме.