- # Table of Contents
    - i. [[Django Project]]
    - ii.
- 
- # Basics
    - ## Creating a Django Project
        - ### Set up Dev Environment
            - ```shell
$ mkdir rp-portfolio
$ cd rp-portfolio
$ python3 -m venv venv

// Activate virtual environment
$ source venv/bin/activate

// In windows command prompt
C:\> venv\Scripts\activate.bat

// Shell - install django
(venv) $ pip install Django

// Create a Django Project
$ django-admin startproject personal_portfolio

```
        - # Structure of Django project
        - ```shell
Structure of Directory

rp-portfolio/
│
├── personal_portfolio/
│   ├── personal_portfolio/
│   │   ├── __init__.py
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   │
│   └── manage.py
│
└── venv/

Move directory

$ mv personal_portfolio/manage.py ./
$ mv personal_portfolio/personal_portfolio/* personal_portfolio
$ rm -r personal_portfolio/personal_portfolio/



rp-portfolio/
│
├── personal_portfolio/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── venv/
│
└── manage.py

// Start server
$ python manage.py runserver```
    - ## Django Application Directories
        - **__init__.py** tells Python to treat the directory as a Python package.
        - **admin.py** contains settings for the Django admin pages.
        - **apps.py** contains settings for the application configuration.
        - **models.py** contains a series of classes that Django’s ORM converts to database tables.
        - **tests.py** contains test classes.
        - **views.py** contains functions and classes that handle what data is displayed in the HTML templates
    - 
- 
