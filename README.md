# Social Network

A Django web app for posting updates, following other users, and interacting with a feed — similar to Twitter.

Built with Python, Django, HTML, CSS, and JavaScript. Includes user profiles, likes, comments, saved posts, and image uploads.

Project walkthrough: [YouTube video](https://www.youtube.com/watch?v=d4_sidaZUZY)

## Features

- Sign up, log in, and log out
- Create, edit, and delete posts (text and images)
- Like and comment on posts
- Save posts to view later
- Follow and unfollow users
- User profiles with bio, profile picture, and cover image
- Feed filtered to people you follow
- User suggestions on the home page
- Paginated post feed

## Tech stack

| Layer | Tools |
|-------|-------|
| Backend | Django 4.2, Python |
| Frontend | HTML, CSS, JavaScript |
| Database | SQLite (local), PostgreSQL (production) |
| Deployment | Gunicorn, WhiteNoise, Render |

## Project structure

```
Social_networking/
├── network/              # Main Django app (models, views, templates, static files)
├── project4/             # Django project settings and URLs
├── manage.py
├── requirements.txt
├── build.sh              # Render build script
├── Procfile              # Gunicorn entry point
└── .env.example          # Environment variable template
```

## Setup

Clone the repo:

```bash
git clone https://github.com/shubhamsingh0202/Social_networking.git
cd Social_networking
```

Create a virtual environment and install dependencies:

```bash
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS/Linux

pip install -r requirements.txt
```

Copy the example env file and adjust values as needed:

```bash
cp .env.example .env
```

For local development, SQLite is used by default. Run migrations and start the server:

```bash
python manage.py migrate
python manage.py runserver
```

Open `http://127.0.0.1:8000` in your browser.

## Environment variables

| Variable | Description |
|----------|-------------|
| `SECRET_KEY` | Django secret key |
| `DEBUG` | Set to `True` for local dev, `False` in production |
| `ALLOWED_HOSTS` | Comma-separated list of allowed hostnames |
| `DATABASE_URL` | PostgreSQL connection string (optional locally) |

See `.env.example` for a starting template.

## Deployment

The app is set up for [Render](https://render.com/) with `build.sh` and a `Procfile`. Production uses PostgreSQL via `DATABASE_URL`, Gunicorn as the WSGI server, and WhiteNoise for static files.

## License

MIT
