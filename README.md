# Project steps

- Create and activate Python virtual environment
```sh
python -m venv .venv
source .venv/bin/activate
```
- Install Django
```sh
pip install -r requirements.txt
```
- Create Django project:
```sh
django-admin startproject momentum_trader
# This creates the overall Django project structure and its configuration files ("momentum_trader", "manage.py").
# The "manage.py" file sets up the environment to run Django commands on the command line:
# - python manage.py runserver
# - python manage.py startapp "app_name"
# - python manage.py migrate
# - python manage.py makemigrations
```
- Move `momentum_trader` directory and `manage.py` file to the main directory folder
- Run server:
```sh
python manage.py runserver
# This starts Django's development web server, allowing us to run and test your web application locally in a browser.
```
- Apply Django migrations to our database:
```sh
python manage.py migrate
# This creates the db.sqlite3 file (that stores the SQLite database) using the configuration from `momentum_trader/settings.py`.
```
- Run server again:
```sh
python manage.py runserver
```
- Visit our server at the provided link (e.g. http://127.0.0.1:8000/)
- Create two apps within our project:
```sh
django-admin startapp portfolio # or: python manage.py startapp portfolio
django-admin startapp trading # or: python manage.py startapp trading
# This creates individual Django apps that represent the respective tables that we want to define in our database.
```
- Add apps (`portfolio` and `trading`) in the list `INSTALLED_APPS` in `momentum_trader/settings.py` to officially register the apps within our project.
- Generate a Django migration files:
```sh
python manage.py makemigrations
# This creates the "migrations" directory inside "portfolio" and "trading" containing a file "0001_initial.py" that specifies the database table structure as defined in "portfolio/models.py" and "trading/models.py".
```
- Create tables in SQLite database:
```sh
python manage.py migrate
# This creates the SQLite tables. Each app ("portfolio" and "trading") has its own table structure specified in its respective "migrations/0001_initial.py" file used by Django to create SQLite tables.
```




# Project directory structure

`momentum_trader/`: holds the overall Django project structure.
`manage.py`: sets up the environment to run Django commands.
`portfolio/`: portfolio app
`trading/`: trading app
`db.sqlite3`: contains the database



# Commands

```sh
django-admin startproject "project-name"
python manage.py startapp "app-name"
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```