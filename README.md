# 'Kittygram' created by Pavel.
```
https://github.com/pgphil86
```

![image](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)

### Languages:
### I. [Русский язык.](https://github.com/pgphil86/kittygram_final/tree/main#i-проект-kittygram)
### II. [English language.](https://github.com/pgphil86/kittygram_final/tree/main#ii-project-kittygram)

## I. Проект "Kittygram".

### Описание проекта.

Это маленькая социальная сеть для размещения фото котов и кошек. Пользователь может регистрироваться, загружать фото с описанием, а так же просматривать страницы других пользователей. 

### Используемые технологии:
1. Python 3.9;
1. Django==3.2.3;
1. djangorestframework==3.12.4;
1. Nginx;
1. gunicorn;
1. React;
1. Docker;
1. PostgreSQL;
1. CI-CD;
1. github-actions.

### Установка:
Проект работает с четыремя контейнерами docker(db, backend, frontend, nginx).
Для запуска необходимы Docker, Docker Compose.
Установка этих компонентов описана на ```https://docs.docker.com/engine/install/```.
Проверить работоспособность Docker можно командой:
```
systemctl status docker
```
Проект использует базу данных PostgreSQL.
Для подключения и выполненя запросов к базе данных необходимо создать и заполнить файл ".env" с переменными окружения в папке "./nginx/".

Шаблон для заполнения файла ".env":
```
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
```
Перед запуском необходимо склонировать проект:
```
git clone git@github.com:pgphil86/kittygram_final.git
```
```
cd backend
```
Cоздать и активировать виртуальное окружение:
```
python -m venv venv
```
```
Linux: source venv/bin/activate
Windows: source venv/Scripts/activate
```
И установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
Далее необходимо собрать образы для фронтенда и бэкенда.
Из папки "./backend/" выполнить команду:
```
docker build -t username/kittygram_backend .
```
Из папки "./frontend/" выполнить команду:
```
docker build -t username/kittygram_frontend .
```
Из папки "./nginx/" выполнить команду:
```
docker build -t username/kittygram_gateway .
```
После создания образов можно создавать и запускать контейнеры.
```
docker-compose up -d
```
После успешного запуска контейнеров выполнить миграции:
```
docker-compose exec backend python manage.py migrate
```
Создать суперюзера (Администратора):
```
docker-compose exec backend python manage.py createsuperuser
```
Собрать статику:
```
docker-compose exec backend python manage.py collectstatic --no-input
```
Теперь доступность проекта можно проверить по адресу http://localhost/
### Примеры возможностей:

*Авторизация или регистрация:*
```
https://kitty.viewdns.net/signin
```
*Главная:*
https://kitty.viewdns.net/

*Добавление:*
https://kitty.viewdns.net/cats/add

*Страница с объектом:*
https://kitty.viewdns.net/cats/pk

[Вверх](https://github.com/pgphil86/kittygram_final/tree/main#kittygram-created-by-pavel)

## II. Project "Kittygram"

This is a small social network for posting photos of cats. The user can register, upload a photo with a description, as well as view the pages of other users.

### Technologies used:
1. Python 3.9;
1. Django==3.2.3;
1. djangorestframework==3.12.4;
1. nginx
1. gunicorn;
1. React;
1. Docker;
1. PostgreSQL;
1. CI-CD;
1. github-actions.

### Installation:
The project works with four docker containers (db, backend, frontend, nginx).
Docker, Docker Compose are required to run.
The installation of these components is described on ```https://docs.docker.com/engine/install /```.
You can check the Docker operability with the command:
```
systemctl status docker
```
The project uses a PostgreSQL database.
To connect and execute queries to the database, you need to create and fill in the ".env" file with environment variables in the "./nginx/" folder.

Template for filling in the ".env" file:
```
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
```
Before launching, you need to clone the project:
```
git clone git@github.com:pgphil86/kittygram_final.git

```
cd backend
```
Create and activate a virtual environment:
```
python -m venv venv
```
```
Linux: source venv/bin/activate
Windows: source venv/Scripts/activate
```
And install dependencies from the file requirements.txt :
```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
Next, you need to collect images for the frontend and backend.
From the folder "./backend/" run the command:
```
docker build -t username/kittygram_backend .
```
From the folder "./frontend/" run the command:
```
docker build -t username/kittygram_frontend .
```
From the folder "./nginx/" run the command:
```
docker build -t username/kittygram_gateway .
```
After creating images, you can create and run containers.
```
docker-compose up -d
```
After successfully launching containers, perform migrations:
```
docker-compose exec backend python manage.py migrate
```
Create a superuser (Administrator):
```
docker-compose exec backend python manage.py createsuperuser
```
Collect static:
```
docker-compose exec backend python manage.py collectstatic --no-input
```
Now the availability of the project can be checked at http://localhost/.

### Examples of features:

*Authorization or registration:*
``
https://kitty.viewdns.net/signin
``
*Home:*
https://kitty.viewdns.net/

*Adding:*
https://kitty.viewdns.net/cats/add

*The page with the object:*
https://kitty.viewdns.net/cats/pk

[Up](https://github.com/pgphil86/kittygram_final/tree/main#kittygram-created-by-pavel)

