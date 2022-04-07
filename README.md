### Описание
Это бэкенд проекта Yatube.

Здесь реализован API, позволяющий создавать, просматривать, редактировать и удалять посты и комментарии.

### Как запустить проект:

#### Linux
Создать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

```
python3 -m pip install --upgrade pip
```

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

#### Windows
Создать и активировать виртуальное окружение:

```
python -m venv env
```

```
env\scripts\activate
```

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

### Документация
После запуска сервера документация будет доступна по адресу [http://localhost:8000/redoc/](http://localhost:8000/redoc/)

#### Примеры работы с API
Сначала нужно создать пользователя (API эту возможность не предоставляет).

Выполните `python manage.py createsuperuser` и заполните предложенные поля (обязательно заполнить только username и password).

Или создайте пользователя любым удобным для вас способом.

Далее необходимо получить пару токенов (API использует JWT токены).

`POST /api/v1/jwt/create/`

В теле запроса нужно отправить json:

`{"username": "your_username", "password": "your_password"}`

В ответе будет json с полями

access - ваш токен.

refresh - токен для обновления access токена.

Теперь access_token можно использовать для выполнения любых запросов.

Создание поста:

`POST /api/v1/posts/`

Тело запроса:

`{"text": "post text"}`

Ответ:

`{'id': 1, 'author': 'Danstiv', 'text': 'Тестовый пост', 'pub_date': '2022-04-07T07:42:56.706607Z', 'image': None, 'group': None}`

Комментирование поста

`POST /api/v1/posts/1/comments/`

Тело запроса:

`{"text": "comment text"}`

Ответ:

`{'id': 1, 'author': 'Danstiv', 'post': 1, 'text': 'Комментарий', 'created': '2022-04-07T07:49:44.293343Z'}`

Получение постов

`GET /api/v1/posts/`

Ответ:

`[{'id': 1, 'author': 'Danstiv', 'text': 'Тестовый пост', 'pub_date': '2022-04-07T07:42:56.706607Z', 'image': None, 'group': None}]`

Удаление поста:

DELETE /api/v1/posts/1/

Параметры и примеры запросов / ответов вы также можете посмотреть в документации.