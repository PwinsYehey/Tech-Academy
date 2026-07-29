---
tags:
  - python/architecture
  - core-concepts
links:
  - "[[python_roadmap]]"
date_created: 2026-07-25
---
# Custom Functions

A **custom function** is a reusable block of code that only runs when you explicitly call its name. Functions allow you to break massive scripts down into clean, modular, and organized sub-systems.

To build a function, you use the **`def`** keyword (short for *define*), give it a descriptive name, add parentheses `()`, and indent the code block underneath.
___
## 🏗️ Defining vs. Calling a Function
Creating a function is like writing a **recipe blueprint**. It sits silently in your computer's memory until you explicitly **call** it to execute the instructions.

```python
# 1. DEFINING the machine blueprint
def boot_system():
    print("Initializing core backend server...")
    print("Establishing database handshake link... OK")

# 2. CALLING the machine to run!
boot_system()
boot_system()  # Runs a second time instantly!
```
___
## 🎛️ Inputs: Parameters vs. Arguments
To make a function dynamic, you can design input slots inside its parentheses. 
* **Parameter (The Slot)**: The **temporary variable** label written inside the function definition blueprint.
* **Argument (The Real Data)**: The **actual value** you pass into those slots when you call the function to run.

```python
# 'username' and 'access_tier' are input PARAMETERS (slots)
def register_user(username, access_tier):
    print(f"Account created: {username}")
    print(f"Security Clearance Level: [{access_tier.upper()}]\n")

# Re-running the same machine with completely different ARGUMENTS (data)
register_user("Prince_Skywalker", "admin")
register_user("Alex_Solo", "guest")
```
___
## 🚪Outputs: The Power of `return`
Up until now, your practice snippets have used `print()` to spit text onto the screen. However, `print()` only shows text to a human observer—it does **not** hand the result back to your program to use in other calculations.

To pass a calculated result out of a function box and save it into a variable, you must use the **`return`** keyword.

```python
# This machine calculates a tax value and returns the raw math answer
def calculate_tax(subtotal):
    tax_amount = subtotal * 0.12
    return tax_amount  # Passes the raw data OUT of the function box!

# Catching the returned data inside a variable outside the function box
final_invoice_tax = calculate_tax(100.00)

print(f"Invoice Tax Processing: ${final_invoice_tax:.2f}")  # Output: $12.00
```

>[!NOTE]
**The Return Law:** The absolute second a function hits a `return` statement, it terminates instantly! Any lines of code written directly below a `return` inside that function box are completely dead and will never execute.

___
##  The print() vs return
### ❌ Scenario A: The `print()` Dead-End

``` python
def calculate_score_print(base_points):
    bonus = base_points * 2
    print(bonus) # 📺 Shows the number to the human, but destroys it right after!

# Try to save the score to use for a multiplier later
player_score = calculate_score_print(10)
# The human sees '20' flash on the screen...
 
# But let's check what is actually saved inside the 'player_score' box:
print(f"Saved Data: {player_score}")  # Output: Saved Data: None

```

### 🍏 Scenario B: The `return` Engine
``` python
def calculate_score_return(base_points):
    bonus = base_points * 2
    return bonus # 🫴 Hands the raw number data out of the machine box!

# Run the machine and catch the handed data
player_score = calculate_score_return(10)

# data is safely trapped inside our variable box! We can use it for calculations:
final_score = player_score + 500
print(f"Final Score: {final_score}")  # Output: Final Score: 520

```

- Use **`print()`** when your only goal is to speak to a human observer (like showing a success log, a security warning alert, or a decorative menu interface).
- Use **`return`** when your goal is to speak to another part of your program (like calculating data rows, formatting a database string, or checking an authentication token) so a variable can catch it and pass it forward.
___
## 🛠️ Practice Playground
Run this live backend user authorization engine inside your vault to see how parameters, arguments, and return values process data modules dynamically:

```python
# Core logic processor
def generate_player_token(user_id, rank):
    # Sanitize and compile data parameters
    formatted_rank = rank.strip().upper()
    token = f"TOKEN-ID:{user_id}-{formatted_rank}"
    
    return token  # Hand the compiled token data back to our script
    print("This line will never print because it sits below a return statement!")

# 1. Running the machine and catching the returned result
user_token_01 = generate_player_token(1092, "   moderator   ")

# 2. Displaying our caught payload output
print("--- BACKEND PAYLOAD RETRIEVED ---")
print(f"Generated Session Security Access Token: {user_token_01}")
```
___
# 🎯 Challenge 13: The API Invoice Processor
### 📜 Instructions
You are building a backend billing module for a SaaS web platform. When a user checks out, your server needs to automatically calculate their tax amount and generate a standardized tracking string to pass to the database.

Write a Python script that does the following:
1. Define a function named **`process_invoice`** that accepts two input parameters:
   - `price` (an integer or float)
   - `username` (a string)
2. Inside the function box:
   - Calculate a tax value by multiplying the `price` by `0.12` (12% tax rate) and store it in a variable named `tax`.
   - Clean up the `username` input using `.strip().lower()` so it is completely sanitized.
   - Use an f-string to build a tracking string layout: `"USER:[sanitized_name]-AMT:[price]-TAX:[tax]"` and store it in a variable named `invoice_record`.
   - Use the correct keyword to **hand the `invoice_record` text string OUT** of the function capsule so a variable outside can catch it.
3. **Outside the function (The main script):** Run your `process_invoice` function machine and pass it two real arguments: `150.00` and the messy name string `"   Prince_Skywalker   "`.
4. Catch the returned result from your function inside a fresh variable named **`final_payload`**.
5. Use a standard `print()` statement to display your caught variable to the screen so you can verify the output.
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 14: Sets**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F14-Scope)