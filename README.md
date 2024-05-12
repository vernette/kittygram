# Kittygram

Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Каждый желающий может загрузить фотографии своих котиков и поделиться ими.

## Запуск проекта

Клонируйте репозиторий и перейдите в папку с проектом:

```bash
git clone https://github.com/vernette/kittygram_final
cd kittygram_final
```

Создайте виртуальное окружение и активируйте его:

```bash
python -m venv venv
source venv/bin/activate
```

Установите зависимости:

```bash
pip install -r backend/requirements.txt
```

Создайте файл `.env` в корне проекта и внесите свои данные. Для примера можно воспользоваться файлом `.env.example`:

```plaintext
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_HOST=db
DB_PORT=5432
DJANGO_SECRET_KEY=django-insecure-123
DJANGO_DEBUG=False
```

`DJANGO_SECRET_KEY` можно не заполнять вручную, так он будет сгенерирован автоматически.

Запустите оркестр:

```bash
sudo docker compose up
```

## Примеры запросов

Получить список котиков:

```http
GET /api/cats/
```

Добавить котика:

```http
POST /api/cats/
Content-Type: application/json

{
  'color': '#FFFFFF',
  'achievements': [],
  'image': 'Картинка в Base64',
  'name': 'Имя котика',
  'birth_year': 'Год рождения котика',
}
```

Удалить котика:

```http
DELETE /api/cats/{id котика}/
```

## Используемые технологии

| Тип        | Название   |
| ---------- | ---------- |
| Веб-сервер | Nginx      |
| Бэкенд     | Django     |
| Фронтенд   | React      |
| БД         | PostgreSQL |

## Автор

- [Никита Скрябин](https://github.com/vernette)
