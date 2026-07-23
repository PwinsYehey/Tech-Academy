---
tags:
  - python/data-structures
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-23
---
# Lists

A **list** is an **ordered (index)** and **changeable (mutable)** collection of items wrapped inside **square brackets `[]`**. 

Lists **can hold any data type**, including strings, integers, floats, and booleans.

Instead of creating 5 different variables for 5 items, you can store them all inside a single list container.
___
## 🏗️ 1. Creating and Indexing Lists
Lists are **ordered**. This means every item you put inside a list receives a permanent address number called an **index**, starting exactly at **0**. Python will always remember this sequence.

```python
# A list of arcade games
arcade_games = ["Pac-Man", "Tetris", "Doom"]

# Accessing items using their index numbers
print(arcade_games[0])   # Output: Pac-Man (The very first item)
print(arcade_games[1])   # Output: Tetris (The second item)
print(arcade_games[-1])  # Output: Doom   (The last item shortcut)
```

___
## 🧳Modifying List with Methods (With Dots `.`)
Lists are **changeable** (mutable). Once a list is created, you can add, delete, or extract items dynamically using their own built-in methods.

| Method               | What it does                                            | Example Code              | Resulting List                     |
| :------------------- | :------------------------------------------------------ | :------------------------ | :--------------------------------- |
| `.append(item)`      | Adds an item to the **very end**                        | `games.append("Zelda")`   | `[..., "Zelda"]`                   |
| `.insert(idx, item)` | Inserts an item at a **specific index**                 | `games.insert(1, "Pong")` | `"Pong"` becomes index 1           |
| `.remove(item)`      | Deletes a **specific item by name**                     | `games.remove("Doom")`    | Deletes `"Doom"`                   |
| `.pop()`             | **Extracts** the last item and hands it out.            | `games.pop()`             | Removes but saved in your variable |
| `.sort()`            | Sorts list **automatically** alphabetically/numerically | `games.sort()`            | Organizes the list                 |

```python
inventory = ["sword", "shield", "potion"]

inventory.remove("shield") 
print(inventory)  # Output: ['sword', 'potion']

inventory.sort()
print(inventory) # ['potion', 'sword']

# Our list is currently: ['potion', 'sword']
dropped_item = inventory.pop() 
print(inventory)     # Output: ['potion'] (Sword is removed from the list!)
print(dropped_item)  # Output: Sword    (But saved inside this variable!)

```

>[!WARNING]
>* You cannot use `.sort()` on a list containing mixed data types.
>* Python sorts uppercase letters before lowercase letters.

___
## 🌎 Built-in Functions Used on Lists (No Dots)
Just like strings, lists can be inspected using global, standalone functions.

| Function | What it inspects                  | Example Code      | Output |
| :------- | :-------------------------------- | :---------------- | :----- |
| `len()`  | Counts total items in the list    | `len(["A", "B"])` | `2`    |
| `max()`  | Finds highest number or character | `max([5, 12, 3])` | `12`   |
| `min()`  | Finds lowest number or character  | `min([5, 12, 3])` | `3`    |
```python
player_party = ["Prince", "Alex", "Sam", "Gemma"]

# Count the items
total_players = len(player_party)
print(f"Total active party members: {total_players}")  # Output: 4
```
___
## 🔄 Looping Through a List
Pairing a `for` loop with a list is an industry-standard way to look at data streams. The loop automatically steps through the collection item-by-item from index 0 to the end.

```python
players = ["Prince", "Alex", "Sam"]

# 'player' is the temporary placeholder; 'players' is the target list
for player in players:
    print(f"🎮 Active Arcade Player: {player}")
```
___
## 🛠️ Practice Playground
Run this live shopping cart inventory tracker inside your vault to watch lists mutate dynamically:

```python
# Starting cart setup
cart = ["laptop", "mouse", "keyboard"]

# 1. User updates their cart
cart.append("headphones")
cart.remove("mouse")

print(f"Shopping Cart Total Items: {len(cart)}")

# 2. Automatically generate invoices for remaining items
for item in cart:
    print(f"📦 Processing shipping container for: {item.title()}")
```
___
# 🎯 Challenge 9: The Arcade Leaderboard Manager
### 📜 Instructions
You are managing the high-score database for a retro arcade machine. Players are constantly achieving new scores, and you need to filter, sort, and update the top scores dynamically.

Write a Python script that does the following:
1. Create a starting list called `leaderboard` with these initial numbers: `[450, 1200, 890]`
2. A new player achieves an amazing score. Use a method to **add** the score `1500` to the very end of the list.
3. A player was caught cheating! Use a method to **remove** the score `450` from the list by its value name.
4. Use a global function to check how many active scores are remaining in the list, and print it out using an f-string: `"Total active scores: X"`.
5. Use a method to **sort** the leaderboard dynamically so that the **highest score sits at the very top** (index 0). 
6. Use a `for` loop to iterate through your final sorted leaderboard and print out each score on its own line like this: `"🏆 Top Score: [Score Value]"`.
### 💻 Write Your Code Here
```python
leaderboard = [450, 1200, 890]

leaderboard.append(1500)
leaderboard.remove(450)

print(f"Total active scores: {len(leaderboard)}")
leaderboard.sort(reverse=True)

for score in leaderboard:
    print(f"Top Score: {score}")
```

### 💻 Assignment
search about sort vs sorted. You should know the difference and when to use it.

###### ⏭️ Next Lesson
[**Module 1 — Lesson 10: Tuples**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F10-Tuples)