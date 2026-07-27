---
tags:
  - python/data-structures
  - core-concepts
links:
  - "[[python_roadmap]]"
date_created: 2026-07-24
---
# Dictionaries

A **dictionary** (`dict` data type) is an **Insertion ordered** and **changeable** collection of data stored in **Key-Value pairs**, wrapped inside **curly braces `{}`**. 

Instead of index positions, you assign a custom **label (Key)** to a piece of **data (Value)**.
___
## 🏗️ Creating and Reading Dictionaries
Every entry inside a dictionary is written as `key: value`, separated by commas. 

```python
# A dictionary representing a user profile record
user_profile = {
    "username": "Prince_Skywalker",
    "level": 15,
    "is_admin": False
}

# Reading data: Attach square brackets [] containing the text KEY name!
print(user_profile["username"])  # Output: Prince_Skywalker
print(user_profile["level"])     # Output: 15
```
### 🧭 The Ordering Rule: Labels vs. Index Numbers
While Lists and Tuples organize data using sequential index numbers (`0, 1, 2`), Dictionaries are organized purely by **Key Labels**. 

Even though modern Python retains the sequence in which you typed your keys (Insertion Order), dictionaries do not possess numerical address slots.

```python
user_profile = {
	"username": "Prince_Skywalker", 
	"level": 15
}

# ❌ THIS CRASHES INSTANTLY:
# Python checks for a text key named 0, fails, and throws a KeyError!
print(user_profile[0]) 

```

>[!NOTE]
If your data requires a strict numerical sequence layout (`0, 1, 2`), use a **List**. If your data requires descriptive row data categorization (`key: value`), use a **Dictionary**.

>[!WARNING]
If you try to lookup a Key that does not exist (like `user_profile["email"]`), Python will instantly crash your script with a `KeyError`. 
### 🎯 Solution for KeyError: The `.get()` Method
To prevent crashes, you can use the `.get()` method instead of brackets. 
If the Key doesn't exist, it safely returns `None` instead of crashing!

```python
# Safe lookup:
print(user_profile.get("email"))  # Output: None (No crash!)

# Custom backup default value:
print(user_profile.get("email", "no_email@provided.com")) # Output: no_email@provided.com
```
#### 🛡️ Managing Missing Keys: Brackets `[]` vs. `.get()`
Choosing how to look up a key depends on whether the data is mandatory or optional:
1. **Use Brackets `user_profile["username"]`**: 
	When the key is **mandatory**. If it is missing, Python throws a `KeyError` and crashes. This is exactly what you want for critical data (like bank info or passwords) so the script stops before causing damage.
2. **Use the `.get()` Method `user_profile.get("theme", "light")`**: 
	When the key is **optional**. If the key is missing, it safely returns a fallback default value (like `"light"`) instead of crashing the program.
___
## 🧳 Modifying Dictionaries (Changeable / Mutable)
Dictionaries are fully changeable. You can **add** new pairs, **update** current values, or **delete** entries dynamically using their own toolbox.

```python
player_data = {
	"name": "Alex",
	"gold": 50
}

# 1. Updating a value: Just re-assign the key!
player_data["gold"] = 75  # Gold updates from 50 to 75

# 2. Adding a completely new Key-Value pair:
player_data["inventory"] = ["sword", "shield"]

# 3. Deleting a pair by its Key name:
del player_data["name"]

print(player_data)  # Output: {'gold': 75, 'inventory': ['sword', 'shield']}
```
___
## 🔏 Core Dictionary Extraction Methods
Sometimes you only want to look at the labels, the data inside, or both. Python provides three essential methods to extract components:

| Method      | What it spits out    | Example Code       | Output                                      |
| :---------- | :------------------- | :----------------- | :------------------------------------------ |
| `.keys()`   | List of all labels   | `profile.keys()`   | `dict_keys(['username', 'level'])`          |
| `.values()` | List of all data     | `profile.values()` | `dict_values(['Prince_Skywalker', 15])`     |
| `.items()`  | List of all pairings | `profile.items()`  | `dict_items([('username', 'Prince'), ...])` |
___
## 🔄 Looping Through Dictionaries
When looping through dictionaries, you pair a `for` loop with the `.items()` method. This allows you to unpack **both the Key and the Value at the same time** using two temporary placeholders!

```python
system_status = {
    "Database": "Online",
    "API_Gateway": "Online",
    "Payment_Service": "Offline"
}

# Using two placeholders: 'service_name' for Key, 'status' for Value
for service_name, status in system_status.items():
    print(f"📡 Node: {service_name} is currently [{status}]")
```
___
## 🛠️ Practice Playground
Run this live server configuration stream modifier inside your vault to see how dictionaries manage JSON-like assets:

```python
# Mock client payload packet
api_request = {
    "endpoint": "/v1/users",
    "method": "POST",
    "ip_address": "192.168.1.50"
}

# Add a processing timestamp
api_request["status_code"] = 200

# Safely read and copy incoming parameters without modifying the dictionary
client_ip = api_request.get("ip_address")
secure_token = api_request.get("auth_token", "GUEST_ACCESS")

print(f"Incoming Request from IP: {client_ip}")
print(f"Security Clearance Tier: {secure_token}")
print(f"Full Payload Record: {api_request}")
```
___
# 🎯 Challenge 11: The User Session Manager

### 📜 Instructions
You are building the account backend for an online application. When a user logs in, your server receives an insertion-ordered data packet representing their profile. You need to inspect, update, and manage this session profile.

Write a Python script that does the following:
1. Create a starting dictionary called `user_session` with these initial **Key-Value pairs**:
   - `"user_id"`: `1092`
   - `"username"`: `"Prince_Skywalker"`
   - `"status"`: `"active"`
2. The user just unlocked an account achievement. **Update** their profile by adding a completely new Key-Value pair: `"achievement"` set to `"First Code Run"`.
3. Use a standard **bracket lookup `[]`** to read the user's mandatory `"username"` and print it inside an f-string: `"Welcome back, [username value]!"`.
4. **Safe Verification Check:** Use the **`.get()` method** to search for an optional security key named `"auth_token"`. Because it is missing, provide a custom default fallback string: `"GUEST_ACCESS"`. Print it inside an f-string: `"Clearance Tier: [token value]"`.
5. Use a `for` loop paired with the **`.items()` method** to unpack and iterate through all pairings in your final dictionary. Print each pair out on its own line like this: `"⚙️ Parameter: [Key Label] -> [Value Data]"`.
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 12: Sets**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F12-Sets)