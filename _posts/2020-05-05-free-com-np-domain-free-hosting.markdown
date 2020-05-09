---
layout: post
title:  "Get free domain .com.np and free hosting"
categories: Free Stuff
---
For Nepali citizens, you can register free **.com.np** domain. In this post, I will teach you to point this domain to Github Pages using Cloudflare DNS for free.

Mercantile Communications Pvt. Ltd. provides .com.np domain registration for free of cost and provides to use DNS service.

<h2>Step 1: Setup Github account and upload website</h2>
To upload your website into the github account you need to learn git. I am not covering the tutorial for using the git. You can refer to this site to learn git. [Learn Git](https://try.github.io/)

Before starting, you need to know that you can only host the static webpages in the github. For example you can upload index.hml, javascript files and images. This means that you can't host the CMS such as WordPress that is built on PHP. So, to sum up you can only host html, js, images and other files such as pdf.

First of all let us create a web site on Github. For this follow the steps below.
1. Sign Up on [Github](https://github.com/), with username, email and password.
1. Login to your Github Account
1. Create new repository with the name <span style="color:red">username</span>.github.io
Here, don't forget to change the username with your own github username that you used while signing up.
1. This is the repository where you will upload your website.
1. Have atleast index.html in this repository so, when you open <span style="color:red">username</span>.github.io in your browser you will see your website running.

<h2>Step 2: Register your Domain Name</h2>
You can apply for new domain through the link below:<br />
[Register your free domain](https://register.com.np/apply-new-domain.php)

To apply the domain name, you need to enter the following details in the above web site:

<ins>Domain name</ins>: yourname.com.np, just enter the domain name you want to register based on your name.<br />

<ins>Name Server</ins>: Enter the name servers as follows.<br />
Primary Name Server: <span style="color:blue;font-weight:bold;">eva.ns.cloudflare.com</span><br />
Secondary Name Server: <span style="color:blue;font-weight:bold;">hank.ns.cloudflare.com</span>

Since, we are using Github Pages to host our web site and Mercantile does not provide us to set up CNAME and A record for our domain.

<ins>You Details</ins>: Enter your Email and Personal details.<br />

<ins>Documents</ins>: Scan and upload your citizenship document. Also write a cover letter mentioning that you want to register the domain.

After submitting all these information you will get an email confirmation from Mercantile Communications. If you do not get reply from them within a week just send them email to **hostmaster@mercantile.com.np**

<h2>Step 3: Point your domain to Github Pages through Cloudflare</h2>
Create a free account on Cloudflare. [Sign up for Cloudflare](https://www.cloudflare.com/)

Add a site to Cloudflare. I am not writing each an every step. Refer to the following link. <br />

[Creating a Clouflare account and adding a Website](https://support.cloudflare.com/hc/en-us/articles/201720164-Creating-a-Cloudflare-account-and-adding-a-website)

Next, after adding the site to Cloudflare, navigate to DNS tab and following record.

After adding all the records your settings will look something like this:
![Create A record for domain in Clouflare](/assets/post-images/2020/point-github-cname-from-clouflare.png)

<h2>Step 4: Create CNAME file in your Github repository</h2>
Till this step, we have point our domain to Githubpages and we have your website running in Github Pages with url <span style="color:red">username</span>.github.io

Now, we need to update our domain name in Github.

In your repository in Github (created in the first Step) create a file name <span style="color:blue;font-weight:bold;">CNAME</span>

In that file write the name of your domain (yourdomain.com.np) as shown in the image below.

![CNAME file for Custom domain in GithubPages](/assets/post-images/2020/cname-file-custom-domain-githubpages.png)

Now, you when you open "yourname.com.np", You will see you website running.

Note that it may take, upto 72 hours for the domain DNS to be updated throughout the web.
