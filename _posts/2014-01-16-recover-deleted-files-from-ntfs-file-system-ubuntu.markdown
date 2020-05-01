---
layout: post
title:  "Recover deleted data from NTFS file system in Ubuntu"
categories: Linux
tags: Ubuntu, Data-BackUp
---
I deleted the archive file which contains important images. And i thought it was gone forever, i did not had any backup too. But i was able to restore the deleted archive file using NtfsUndelete.

It was good that i had archived the photos so it was easy to restore. I was using Ubuntu and i deleted the files that was from another drive which is using Ntfs file system. So, i will explain how i was able to recover my files.

<h2>Install NtfsUndelete on Ubuntu</h2>

We will be installing NtfsUndelete at first(If you have it installed already then skip this step). To install open Terminal(ctrl + alt + t) and enter the following:

```bash
$ sudo apt-get install ntfsprogs
```

ntfsprogs is the package which contains NtfsUndelete itself and some other useful tools like ntfslevel and ntfsinfo.

<h2>Search for your deleted files</h2>

First of all enter the following in the terminal

```bash
$ sudo fdisk -l
```

It will list all the drive in your computer as shown below and note the Device name in which you have deleted the files that are to be recovered. For example my device name will be /dev/sda4.

![Ubuntu Terminal Show devices list](/assets/post-images/2014/device-list-ubuntu.png)


Now its time to search for the deleted files in the drive. Enter following command in your terminal:

```bash
$ sudo ntfsundelete /dev/sda4 -s -m '*.zip'
```

In this above code /dev/sda4 is your device name and *.zip is the file extension(it means all the files with .zip extension). If you are searching for .jpg or something then change this file extension.

<span style="text-decoration: underline;">Note</span>: You must unmount the drive before searching for the deleted files or it will show the error as shown below.

Now it will list all the files that were deleted in that drive as shown below:

![Ubuntu Terminal Deleted Files](/assets/post-images/2014/deleted-files.png)

<h2>Finally recover the deleted files</h2>
Now it's time to recover your deleted files and bring them back. Enter the following in the Terminal:

```bash
$ sudo ntfsundelete /dev/sda4 -u -i 2840
```

In this above code 2840 is the Inode number which you can find while listing the deleted files above. If you want to recover the .jpg or .png image files and there are many in numbers then you can also recover them by using the following command:

```bash
$ sudo ntfsundelete /dev/sda4 –u –m *.jpg
```

As mentioned earlier /dev/sda4 is you device name and *.jpg is the extension of the files to be recovered.

When you will get 'Undeleted Successfully' message then you can find your files in Home folder.

Here is the screenshot when i recovered .zip file using Inode.

![Ubuntu Files Recovered Successfully](/assets/post-images/2014/file-recovered-successfully.png)

So, i hope you are able to recover your deleted files using <span style="text-decoration: underline;">NtfsUndelete</span>. I found this tool very useful as it did a lot for me.

For more information visit <a href="https://help.ubuntu.com/community/DataRecovery/NtfsUndelete">Ubuntu Wiki Page</a> about NtfsUndelete.
