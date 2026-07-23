---
tags:
  - python/data-structures
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-24
---
# Tuples

A **tuple** (`tuple` data type) is an **ordered** and **unchangeable** collection of items wrapped inside **parentheses `()`**. 

Once you lock items inside a tuple, they are **completely frozen**. You **cannot add, remove, or modify a single thing**.
___
## 🏗️ Creating and Indexing Tuples
Tuples are **ordered**, that use index positions starting at **0**, exactly like lists and strings.

```python
# System configurations are perfect for tuples
server_config = ("192.168.1.1", 8080, "secure_admin")

print(server_config)   # Output: "192.168.1.1", 8080, "secure_admin (all items)
print(server_config[-1])  # Output: secure_admin (Last item shortcut)
```

>[!NOTE]
**The Single-Item Trait:** If you ever want to create a tuple containing only **one** single item, you *must* include a trailing comma `,` after the item, or Python will mistake it for a standard math parenthesis string!

```python
broken_tuple = ("admin")   # Python reads this as a plain String (str)!
working_tuple = ("admin",) # Python reads this as a real Tuple (tuple)!
```
___
## 🔒 The Golden Law: Unchangeable (Immutable)
The official computer science word for unchangeable is **immutable**. Because tuples are frozen in computer memory, trying to use list methods on them will crash your program.

```python
screen_dimensions = (1920, 1080)

# ❌ THIS WILL CRASH THE PROGRAM:
screen_dimensions.append(60) 
screen_dimensions = 2560 

# Python will instantly throw a 'TypeError' because tuples cannot be mutated!
```
___
## 🧳 Core Tuple Methods and Functions
Because tuples cannot change, their built-in toolbox is tiny. They only contain tools to **read** data, never to write or modify it.

| Tool           | Type     | What it does                          | Example Code       | Output |
| :------------- | :------- | :------------------------------------ | :----------------- | :----- |
| `.count(item)` | Method   | Counts how many times an item appears | `points.count(7)`  | `2`    |
| `.index(item)` | Method   | Finds the address position of an item | `points.index(10)` | `0`    |
| `len()`        | Function | Counts the total elements inside      | `len(points)`      | `3`    |

```python
points = (10, 7, 7)

print(points.count(7))  # Output: 2
print(points.index(7))  # Output: 1 (Finds the VERY FIRST match it hits)
```
___
## 📦 Tuple Unpacking (The Developer Shortcut)
One of the coolest features of a tuple is **unpacking**. It allows you to extract all the items inside a tuple and assign them to separate, individual variables on a single line!

```python
# A tuple holding coordinate coordinates
coordinate = (40.7128, -74.0060)

# Unpacking the tuple into two fresh variables
latitude, longitude = coordinate

print(f"Latitude: {latitude}")    # Output: 40.7128
print(f"Longitude: {longitude}")  # Output: -74.0060
```

>[!NOTE]
*The number of variables on the left side MUST match the exact number of items inside the tuple, or Python will throw an error.*

___
## 🚨 Warning: When to use a List vs. a Tuple
Choosing between them in the real world comes down to data safety:
* Use a **List `[]`** when your data needs to grow, shrink, or change dynamically (like a shopping cart, a game inventory, or a leaderboard stream).
* Use a **Tuple `()`** when your data must be protected against accidental changes (like GPS coordinates, screen resolution boundaries, server ports, or months of the year).
___
## 🛠️ Practice Playground
Run this server node simulation inside your vault to see tuple unpacking and immutability in action:

```python
# Hardcoded server parameters
database_node = ("postgre-db-01", "localhost", 5432)

# Unpacking the configuration parameters for our backend setup
node_name, host, port = database_node

print("Establishing database handshake link...")
print(f"Targeting Node: {node_name} via Port: {port}")

# Loop through a tuple exactly like a list!
print("\nPrinting full system array metadata:")
for details in database_node:
    print(f"-> {details}")
```
___
# 🎯 Challenge 10: The Server Environment Configurator
### 📜 Instructions
You are setting up the global configuration parameters for a backend web server application. These settings are highly sensitive and must be frozen in memory so no other script can accidentally modify them while the application is running.

Write a Python script that does the following:
1. Create a **tuple** named `server_config` containing three items in this exact order:
   - Host address (string): `"127.0.0.1"`
   - Port number (integer): `8080`
   - Security status (string): `"active"`
2. Attempting to modify a tuple will cause a crash, but let's practice **reading** metadata. Use a global function to count the total number of configuration parameters inside `server_config`. Print it out inside an f-string: `"Total parameters locked: X"`.
3. Use a tuple method to check the **index position** of the port number `8080` inside your tuple. Print it out inside an f-string: `"Port parameter found at index: X"`.
4. Use **tuple unpacking** to extract all three items from `server_config` into three separate variables named: `host`, `port`, and `status`.
5. Use a single f-string to display the final unpacked system card output exactly like this:
   ```text
   --- SYSTEM LIVE ---
   Host: [host value]
   Port: [port value]
   Status: [status value]
   ```
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 11: Dictionaries**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F11-Dictionaries)