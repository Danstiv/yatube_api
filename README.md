### Описание
Это бэкенд проекта yatube.
Сдесь реализован API, позволяющий создавать, просматривать, редактировать и удалять посты и комментарии.

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