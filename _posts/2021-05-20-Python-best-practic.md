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
1. """
2.
3. This python module will read all '.txt' files in a directory.
4. 
5. """
6. # Import Module
7. import os
8. 
9. # Folder Path "Enter Folder Path (local)"
10. path = "C:/pytest"
11. 
12. # Change the directory
13. os.chdir(path)
14.
15.
16.# Read text File
17. def read_text_file(file_path):
18. 	with open(file_path, 'r') as f:
19.		print(f.read())
20.
21.
22. # main
23. def main():
24.
25.	# iterate through all file
26.	for file in os.listdir():
27.		# Check whether file is in text format or not
28.		if file.endswith(".txt"):
29.			file_path = f"{path}\{file}"
30.
31.			# call read text file function
32.			read_text_file(file_path)
33.
34.
35. if __name__ == "__main__":
36.	main()
```
  

Now what those error says in Pylint.

18, 19, 26, 28, 29, 32, 36 - In those lines Tabs are used instead of space where as other lines use spaces. So mixed-indentation error.
37 Has a blcn space as extra line
29 Now here the eror is due to the backslash is in a literal string, not as an escape. It should be something 
```
f"{PATH}\\{file}"
```
10 Is constant name, that should be in UPPER CASE
17 & 23 Actually says that use function docstring as bellow:
```
def main()
    """ main block """
```
18 & 30 Says variable name should be in snake case, should not be single charecter like 'f'

So after correction the pylint shows:
![image](https://user-images.githubusercontent.com/39100362/119238952-5c528380-bb63-11eb-95aa-41b276378b99.png)

Corrected Code:
```
"""

This python module will read all '.txt' files in a directory.

"""
1. # Import Module
2. import os
3. 
4. # Folder Path "Enter Folder Path (local)"
5. PATH = "C:/pytest"
6. # Change the directory
7. os.chdir(PATH)
8.
9.
10.def read_text_file(file_path):
11.    """ Read text File """
12.    with open(file_path, 'r') as file_content:
13.        print(file_content.read())
14.
15.
16. def main():
17.    """ main block """
18.    # iterate through all file
19.    for file in os.listdir():
20.        # Check whether file is in text format or not
21.        if file.endswith(".txt"):
22.            file_path = f"{PATH}\\{file}"
23.            # call read text file function
24.            read_text_file(file_path)
25.
26.
27.if __name__ == "__main__":
28.    main()
```
