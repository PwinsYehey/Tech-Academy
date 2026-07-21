---
tags:
  - python/basics
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-21
---
# Strings and Text

In Python, a **string** (written as `str`) is a sequence of characters used to store and manipulate text. Strings are surrounded by either single quotes (`'`) or double quotes (`"`).
___
## 🛠️ Creating Strings
Python does not care if you use single or double quotes, but you must be consistent.

```python
# Both of these are valid strings
store_name = "Prince's Coding Shop"  # Double quotes allow single quotes inside
greeting = 'He said, "Hello!"'      # Single quotes allow double quotes inside

print(store_name)
print(greeting)
```
___
## 💬 Code Comments (`#`)
Comments are notes written for humans, not the computer. Python completely ignores lines starting with a hashtag `#`. 

You use comments to explain complex logic or temporarily disable lines of code when testing.

```python
# This is a single-line comment. Python will skip this completely.

message = "Hello World"  # This is an inline comment explaining this variable

# print(message) 
# This is a multi-line comment.
# The line above is "commented out" so it will not run!
```
___
## 🔗 String Concatenation (Combining Text)
You can glue strings together using the `+` operator. 

```python
first_name = "Prince"
last_name = "Skywalker"

# Combining strings with spaces
full_name = first_name + " " + last_name

print(full_name)  # Output: Prince Skywalker
```

>[!WARNING]
You can only concatenate strings with other strings. If you try to add a string to an integer, Python will throw a `TypeError`.

___
## 🎯 String Interpolation / F-Strings (Formatted Strings)
Instead of messy `+` signs, modern Python uses **f-strings** to inject variables directly into text. Just put an `f` before the opening quote and wrap your variables in curly braces `{}`.

```python
user = "Prince"
level = 5

# Clean and readable formatting
message = f"Welcome back, {user}! You are at level {level}."
print(message)  # Output: Welcome back, Prince! You are at level 5.
```
___
## 🧰 Essential String Methods (With Dots `.`)
Python has built-in tools (called **methods**) to modify text on the fly. Methods are written with a dot `.` right after the variable name.

| Method     | Description                         | Example Code             | Output           |
| :--------- | :---------------------------------- | :----------------------- | :--------------- |
| `.upper()` | Converts to ALL CAPS                | `"hi".upper()`           | `"HI"`           |
| `.lower()` | Converts to lowercase               | `"HI".lower()`           | `"hi"`           |
| `.title()` | Capitalizes first letter of words   | `"hello prince".title()` | `"Hello Prince"` |
| `.strip()` | Removes empty spaces from start/end | `"  hi  ".strip()`       | `"hi"`           |

```python
text = "  Python Is Fun  "

print(text.upper())            # "  PYTHON IS FUN  "
print(text.strip().lower())    # "python is fun"
```

>[!TIP]
Since both `.strip()` and `.lower()` are string methods, Python allows you to link them together in a single line using a dot. This is called **method chaining** (reads from left to right). 

___
## 🌎 Built-in Functions Used on Strings (No Dots)
Functions are **global tools**. They do not belong to strings, but they can inspect them. You pass the string *inside* the parentheses.

| Function  | Description                  | Example Code  | Output          |
| :-------- | :--------------------------- | :------------ | :-------------- |
| `len()`   | Counts the total characters  | `len("code")` | `4`             |
| `print()` | Displays text to the console | `print("Hi")` | `Hi`            |
| `type()`  | Checks the data type         | `type("Hi")`  | `<class 'str'>` |
```python
text = "  python is fun  "

print(len(text))         # 17 (includes spaces!)
```
___
## ✂️ String Indexing
Every character in a string has an address number called an **index**, starting at **0**. You can grab a single character using square brackets `[]`.

```python
word = "Python"

# Indexing starts at 0!
print(word[0])  # Output: P
print(word[2])  # Output: t

# Negative indexing starts from the back
print(word[-1]) # Output: n (the last letter)
```
___
## 🛠️ Practice Playground
Run this block using your **Execute Code** plugin to see string magic in action:

```python
raw_username = "   pRiNcE_sKyWaLkEr   "

# 1. Using a Method to clean spaces and lower case
clean_username = raw_username.strip().lower()

# 2. Using a Function to count the final characters
username_length = len(clean_username)

print(f"Cleaned: {clean_username}")
print(f"Length: {username_length}")
```
___
# 🎯 Challenge 2: The Data Cleaner
### 📜 Instructions
Imagine you are building a login system. A user signs up, but they typed their email address with accidental spaces at the edges and a mix of messy uppercase letters. 

Write a Python script that does the following:
1. Create a variable called `dirty_email` containing the text: `"   Prince_Skywalker@EMail.Com   "`
2. Use a **string method** to clean up (remove) the empty spaces from the edges. Store this in a new variable.
3. Use a **string method** to convert the entire email to lowercase letters (emails should always be lowercase!). Store this in a new variable.
4. Add a **comment** above your code explaining what your cleaning step does.
5. Use a **built-in function** to count how many characters are in your final, cleaned email.
6. Use an **f-string** to print out the final email and its length in a clean message.
### 💻 Write Your Code Here
```python



```

