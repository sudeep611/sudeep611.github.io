---
layout: post
title:  "URL Shortener with Django (Part 1) - Creating virtual environment and installing Django"
categories: Programming
tags: Python, Django
---

I finally got the time to write a Django tutorial. In this tutorial we are building URL Shortener. If you are confused with what we are building then we are building something similar to (<a href="http://bit.ly">bit.ly</a>) or (<a href="http://goo.gl">goo.gl</a>).

We are building the app that will make a shorter URL of a longer URL. (Example) Normally the shorter URL will be <span style="text-decoration: underline;">localhost:8000/4hh5kr</span> for <span style="text-decoration: underline;">www.facebook.com</span>

I am using Django <strong>1.7.1</strong> with Python <strong>3.3.2+</strong>. Don't worry if you have different version of Django because we will set up our virtual environment and install latest version of Django. But be sure you do have Python 3+ because installing Python will not be covered in this tutorial.

I assume that you have completed <a title="Official Django tutorial" href="https://docs.djangoproject.com/en/1.7/intro/tutorial01/">Writing your first Django app</a>. It is not really essential to complete this tutorial but it is highly recommended that you complete this tutorial before we begin. It will give you a lot of knowledge that will be useful in this tutorial.

You can also get the source code of this app in <a href="https://github.com/sudeep611/django_urlshortener">Github</a>(django_urlshortener).

Well let's start to build our URL Shortener then.

<h2>Create a virtual environment and install Django</h2>
Let us start by creating a virtual environment and installing Django. So, open up your Terminal and follow the instruction below.

Create a new folder for our project.

```bash
$ mkdir tutorial
```

Go inside the tutorial folder (folder we just created)

```bash
$ cd tutorial
```

Create virtual environment with python 3.

```bash
$ virtualenv -p /usr/bin/python3 py3env
```

Activate our virtual environment py3env.

```bash
$ source py3env/bin/activate
```

(Note: To deactivate it you can just use "deactivate" but now don't deactivate it.)

Run the following command to install Django:

```bash
$ pip install Django==1.7.1
```

Depending on your Internet speed, it may take some minute or less than a minute.

After done, let us check that Django is really installed.

To check the version of Django installed, enter the following command:

```bash
$ python -c 'import django; print(django.get_version())'
```

You must see something similar to the following:

![check Django version](/assets/post-images/2015/check_django_version.png)

So, this is the end of the first part. We set up our virtual environment and installed Django. Now you are ready to move to next part.

<span style="color: #ff0000;">Before moving to Part 2, from now whenever you follow this tutorial don't forget to activate virtual environment (py3env) or things may go little wired.</span>



Post Series: <br/>
Part 1: [Create a virtual environment and install Django](https://sudeepacharya.com.np/blog/2015/01/12/urlshortener-with-django-create-virtual-environment-install-django/)<br/>
Part 2: [Create a new project and make sure it works](https://sudeepacharya.com.np/blog/2015/01/13/urlshortener-with-django-creating-new-django-project/)<br/>
Part 3: [Create Django App, Model for our App and work with Django Admin](https://sudeepacharya.com.np/blog/2015/01/14/urlshortener-with-django-creating-app-model/)<br/>
Part 4: [Working with URLs and Views](https://sudeepacharya.com.np/blog/2015/01/15/urlshortener-with-django-urls-and-views/)<br/>
Part 5: [Working on Templates, Static files and finishing up](https://sudeepacharya.com.np/blog/2015/01/16/urlshortener-with-django-working-with-templates/)<br/>
