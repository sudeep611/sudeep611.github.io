---
layout: post
title:  "URL Shortener with Django (Part 4) - Working with Urls and views"
categories: Programming
tags: Python, Django
---
Now we will be working with our actual URLs and Views of our site.

Open up your "urlshortener/urls.py" and add the following code to it:

[urlshortener/urls.py]

```python
from django.conf.urls import patterns, include, url
from django.contrib import admin

urlpatterns = patterns('',
    url(r'^admin/', include(admin.site.urls)),
    # if the URL pattern match /admin/ then open up admin panel

    url(r'', include('shortenersite.urls',
 namespace='shortenersite')),
    # if anything rather then /admin/ then it will look for shortenersite/urls
    )
```

Next, create a new file 'urls.py' inside shortenersite. And add the following code.

[shortenersite/urls.py]

```python
from django.conf.urls import patterns, include, url

urlpatterns = patterns('shortenersite.views',
    url(r'^$', 'index', name='home'),
    # for our home/index page

    url(r'^(?P<short_id>\w{6})$', 'redirect_original', name='redirectoriginal'),
    # when short URL is requested it redirects to original URL

    url(r'^makeshort/$', 'shorten_url', name='shortenurl'),
    # this will create a URL's short id and return the short URL
)
```

Now we are done with our URLs now let us create views. But before that add these lines to your settings.py file.

[urlshortener/settings.py]

```python
SITE_URL = "http://localhost:8000"
```

We will need this because while generating the short URL which looks like http://localhost.com:8000/A34js2. SITE_URL can be different in different cases. Normally it is the URL of the website where this project is hosted on.

Now open up your "shortenersite/views.py" and add the following code.

[shortenersite/views.py]

```python
from django.shortcuts import render_to_response, get_object_or_404
import random, string, json
from shortenersite.models import Urls
from django.http import HttpResponseRedirect, HttpResponse
from django.conf import settings
from django.core.context_processors import csrf

def index(request):
    c = {}
    c.update(csrf(request))
    return render_to_response('shortenersite/index.html', c)

def redirect_original(request, short_id):
    url = get_object_or_404(Urls, pk=short_id) # get object, if not        found return 404 error
    url.count += 1
    url.save()
    return HttpResponseRedirect(url.httpurl)

def shorten_url(request):
    url = request.POST.get("url", '')
    if not (url == ''):
        short_id = get_short_code()
        b = Urls(httpurl=url, short_id=short_id)
        b.save()

        response_data = {}
        response_data['url'] = settings.SITE_URL + "/" + short_id
        return HttpResponse(json.dumps(response_data),  content_type="application/json")
    return HttpResponse(json.dumps({"error": "error occurs"}), content_type="application/json")

def get_short_code():
    length = 6
    char = string.ascii_uppercase + string.digits + string.ascii_lowercase
    # if the randomly generated short_id is used then generate next
    while True:
        short_id = ''.join(random.choice(char) for x in range(length))
        try:
            temp = Urls.objects.get(pk=short_id)
        except:
            return short_id
```

Let's talk about what the above views does.

<span style="text-decoration: underline;">index</span> : It opens the index page by rendering the template.<br />
<span style="text-decoration: underline;">redirect_original</span> : It redirects short URL to it's original URL.<br />
<span style="text-decoration: underline;">shorten_url</span> : We will make a request to this view to create and return us the short URL.<br />
<span style="text-decoration: underline;">get_short_code</span> : This will generate the unique short code/id for URLs.

So, this is the end of the part 4. At this moment this app do not work so have a patience and move to next part. In the next part we will add our template and static files and finish up our project.

Post Series: <br/>
Part 1: [Create a virtual environment and install Django](https://sudeepacharya.com.np/blog/2015/01/12/urlshortener-with-django-create-virtual-environment-install-django/)<br/>
Part 2: [Create a new project and make sure it works](https://sudeepacharya.com.np/blog/2015/01/13/urlshortener-with-django-creating-new-django-project/)<br/>
Part 3: [Create Django App, Model for our App and work with Django Admin](https://sudeepacharya.com.np/blog/2015/01/14/urlshortener-with-django-creating-app-model/)<br/>
Part 4: [Working with URLs and Views](https://sudeepacharya.com.np/blog/2015/01/15/urlshortener-with-django-urls-and-views/)<br/>
Part 5: [Working on Templates, Static files and finishing up](https://sudeepacharya.com.np/blog/2015/01/16/urlshortener-with-django-working-with-templates/)<br/>
