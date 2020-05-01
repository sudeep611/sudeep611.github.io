---
layout: post
title:  "How to set up basic PHP Project structure with Composer"
categories: Programming
tags: PHP
---
Most of the time beginners learning PHP are unaware of [Composer](https://getcomposer.org/), if you are among them, Composer is a dependency management tool for PHP.

Let's take a simple example, rather than using include command in each of the PHP file, composer makes it easy by specifying that file as a dependency. Another example would be if you use some library then it makes easier to use and update it with a single command.

Is it compulsory to use Composer for my PHP project?

I wouldn't answer it in Yes or No format. I would say that you can write simple project with couple of file and classes without dependency management tools like Composer, but life will be much much easier by using Composer. Time will come where you will be unable to maintain the project on your own without it when your project grows larger.

Alright, let's jump onto our subject, in this post i will write about setting up the basic PHP project with composer on it. The whole project files can be found on my [Github Page](https://github.com/sudeep611/PHP_Project_Getting_Started). You are welcome to contribute :)

Before beginning, i will assume that you have PHP and Composer installed in your machine. Read my previous post:

[How to install PHP Composer in MAC](https://sudeepacharya.com.np/blog/2020/01/04/how-to-install-php-composer-in-your-mac/)

Setting up the basic PHP Project Skeleton code with Composer

Create a root folder with your project name, i will name it as "MyPHPProject"

```bash
$ mkdir MyPHPProject
```

Navigate to this folder

```bash
$ cd MyPHPProject
```

Create 'src' folder where we will have our projects PHP Classes and files

```bash
$ mkdir src
```

Navigate to 'src' folder

```bash
$ cd src
```

Inside it create folder 'HelloWorld' and navigate to it

```bash
$ mkdir HelloWorld || cd HelloWorld
```

Let's create HelloWorld.php and write some PHP code inside it.

```bash
$ touch HelloWorld.php
```

Open "HelloWorld.php" and paste the following code

```php
<?php

namespace HelloWorld;

class HelloWorld {
	public function printHelloWorld() {
		return "Hello World";
	}
}
```

Now, let's go back to 'src' folder

```bash
$ cd ..
```

Create folder named 'files'

```bash
$ mkdir files
```

If in future you need to keep any files such as JavaScript, Images then you can use this folder.

Let's go back to our main project root folder.

```bash
$ cd ..
```

Now let us create 'composer.json' file

```bash
$ touch composer.json
```

Paste the following in your composer.json file

```json
{
    "name": "sudeep/HelloWorld",
    "description": "This is the description of the project.",
    "license": "MIT",
    "minimum-stability": "dev",
    "require": {
        "php": ">=7.0"
    },
    "autoload": {
        "psr-0": {
            "HelloWorld": "src/"
        }
    },
    "require-dev": {
        "phpunit/phpunit": "^8"
    }
}
```

In the above code edit as per your requirement, one new thing you might have noticed is [phpunit](https://phpunit.de/), we will use phpunit for writing test case to our project later.

Next, install composer.

```bash
$ composer install
```

This will install composer for your current project. It will install the library and dependencies mentioned in the composer.json file above.

Now, you will notice some more files such as vendor folder added to your project, this is the file added by composer.

Next, Let's create 'index.php' which is the entry point for our PHP project.

```bash
$ touch index.php
```

Paste the following code in index.php

```php
<?php

// Autoload files using the Composer autoloader.
require_once __DIR__ . '/vendor/autoload.php';

use HelloWorld\HelloWorld;

$entry = new HelloWorld();
echo($entry->printHelloWorld());
```

Let's run the PHP project. Enter the following code in command line.

```bash
$ php -S localhost:4000
```

Open the 'localhost:4000' in your Browser and you will see Hello World printed.

Next, let us add the tests folder where we will be writing our test cases. And navigate to it

```bash
$ mkdir tests || cd tests
```

Let us create HelloWorldTest.php inside tests folder

```bash
$ touch TestHelloWorld.php
```

And paste the following code inside it

```php
<?php

// Autoload files using the Composer autoloader.
require_once __DIR__ . '/../vendor/autoload.php';

use HelloWorld\HelloWorld;
use PHPUnit\Framework\TestCase;

final class HelloWorldTest extends TestCase
{
	public function testPrintHelloWorld() {
		$actualClass = new HelloWorld();
        $this->assertEquals('Hello World', $actualClass->printHelloWorld());
	}
}
```

For running the test file you can use the following command.

[To Make sure PHPUnit is installed in your machine.]

```bash
$ phpunit HelloWorldTest.php
```

That's all!
