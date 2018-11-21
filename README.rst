.. _django-fsm: https://github.com/kmmbvnr/django-fsm

===============================
django-fsm-admin
===============================

Mixin and template tags to integrate django-fsm_
state transitions into the django admin.

Installation
------------
::

    $ pip install django-fsm-admin

Or from github:

::

    $ pip install -e git://github.com/xhens/django-fsm-admin.git#egg=django-fsm-admin

Usage
-----
1. Add ``fsm_admin`` to your INSTALLED_APPS

2. Ensure that you have "django.core.context_processors.request" in your TEMPLATE_CONTEXT_PROCESSORS in Django settings

3. In your ``admin.py`` file, use `FSMTransitionMixin` to add behaviour to your ModelAdmin.

::
    
    from fsm_admin.mixins import FSMTransitionMixin

    class YourModelAdmin(FSMTransitionMixin, admin.ModelAdmin):
        pass

        admin.site.register(YourModel, YourModelAdmin)

Try the example
---------------

::

    $ git clone git@github.com:xhens/django-fsm-admin.git
    $ cd django-fsm-admin
    $ mkvirtualenv fsm_admin
    $ pip install -r requirements.txt
    $ python fsm_admin/setup.py develop
    $ cd example
    $ ./manage.py syncdb
    $ ./manage.py runserver

