---
tags:
  - python/cheat-sheet
  - python/data-structures
links:
  - "[[python_roadmap]]"
  - "[[09-lists]]"
  - "[[10-tuples]]"
  - "[[11-dictionaries]]"
  - "[[12-sets]]"
date_created: 2026-07-30
---
# Data Structures Matrix

A **data structure** is a specialized structural container or "digital storage layout" inside computer memory (RAM) used to **organize**, **group**, and **manage** multiple data items simultaneously. 

Selecting the correct data structure dictates how efficiently your code handles search lookup speeds, saves computer memory, and protects data fields from accidental modification.

| Structure   | Brackets | Ordered by                | Changeable?     | Allows Duplicates?           | Main Use Case                             |
| :---------- | :------- | :------------------------ | :-------------- | :--------------------------- | :---------------------------------------- |
| **`list`**  | `[]`     | Numeric Indexes (`0,1,2`) | **Yes**         | **Yes**                      | General purpose collection of mixed data. |
| **`tuple`** | `()`     | Numeric Indexes (`0,1,2`) | **No** (Frozen) | **Yes**                      | Protecting data from accidental changes.  |
| **`dict`**  | `{}`     | Key Labels (`key:val`)    | **Yes**         | **No** (Keys must be unique) | Fast lookups using a custom label.        |
| **`set`**   | `{}`     | **Unordered Chaos**       | **Yes**         | **No**                       | De-duplicating data and math set logic.   |

## 🔧 Core Functions & Methods
Use these native code tools to **measure**, **modify**, and **manipulate** your active collection data containers:
### 📁 List 
##### Methods
* `.append(item)`: Adds an item to the **very end** of the list.
* `.insert(index, item)`: Inserts an item at a **specific index position**.
* `.remove(item)`: Deletes a **specific item by its value name**.
* `.pop(index)`: **Extracts** and removes an item by its index slot (defaults to last item if empty).
* `.sort()`: Sorts list **automatically** in alphabetical or numerical ascending order.
##### Native Functions
* `len(collection)`: **Counts** the total number of items currently inside the list.
* `max(collection)`: **Finds the highest** numeric number or alphabetical character.
* `min(collection)`: **Finds the lowest** numeric number or alphabetical character.
___
### 📁 Tuple
##### Methods
* `.count(item)`: **Counts** how many times a specific item appears inside the container.
* `.index(item)`: **Finds the address slot position** number of a specific item.
##### Native Functions
* `len(collection)`: **Counts** the total number of items currently locked inside the tuple.
___
### 📁 Dictionary
##### Methods
* `.get(key, fallback)`: **Reads** and returns a clean fallback value if the key does not exist instead of crashing.
* `.keys()`: Extracts a standalone list containing only your text **labels**.
* `.values()`: Extracts a standalone list containing only your raw **data**.
* `.items()`: Unpacks your mappings into a list of iterating **key-value pairings**.
##### Core Operators & Statements
* `dict_name["key"] = value`: **Updating** an existing value by re-assigning its key label.
* `dict_name["new_key"] = value`: **Adding** a brand-new key-value pair directly to the dictionary.
* `del dict_name["key"]`: **Deleting** a targeted key-value pair permanently by its explicit key name.
___
### 📁 Set
##### Methods
* `.add(item)`: **Adds** a brand-new item. If it is a duplicate, the set silently discards it.
* `.remove(item)`: **Deletes** an item by value (triggers a hard crash if the item is missing).
* `.discard(item)`: **Safely deletes** an item by value (remains completely silent if the item is missing).
##### Type Casting Operations
* `set(collection)`: Converts an array container into a set to **instantly erase all duplicate records**.
