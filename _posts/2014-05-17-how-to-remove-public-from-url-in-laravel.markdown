---
layout: post
title:  "How to remove /public/ from URL in Laravel"
categories: Programming
tags: PHP
---

By default in Laravel the URL to access your site is http://example.com/public/. It is not good to keep public in URL as it makes URL ugly and longer.

So, let's talk about the solution to remove /public/ from the URL.

<h2>Method I : Using .htaccess</h2>
Create a .htaccess file your Laravel root directory if it does not exists already. (Normally it is under your <i>public_html</i> folder)

And add the following code to it:
```
<IfModule mod_rewrite.c>
    RewriteEngine On

    RewriteRule ^(.*)$ public/$1 [L]
</IfModule>
```

Now you can access your site via http://example.com.

<h2>Method II : Moving the contents of public folder to root directory</h2>
Actually i prefer this method because the above method is not so good to use in production environment.

So now lets make a new folder <b>laravelfiles</b> in your root directory and move all the files and folder except public directory to laravelfiles.

And move everything of public directory to root folder. Now your root directory will look something like this:

![](/assets/post-images/2014/laravel-remove-public.png){:class="img-responsive"}

Now we have to change the paths in laravelfiles/bootstrap/paths.php file and index.php.

Find these lines in <b>laravelfiles/bootstrap/paths.php</b>

```php
    'app' => __DIR__.'/../app',
    'public' => __DIR__.'/../public',
```

Change these two lines to:

```php
    'app' => __DIR__.'/../app',
    'public' => __DIR__.'/../../',
```

Find these lines in <b>index.php</b>
```php
    require __DIR__.'/../bootstrap/autoload.php';

    $app = require_once __DIR__.'/../bootstrap/start.php';
```

And change to:

```php
    require __DIR__.'/laravelfiles/bootstrap/autoload.php';

    $app = require_once __DIR__.'/laravelfiles/bootstrap/start.php';
```
