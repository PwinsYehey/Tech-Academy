---
tags:
  - python/cheat-sheet
  - strings
links:
  - "[[02-strings-and-text]]"
date_created: 2026-07-30
---
# String Methods

**String methods are built-in functions that let you analyze or modify text.** 

Because strings in Python are **immutable** (cannot be changed after creation), these methods always return a _new_ altered string, leaving the original text untouched.

**Syntax Pattern:**
``` python
# Format: variable_name.method_name()
text = "python"
print(text.upper())  # Outputs: "PYTHON"
```

| Method              | Action                                     | Example Code (`text = "pyThOn"`) | Result          |
| :------------------ | :----------------------------------------- | :------------------------------- | :-------------- |
| **`.upper()`**      | Converts all characters to lowercase       | `text.upper()`                   | `"PYTHON"`      |
| **`.lower()`**      | Converts all characters to lowercase       | `text.lower()`                   | `"python"`      |
| **`.capitalize()`** | Capitalizes only the first letter          | `text.capitalize()`              | `"Python"`      |
| **`.title()`**      | Capitalizes the first letter of every word | `"hello world".title()`          | `"Hello World"` |
| **`strip()`**       | Removes all whitespace from start and end  | `" hello ".strip()`              | `"hello"`       |
___
## 🚨 The Immutability Trap (Crucial Architecture)
Because strings are completely frozen in memory, simply running a method on a line by itself does absolutely nothing to your original variable box [💡]!

```python
# ❌ THE INEFFECTIVE WAY:

username = "  Prince_Skywalker  "
username.strip() 

print(username) # Output: "  Prince_Skywalker  " (The spaces are STILL there!)
----------------------------------------------------------------------------------
# 🟢 THE ARCHITECTURAL WAY (Re-assignment):

username = "  Prince_Skywalker  "
username = username.strip().lower()

print(username) # Output: "prince_skywalker" (Cleaned and secured!)
```
