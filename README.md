# Django Tracker App

A simple deployable task tracker built with Django.

## Run locally

```bash
python -m venv venv
# activate your virtual environment
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Open http://127.0.0.1:8000/

## Deploy

This project is ready for Render.

Environment variables:
- `SECRET_KEY`
- `DEBUG` (set to `0` on production)
- `DATABASE_URL` (optional; if set, it will be used instead of SQLite)

Build command:
```bash
pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate
```

Start command:
```bash
gunicorn tracker_project.wsgi:application
```
