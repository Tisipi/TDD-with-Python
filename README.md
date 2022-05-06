# TTD-with-Python

I used this repository while reading the book [Test-Driven Development with Python](https://learning.oreilly.com/library/view/test-driven-development-with/9781491958698/), 2nd Edition, by **Harry J.W. Percival**.

If you need help with Django take a look at the [Django Girls tutorial](https://tutorial.djangogirls.org/en/) or the [official v1.11 tutorial](https://docs.djangoproject.com/en/1.11/intro/tutorial01/). Please note: This is an old **unsafe** version!


## Windows 10 Installation
Install *geckodriver.exe* in Python36-32\Scripts directory.

Create python *virtualenv* in directory python-tdd-book:
```
pip install virtualenv
py -3.6 -m venv virtualenv

# To activate virtualenv:
virtualenv\Scripts\activate

# To deactivate virtualenv:
deactivate
```

## Linux Installation (Mint, Manjaro)
Install geckodriver in /usr/local/bin.

Create python *virtualenv* in directory python-tdd-book:
```
sudo apt-get install python3-venv
python3.6 -m venv virtualenv

# To activate virtualenv:
source virtualenv/bin/activate

#To deactivate virtualenv:
deactivate
```

## Selenium and Django

Install *Django* and *Selenium* in virtualenv:
```
pip install "django<1.12" "selenium<4"
```

In case of problems install specific versions used in book:
```
pip install django==1.11.3
pip install selenium==3.9.0
```

Create a Django project called superlists (note the "." at the end):
```
# On windows:
python virtualenv\Scripts\django-admin.py startproject superlists .
# On Linux:
django-admin.py startproject superlists .
```

To run Django’s development server:  
`python manage.py runserver`    

**Update 2022**:  
Import error when using Python 3.10.2:  
ImportError: cannot import name 'Iterator' from 'collections' (/usr/lib/python3.10/collections/__init__.py)  

Workaround is to use an older version like Python 3.6:  
- Install python3.6  
- Install *virtualenv* which allows to specify a specific python version in your virtual environment:  
`pip install virtualenv`  
- Create virtual environment with Python 3.6:  
`virtualenv virtualenv -p python3.6`
  
  
## Django App

Start an App called "lists":  
`python manage.py startapp lists`

Don't forget to register the lists App in superlists/settings.py:
```
INSTALLED_APPS = [
	...
    'lists',
]
```

Invoke Django test runner (to run unit tests):  
`python manage.py test`
You can also add the App name:
`python manage.py test lists`


## Django Migration
When you change something in the Django model (for example change or add a field), the database tables that store these models need to be changed too. A Django migration propagates these changes in the model into the database schema.

```
python manage.py makemigrations
```

## Django Database Creation
Actually create the database after the Django migration.
```
python manage.py migrate
```

The default database is SQLite. It is just a file located in your base directory:
```
<your Django project>/settings.py:
DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.sqlite3",
        "NAME": os.path.join(BASE_DIR, "db.sqlite3"),
    }
}
```
You can simply delete and recreate it:
```
rm db.sqlite3
python manage.py migrate --noinput
```

## Overview Files

├── db.sqlite3  
├── functional_tests.py           <<< Functional tests  
├── geckodriver.log  
├── lists                         <<< Directory of lists App  
│   ├── admin.py  
│   ├── apps.py  
│   ├── __init__.py  
│   ├── migrations                <<< Directory containing Django migrations  
│   ├── models.py                 <<< Django models  
│   ├── templates                 <<< HTML template directory  
│   ├── tests.py                  <<< Unittests of lists App  
│   └── views.py                  <<< Django views  
├── manage.py                     <<< Django's management script  
├── README.md  
├── superlists                    <<< Django's main project directory  
│   ├── __init__.py  
│   ├── settings.py               <<< register the lists App  
│   ├── urls.py                   <<< URL patterns mapping URLs to views  
│   └── wsgi.py  
└── virtualenv  
    ├── bin  
    ├── lib  
    ├── pyvenv.cfg  
    └── selenium  
    
