---
layout: post
title:  "Recursive directory traverse and append .png file to list"
categories: Programming
tags: Python
---
Python Developer's Meetup Nepal #13 Question Solution

Q: Write a python script that recursively walks all sub-directories and searches all files with extension *.png or *.PNG and append them to the list.

Solution:

```python
import os

# list variable to store the .png and .PNG file
png_file_list = []

# Recursive function to traverse all the sub-dirctory and check for png files
def traverse_directory(dir_path):
    for child in os.listdir(dir_path):
        path = os.path.join(dir_path, child)
        if os.path.isdir(path):
            traverse_directory(path)
        else:
        	# split the path and store file name only
        	file_name = path.split('\\')[-1]
        	# split the file name and store extension
        	file_name_extension = file_name.split('.')[-1]
        	# check if the file name has extension .png or .PNG
        	if(file_name_extension == 'png' or file_name_extension == 'PNG'):
        		png_file_list.append(file_name)

# Traverse current directory for files and folders
traverse_directory(".")

# Print the final list
print(png_file_list)
```
