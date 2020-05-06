---
layout: post
title:  "How to Install PHP Composer in your Mac"
categories: Programming
tags: PHP
---
Composer is the easiest way to manage dependencies to your small to large PHP projects.

Use the following commands to install composer in your Mac


```bash
$ curl -sS https://getcomposer.org/installer | php
```

Now the composer is installed in your current directory.

Now, you can access it using the following command

```bash
$ php composer.phar [command]
```

It works but you don't always want to use this directory path to access the composer, So in the next step we will make it accessible globally.

Let us move it to usr/local/bin to make it globally accessible from your terminal.

```bash
$ mv composer.phar usr/local/bin
```

Next, create alias and add it to your bashrc file to load it every time you restart your terminal or mac book.

```bash
$ echo 'alias composer="php /usr/local/bin/composer.phar"' >> ~/.bash_profile
```

That's all, Restart your terminal and now try using composer in your terminal and it works. Every time the terminal opens it autoloads this alias now.

Bonus: If it is for other platform such as Ubuntu, you need to write to bashrc instead of bash_profile.

```bash
$ echo 'alias composer="php /usr/local/bin/composer.phar"' >> ~/.bashrc
```
