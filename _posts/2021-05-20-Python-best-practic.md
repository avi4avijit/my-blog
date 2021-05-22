---
layout: post
title:  "Python best practice"
date:   2021-05-20 17:46:42 +0530
categories: Software
---

## What is Coding Standard ?

A coding standard gives a consistent appearance to the codes written by different engineers. It improves the readability and maintainability of the code, and it reduces complications. It helps to reuse the code and detect errors quickly. It promotes sound programming practices and increases the efficiency of the programmers.

## Why Coding Standard is important?

It is essential because they help to ensure safety, security, and reliability. Coding principles and instructions make sure that the software is:

- Safe: Can be used without causing harm.
- Secure: Cannot be hacked.
- Reliable: Every time, it functions as it should.
- Testable: Can be tested at the code level.
- Maintainable: Can be maintained, even as your codebase grows.
- Portable: Works the same in every environment.

Developing code in PyCharm will show an underlying line indication if the Style guide is not followed correctly. If the cursor is placed on that line, it will show what is missing.

## What is PEP 8 -- Style Guide for Python Code ?

![image](https://user-images.githubusercontent.com/39100362/119229754-010a9c00-bb37-11eb-9041-f2c8a0c1fe70.png)

When developing code in PyCharm it will show underlying line indication if Style guide is not followed properly. If cursor is placed on that line it will show what is missing.

Here is the Guide from Python site which describe details. [pep-008](https://www.python.org/dev/peps/pep-0008/)

## How to check your developed code follow the professional standard ?

We can use Python static code analysis tool to check for programming error, enforching coding standard and hence can ensure it follows the professional grade. 
Now there are couple of tools available in market. Example 
- pylint
- pyflakes
- mypy
- pysonar2
- autopep8

Every tool has their stronger and weaker points.
As per the easy to use level Pylint is currently our good-to-go tool

## How to install and use pylint ?

I have used Pylint 2.8.2. 

Install it using:
```
  pip install pylint
```  
[Ref: pylint site](https://pypi.org/project/pylint/)

How to use?
```
  pylint file_reader.py
```
Example run screenshot bellow:
![image](https://user-images.githubusercontent.com/39100362/119237671-a3d51180-bb5b-11eb-830c-b36578bd152e.png)

Original Code:
```
"""

This python module will read all '.txt' files in a directory.

"""
# Import Module
import os

# Folder Path "Enter Folder Path (local)"
path = "C:/pytest"

# Change the directory
os.chdir(path)


# Read text File
def read_text_file(file_path):
	with open(file_path, 'r') as f:
		print(f.read())


# main
def main():

	# iterate through all file
	for file in os.listdir():
		# Check whether file is in text format or not
		if file.endswith(".txt"):
			file_path = f"{path}\{file}"

			# call read text file function
			read_text_file(file_path)


if __name__ == "__main__":
	main()
```
  


