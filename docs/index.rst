=====================================================
GET STARTED WITH DJANGO PART 1: BUILD A PORTFOLIO APP
=====================================================

Overview
========

Tutorial
--------

This project is based upon the Django tutorial in the following location:

   https://realpython.com/get-started-with-django-1/

The tutorial is pretty limited, but a good introduction into building Django Apps, the
admin site and using the shell to analyse the model characteristics.

Warning:
--------

In a similar manner to Flask, there is a default value for SECRET_KEY should be changed to some 
random bytes in production.

    python -c 'import os; print(os.urandom(16))'

    b'_5#y2L"F4Q8z\n\xec]/'


Installation Guide
==================

Manual Installation
-------------------

- If it exists, remove the venv virtual environment directory using the following:
    - ``rm -rf venv      (mac)``
    - ``rmdir venv /s    (windows)``
- Recreate the virtual environment directory using the following:
    - Mac:
        - ``virtualenv --no-site-packages -p python3 venv``
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``pip install -r requirements.txt``
    - Windows:
        - ``virtualenv --no-site-packages -p python venv``
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``pip install -r requirements.txt``
- Make model migrations:
    - Mac:
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``python manage.py makemigrations personal_portfolio``
        - ``python manage.py makemigrations projects``
        - ``python manage.py makemigrations blog``
        - ``python manage.py check``
        - ``python manage.py migrate``
    - Windows:
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``python manage.py makemigrations personal_portfoliop``
        - ``python manage.py makemigrations projects``
        - ``python manage.py makemigrations blog``
        - ``python manage.py check``
        - ``python manage.py migrate``
- You can setup a superuser account for the admin part of the Django polls app using the following:
    - Mac:
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``python manage.py createsuperuser``
    - Windows:
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``python manage.py createsuperuser``
- Within the tutorial, the projects and blog were setup using the command line tool.   This isn't 
  necessary for the website to work, but makes it more appealing.   Please see the following link:

    https://realpython.com/get-started-with-django-1/

MakeFile Installation (Mac, Linux or Unix)
------------------------------------------   
This project was written and tested on a mac and it has not been tested on Linux.

- To get help:
    - Run 'make' to get help on this project.
- It is sensible to reset the virtual environment so that it reflects the current requirements.txt file:
    - Run 'make venv' to build the virtual environment from requirements.txt.
- The first time that this project is installed, or when model changes are made:
    - Run 'make venv-migrations' to migrate models.
- To create a superuser for the admin site:
    - Run 'make venv-admin'
- Within the tutorial, the projects and blog were setup using the command line tool.   This isn't 
  necessary for the website to work, but makes it more appealing.   Please see the following link:

    https://realpython.com/get-started-with-django-1/
    
Running the Application
=======================

Manual
------

- To run the app using the normal environment:
    - Mac:
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``python manage.py runserver``
    - Windows:
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``python manage.py runserver``
    - Please note that the standard localhost is not a valid website that produces html.   You will need to use:
        - ``http://localhost/projects/``
        - ``http://localhost/blog/``
        - ``http://localhost/admin/``

MakeFile
--------

- To run the Django site:
    - Run 'make venv-run'

Testing the Application
=======================

DANGER:   Currently there are no tests associated with this project.   They were not part of the tutorial.

Test Coding Standards
=====================

Manual
------

- Test the code within the personal_portfolio directory:
    - Mac:
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``pycodestyle --statistics ./personal_portfolio/*.py``
    - Windows:
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``pycodestyle --statistics filename.py``
- Test the code within the projects directory:
    - Mac:
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``pycodestyle --statistics ./projects/*.py``
    - Windows:
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``pycodestyle --statistics filename.py``
- Test the code within the blog directory:
    - Mac:
        - ``deactivate or source deactivate``
        - ``source venv/bin/activate``
        - ``pycodestyle --statistics ./blog/*.py``
    - Windows:
        - ``deactivate or source deactivate``
        - ``.\venv\Scripts\activate``
        - ``pycodestyle --statistics filename.py``

MakeFile
--------

- Test the code within the personal_portfolio directory:
    - Run 'make pystat-pp'

- Test the code within the projects directory:
    - Run 'make pystat-projects'

- Test the code within the blog directory:
    - Run 'make pystat-blog'

Cleanup
=======

Manual
------

- The project can become cluttered with a number of directories and files.   The following can be used to clean them up:
    - Mac:
        - ``rm -rf ./personal_portfolio/__pycache__*``
        - ``rm -rf ./projects/__pycache__*``
        - ``rm -rf ./projects/migrations/__pycache__*``
        - ``rm -rf ./blog/__pycache__*``
        - ``rm -rf ./blog/migrations/__pycache__*``
    - Windows:
        - ``rmdir /S personal_portfolio\__pycache__``
        - ``rmdir /S projects\__pycache__``
        - ``rmdir /S projects\migrations\__pycache__``
        - ``rmdir /S blog\__pycache__``
        - ``rmdir /S blog\migrations\__pycache__``

- If you wish to remove the venv virtual environment directory:
    - ``rm -rf venv``
    - ``rmdir /S venv``

MakeFile
--------

- To clean files such as pytest_cache, dist etc:
    - Run 'make venv-clean'

- If you wish to remove the venv virtual environment directory:
    - Run 'make clean-venv'

Distribution
============