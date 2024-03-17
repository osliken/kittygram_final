[![Main Kittygram workflow](https://github.com/osliken/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/osliken/kittygram_final/actions/workflows/main.yml)

# Kittygram - блог для размещения фотографий котиков.

## Описание проекта: 

В проекте Kittygram пользователи могут делиться фотографиями котиков. Зарегистрированные пользователи могут создавать, удалять, редактировать свои записи.

## Ссылка на приложение в сети:

[https://osliken.ru/](https://osliken.ru/)


## Стэк проекта:

- Git
- Docker
- Postgres
- Python 3.x
- Node.js 9.x.x
- Gunicorn
- Nginx
- Django
- React

## Как развернуть проект:

- Клонироуйте репозиторий:

    ```bash
    git clone git@github.com:osliken/kittygram_final.git
    ```
- Создайте файл .env

    ```bash
    touch .env
    ```
- Добавьте в файл .env переменные окружения:

    ```bash
    POSTGRES_USER=<имя пользователя>
    POSTGRES_PASSWORD=<пароль>
    POSTGRES_DB=<база данных>
    DB_NAME=<имя базы данных>
    DB_HOST=db
    DB_PORT=5432
    SECRET_KEY=<ключ Django>
    ```
- Запустите Docker compose

    ```bash
    sudo docker compose -f docker-compose.yml up -d
    ```
- Сделайте миграции и соберите статику

    ```bash
    sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
    sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
    sudo docker compose -f docker-compose.production.yml exec backend mkdir -p /backend_static/static/
    sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
    ```



## Автор

- Петров Сергей - [GitHub](https://github.com/osliken)
