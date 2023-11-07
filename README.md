# api_final
api final
### Описание:

Этот проект, созданный на основе Django REST API, который позволяет получить информацию в формате JSON о публикациях, комментариях и группах сервиса Yatube. Авторизованные пользователи могут добавлять новые посты и комментарии, а также изменять и удалять созданные.

### Стек использованных технологий:

1. Django: Основной фреймворк веб-приложения.
2. Django REST Framework (DRF): Мощный и гибкий инструмент для построения Web API.
3. SQLite или другая база данных: По умолчанию Django использует SQLite, но для продакшена может использоваться PostgreSQL, MySQL и т.д.
4. Python: Язык программирования, на котором основан Django.
5. Djoser: Библиотека для управления аутентификацией пользователей через REST API.
6. Simple JWT: Библиотека для работы с JSON Web Tokens (JWT) для аутентификации.
7. Django Filters: Библиотека для фильтрации запросов.
8. Git: Система контроля версий для управления исходным кодом проекта.

### Установка:

**Клонируйте репозиторий и перейдите в него в командной строке:**

```
git clone https://github.com:yandex-praktikum/api_final_yatube.git
```

```
cd api_final_yatube
```

**Cоздайте и активируйте виртуальное окружение:**

```
python3 -m venv env
```

```
source env/bin/activate
```

**Установите зависимости из файла requirements.txt:**

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

**Выполните миграции:**

```
python3 manage.py migrate
```

**Запустите проект:**

```
python3 manage.py runserver
```
### Примеры запросов к API:

*Получить список всех постов (GET):*

http://127.0.0.1:8000/api/v1/posts/

Пример ответа:
[
  {
    "id": 1,
    "text": "Первый пост",
    "pub_date": "2021-07-23T14:30:59Z",
    "author": "username",
    "image": null,
    "group": null
  },
  {
    "id": 2,
    "text": "Второй пост",
    "pub_date": "2021-07-24T17:15:22Z",
    "author": "another_username",
    "image": null,
    "group": null
  }
]

*Получить определенный пост (GET):*

http://127.0.0.1:8000/api/v1/posts/1/

Пример ответа:
{
  "id": 1,
  "text": "Первый пост",
  "pub_date": "2021-07-23T14:30:59Z",
  "author": "username",
  "image": null,
  "group": null
}

*Получить коментарии определенного поста (GET):*

http://127.0.0.1:8000/api/v1/posts/1/comments/

Пример ответа:
[
  {
    "id": 1,
    "author": "username",
    "text": "Комментарий к посту",
    "created": "2021-07-23T15:00:00Z",
    "post": 1
  }
]

*Получить список всех групп (GET):*

http://127.0.0.1:8000/api/v1/groups/

Пример ответа:
[
  {
    "id": 1,
    "name": "Группа 1",
    "slug": "group-1",
    "description": "Описание группы 1"
  }
]

*Создать новый пост (POST):*

*http://127.0.0.1:8000/api/v1/posts/*

Требуется аутентификация. Тело запроса должно содержать данные нового поста в формате JSON, например:
{
  "text": "Новый пост",
  "group": 1
}

Пример ответа (после успешного создания):
{
  "id": 3,
  "text": "Новый пост",
  "pub_date": "2021-07-25T19:34:56Z",
  "author": "authenticated_username",
  "image": null,
  "group": 1
}
