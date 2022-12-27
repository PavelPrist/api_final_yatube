# Проект «API для Yatube»
### Описание
Проект Yatube представляет собой социальную сеть с возможностью добавлять посты, комментировать, подписываться на автора, распределять посты по группам.

### Технологии
Python 3.7, Django==3.2.16, DRF, JWT, Djoser

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/PavelPrist/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source env/bin/activate
```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры работы с API для авторизованных пользователей

Чтобы создать публикацию:
```
POST /api/v1/posts/
```
в body
{
"text": "string",
"image": "string",
"group": 0
}

Чтобы обновить публикацию:
```
PUT /api/v1/posts/{id}/
```
в body
{
"text": "string",
"image": "string",
"group": 0
}

### Создание пользователя и получение токена для авторизации:

Для создания пользователя:
```
POST /api/v1/users/
```
В body передаются данные логин и пароль:
```
{
"username": "string",
"password": "string"
}

```
Для доступа используется JWT-токен (Joser),
который можно получить выполнив POST запрос по адресу:
```
POST /api/v1/jwt/create/
```
В body передаются данные пользователя (например в postman):
```
{
"username": "string",
"password": "string"
}
```
Автор:  Павел Сердюков.