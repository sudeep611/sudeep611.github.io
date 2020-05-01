---
layout: post
title:  "Screen Brightness reset to maximum after each restart in Ubuntu"
categories: Linux
tags: Ubuntu
---
I just installed Ubuntu 13.10 in my Dell Inspiron 3421. Previously there was no problem with the screen brightness.

But certainly i was having the problem with screen brightness. I normally work with low screen brightness.

But whenever i restart my Laptop the Screen Brightness was set to maximum. If you are also having this same problem then i have found the fix for this. Let's see how i was able to fix the screen brightness issue.

First open the Terminal and type
```bash
$ sudo gedit /etc/rc.local
```

![Ubuntu 13.10 Screen](/assets/post-images/2014/ubuntu13-10-terminal.png)

and it will open file(rc.local in gedit) then add the following code just above the line <span style="color: #ff0000;">exit 0</span>

```bash
echo 7 > /sys/class/backlight/acpi_video0/brightness
```

You can change the number 7 which is the brightness level value.

Source: <a href="http://askubuntu.com/questions/79983/screen-brightness-reset-to-minimum-after-every-reboot">Ask Ubuntu</a>
