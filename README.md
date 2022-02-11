# TTD-with-Python

I used this repository while reading the book [Test-Driven Development with Python](https://learning.oreilly.com/library/view/test-driven-development-with/9781491958698/), 2nd Edition, by **Harry J.W. Percival**.


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

## Linux Mint Installation
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

Create a Django project (note the "." at the end):
```
# On windows:
python virtualenv\Scripts\django-admin.py startproject superlists .
# On Linux:
django-admin.py startproject superlists .
```

To run Django’s development server:  
`python manage.py runserver`


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

Invoke Django test runner:  
`python manage.py test`

