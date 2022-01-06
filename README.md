# Django
Learning

<!--ts-->
Table of Contents
=================
  + [Configurations](#Configurations)
  + [Create Project](#Create_Project)
  + [Hello world](#Hello_World)
<!--te-->

Configurations
============
 + [Install Python](https://www.python.org/)
 + To work on  virtual environment
    * cmd commands -> pip install virtualenvwrapper-win
    * -> mkvirtualenv test (test - anyname)
 + install Django
    * -> pip install django (check version django-admin --version)
 
Create_Project
=================
### Create working directory
 + -> mkdir projects (make directory)
 + -> cd projects (change directory)

### New project and sample run
 + [Documentation](https://docs.djangoproject.com/en/4.0/intro/tutorial01/)
 + -> django-admin startproject firstproject (firstproject - anyname)
 + -> dir firstproject
 + -> python manage.py runserver (py provides the live server to run projects - IP generated)
 
Hello_World
================
 + use Visual studio code IDE (Integreated Development Environment)
 + Open folder (projects -> firstproject) created already.
 + Go to Terminal check -> django --version if not installed -> pip install django
 + -> workon test
 + Inside firstproject -> python manage.py startapp calc (new project created)
 + Inside calc -> create newfile urls.py
 
#### In calc -> urls.py
<pre>
from django import path
from . import views
urlpatterns = [path('', views.home, name = 'home')]
</pre>

#### In calc -> views.py
<pre>
from django import HttpResponse
def home(request):
  return HttpResponse("Hello World")
</pre>

#### In firstproject -> urls.py
<pre>
from django.urls import path, include
urlpatterns = [path('', include('calc.urls'))]
</pre>
 + --> python manage.py runserver and check the webpage showing Hello World
