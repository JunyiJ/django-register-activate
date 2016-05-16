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

To get up and running quickly, consult :ref:`the quick start guide
<quickstart>`, which describes the steps necessary to configure
``django-register-activate``. For more detailed
information, read through the
documentation listed below.


.. toctree::
   :caption: Installation and configuration
   :maxdepth: 1

   install
   quickstart

Installation
------------
Before installation, make sure that you have `Django <https://www.djangoproject.com/>`_ installed.

The easiest way is to use `pip <https://pypi.python.org/pypi/pip/>`_ installation

Install register_activate by running:

    ``pip install register_activate``

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

