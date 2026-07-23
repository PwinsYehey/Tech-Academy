---
tags:
  - python/control-flow
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-23
---
# For Loops and Ranges

A **`for` loop** is used to iterate over a sequence (like a string, a list, or a series of numbers). It repeats its inner code block once for every single item in that sequence.
___
## 🏗️ 1. Looping Through Text (String Iteration)
Because a string is just a chain of individual characters, a `for` loop can step through it letter-by-letter automatically. 

```python
word = "CODE"

# Read this as: "For every single letter INSIDE the word..."
# 'letter' is a temporary placeholder variable that holds the current character
for letter in word:
    print(f"Character: {letter}")
```
### 🔍 Anatomy of the Loop Line: `for letter in word:`
To understand how Python reads this line, break it down into its two core mechanics:
1. **The Temporary Placeholder (`letter`)**: This is a custom variable you create on the fly. You can name it anything you want (e.g., `char`, `x`, `letter`). Python assigns it a new value automatically every round, holding onto the current item in the sequence.
2. **The Directional Bridge (`in`)**: The `in` keyword acts as a gatekeeper. It tells Python to step inside the target sequence (`word`) and pull out its contents one by one, from the very first element (index 0) to the absolute end.
### ⏳ Step-by-Step Execution:
* **Round 1:** The `in` keyword grabs the first character `'C'`. Python assigns it to the `letter` placeholder. The block runs and prints: `Character: C`.
* **Round 2:** The loop resets. The `in` keyword moves to the next character `'O'`. The `letter` placeholder updates to `'O'`. The block runs and prints: `Character: O`.
* **Rounds 3 & 4:** This repeats automatically for `'D'` and `'E'`, then shuts down cleanly when the sequence is empty.
___
## 🔢 The `range()` Built-in Function
When you want to repeat an action an exact number of times, you pair the `for` loop with the global built-in function **`range()`**. 

>[!INFO]
>`range(5)` generates 5 numbers, but it starts counting from **0** and stops *before* the target number (`0, 1, 2, 3, 4`).

```python
# Repeat an action exactly 3 times
for i in range(3):
    print(f"Round number: {i}")
```
### 🎛️ Tuning the Range: Start, Stop, and Step
The `range()` function can take up to three configuration numbers inside its parentheses: `range(start, stop, step)` [💡].

```python
# 1. range(start, stop) -> Starts at 5, stops BEFORE 9
for num in range(5, 9):
    print(num)  # Output: 5, 6, 7, 8

# 2. range(start, stop, step) -> Count from 0 to 10 by jumping 2s
for even_num in range(0, 11, 2):
    print(even_num)  # Output: 0, 2, 4, 6, 8, 10

# 3. Counting Backwards -> Use a negative step
for countdown in range(3, 0, -1):
    print(countdown)  # Output: 3, 2, 1
```

---
## 🔏 The `break` and `continue` Laws
Just like `while` loops, `for` loops fully support the control keywords to abort early or skip rounds.

```python
# Skip a specific number using continue
for score in range(1, 5):
    if score == 3:
        continue # Skip round 3 entirely!
    print(f"Logged score: {score}")
```
___
## 🛠️ Practice Playground
Run this automated scanner simulation inside your vault to see how a `for` loop evaluates text strings character-by-character:

```python
serial_number = "TX-892-B"
has_error = False

print(f"Initiating security scan for hardware: {serial_number}...")

for character in serial_number:
    # Check if the hardware contains an illegal character
    if character == "9":
        print("CRITICAL ERROR: Malicious element '9' detected inside sequence!")
        has_error = True
        break # No need to keep scanning, terminate the loop instantly!
    
    print(f"Processing node... [{character}] OK")

if has_error == False:
    print("SCAN COMPLETE: Hardware integrity verified.")
```
___
# 🎯 Challenge 8: The Automated Password Guard
### 📜 Instructions
You are building an automatic security scanner for a system password. The password must be scanned letter-by-letter to ensure it contains a special character. If an illegal character (like an exclamation mark `!`) is detected, the password must be rejected immediately.

Write a Python script that does the following:
1. Create a variable `user_password` and set it to `"Secret!Pass"`
2. Create a safety flag variable called `is_compromised` and initialize it to `False`.
3. Use a **`for` loop** to look at every `character` inside the `user_password` string.
4. Inside the loop:
   - Check if the current character is equal to `!`
   - If it is equal to `!`, print out: `"🚨 SECURITY ALERT: Illegal character '!' detected!"`
   - Inside that same check, flip your `is_compromised` flag variable to `True` and use a keyword to **abort the loop instantly**.
1. **After the loop is completely finished (outside the loop):** Use an `if` statement to check your flag. If `is_compromised == False` (or using `if not is_compromised:`), print out: `"✅ PASSWORD SECURE: No illegal characters found."`
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 09: Lists**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F09-Lists)