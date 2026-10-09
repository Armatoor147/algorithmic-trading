Project steps:
- Create Python virtual environment
- Install Django
- Create Django project:
```sh
django-admin startproject momentum_trader
```
- Move `momentum_trader` directory and `manage.py` file to the main directory folder
- Run server:
```sh
python manage.py runserver
```
- Apply Django migrations to our database:
```sh
python manage.py migrate
```
- Run server again:
```sh
python manage.py runserver
```
- Visit our server at the provided link (e.g. http://127.0.0.1:8000/)
- Create two apps within our project:
```sh
django-admin startapp portfolio
django-admin startapp trading
```