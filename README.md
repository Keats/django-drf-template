# django-drf-template
[![Requirements Status](https://requires.io/github/Keats/django-drf-template/requirements.png?branch=master)](https://requires.io/github/Keats/django-drf-template/requirements/?branch=master)

Project template for Django 1.7 + Django REST framework containing things I use and find useful.  
Part of it is based on [Two Scoops of Django template](https://github.com/twoscoops/django-twoscoops-project).  

## Features

It contains the following things: 

- [Django REST framework](http://www.django-rest-framework.org/): for writing your API
- [django-model-utils](https://django-model-utils.readthedocs.org/en/latest/): for things like TimestampedModel and other nice things for models
- [django-cors-headers](https://github.com/ottoyiu/django-cors-headers): automatically allows CORS on local dev and allows for a whitelist in production
- bcrypt: hash password with bcrypt instead of PBKDF2

There are also goodies on dev and test environments:

- [django-debug-toolbar](https://github.com/django-debug-toolbar/django-debug-toolbar): lots of information on request/response
- ipdb: pdb in ipython. Awesome
- [django-extensions](https://github.com/django-extensions/django-extensions): adds some useful management commands
- [coverage](http://nedbatchelder.com/code/coverage/): measures code coverage
- [factory-boy](https://factoryboy.readthedocs.org/en/latest/): my library of choice to create objects in tests, I go more into details on my [blog](http://vincent.is/using-factory-boy-or-model-mommy/)
- [flake8](http://flake8.readthedocs.org/): for code quality
- [mkdocs](http://www.mkdocs.org/): for documentation

## Install
You will need Postgres installed and the following ones (for ubuntu/debian, for others systems look in your package managers).

```bash
$ sudo apt-get install libpq-dev python-dev libffi-dev
```

Create your virtualenv (examples will use virtualenvwrapper), I will use the name myproject but use your own name.

```bash
$ mkdir myproject && cd myproject
$ mkvrirtualenv myproject
$ pip install django
$ django-admin.py startproject myproject --template=https://github.com/Keats/django-drf-template/archive/master.zip
$ cd myproject
$ pip install -r requirements/local.txt
$ python myproject/manage.py migrate
```

If you want, you can also add a pre-commit flake8 hook to ensure that commit respects it.

```bash
$ flake8 --install-hook
```

By default it will not stop commits because of warning, a quick look at .git/hooks/pre-commit shows that putting an environment variable of FLAKE8_STRICT will stop them.  


And with all that, you should be almost good to go. 
There are a few hardcoded temporary settings that you will want to replace, look for the string 'Ann Onymous' and you should find them.  
