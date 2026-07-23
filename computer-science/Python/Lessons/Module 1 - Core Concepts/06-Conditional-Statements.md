---
tags:
  - python/control-flow
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-22
---
# Conditional Statements (`if`, `elif`, `else`)

Conditional statements allow your program to execute different branches of code depending on whether a specific condition resolves to `True` or `False`. 
___
## 🏗️ The Structure of a Decision
Python checks conditions from top to bottom. It will execute the code block of the **very first** condition that is true, and then skip all remaining blocks completely.
### 📐 The Indentation Rule
Unlike other languages that use brackets `{}`, Python relies entirely on **whitespace indentation** (usually 4 spaces or 1 tab) to know which lines belong inside a condition box. If you forget to indent, Python will throw an `IndentationError`.

```python
score = 85

if score >= 50:
    print("You passed!")  # Indented: Belongs inside the 'if' statement
print("This line always runs.")  # Not indented: Outside the 'if' structure
```
___
## 🚦 The 3 Control Keywords
### 1️⃣ Using `if` (The Initial Gate)
The starting point of any conditional check. You use a standalone `if` when you only care about checking one specific condition. If that condition is false, Python skips the block entirely and moves on.

```python
score = 95

# A single, simple check
if score >= 90:
    print("🌟 RANK S: Perfect Execution!")
```

>What if the player didn't get an S Rank, but still did incredibly well?

### 2️⃣ Adding `elif` (The Backup Options)
We use `elif` (short for "Else If") to chain additional specific checks (chain as many as you want). Python checks them in order and stops the moment it finds a `True` match.

```python
score = 85

if score >= 90:
    print("🌟 RANK S: Perfect Execution!")
elif score >= 80:
    print("🥇 RANK A: Excellent work!")  # Python catches this and stops!
elif score >= 70:
    print("🥈 RANK B: Good job!")
```

>What if the player scores really low and misses every single rank checkpoint? 

### 3️⃣ Level 3: Adding `else` (The Safety Net Catch-All)
We place `else` at the absolute bottom. It requires no condition text because it automatically runs if **every single check above fails**.

```python
score = 45

if score >= 90:
    print("🌟 RANK S: Perfect Execution!")
elif score >= 80:
    print("🥇 RANK A: Excellent work!")
elif score >= 70:
    print("🥈 RANK B: Good job!")
else:
    print("💀 GAME OVER: Try again!")   # All checks failed, so this runs!
```

---
## 🪆 Nested Conditionals (Conditions Inside Conditions)
You can place an entire `if` statement inside another `if` statement to perform deeper, multi-layered verifications.

```python
has_ticket = True
is_vip = False

if has_ticket:
    print("Welcome to the arena!")
    # Nested check begins
    if is_vip:
        print("Please proceed to the luxury lounge.")
    else:
        print("Please proceed to standard seating.")
else:
    print("Access Denied: Ticket required.")
```
___
## 🛠️ Practice Playground
Run this interactive test snippet in your vault. Change the values to simulate different scenarios:

```python
# System setup
user_role = "moderator"  # Try changing to: "admin", "user", "guest"
is_banned = False

if is_banned:
    print(" ACCESS DENIED: Account suspended.")
else:
    # Evaluating user tier clearances
    if user_role == "admin":
        print("Dashboard: Full system root access granted.")
    elif user_role == "moderator":
        print("Dashboard: Moderation clearance active.")
    elif user_role == "user":
        print("Dashboard: Standard profile loaded.")
    else:
        print("Dashboard: Public preview viewing only.")
```
___
# 🎯 Challenge 6: The Movie Ticket Pricing Gate
### 📜 Instructions
You are writing the backend logic for a digital cinema kiosk. The system needs to calculate ticket prices dynamically based on the customer's age and whether they have a student discount card.

Write a Python script that does the following:
1. Use `input()` to ask the user for their **Age** and immediately cast it to an integer.
2. Use `input()` to ask if they have a student card: `"Do you have a student card? (yes/no): "`. Store this text in a variable.
3. Determine the base ticket price using these conditions:
   - If they are under **12** years old, the ticket is **\$5.00**.
   - If they are **65** or older, the ticket is **\$7.00** (Senior citizen rate).
   - For anyone else (ages 12 to 64), the standard ticket is **\$12.00**.
4. **Nested Condition Check:** Inside that standard price block (12 to 64), check if their student card variable is equal to `"yes"`. If it is, give them a **\$3.00 discount** off the standard price!
5. Use an f-string to print a clean final message showing their calculated ticket price: `"Your final ticket price is: $X.XX"`. 
	* *(Hint: Use your currency formatting trick `:.2f` here to force trailing zeros!)*
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 07: While Loops**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F07-While-Loops)