---
layout: post
title:  "URL Shortener with Django (Part 2) - Creating a new django project"
categories: Programming
tags: Python, Django
---
Creating a Django project

```bash
$ django-admin startproject urlshortener
```

Now you will see new directory "urlshortener". Now our folder structure looks something like:

```bash
tutorial/
    - py3env
    - urlshortener
        - urlshortener
            = __init__.py
            = settings.py
            = urls.py
            = wsgi.py
        = manage.py
```

(Folder is denoted as - and file is denoted by =)

<span style="color: #ff0000;">The folder "urlshortener" just inside "tutorial" is our root directory. And we will work inside this root directory from now on wards.</span>

Let us review what are these files. "urlshortener" inside tutorial folder is Django project directory, you can rename it to whatever you like or leave it as it is. From now on wards we will be working inside this directory.

And inside "urlshortener" folder you will see "urlshortener" folder which contains our project files and we have "manage.py".

For now let us leave "manage.py" and look into the "urlshortener/urlshortener" folder. You can see there are following files:
<ol>
 	<li>__init__.py - It is the file used to make python treat that this is a directory containing packages.</li>
 	<li>settings.py - Contains the settings for our Django project.</li>
 	<li>urls.py - Use to handle url routing.</li>
 	<li>wsgi - WSGI config for our project</li>
</ol>
You must be in hurry to see your app running. So, let us run it now.

Type the following command from your root directory (i.e the "urlshortner" where manage.py is located)

```bash
$ python manage.py syncdb
```

You will be asked to create superuser, create it because we gonna need it after some time.

![python django syncdb](/assets/post-images/2015/python_django_syncdb.png)

Now enter the following command:

```bash
$ python manage.py runserver
```

Open your favorite Browser(mine is Google Chrome) and navigate to

<b>http://localhost:8000</b> - 8000 port is default for django, you can also run it in another port by using

```bash
$ python manage.py runserver 5000
```

So now our URL will be <b>http://localhost:5000</b>

If you can see web page telling you "It worked!, Congratulations" then everything up to now is working fine.

Alright, This is the end of the Part 2. In this part you created Django project and ran it and it worked.

Post Series: <br/>
Part 1: [Create a virtual environment and install Django](https://sudeepacharya.com.np/blog/2015/01/12/urlshortener-with-django-create-virtual-environment-install-django/)<br/>
Part 2: [Create a new project and make sure it works](https://sudeepacharya.com.np/blog/2015/01/13/urlshortener-with-django-creating-new-django-project/)<br/>
Part 3: [Create Django App, Model for our App and work with Django Admin](https://sudeepacharya.com.np/blog/2015/01/14/urlshortener-with-django-creating-app-model/)<br/>
Part 4: [Working with URLs and Views](https://sudeepacharya.com.np/blog/2015/01/15/urlshortener-with-django-urls-and-views/)<br/>
Part 5: [Working on Templates, Static files and finishing up](https://sudeepacharya.com.np/blog/2015/01/16/urlshortener-with-django-working-with-templates/)<br/>
