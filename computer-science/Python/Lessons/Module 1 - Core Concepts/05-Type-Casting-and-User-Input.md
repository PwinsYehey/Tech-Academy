---
tags:
  - python/basics
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-21
---
# Type Casting and User Input

Up until now, your scripts have been completely hardcoded. To make real programs, you need to collect information from a human user using **User Input** and safely convert that data using **Type Casting**.
___
## 📥 Collecting Data with `input()`
Python has a built-in global function called `input()`. It pauses your script, prints a prompt message, and waits for the user to type something on their keyboard and press **Enter**.

>[!NOTE]
The `input()` function **always** returns the data as a **String (`str`)**, no matter what the user typed. Even if they type the number `25`, Python reads it as the text `"25"`.

```python
# The program pauses here until the user types something
user_name = input("Enter your name: ")

print(f"Hello, {user_name}!")
print(type(user_name)) # Output will ALWAYS be <class 'str'>
```
___
## 🔄 Type Casting (Data Conversion)
Because `input()` only returns text strings, trying to do math with an input value will cause your code to crash or behave weirdly. 

**Type Casting** is the process of converting a variable from one data type to another using built-in functions.
### 🧰 The 4 Casting Functions

| Function  | Converts Data Into       | Example         | Result                              |
| :-------- | :----------------------- | :-------------- | :---------------------------------- |
| `str()`   | String (Text)            | `str(42)`       | `"42"`                              |
| `int()`   | Integer (Whole number)   | `int("42")`     | `42`                                |
| `float()` | Float (Decimal number)   | `float("3.14")` | `3.14`                              |
| `bool()`  | Boolean (`True`/`False`) | `bool("Hello")` | `True` (Empty text `""` is `False`) |
___
## 🚨 The Dangerous Mistake: Forgetting to Cast
Look at what happens if you forget to convert your user inputs before doing math:
```python
# Enter your first and second number
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")

# Problem: Python glues the strings together instead of adding them!
bad_total = num1 + num2 

print(bad_total)
```

### 🛠️ The Fix: Immediate Wrapping
To fix this, professional programmers wrap the `input()` function directly inside a casting function like `int()` or `float()` on a single line:
```python
# Convert the text into a real integer immediately upon entry
age = int(input("Enter your age: ")) 

# Now you can safely do math!
years_left = 100 - age

print(f"In 100 years you will be {age + 100}")
```
___
## 🛠️ Practice Playground
Click the **Run** button on the code block below to test it out:
```python
# Simulating an input value that came in as a string
birth_year_input = "2002" 

# 1. Cast the string to an integer
birth_year = int(birth_year_input)

# 2. Perform math
current_year = 2026
calculated_age = current_year - birth_year

print(f"Calculated Age: {calculated_age} years old.")
print(f"Data type after casting: {type(birth_year)}")
```
___
# 🎯 Challenge 5: The Gamer XP Calculator
### 📜 Instructions
You are building the registration screen for a retro arcade game. The game needs to calculate a player's starting score modifier based on their current level.

Write a Python script that does the following:
1. Use `input()` to ask the player for their **Username** and store it.
2. Use `input()` to ask the player for their **Current Level** (a whole number).
3. **Type cast** the level input into a real integer immediately so you can use it for calculations.
4. Calculate a variable called `xp_bonus` by multiplying their level by `1.5`.
5. Use an **f-string** to display a player card that outputs exactly like this:
   ```text
   --- PLAYER REGISTERED ---
   Welcome, [Username]!
   Starting Level: [Level]
   Your calculated XP Bonus modifier is: [Bonus Value]
   ```
### 💻 Write Your Code Here
```python
username = str(input(f"Enter Username: "))
level = int(input(f"Enter Current Level: "))

xp_bonus = level * 1.5

print("--- PLAYER REGISTERED ---")
print(f"Wecome, {username}")
print(f"Starting level: {level}")
print(f"Your calculated XP Bonus modifier is: {xp_bonus}")
```
###### ⏭️ Next Lesson
[**Module 1 — Lesson 06: Conditional Statements**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F06-Conditional-Statements)