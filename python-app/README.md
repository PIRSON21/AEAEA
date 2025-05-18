# FastAPI Feedback API

Контактная форма с сохранением заявок в MongoDB. Сделано на FastAPI.

---

## 📁 Структура проекта

```
python-app/
│
├── app/
│   ├── __init__.py
│   ├── main.py              # Точка входа в приложение
│   ├── models/
│   │   └── feedback.py      # Pydantic-модель запроса
│   ├── routes/
│   │   └── feedback.py      # Роут POST /feedback
│   └── database.py          # Подключение к MongoDB
│
├── .env                     # Настройки окружения
├── template.env             # Пример настройки окружения
├── .gitignore               # Игнор файлов внутри python-app
├── requirements.txt         # Зависимости
└── README.md                # Этот файл
```

---

## ⚙️ Установка

### 1. Клонируй репозиторий и перейди в папку:

```bash
git clone <url>
cd python-app
```

### 2. Создай и активируй виртуальное окружение:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Установи зависимости:

```bash
pip install -r requirements.txt
```

### 4. Настрой `.env`

Создай файл `.env` по примеру из `template.env` в корне `python-app/`.

---

## Запуск приложения

```bash
uvicorn app.main:app --reload
```

### Приложение будет доступно по адресу:
```
http://127.0.0.1:8000
```

---

## Пример запроса

### `POST /feedback`

```json
{
  "name": "Егор",
  "phone": "+7 (999) 123-45-67",
  "email": "egor@example.com",
  "subject": "Хочу сотрудничать!",
  "message": "Привет! Интересует ваш продукт."
}
```

---

##  Ответ (успех)

```json
{
    "status": "success",
    "message": "Спасибо за сообщение!"
}
```

---

## 📌 Зависимости

- [`FastAPI`](https://fastapi.tiangolo.com/)
- [`Uvicorn`](https://www.uvicorn.org/)
- [`Motor`](https://motor.readthedocs.io/) (async MongoDB)
- [`python-dotenv`](https://saurabh-kumar.com/python-dotenv/)
