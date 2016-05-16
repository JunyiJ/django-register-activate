=====
Register-Activate
=====

Register-activate is a simple Django app to conduct sign up, custom user email 
account verification and activation, login and logout functions. This app modifies django'
User model to realize the registering and activation process together with database.

Detailed documentation is in the "docs" directory.

Quick start
-----------
1. In your setting.py, import the module register_activate like this::
2. In your setting.py, get the absolut path the register_activate_dir (following BASE_DIR) like this::
    register_activate_dir=os.path.dirname(os.path.dirname(os.path.abspath(register_activate.__file__)))
3. In your setting.py, add "register_activate" to your INSTALLED_APPS setting like this::

    INSTALLED_APPS = [
        ...
        'register_activate',
    ]
4. In your setting.py, add the template path of register_activate to TEMPLATES by updating 'DIRS' like this:
    TEMPLATES = [
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
    ]

5. In your setting.py, add the AUTHENTICATION_BACKENDS setting like this::
    AUTHENTICATION_BACKENDS=[
    'django.contrib.auth.backends.ModelBackend',
    'register_activate.email_auth.EmailBackend',
    ]


6. In your project urls.py, include the polls URLconf like this::
    from django.conf.urls import url, include
    from django.contrib import admin
    urlpatterns = [
    ...
    url(r'^register_activate/',include('register_activate.urls')),
    url(r'^admin/', admin.site.urls),
]

7. Run `python manage.py migrate` to create the models.

8. Run `python manage.py runserver` to start the server.

8. Visit http://127.0.0.1:8000/register_activate/signup to create an account.

9. After creating your account, your account is not activated yet.
    You will receive an email from a google account django.registeractivate@gmail.com 
    with an activation link. By clicking that link your account will be activated.
    You can change the from email to your own email address by go to 
    register_activate/views to your own account and password::
    fromaddr='django.registeractivate@gmail.com'
    username='django.registeractivate'
    password='django_register_activate'
    (You can use register_activate_dir=os.path.dirname(os.path.dirname(os.path.abspath(register_activate.__file__))) to find where this package is)
