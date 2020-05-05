---
layout: post
title:  "Moving to Github Pages using Jekyll  from WordPress.com"
categories: Jekyll
---
I started my blog "hellocoding.wordpress.com" in 2013. WordPress.com provides the basic functionality of posting the post for free. It does not give the way to embed JavaScript and does not offer much control over your blog.

After a few years of blogging in WordPress.com, I realised that I want more control over my site so that I can improve my SEO, make a page redirection and make my site how I want in every possible way.

Then I decided to move my blog to [Github Pages](https://pages.github.com/), which provides free hosting of the website and gives you to host the static web pages using the static site generator such as [Jekyll](https://jekyllrb.com/).

## Comparison of Github Pages with Jekyll over WordPress.com

| WordPress.com                                                            	| GithubPages (With Jekyll)                                                              	|
|--------------------------------------------------------------------------	|----------------------------------------------------------------------------------------	|
| - Provides free domain example.wordpress.com                             	| - Provides free domain username.github.io<br>- Also provides free url to your projects 	|
| - Can not host JavaScript                                                	| - <span style="color:green">Can host JavaScript</span>                                                                  	|
| - Can not have any control over your theme limited to changing colors.   	| - <span style="color:green">Full control over the design of your website</span>                                         	|
| - Shows the advertisement of its own                                     	| - <span style="color:green">No ads at all</span>                                                                        	|
| - <span style="color:green">Anyone with basic knowledge of using website can blog at WordPress.com</span> 	| - You need to have more complex knowledge of markdown, css, html, git                  	|

We have discussed pretty much about the advantages over one another, Next, I am gonna talk about moving to Github Pages.

First of all, if you don't want to use Jekyll to generate your static website there are other alternatives available to Jekyll. Some are [Gatsby](https://www.gatsbyjs.org/), [11ty](https://www.11ty.dev/) and [Hugo](https://gohugo.io/). The reason I choose Jekyll is that the Github Pages have good support for it but you can go with any of them.

### What you should know about moving to Github Pages
You cannot redirect your post URL to Github Pages site. It is because the WordPress.com does not allow us to redirect URL. It is one of the bad things for SEO because you gonna copy the same post from your WordPress.com blog to the new blog at Github Pages which might make the search engines that you have copied the content.

**Solution:** This solution is not the best but WordPress.com does not give us more choices. In each of the blog post at WordPress.com, write that you have moved your blog post to the new URL.

This is what I have done to my previous blog at WordPress.com

![Moving blog from WordPress.com to Jekyll at Github Pages](/assets/post-images/2020/this-post-has-been-moved-to-new-url.png)

Again, it is not a good solution but people will know that you have moved your blog to new site.

### Tips to learn and prepare to move your blog
1. Learn about [Jekyll](https://jekyllrb.com/tutorials/home/)
1. Learn how to write the post in [markdown](https://www.markdowntutorial.com/)

I suggest you copy each post manually to get the best result. You have to link images by keeping in the appropriate folder. One of the good thing about Markdown is that it also supports HTML tags.
