---
tags:
  - python/basics
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-21
---
# Variables and Data Types

In Python, **variables** are like labeled storage boxes. You put data inside them so you can use and manipulate it later. 
___
## 📦 Declaring Variables
Python is **dynamically typed**. You do not need to declare the type of data beforehand. Python figures it out automatically.

```python
# Assigning values to variables
age = 25
name = "Alex"
is_learning = True

# You can print them to the console
print(name)
print(age)
```
### 📏 Naming Rules
- Must start with a letter or an underscore `_`.
- Cannot start with a number.
- Can only contain alphanumeric characters and underscores (`A-z`, `0-9`, and `_`).
- Case-sensitive (`Age`, `age`, and `AGE` are three different variables).
- **Best Practice:** Use `snake_case` for variable names (e.g., `user_profile_name`).
___
## 🗂️ The 4 Essential Data Types
Here are the four foundational data types you will use every day:

| Data Type            | Description                    | Example               |
| :------------------- | :----------------------------- | :-------------------- |
| **Integer** (`int`)  | Whole numbers without decimals | `score = 10`          |
| **Float** (`float`)  | Numbers with decimal points    | `price = 19.99`       |
| **String** (`str`)   | Text wrapped in quotes         | `greeting = "Hello!"` |
| **Boolean** (`bool`) | True or False states           | `is_active = True`    |
___
## 🕵️ Checking Data Types
If you are ever unsure what data type a variable is holding, use the built-in `type()` function.

```python
x = 42
y = "42"

print(type(x))  # Output: <class 'int'>
print(type(y))  # Output: <class 'str'>
```
___
## 🔄 Type Conversion (Casting)
You can convert a variable from one data type to another using functions like `int()`, `float()`, and `str()`.

```python
# Converting a float to an integer (it cuts off the decimal)
pi = 3.14
pi_integer = int(pi) 
print(pi_integer)  # Output: 3

# Converting an integer to a string to combine it with text
points = 50
message = "Your score is " + str(points)
print(message)  # Output: Your score is 50
```
___
## 🛠️ Practice Playground
Click the **Run** button on the code block below to test it out:

```python
# Change these values and run the block!
my_name = "Your Name"
items_count = 5
price_per_item = 2.50

# Calculate total cost
total_cost = items_count * price_per_item

print("Hello " + my_name)
print("Total cost is:")
print(total_cost)
print(type(total_cost))
```
___
# 🎯 Challenge 1: The Space Explorer Profile
### 📜 Instructions
Your goal is to create a profile for an astronaut character using variables. 

Write a Python script that does the following:
1. Create a variable for the astronaut's name (Text).
2. Create a variable for their age (Whole number).
3. Create a variable for their ship's current speed in lightyears (Decimal number).
4. Create a boolean variable stating if they have reached Mars yet (`True` or `False`).
5. Print all four variables to the console.
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 02: Strings and Text**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F02-Strings-and-Text)