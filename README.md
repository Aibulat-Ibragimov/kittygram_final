![example workflow](https://github.com/Aibulat-Ibragimov/kittygram_final/actions/workflows/main.yml/badge.svg)
# Kittygram
## **Описание проекта**

Этот проект предоставляет возможность делиться изображениями вашего питомца и наслаждаться фотографиями котов и кошек от других участников.
Включите в описание информацию о вашем питомце, включая его кличку, окраску и достижения.

## **Стэк технологий**

Python 3.9 <br>
Django 3.2.3 <br>
djangorestframework 3.12.4 <br>
djoser 2.1.0 <br>
webcolors 1.11.1 <br>
gunicorn 20.1.0 <br>
psycopg2-binary 2.9.6 <br>
pytest-django 4.4.0 <br>
pytest-pythonpath 0.7.3 <br>
pytest 6.2.4 <br>
PyYAML 6.0 <br>
python-dotenv 1.0.0 <br>

---


## Локальный запуск проекта

Клонировать репозиторий и перейти в него в командной строке:

```bash
git clone https://github.com/Aibulat-Ibragimov/kittygram_final.git
cd kittygram_final
```

Cоздать и активировать виртуальное окружение, установить зависимости:

```bash
python3 -m venv venv && \ 
    source venv/scripts/activate && \
    python -m pip install --upgrade pip && \
    pip install -r backend/requirements.txt
```

Установите [docker compose](https://www.docker.com/) на свой компьютер.

Запустите проект через docker-compose:

```bash
docker compose -f docker-compose.yml up --build -d
```

Выполнить миграции:

```bash
docker compose -f docker-compose.yml exec backend python manage.py migrate
```

Соберите статику и скопируйте ее:

```bash
docker compose -f docker-compose.yml exec backend python manage.py collectstatic  && \
docker compose -f docker-compose.yml exec backend cp -r /app/backend_static/. /backend_static/static/
```

## .env

В корне проекта создайте файл .env и пропишите в него свои данные.

Пример:

```apache
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
SECRET_KEY='django-insecure-cg6*%6d51ef8f#4!r3*$vmxm4)abgjw8mo!4y-q*uq1!4$-89$'
ALLOWED_HOSTS=aibulatskittygram.ddns.net
```

**~~Автор проекта:~~** Ибрагимов Айбулат https://github.com/Aibulat-Ibragimov
