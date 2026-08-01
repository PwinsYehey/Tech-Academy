---
tags:
  - python/advanced
  - oop
  - architecture
links:
  - "[[python_roadmap]]"
  - "[[Dictionaries]]"
date_created: 2026-08-01
---

# Intro to OOP (Object-Oriented Programming)

**Object-Oriented Programming (OOP)** is an advanced programming **paradigm** (a philosophy and mental model) where code architecture is organized into secure, self-contained, real-world structural capsules called **Objects**. 

Up until now, you wrote code using **Procedural Programming** (loose data variables sitting out in the open, passed manually into separate function tools). In OOP, you bind data variables and structural tools together into a single, unified blueprint.
___
## 🏗️ The Core Paradigm Shift

| Paradigm Style                 | Architectural Mental Model    | How It Handles Code                                                           |
| :----------------------------- | :---------------------------- | :---------------------------------------------------------------------------- |
| **Procedural (Module 1)**      | A factory conveyor belt.      | Code is a linear sequence of top-to-bottom steps and detached functions.      |
| **Object-Oriented (Module 2)** | A lego space-station cluster. | Code is built out of independent, interacting objects that manage themselves. |
___
## 🎨 Class vs. Object (The Cookie Cutter Analogy)
The entire architecture of OOP relies on understanding two distinct concepts: **Classes** and **Objects** 
*   **The Class (The Blueprint)**: A factory template, cookie cutter, or architectural blueprint [💡]. It does not hold real user data itself; it simply defines what variables and tools *every future item built from it* is guaranteed to possess [💡].
*   **The Object (The Instance)**: The physical house built from the blueprint, or the actual cookie cut from the mold [💡]. It is a real, live data capsule sitting in your computer's RAM holding unique, custom values [💡].

```text
 🧱 THE MASTER BLUEPRINT (Class)         🏠 REAL-WORLD ASSETS (Objects / Instances)
 ┌─────────────────────────────┐        ┌─────────────────────────────┐
 │ class BankAccount:          │───────►│ Account A: Prince_Skywalker │
 │   • variable: balance       │        │   • balance = $50,000       │
 │   • function: withdraw()    │        └─────────────────────────────┘
 └─────────────────────────────┘        ┌─────────────────────────────┐
                                 ───────►│ Account B: Alex_Solo        │
                                        │   • balance = $120          │
                                        └─────────────────────────────┘
```

---

## 🔧 3. Vocabulary Upgrades

When variables and functions are moved inside a Class blueprint capsule, the software engineering community assigns them upgraded professional names:

*   **Attributes (Variables)**: Variables locked inside the object that track its internal **state** or characteristics (e.g., `balance`, `username`, `color`) [💡].
*   **Methods (Functions)**: Specialized function tools locked inside the object that drive its **behavior** or calculations (e.g., `.withdraw()`, `.accelerate()`) [💡].

---

## 🛠️ Practice Playground

Run this advanced simulation script inside your vault sandbox to watch Python dynamically manufacture two independent, self-contained transaction accounts from a single custom Class blueprint [💡]:

```python
# 1. We construct the master template blueprint (The Class)
class BankAccount:
    # A placeholder tool to simulate our blueprint data parameters
    def configure_account(self, owner_name, starting_balance):
        self.owner = owner_name
        self.balance = starting_balance
        
    def display_ledger(self):
        print(f"💰 Account Owner: {self.owner} | Current Capital: \${self.balance}")

# =====================================================================
# 2. RUNNING THE FACTORY (Instantiating Real Objects from the Blueprint)
# =====================================================================
print("🏭 Booting Module 2 System Blueprints...\n")

# Object A Creation
account_a = BankAccount() # Create a blank house from the master blueprint
account_a.configure_account("Prince_Skywalker", 50000)

# Object B Creation
account_b = BankAccount() # Create a second independent house
account_b.configure_account("Alex_Solo", 120)

# 3. Triggering the internal object method behaviors!
account_a.display_ledger()
account_b.display_ledger()
```
