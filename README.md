# api_final
api final
### Описание:

Этот проект, созданный на основе Django REST API, который позволяет получить информацию в формате JSON о публикациях, комментариях и группах сервиса Yatube. Авторизованные пользователи могут добавлять новые посты и комментарии, а также изменять и удалять созданные.

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
*Получить определенный пост (GET):*

http://127.0.0.1:8000/api/v1/posts/1/
*Получить коментарии определенного поста (GET):*

http://127.0.0.1:8000/api/v1/posts/1/comments/
*Получить список всех групп (GET):*

http://127.0.0.1:8000/api/v1/groups/
*Создать новый пост (POST):*

(Нужна аутентификация)

*http://127.0.0.1:8000/api/v1/posts/*


