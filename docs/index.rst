.. register_activate documentation master file, created by
   sphinx-quickstart on Mon May 16 16:04:57 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to register_activate's documentation!
=============================================

.. toctree::
   :maxdepth: 2

*Register_activate* is a simple, user-friendly django application for user sign up, email 
account verification and activation, login and logout. It 
is based on `Django's user model <https://docs.djangoproject.com/en/1.9/ref/contrib/auth/>`_ but have certain advantages
over the django user model: 

Features
--------
- Register_activate provides a complete user signup form, with username, password and email.
- Register_activate provides functions for password verification, user authentication and email verification and activation. 
- In register_activate, email becomes a requried field for registration. 
- Register_activate provides a clear and comfortable user-interface.
- Easy to use once you updated your project settings.py and urls.py

Installation
------------
Before installation, make sure that you have `Django <https://www.djangoproject.com/>`_ installed.

The easiest way is to use `pip <https://pypi.python.org/pypi/pip/>`_ installation

Install register_activate by running:

    ``pip install register_activate``
    
Configuration
------------
1. In your setting.py, import the module register_activate like this::

   ``import register_activate``

2. In your setting.py, get the absolut path the register_activate_dir (following BASE_DIR) like this::

   ``register_activate_dir=os.path.dirname(os.path.dirname(os.path.abspath(register_activate.__file__)))``
    
3. In your setting.py, add "register_activate" to your INSTALLED_APPS setting like this::

    ``INSTALLED_APPS = [
        ...
        'register_activate',
    ]``
    
4. In your setting.py, add the template path of register_activate to TEMPLATES by updating 'DIRS' like this::

    ``TEMPLATES = [
        {
         'BACKEND': 'django.template.backends.django.DjangoTemplates',
         'DIRS': [os.path.join(register_activate_dir,'register_activate/templates/register_activate')],
         'APP_DIRS': True,
         'OPTIONS': {
             'context_processors': [
                 'django.template.context_processors.debug',
                 'django.template.context_processors.request',
                 'django.contrib.auth.context_processors.auth',
                 'django.contrib.messages.context_processors.messages',
             ],
         },
        },
    ]``

5. In your setting.py, add the AUTHENTICATION_BACKENDS setting like this::

    ``AUTHENTICATION_BACKENDS=[
       'django.contrib.auth.backends.ModelBackend',
       'register_activate.email_auth.EmailBackend',
    ]``


6. In your project urls.py, include the polls URLconf like this::

    ``from django.conf.urls import url, include
    from django.contrib import admin
    urlpatterns = [
       ...
       url(r'^register_activate/',include('register_activate.urls')),
       url(r'^admin/', admin.site.urls),
   ]``
   

7. Run ``python manage.py migrate`` to create the models.

8. Run ``python manage.py runserver`` to start the server.

9. Visit http://127.0.0.1:8000/register_activate/signup to create an account.

10. After creating your account, your account is not activated yet.
    You will receive an email from a google account django.registeractivate@gmail.com 
    with an activation link. By clicking that link your account will be activated.
    You can change the from email to your own email address by go to 
    register_activate/views to your own account and password::
    fromaddr='django.registeractivate@gmail.com'
    username='django.registeractivate'
    password='django_register_activate'
    (You can use ``register_activate_dir=os.path.dirname(os.path.dirname(os.path.abspath(register_activate.__file__)))`` to find where this package is)

Contribute
----------

- Issue Tracker: https://github.com/JunyiJ/django-register-activate/tree/master/issues
- Source Code: https://github.com/JunyiJ/django-register-activate/

Support
-------

If you are having issues, please let me know.
jiaojunyi90@gmail.com

License
-------

The project is licensed under the BSD license.

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

