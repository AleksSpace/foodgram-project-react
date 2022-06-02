![foodgram workflow](https://github.com/DmitryTok/foodgram-project-react/actions/workflows/main.yml/badge.svg)
[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![GitHub%20Actions](https://img.shields.io/badge/-GitHub%20Actions-464646?style=flat-square&logo=GitHub%20actions)](https://github.com/features/actions)
[![Yandex.Cloud](https://img.shields.io/badge/-Yandex.Cloud-464646?style=flat-square&logo=Yandex.Cloud)](https://cloud.yandex.ru/)
# Продуктовый помощник
Приложение "Продуктовый помощник": сайт, на котором вы можете публиковать рецепты, добавлять чужие рецепты в избранное и подписываться на публикации других авторов. Сервис "Список покупок" позволяет пользователям создавать список продуктов, необходимых для приготовления выбранных блюд.

# Запуск проекта
## Запуск проекта в dev-режиме без Docker
### Клонируйте репозиторий на свой компьютер
```
HTTPS - git clone https://github.com/AleksSpace/foodgram-project-react.git
SSH - git clone git@github.com:AleksSpace/foodgram-project-react.git
GitHub CLI - git clone gh repo clone AleksSpace/foodgram-project-react
```
### Создайте и активируйте виртуальное окружение
```
python -m venv venv
. venv/Scripts/activate
```
### Обновите pip и установите зависимостси
```
python -m pip install --upgrade pip
pip install -r requirements.txt
```
## Создайте файл .env
С помощью команды ниже в папке будет создан .env-файл
```
echo 'SECRET_KEY=some-secret-key
ALLOWED_HOSTS=*
DEBUG=1
DB_ENGINE=django.db.backends.sqlite3 # укажите, что мы работаем с базой данных postgresql
DB_NAME=db.sqlite3 # имя базы данных
DB_USER=<...> # логин для подключения к базе данных
DB_PASSWORD=<...> # пароль для подключения к базе данных (создайте свой собственный)
DB_HOST=<...> # название хоста (контейнера)
DB_PORT=<...> # порт для подключения к базе данных
' > .env
```
## Запуск проекта
```
python manage.py migrate - Выполнение миграций
python manage.py createsuperuser - Создание суперпользователя
python manage.py importingredients ingredients.json - Загрузка тестовой БД
python manage.py runserver localhost:8080 - Запуск Dev-сервера
```
***
## Проект будет доступен по ссылке:
http://localhost/

http://localhost/admin/

## Запуск проекта в контейнерах Docker
### Клонируйте репозиторий на свой компьютер
```
HTTPS - git clone https://github.com/AleksSpace/foodgram-project-react.git
SSH - git clone git@github.com:AleksSpace/foodgram-project-react.git
GitHub CLI - git clone gh repo clone AleksSpace/foodgram-project-react
```
### Создайте и активируйте виртуальное окружение
```
python -m venv venv
. venv/Scripts/activate
```
### Обновите pip и установите зависимостси
```
python -m pip install --upgrade pip
pip install -r requirements.txt
```
## Создайте файл .env
На production обязательно заменить значение SECRET_KEY
С помощью команды ниже в папке будет создан .env-файл
```
echo 'SECRET_KEY=some-secret-key
ALLOWED_HOSTS=*
DEBUG=1
DB_ENGINE=django.db.backends.sqlite3 # укажите, что мы работаем с базой данных postgresql
DB_NAME=db.sqlite3 # имя базы данных
DB_USER=<...> # логин для подключения к базе данных
DB_PASSWORD=<...> # пароль для подключения к базе данных (создайте свой собственный)
DB_HOST=<...> # название хоста (контейнера)
DB_PORT=<...> # порт для подключения к базе данных
' > .env
```

### Сборка контейенеров
Соберите контейнеры и запустите их

```
docker compose up -d
docker compose exec backend python manage.py createsuperuser
```

### Заполнение базы данных
Заполните БД подготовленными данными при первом запуске

```
docker compose cp ../data/ingredients.json backend:/app/ingredients.json 
docker compose exec backend python manage.py importingredients ingredients.json
docker compose exec backend rm ingredients.json
```
***
## Проект будет доступен по ссылке:
```
API - http://localhost/

Redoc - http://localhost/api/docs/

Frontend - http://localhost/

Админка - http://localhost/admin/
```

## Deploy на сервер
При пуше в ветку master выполняется автоматическое разворачивание проекта на сервере (после всех тестов)

Об авторе
- [Заикин Алексей](https://github.com/AleksSpace "GitHub аккаунт")
