---
tags:
  - python/basics
  - core-concepts
links:
  - "[[Python Roadmap]]"
date_created: 2026-07-21
---
# Booleans and Logic

A **Boolean** (written as `bool`) is a data type that can only hold one of two possible values: **`True`** or **`False`**. They act as the switches that allow your code to make decisions.

>[!WARNING]
Python is case-sensitive! You must capitalize the first letter (`True` and `False`). Writing `true` or `false` in lowercase will crash your code.

___
## 🎛️ Comparison Operators (Generating Booleans)
You generate Booleans by comparing two values. Python evaluates the comparison and spits out either `True` or `False`.

| Operator | Meaning | Example Code | Result |
| :--- | :--- | :--- | :--- |
| `==` | **Equal to** | `5 == 5` | `True` |
| `!=` | **Not equal to** | `5 != 3` | `True` |
| `>` | Greater than | `5 > 10` | `False` |
| `<` | Less than | `5 < 10` | `True` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `4 <= 3` | `False` |

>[!Note]
A **single equals sign (`=`)** is for **assigning values** to variables (e.g., `x = 5`).
A **double equals sign (`==`)** is for **asking a question** (e.g., "Does x equal 5?").

---
## 🧮 Logical Operators (Combining Booleans)
You can chain multiple comparison checks together using the three logical operators: `and`, `or`, and `not`.

### 🤝 `and` (Both must be True)
Returns `True` only if **every single condition** is true. If even one part is false, the whole thing becomes false.
```python
is_weekend = True
is_sunny = False

# True and False -> False
go_to_beach = is_weekend and is_sunny 

print(go_to_beach)  # Output: False
```

### 🚪 `or` (At least one must be True)
Returns `True` if **at least one** condition is true. It only returns false if every single item is false.
```python
has_cash = False
has_card = True

# False or True -> True
can_buy_food = has_cash or has_card

print(can_buy_food)  # Output: True
```

### 🔄 `not` (The Inverter)
Flips a Boolean value to its exact opposite. It turns `True` into `False`, and `False` into `True`.
```python
is_locked = True

is_open = not is_locked
print(is_open)  # Output: False
```
___
## 🛠️ Practice Playground
Run this block in your vault to see how logic gates combine to check complex conditions:
```python
# Player Stats
player_level = 12
has_magic_key = True
is_poisoned = False

# Condition 1: Can the player pass through the Boss Door?
# Rule: Must be level 10 OR have the magic key
can_enter_boss = (player_level >= 10) or has_magic_key

# Condition 2: Is the player perfectly safe?
# Rule: Must not be poisoned
is_safe = not is_poisoned

print(f"Can enter boss room: {can_enter_boss}")
print(f"Is player perfectly safe: {is_safe}")
```
___
# 🎯 Challenge 4: The Security Gatekeeper
### 📜 Instructions
Imagine you are writing the security screening logic for a high-tech corporate building. A person wants to enter the vault room. 

Write a Python script that calculates if they are allowed access based on these variables:
1. Create a variable `has_id_badge` and set it to `True`.
2. Create a variable `is_employee` and set it to `False`.
3. Create a variable `has_guest_pass` and set it to `True`.
4. Calculate a boolean variable called `can_enter_building`. 
   * **Rule:** A person can enter the building if they have an ID badge **AND** they are an employee... **OR** if they have a guest pass. 
   * *(Hint: Use parentheses to group your "badge and employee" check together!)*
1. Use an f-string to print a clean message showing the final result, like: `"Access Granted: True/False"`.
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 05: Type Casting and User Input**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F05-Type-Casting-and-User-Input)