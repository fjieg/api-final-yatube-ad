## Проект API-Yatube

Это учебный проект реализованный в рамках прохождения курса яндекс практикума бэкэнд на python (спринт 10).

### Возможности

- Публикация постов
- Комментирование постов
- Создание групп
- Подписка на авторов
- JWT-аутентификация

### Основные эндпоинты

| Метод | Эндпоинт | Описание |
|-------|----------|----------|
| POST | `/api/v1/auth/jwt/create/` | Получение JWT-токена |
| GET | `/api/v1/posts/` | Список постов |
| POST | `/api/v1/posts/` | Создать пост |
| GET | `/api/v1/posts/{id}/` | Пост по id |
| PUT/PATCH | `/api/v1/posts/{id}/` | Обновить пост (автор) |
| DELETE | `/api/v1/posts/{id}/` | Удалить пост (автор) |
| GET/POST | `/api/v1/posts/{post_id}/comments/` | Комментарии поста |
| GET/PUT/PATCH/DELETE | `/api/v1/posts/{post_id}/comments/{id}/` | Комментарий |
| GET | `/api/v1/groups/` | Список групп |
| GET | `/api/v1/groups/{id}/` | Группа по id |
| GET/POST | `/api/v1/follow/` | Подписки |
| GET | `/redoc/` | Документация API |

### Права доступа

- Все эндпоинты требуют JWT-токен (кроме `redoc`)
- Изменение/удаление постов и комментариев - только автору
- Подписки - только для авторизованных

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone <url-репозитория>
```

```
cd api-final-yatube-ad
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate  # Windows
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:
```
cd yatube_api
```

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```
