# newsletter

A newsletter app where a user can subscribe to various newsletters simultaneously and will receive the issues over their emails regularly.

### Requirements:

- Python 3+ version
- Pipenv

### Installtion

```
pipenv install celery
pipenv install python-dotenv
pipenv install psycopg2-binary
```

### Create a `.env` file

Create a .envfile and assign the secrets.

```
CDEMAIL_HOST=$CDEMAIL_HOST
EMAIL_USE_TLS=True
EMAIL_PORT=$EMAIL_PORT
EMAIL_HOST_USER=$EMAIL_HOST_USER
EMAIL_HOST_PASSWORD=$EMAIL_HOST_PASSWORD
CELERY_BROKER_URL="pyamqp://localhost:5672"
SECRET_KEY=$SECRET_KEY
DATABASE_URL=postgres://postgres:password@localhost:5432/postgres
POSTGRES_PASSWORD=password
APP_DOMAIN=*
DEBUG=True
```

### Run the Project

- Run docker-compose to start the dependencies:
  `docker-compose up`
- Generate migrations for our models:
  `python manage.py makemigrations`
- To apply generated migrations to database run:
  `python manage.py migrate`
- To create a user for login run the following command and provide your details:
  `python manage.py createsuperuser`
- Run the following command to run the app and open http://127.0.0.1:8000/admin to open Django Admin :
  `python manage.py runserver`
- Run celery:
  `celery -A newsletter_site worker --loglevel=INFO`
