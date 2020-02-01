---
layout: posts
title: Hackathon
---

To start a Django project, you need to:
- Create Django project and app
create project by     .../python.exe -m django startproject project name in terminal
<br/>
create app by         .../python.exe  manage.py startapp app name in terminal

- Create data model in models.py:
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/model.png)

- add app to INSTALLED_APPS

![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/installapp.png)


- create database
use this codes :
<br/>
c:\vscode\python\python.exe manage.py makemigrations
<br/>
c:\vscode\python\python.exe manage.py migrate
<br/>
hint: Any changes to the models.py require a migrate

<br/>
- Add MyData to the admin panel: in admin.py
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/admin.png)

- create super user for admin panel:<br/>
c:\vscode\python\python.exe manage.py createsuperuser

- start django development server<br/>
c:\vscode\python\python.exe manage.py runserver<br/>
- Goto http://127.0.0.1:8000/admin<br/>

- create templates folder inside django base dir (e.g., c:\git\FC98991\hackathon\mydemoproject1\templates)<br/>
- create form.html inside templates directory:
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/html.png)

- in settings.py add to TEMPLATES= ...         'DIRS' : [os.path.join(BASE_DIR, 'templates')],
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/path.png)

- in urls.py :
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/url.png)

- in views.py implement add_data:
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/views.png)

- Disable CSRF in setting.py:
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/csrf.png)

- in urls.py add /alldata:<br/>
    path('alldata/', views.get_all_data)

- in views.py implement get_all_data:<br/>
    def get_all_data(request):<br/>
        d = MyData.objects.all()<br/>
        return render(request, 'alldata.html', context={'data':d})<br/>


- create alldata.html in templates directory:
![an image alt text]({{ali6600alamdari.github.io}}/alialamdari.github.io/assets/images/html2.png)
 