# TTD-with-Python
Test-Driven Development with Python

I used this repository while reading the book **Test-Driven Development with Python**, 2nd Edition, by **Harry J.W. Percival**.


## Notes/Help

### Windows 10 Installation
Install *geckodriver.exe* in Python36-32\Scripts directory.

Create python *virtualenv* in directory python-tdd-book:
- pip install virtualenv
- py -3.6 -m venv virtualenv
- To activate virtualenv:  
  virtualenv\Scripts\activate  
- To deactivate virtualenv:  
  deactivate  

Install *Django* and *Selenium* in virtualenv:  
>pip install "django<1.12" "selenium<4"

Create a Django project (note the "." at the end):  
>python virtualenv\Scripts\django-admin.py startproject superlists .

To run Django’s development server:  
>python manage.py runserver  


### Linux Mint Installation
Install geckodriver in /usr/local/bin

Create python *virtualenv* in directory python-tdd-book:
- sudo apt-get install python3-venv
- python3 -m venv virtualenv
- To activate virtualenv:  
  source virtualenv/bin/activate
- To deactivate virtualenv:  
  deactivate  