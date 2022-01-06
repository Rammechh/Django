# Django
Learning

<!--ts-->
Table of Contents
=================
  + [Configurations](#Configurations)
  + [Create Project](#Create_Project)
  + [Hello world](#Hello_World)
  + [Django Template Language](#Django_Template_Language)
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

Django_Template_Language
==================
 + Instead of creating static html pages. django provides tempates for creating dynamic pages
 + -> In firstproject -> create folder templates -> create file home.html
#### home.html
<pre>
<h5!>Hello World!!!</h5>
</pre>
 + in settings.py > in templates section 
<pre>
DIRS : [os.path.join(BASE_DIR, 'templates')],
</pre>

#### In calc -> views.py
<pre>
def home(request):
    #return HttpResponse("Hello World")
    return render(request,'home.html', {'name': 'Ram'})
</pre>

#### In templates -> home.html
<pre>
<h1!>Hello {{name}}!!!</h1>
</pre>

 + create a base page common for all pages
 + templates -> create base.html
 
#### base.heml
<pre>

</pre>
