# 0x01. Python - if/else, loops, functions
`Python`

## Overview
This project introduces learners to the control structures in Python and functionl programming using python.
Learners should make sure to go through each instruction before going into the project tasks

## Resources:
- [The Python tutorial (only the first three chapters below)](https://docs.python.org/3/tutorial/index.html)
- [Whetting Your Appetite](https://docs.python.org/3/tutorial/appetite.html)
- [Using the Python Interpreter](https://docs.python.org/3/tutorial/interpreter.html)
- [An Informal Introduction to Python (Read up until “3.1.2. Strings” included)](https://docs.python.org/3/tutorial/introduction.html)
- [How To Use String Formatters in Python 3](https://realpython.com/python-f-strings/)
- [Learn to Program](https://www.youtube.com/playlist?list=PLGLfVvz_LVvTn3cK5e6LjhgGiSeVlIRwt)
- [Pycodestyle – Style Guide for Python Code](https://pypi.org/project/pycodestyle/)

## Learning Objectives
- Why Python programming is awesome
- Who created Python
- Who is Guido van Rossum
- Where does the name ‘Python’ come from
- What is the Zen of Python
- How to use the Python interpreter
- How to print text and variables using `print`
- How to use strings
- What are indexing and slicing in Python
- What is the official Python coding style and how to check your code with `pycodestyle`

## Requirements

## Python scripts
- Your code should use the pycodestyle
- All your files must be executable
- All your files should end with a new line
- The first line of all your files should be exactly #!/usr/bin/python3
- A `README.md` file at the root of the repo, containing a description of the repository
- A `README.md` file, at the root of the folder of this project, is mandatory

## Shell scripts
- All your scripts should be exactly two lines long (wc -l file should print 2)
- All your files should end with a new line
- The first line of all your files should be exactly #!/bin/bash
- All your files must be executable

## More Info
Zen
```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!`
```
## Pycodestyle
__Pycodestyle__ is now the [new standard of Python style code](https://github.com/PyCQA/pycodestyle/issues/466)

## Tasks

### 0. A Python shell

Write a Shell script that runs a Python script.

The Python file name will be saved in the environment variable `$PYFILE`
```
exa@ubuntu:~/py/0x00$ cat main.py
#!/usr/bin/python3
print("Best School")

exa@ubuntu:~/py/0x00$ export PYFILE=main.py
exa@ubuntu:~/py/0x00$ ./0-run
Best School
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `0-run`

### 1. A Python code shell
Write a Shell script that runs Python code.

The Python code will be saved in the environment variable `$PYCODE`
```
exa@ubuntu:~/py/0x00$ export PYCODE='print(f"Best School: {88+10}")'
exa@ubuntu:~/py/0x00$ ./1-run_inline
Best School: 98
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `1-run_inline`

### 2. Print string with quotes
Write a Python script that prints exactly `"Programming is like building a multilingual puzzle,` followed by a new line.

- Use the function print
```
exa@ubuntu:~/py/0x00$ ./2-print.py
"Programming is like building a multilingual puzzle
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `2-print.py`

### 3. Print integer
Complete the source code in order to print the integer stored in the variable `number`, followed by `Battery street`, followed by a new line.

- You can find the source code [here](https://github.com/alx-tools/0x00.py/blob/master/3-print_number.py)
- The output of the script should be:
    - the number, followed by `Battery street`,
    - followed by a new line
- You are not allowed to cast the variable `number` into a string
- Your code must be 3 lines long
- You have to use [f-strings](https://realpython.com/python-f-strings/) tips

```
exa@ubuntu:~/py/0x00$ ./3-print_number.py
98 Battery street
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `3-print_number.py`

### 4. Print float
Complete the source code in order to print the float stored in the variable `number` with a precision of 2 digits.

- You can find the source code [here](https://github.com/alx-tools/0x00.py/blob/master/4-print_float.py)
- The output of the program should be:
    - `Float:`, followed by the float with only 2 digits
    - followed by a new line
- You are not allowed to cast `number` to string
- You have to use f-strings
```
exa@ubuntu:~/py/0x00$ ./4-print_float.py
Float: 3.14
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `4-print_float.py`

### 5. Print string
Complete the source code in order to print 3 times a string stored in the variable `str`, followed by its first 9 characters.

- You can find the source code [here](https://github.com/alx-tools/0x00.py/blob/master/5-print_string.py)
- The output of the program should be:
    - 3 times the value of `str`
    - followed by a new line
    - followed by the 9 first characters of `str`
    - followed by a new line
- You are not allowed to use any loops or conditional statement
- Your program should be maximum 5 lines long
```
exa@ubuntu:~/py/0x00$ ./5-print_string.py
ALX ALX ALX ALX
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: PyLAMP-Program_Projects
- Directory: 0x00-python-hello_world
- File: 5-print_string.py

### 6. Play with strings
Complete the source code to print `Welcome to ALX`

- You can find the source code [here](https://github.com/alx-tools/0x00.py/blob/master/6-concat.py)
- You are not allowed to use any loops or conditional statements.
- You have to use the variables `str1` and `str2` in your new line of code
- Your program should be exactly 5 lines long
```
exa@ubuntu:~/py/0x00$ ./6-concat.py
Welcome to ALX!
exa@ubuntu:~/py/0x00$ wc -l 6-concat.py
5 6-concat.py
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `6-concat.py`

### 7. Copy - Cut - Paste
Complete the source code

- You can find the source code [here](https://github.com/alx-tools/0x00.py/blob/master/7-edges.py)
- You are not allowed to use any loops or conditional statements
- Your program should be exactly 8 lines long
- `word_first_3` should contain the first 3 letters of the variable `word`
- `word_last_2` should contain the last 2 letters of the variable `word`
- `middle_word` should contain the value of the variable `word` without the first and last letters
```
exa@ubuntu:~/py/0x00$ ./7-edges.py
First 3 letters: Hol
Last 2 letters: on
Middle word: olberto
exa@ubuntu:~/py/0x00$ wc -l 7-edges.py
8 7-edges.py
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `7-edges.py`

### 8. Create a new sentence
Complete the source code to print `object-oriented programming with Python`, followed by a new line.

- You can find the source code [here](https://github.com/alx-tools/0x00.py/blob/master/8-concat_edges.py)
- You are not allowed to use any loops or conditional statements
- Your program should be exactly 5 lines long
- You are not allowed to create new variables
- You are not allowed to use string literals
```
exa@ubuntu:~/py/0x00$ ./8-concat_edges.py
object-oriented programming with Python
exa@ubuntu:~/py/0x00$ wc -l 8-concat_edges.py
5 8-concat_edges.py
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `8-concat_edges.py`

### 9. Easter Egg
Write a Python script that prints “The Zen of Python”, by TimPeters, followed by a new line.

Your script should be maximum 98 characters long (please check with `wc -m 9-easter_egg.py`)
```
exa@ubuntu:~/py/0x00$ ./9-easter_egg.py
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
exa@ubuntu:~/py/0x00$
```
Repo:

- GitHub repository: `PyLAMP-Program_Projects`
- Directory: `0x00-python-hello_world`
- File: `9-easter_egg.py`
