---
layout: post
title:  "URL Shortener with Django (Part 3) - Creating django app and model"
categories: Programming
tags: Python, Django
---
Now, Let us create a Django app. From your project's root directory run this command

```bash
$ django-admin startapp shortenersite
```

This will create a new folder 'shortenersite' inside our root directory which is actually a Django app. You can see the following files and folder inside shortenersite:
<ol>
 	<li>migrations - Contains database migration file.</li>
 	<li>admin.py - We will use this file to configure Django Admin settings for this app.</li>
 	<li>models.py - Contains the model (generally model.py deals with database.)</li>
 	<li>view.py - Used to create views.</li>
 	<li>tests.py - Contains the test suite for our app but we will not be using this file in our tutorial.</li>
</ol>
Now add this app to our project. Open up "urlshortener/settings.py" file and add 'shortenersite' to INSTALLED_APPS. So now the INSTALLED_APPS will look something like this.

[urlshortener/settings.py]

```python
# Application definition

INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'shortenersite',
)
[/code]
```

Now let us work in our models.py. Open up "shortenersite/models.py" and add the following code to it.

[shortenersite/models.py]

```python
from django.db import models

# Create your models here.
class Urls(models.Model):
    short_id = models.SlugField(max_length=6,primary_key=True)
    httpurl = models.URLField(max_length=200)
    pub_date = models.DateTimeField(auto_now=True)
    count = models.IntegerField(default=0)

def __str__(self):
    return self.httpurl
```

<b>What we just did?</b>
We created table named 'Urls' in our database with the following field:
<ol>
 	<li>short_id (it will store short URL id), (It is of max_length 6 and it is a primary key)</li>
 	<li>httpurl (it will store URL), (It is of max_length 200)</li>
 	<li>pub_date (It will store the date and time)</li>
 	<li>count (It will store the number of times the URL is visited)</li>
</ol>
Run this command to make changes to database.

```bash
$ python manage.py makemigrations
```
```bash
$ python manage.py migrate
```

We just updated our database. We are using sqlite3 which is set up by default for us. So, we do not need to configure anything regarding database settings for now, but if you want to use other database rather then sqlite3 then you can change DATABASES option in "urlshortener/settings.py".

Now let us add this model to Django admin.

But before that let us be sure that you do not have comment in the following line in "urlshortener/urls.py".

[urlshortener/urls.py]

```python
url(r'^admin/', include(admin.site.urls)),
```

Open your "shortenersite/admin.py" And add the following:

[shortenersite/admin.py]

```python
from django.contrib import admin
from shortenersite.models import Urls
# Register your models here.

class UrlsAdmin(admin.ModelAdmin):
    list_display = ('short_id','httpurl','pub_date', 'count')
    ordering = ('-pub_date',)

admin.site.register(Urls, UrlsAdmin) # Register the Urls model with UrlsAdmin options
```

Simply the above code registers the Urls model we created above to Django Admin.

Run the Django project with

```bash
$ python manage.py runserver
```

and Open up

```
http://localhost:8000/admin/
```

Enter your Login details i.e the credentials of superuser that you have created before. Now you should see something like this.

![django admin](/assets/post-images/2015/django_admin.png)

We have Urlss(Model name in plural form) under Shortenersite(App Name). I hope you understand this. Django admin is one of the beautiful feature i like most about Django. And i am sure you will also feel same about Django admin.

Open up Urlss and you can add Urls by clicking Add urls. You can see the fields like Short id, Httpurl and count that we have created. DateTime is added automatically so, you do not have to worry about it.

Alright, This is the end of the Part 3, and we have created app, models for our app and registered the model to see it in Django Admin.

Till now we have just done the Back-end, In the next two tutorials we will be working on Front-end. We will build web app from where user can input the URLs and will get the short URL for his URL.

Post Series: <br/>
Part 1: [Create a virtual environment and install Django](https://sudeepacharya.com.np/blog/2015/01/12/urlshortener-with-django-create-virtual-environment-install-django/)<br/>
Part 2: [Create a new project and make sure it works](https://sudeepacharya.com.np/blog/2015/01/13/urlshortener-with-django-creating-new-django-project/)<br/>
Part 3: [Create Django App, Model for our App and work with Django Admin](https://sudeepacharya.com.np/blog/2015/01/14/urlshortener-with-django-creating-app-model/)<br/>
Part 4: [Working with URLs and Views](https://sudeepacharya.com.np/blog/2015/01/15/urlshortener-with-django-urls-and-views/)<br/>
Part 5: [Working on Templates, Static files and finishing up](https://sudeepacharya.com.np/blog/2015/01/16/urlshortener-with-django-working-with-templates/)<br/>
