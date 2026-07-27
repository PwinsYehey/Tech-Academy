---
tags:
  - python/control-flow
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-22
---
# While Loops

A **`while` loop** is an automation structure that repeatedly executes a block of code **as long as a specific condition remains `True`**. Think of it like a continuous `if` statement that keeps circling back to the top.
___
## 🏗️ The Anatomy of a Safe Loop
Every healthy loop requires three structural pillars to ensure it performs its job and shuts down safely.
1. **The Starting State (Initialization)**: A variable created *before* the loop starts to track its progress.
2. **The Condition Box**: The rule that keeps the gate open.
3. **The Step (Iteration)**: A mechanism *inside* the loop that modifies the tracking variable every round so the condition eventually becomes `False`.

```python
# 1. Starting State
countdown = 3

# 2. Condition Box (Loop keeps running while this is True)
while countdown > 0:
    print(f"T-minus {countdown}...")
    
    # 3. The Step (Counting down by 1)
    countdown -= 1 

print("🚀 Blastoff!")
```
___
## 🚨 The Danger Zone: Infinite Loops
If you forget **The Step**, or if your condition can never turn `False`, you create an **Infinite Loop**. Your computer will run the block billions of times until your system freezes or crashes.

```python
# ⛔ EXTREMELY DANGEROUS CODE - DO NOT RUN
health = 10

while health > 0:
    print("Player is alive!")
    # Because 'health' never changes inside this block, 
    # health > 0 is True FOREVER. 
```
___
## 🛠️ Controlling Loops: `break` and `continue`
Python gives you two powerful utility keywords to manipulate loops from the inside on the fly.
### ⏹️ `break` (The Emergency Exit)
Instantly kills the loop and jumps completely outside the block, even if the main loop condition is still `True`.

```python
# Creating an intentionally infinite loop that we control from inside
while True:
    command = input("Type 'exit' to quit: ").strip().lower()
    
    if command == "exit":
        print("Shutting down system...")
        break # Aborts the loop instantly!
    
    print(f"Processing command: {command}")
```

### 🔄 `continue` (The Skip Round Button)
Instantly skips the current iteration of the loop, then continues to the next iteration.

```python
floor = 0

while floor < 5:
	floor += 1

	if floor == 3:
		continue # Skip printing for floor 3, then continue printing next floor

	print(f"Elevator arrived at floor {floor}")
```
___
## 🛠️ Practice Playground
Run this login simulator script in your playground to see a practical use of an interactive `while` loop:

```python
# Hardcoded security setup
correct_pin = "1234"
attempts_left = 3

while attempts_left > 0:
    user_guess = input(f"Enter 4-digit PIN ({attempts_left} attempts remaining): ")
    
    if user_guess == correct_pin:
        print("Access Granted! Welcome to the vault.")
        break # Correct PIN found, no need to ask again!
    else:
        attempts_left -= 1
        print("Incorrect PIN.")

if attempts_left == 0:
    print("SYSTEM LOCKED: Out of attempts.")
```
---
# 🎯 Challenge 7: The Hot-and-Cold Number Guesser
### 📜 Instructions
You are building a classic retro mini-game. The game has a secret number locked in, and the user gets a limited number of attempts to guess it. The loop should keep asking until they get it right or run out of turns.

Write a Python script that does the following:
1. Create a variable called `secret_number` and set it to `7`.
2. Create a variable called `guesses_left` and set it to `4`.
3. Build a `while` loop that keeps running **as long as `guesses_left` is greater than 0**.
4. Inside the loop:
   - Decrease `guesses_left` by `1` immediately.
   - Use `input()` to ask the user: `"Guess the secret number (1-10): "` and cast it to an **integer**.
   - If their guess matches `secret_number`, print `"🎉 YOU WIN! You found the secret number!"` and use a keyword to **exit the loop instantly**.
   - If their guess is less than `secret_number`, print `"Too low!"`.
   - If their guess is greater than `secret_number`, print `"Too high!"`.
1. **After the loop (outside it):** Check if they ran out of guesses without winning. If `guesses_left == 0`, print `"💀 GAME OVER! Better luck next time."`
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 08: For Loops and Ranges**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F08-For-Loops-and-Ranges)