---
tags:
  - python/data-structures
  - core-concepts
links:
  - "[[Python MOC]]"
date_created: 2026-07-25
---
# Sets

A **set** (`set` data type) is an **unordered** collection of **unique** items wrapped inside **curly braces `{}`**. 
Unlike a dictionary, sets contain standalone items instead of `key: value` pairs.
___
## 🏗️ Core Mechanics: Unique and Unordered
Sets have two golden rules that make them completely different from Lists and Tuples:
1. **Duplicates are Banned**: If you try to add an item that already exists inside the set, Python ignores it completely.
2. **Completely Unordered**: Sets do not have index positions (`0, 1, 2`) and they do **not** maintain insertion order. Python shuffles the items in memory constantly to maximize lookup speeds.

```python
# Duplicates are automatically scrubbed out on creation
registered_emails = {"user@test.com", "admin@test.com", "user@test.com"}

print(registered_emails)  
# Output: {'admin@test.com', 'user@test.com'} (The duplicate is gone!)

# ❌ THIS CRASHES INSTANTLY:
print(registered_emails[0])  
# TypeError: 'set' object is not subscriptable (No index lookups allowed!)
```
___
## 🧳 Modifying Sets (Changeable / Mutable)
While you cannot change an item *in place* (because there are no indexes), you can **freely add** and **drop items** from the master set container.

| Method           | What it does             | Example Code          | Resulting Set                             |
| :--------------- | :----------------------- | :-------------------- | :---------------------------------------- |
| `.add(item)`     | Adds a brand-new item    | `tags.add("python")`  | Inserts the item if unique                |
| `.remove(item)`  | Deletes an item by value | `tags.remove("css")`  | Removes item (Crashes if missing)         |
| `.discard(item)` | Safely deletes an item   | `tags.discard("css")` | Removes item safely (No crash if missing) |

```python
active_sessions = {"session_01", "session_02"}

active_sessions.add("session_03")      # Adds item
active_sessions.discard("session_99")  # Safe: Does nothing since key is missing

print(active_sessions)
```
___
## 🌎 The Ultimate Trick: Deduping Lists
The most common real-world use case for a set is to instantly strip out duplicate entries from a standard List by passing the list through the `set()` conversion function.

```python
# A list contaminated with duplicate player IDs from a database
raw_player_ids = [109, 204, 109, 305, 204]

# Step 1: Cast the list into a set to erase duplicates
unique_set = set(raw_player_ids)  # {109, 204, 305}

# Step 2: Cast it back into a standard list so you can sort or index it again!
clean_list = list(unique_set)

print(clean_list)  # Output: [109, 204, 305] (Cleaned and restored!)
```
___
## 🔄 Looping Through a Set
Even though sets have no index values, you can still step through them item-by-item using a standard `for` loop placeholder bridge!

```python
security_alerts = {"firewall_trip", "port_scan"}

for alert in security_alerts:
    print(f"SYSTEM THREAT DETECTION FLAGGED: {alert}")
```
___
## 🚨 Final Data Structure Cheat Sheet
To wrap up Phase 3, here is how to select the right tool for any real-world problem:

| Structure | Brackets | Ordered by | Changeable? | Unique Items Only? | Common Use Case |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **`list`** | `[]` | Numeric Indexes (`0,1,2`) | **Yes** | No | Shopping Carts, Inventories |
| **`tuple`**| `()` | Numeric Indexes (`0,1,2`) | **No** (Frozen) | No | Server Ports, GPS Locations |
| **`dict`** | `{}` | Key Labels (`key:val`) | **Yes** | Keys must be unique | API Payloads, User Accounts |
| **`set`**  | `{}` | **Unordered Chaos** | **Yes** | **Yes** (Bans Dups) | Removing Duplicates, Tags |
___
## 🛠️ Practice Playground
Run this live security log analyzer inside your vault to see how sets dynamically sanitize duplicate incoming network events:

```python
# A raw database log of incoming network connections (flooded with duplicates)
raw_traffic_log = ["192.168.1.1", "10.0.0.5", "192.168.1.1", "172.16.0.2", "10.0.0.5"]

print(f"📊 Total Raw Log Entries: {len(raw_traffic_log)}")

# 1. Clean the list instantly by converting it to a Set
unique_ips = set(raw_traffic_log)
print(f"🔒 Total Unique IP Addresses Detected: {len(unique_ips)}")

# 2. Add a new connection to our unique monitoring tray
unique_ips.add("192.168.1.99")

# 3. Safely drop an IP without risking a system crash
unique_ips.discard("10.0.0.5")  # Removes the item
unique_ips.discard("8.8.8.8")   # Missing IP: Bypassed safely with NO crash!

print("\n--- Active Unique IP Monitoring Matrix ---")
for ip in unique_ips:
    print(f"📡 Tracking active traffic node -> {ip}")
```
___
# 🎯 Challenge 12: The Database IP Cleaner
### 📜 Instructions
You are auditing the security traffic logs for a company server. The network database generated a raw list of IP addresses that accessed a secure portal, but it is heavily contaminated with duplicate records from repetitive background syncs. You need to sanitize the data instantly.

Write a Python script that does the following:
1. Create a starting list named `raw_log` with these contaminated duplicate entries:
   `["192.168.1.1", "10.0.0.4", "192.168.1.1", "172.16.5.9", "10.0.0.4"]`
2. Use a global function to count the total entries in `raw_log` and print it out: `"Raw log entries received: X"`.
3. **The Deduping Trick:** Cast the list into a **Set** named `unique_ips` to instantly scrub out all duplicate addresses.
4. Print out the total number of items remaining inside your `unique_ips` set: `"Clean unique IPs remaining: X"`.
5. Use a method to **safely remove** the address `"10.0.0.4"` from your unique set. Use the specific method that **guarantees no system crashes** even if the item wasn't found!
6. Use a `for` loop to iterate through your final clean set and print out each active address on its own line like this: `"📡 Protected Node Address: [IP Value]"`.
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 1 — Lesson 13: Sets**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%201%20-%20Core%20Concepts%2F13-Custom-Functions)