---
tags:
  - python/basics
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-21
---
# Integers and Floats

Python splits numbers into two distinct groups: **Integers** (negative, zero, positive numbers) and **Floats** (decimal numbers). 
___
## 🔢 The Two Number Types
### Integers (`int`)
Numbers without fractions or decimal points. They include all negative numbers, zero, and positive numbers.

```python
score = 100
temperature = -5
players = 0
```
### Floats (`float`)
Numbers that contain a decimal point. Python automatically flags any number with a dot as a float.

```python
price = 19.99
pi = 3.14159
distance = 5.0  # Even with a zero, the decimal makes this a float!
```
___
## ➕ Basic Math Operators
Python uses standard math symbols, but with a couple of unique twists for division.

| Operator | Action                 | Example Code | Result                       |
| :------- | :--------------------- | :----------- | :--------------------------- |
| `+`      | Addition               | `10 + 5`     | `15`                         |
| `-`      | Subtraction            | `10 - 5`     | `5`                          |
| `*`      | Multiplication         | `10 * 5`     | `50`                         |
| `/`      | **True Division**      | `10 / 3`     | `3.3333333333333335`         |
| `//`     | **Floor Division**     | `10 // 3`    | `3` (Forcefully rounds down) |
| `%`      | **Modulo** (Remainder) | `10 % 3`     | `1` (The leftover amount)    |
| `**`     | Exponent (Power)       | `2 ** 3`     | `8` (2³)                     |
>[!WARNING]
True division (`/`) **always** returns a float, even if the number divides perfectly!

---
## 📐 The Order of Operations (PEMDAS)
When you write a complex mathematical equation on a single line, Python does not just read it blindly from left to right. It evaluates operators based on standard mathematical precedence.
1. **P**arentheses `()` Always evaluated first.
2. **E**xponents `**` Powers/Roots are calculated next.
3. **M**ultiplication & **D**ivision (`*`, `/`, `//`, `%`) Checked from left to right.
4. **A**ddition & **S**ubtraction (`+`, `-`) Checked last, from left to right.

```python
# PEMDAS Example
calculation = (2 + 3) * 4 ** 2
# 1. Parentheses: (2 + 3) = 5
# 2. Exponent: 4 ** 2 = 16
# 3. Multiply: 5 * 16 = 80
print(calculation)  # Output: 80
```

## 🔄 Shortcuts: Augmented Assignment
When updating a numeric variable, you can combine the math operator with the `=` sign to save typing.

```python
gold_coins = 50

# The long way
gold_coins = gold_coins + 10  # gold_coins is now 60

# The professional shortcut way
gold_coins += 10               # gold_coins is now 70
gold_coins -= 5                # gold_coins is now 65 (spent some gold)
```
___
## 🧮 Built-in Math Functions (No Dots)
Python has built-in global functions to quickly manipulate numeric values without importing extra tools.

| Function | Description | Example Code | Output |
| :--- | :--- | :--- | :--- |
| `abs()` | Absolute value (removes negative signs) | `abs(-15)` | `15` |
| `round()` | Rounds a float to the nearest whole | `round(4.6)` | `5` |
| `round(x, n)`| Rounds a float to `n` decimal places | `round(3.14159, 2)` | `3.14` |

```python
my_balance = -45.678

print(abs(my_balance))        # Output: 45.678
print(round(abs(my_balance))) # Output: 46
```

---
## 🛠️ Practice Playground
Click the **Run** button on the code block below to test and see how different number data types interact:

```python
# Change these values and hit Run!
item_price = 2.50
quantity = 3
shipping_cost = 5

# Notice how an int and a float mixed together turns into a float automatically!
subtotal = item_price * quantity
total_cost = subtotal + shipping_cost

print(f"Subtotal Type: {type(subtotal)}")
print(f"Total Bill: {total_cost}")

# Modulo trick: Check if a number is even or odd
number_to_test = 7
remainder = number_to_test % 2
print(f"When we divide {number_to_test} by 2, the leftover remainder is: {remainder}")
```
---
# 🎯 Challenge 3: The Split-the-Bill Calculator
### 📜 Instructions
Imagine you and two friends went out to eat. The total bill came to a messy decimal amount. You need to calculate how much everyone owes, but you want to round it to a clean 2 decimal places so it looks like real currency.

Write a Python script that does the following:
1. Create a variable called `total_bill` with the value `145.67`
2. Create a variable called `people_count` with the value `3`
3. Calculate each person's share by dividing `total_bill` by `people_count`. Store this in a variable called `raw_share`.
4. Use a **built-in math function** to round `raw_share` to exactly **2 decimal places**. Store this in a variable called `final_share`.
5. Use an **augmented assignment operator** (like `+=`, `-=`, etc.) to add a `$5.00` tip to the `final_share` variable.
6. Use an **f-string** to print a message like: `"Each person owes: $X.XX"` (replace X.XX with your final variable).
### 💻 Write Your Code Here
```python



```
___
## 💡 Pro-Tip: The Currency Trait (`:.2f`)
When rounding decimal numbers for currency, Python's `round()` function will automatically drop trailing zeros. For example, `$53.50` will print as `$53.5`.

To force Python to always display exactly **two decimal places** for money, skip `round()` and use the `:.2f` formatting rule inside your f-string.

```python
price = 53.50

# Problem: round() drops the zero
print(f"Price: {round(price, 2)}")  # Output: \$53.5

# Solution: :.2f forces two decimals
print(f"Price: {price:.2f}")       # Output: \$53.50
```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 04: Booleans and Logic**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F04-Booleans-and-Logic)