

# PostgreSQL Connection with Django – Complete Guide

## Step 1: Install PostgreSQL

### Download and Install PostgreSQL
- Visit: https://www.postgresql.org/download/
- Download for your OS (Windows/Mac/Linux).
- Install with default settings.
- Set a **password** for the default user `postgres` (you will use this in Django settings).

### Install `pgAdmin`
- It’s a GUI tool to manage PostgreSQL databases.

## Step 2: Create Database

1. Open **pgAdmin** or use SQL Shell.
2. Run the following command in SQL Shell or pgAdmin query tool:

```sql
CREATE DATABASE ytclone;
```

- You can replace `ytclone` with your project name.

## Step 3: Install PostgreSQL Adapter for Django

Run this command in your Django environment:

```bash
pip install psycopg2
```

If it fails, use the binary version:

```bash
pip install psycopg2-binary
```

## Step 4: Configure Django to use PostgreSQL

Open `settings.py` in your Django project folder.

Replace the default database configuration:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'ytclone',
        'USER': 'postgres',
        'PASSWORD': 'your_password_here',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

## Step 5: Apply Migrations

Run migrations to create tables in the PostgreSQL database:

```bash
python manage.py makemigrations
python manage.py migrate
```

## Step 6: Create Superuser (Optional but Recommended)

```bash
python manage.py createsuperuser
```

## Step 7: Run Django Server

```bash
python manage.py runserver
```

## Step 8: Verify PostgreSQL Connection

- Log in to **pgAdmin**.
- Open the `ytclone` database.
- Check **Schemas → Tables**.
- You should see tables like:
  - `auth_user`
  - `api_video`
  - `django_migrations`
  - and others

## Notes

- PostgreSQL is more robust and production-ready compared to SQLite.
- Use strong passwords and proper security when deploying.

## Common Errors & Solutions

| Error                                          | Solution                                  |
|------------------------------------------------|--------------------------------------------|
| `psycopg2.OperationalError`                    | Check DB name, password, port, and user.  |
| `FATAL: password authentication failed`        | Wrong password/user — fix in settings.    |
| Cannot connect to server (Connection refused)  | PostgreSQL service not running — start it.|

## Complete Example `settings.py` Database Section

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'ytclone',
        'USER': 'postgres',
        'PASSWORD': '12345',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

## Resources
For a comprehensive understanding of this concept, refer to the following resource.
### In Hindi
- [How to connect PostgreSQL with Django (Hindi)](https://youtu.be/5EY6JFptZgw?si=i3otQPYFDtKCiqO2)

### In English
- [Django with PostgreSQL Setup](https://youtu.be/auGKVnywcIE?si=GaoyjwFV3a8t7RLd)
- [PostgreSQL Basics](https://youtu.be/qw--VYLpxG4?si=vluyiMTVhyKiJ328)
- [Beginner PostgreSQL Tutorial](https://youtu.be/SpfIwlAYaKk?si=oMQqT8gUl4l-Ptq7)

### Dive Deeper
- [Advanced PostgreSQL Playlist](https://www.youtube.com/playlist?list=PLSU32T6nmU25qowhWMM4ZUDUbSvsV78GG)
