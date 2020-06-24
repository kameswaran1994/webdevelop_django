step1: 

Install python 3 and create venv using python3 -m venv foldername. Activate virtual env, source bin/activate



step 2:

use any IDE, Install django module. confirm using pythom3 -m django --version




step 3:

After install django, 

create a project using
#django-admin startproject webdevelop<projectname>

create startapp for many app purpose 
after creation of webdevelop project. You will get manage.py file

webdevelop:
    ---> demoapp
    ---> webdevelop
    manage.py

ls -ll --> manage.py #verify the directory

#manage.py startapp demoapp<projectname for many app)



step 4:

create directory under demoapp

demoapp --> templates --> demoapp --> hi.html

demoapp dir:

apps.py --> copy class name (Demoapp Config)

webdevelop:
setting.py --> add lines in Install app = [ 'demoapp.apps.Demoapp Config',]

demoapp dir:
views.py --> def hi(request):
    return render(request,'demoapp/hi.html')



step 5:

#Inform to urls.py

#create urls.py in demoapp dir:

from django.urls import path
from . import views

urlpatterns = [
    path('',views.hi,name=' home-page'),
] 



step 6:

# urls.py in webdevelop dir: add include in that file

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',include('demoapp.urls'))



step 7 :

# manage.py runserver
