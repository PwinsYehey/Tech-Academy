---
tags:
  - python/cheat-sheet
  - code-style
links:
  - "[[01-variables-and-data-types]]"
  - "[[13-custom-functions]]"
date_created: 2026-07-30
---
# Naming Conventions

Pythons **naming convention** is a strict formatting protocol that dictates how identifiers (variables, functions, classes, and files) are written in text. 

Adhering to these rules guarantees your scripts match universal industry design patterns, allowing teams to read, maintain, and scan your software architecture effortlessly.
## Core Syntax Rules (Mandatory)
If you break these rules, Python will throw an immediate `SyntaxError`:
- **No Spaces Allowed**: Use underscores (`_`) instead of spaces.
- **Cannot Start with Numbers**: `user_1` is valid, but `1_user` will crash.
- **Special Characters Forbidden**: Do not use symbols like `-`, `@`, `$`, or `!`.
- **No Keywords**: You cannot name a variable `if`, `for`, or `class`.

| Style Name      | Description                                         | Used For                                  | Example                       |
| --------------- | --------------------------------------------------- | ----------------------------------------- | ----------------------------- |
| **Snake Case**  | All lowercase words joined by underscores           | Variables, Functions, Methods, files(.py) | `user_age`, `calculate_total` |
| **Pascal Case** | Every word starts with a capital letter (No spaces) | Classes                                   | `UserProfile`, `ShoppingCart` |
| **UPPERCASE**   | All capital words joined by underscores             | Constants (Unchanging values)             | `MAX_LIMIT`, `API_KEY`        |
