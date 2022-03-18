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
# foodgram-project-react
Приложение "Продуктовый помощник": сайт, на котором вы можете публиковать рецепты, добавлять чужие рецепты в избранное и подписываться на публикации других авторов. Сервис Списка покупок позволяет пользователям создавать список продуктов, необходимых для приготовления выбранных блюд.

# Запуск проекта
## Клонируйте репозиторий на свой компьютер
```
HTTPS - https://github.com/AleksSpace/foodgram-project-react.git
SSH - git@github.com:AleksSpace/foodgram-project-react.git
GitHub CLI - gh repo clone AleksSpace/foodgram-project-react
```
## Создайте и заполните файл .env
```
DB_ENGINE=<...> # укажите, что мы работаем с базой данных postgresql
DB_NAME=<...> # имя базы данных
POSTGRES_USER=<...> # логин для подключения к базе данных
POSTGRES_PASSWORD=<...> # пароль для подключения к базе данных (создайте свой собственный)
DB_HOST=<...> # название хоста (контейнера)
DB_PORT=<...> # порт для подключения к базе данных
SECRET_KEY=<...> # ключ от settings.py
```
## 1.Сборка и запуск контейнера из папки "infra"
```
docker-compose up -d --build
```
## 2.Совершайте миграции
```
docker-compose exec backend python manage.py migrate
```
## 3.Создайте суперпользователя Django
```
docker-compose exec backend python manage.py createsuperuser
```
## 4.Соберите статику
```
docker-compose exec backend python manage.py collectstatic --no-input
```
## 5.Загрузка данных в базу данных
```
docker-compose exec web python manage.py loaddata fixtures/ingredients.json
```
***
## Проект доступен по ссылке :
http://51.250.27.112/

http://51.250.27.112/admin/

login - admin@admin.ru, pass - admin