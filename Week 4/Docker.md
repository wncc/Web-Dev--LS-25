# Dockerizing a Django App with PostgreSQL (Optional)

This guide explains step-by-step how to Dockerize a Django app using PostgreSQL as the database, with references to useful video tutorials.

---

## Recommended Video Tutorials

| Title                                      | Link                                                           |
| ------------------------------------------ | -------------------------------------------------------------- |
| Dockerizing Django with PostgreSQL         | [Watch here](https://youtu.be/37aNpE-9dD4?si=3OhXZ9goJ6I8f_Rb) |
| Dockerize Django App (in-depth)            | [Watch here](https://youtu.be/ol2jTRUYQtw?si=eeRqzSp61ntNrHkZ) |
| Django Deployment with Docker (Full Guide) | [Watch here](https://youtu.be/N0x_koFpoVs?si=WsufxaT4X-1ebzsR) |

---

## Project Structure Overview

```
django_project/
├── app/                      # Django app
├── project/                  # Django project (with settings.py)
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── .env
├── .dockerignore
└── manage.py
```

---

## Step 1: Create requirements.txt

Run this in your terminal:

```bash
pip freeze > requirements.txt
```

---

## Step 2: Create .env File

```env
POSTGRES_DB=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

Use these values in your `settings.py` when configuring your PostgreSQL database.

---

## Step 3: Update `settings.py` in Django

Replace the default `DATABASES` block with:

```python
import os

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ.get('POSTGRES_DB'),
        'USER': os.environ.get('POSTGRES_USER'),
        'PASSWORD': os.environ.get('POSTGRES_PASSWORD'),
        'HOST': os.environ.get('DB_HOST'),
        'PORT': os.environ.get('DB_PORT'),
    }
}
```

---

## Step 4: Create Dockerfile

```Dockerfile
# Use official Python image
FROM python:3.10-slim

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set work directory
WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --upgrade pip && pip install -r requirements.txt

# Copy the entire Django project
COPY . .

# Run the development server
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```

---

## Step 5: Create docker-compose.yml

```yaml
version: '3.9'

services:
  web:
    build: .
    command: python manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/app
    ports:
      - "8000:8000"
    env_file:
      - .env
    depends_on:
      - db

  db:
    image: postgres:14
    volumes:
      - postgres_data:/var/lib/postgresql/data/
    environment:
      POSTGRES_DB: ${POSTGRES_DB}
      POSTGRES_USER: ${POSTGRES_USER}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}

volumes:
  postgres_data:
```

---

## Step 6: Create .dockerignore

```
__pycache__/
*.pyc
*.pyo
*.db
.env
*.sqlite3
```

---

## Step 7: Build and Run the Project

```bash
docker-compose up --build
```

Django app runs on: [http://localhost:8000](http://localhost:8000)

---

## Step 8: Apply Migrations Inside Container

```bash
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
```

---

## Extra Tips

* Use `collectstatic` in production for static files.
* Use `gunicorn` instead of `runserver` for production environments.
* Ensure `ALLOWED_HOSTS` is set correctly in production.
* Always set `DEBUG=False` in production for security.

---

## Summary

You now have:

* A Django app container
* A PostgreSQL container
* Environment variables configured
* Docker Compose orchestrating both services

This setup is ideal for local development and easily extendable for cloud deployment.
