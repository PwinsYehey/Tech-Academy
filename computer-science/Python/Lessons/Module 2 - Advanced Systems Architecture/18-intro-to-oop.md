---
tags:
  - python/advanced
  - oop
  - architecture
links:
  - "[[python_roadmap]]"
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
*   **The Class (The Blueprint)**: A factory template, cookie cutter, or architectural blueprint. It does not hold real user data itself; it simply defines what variables and tools *every future item built from it* is guaranteed to possess.
*   **The Object (The Instance)**: The physical house built from the blueprint, or the actual cookie cut from the mold. It is a real, live data capsule sitting in your computer's RAM holding unique, custom values.

```text
 🧱 THE MASTER BLUEPRINT (Class)     🏠 REAL-WORLD ASSETS (Objects/Instances)
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
## 🔧 Vocabulary Upgrades
When variables and functions are moved inside a Class blueprint capsule, the software engineering community assigns them upgraded professional names:
*   **Attributes (Variables)**: Variables locked inside the object that track its internal **state** or characteristics (e.g., `brand`, `storage_gb`, `battery_pct`).
*   **Methods (Functions)**: Specialized function tools locked inside the object that drive its **behavior** or calculations (e.g., `.send_text()`, `.charge_battery()`).

```
 ┌────────────────────────────────────────────────────────┐
 │ 📦 INSTANCE OBJECT: prince_smartphone                  │
 ├────────────────────────────────────────────────────────┤
 │ 🔒 ATTRIBUTES (The Character States / Data Storage)     │
 │  • brand        = "Apple"                              │
 │  • storage_gb   = 256        <── What the phone IS     │
 │  • battery_pct  = 82                                   │
 ├────────────────────────────────────────────────────────┤
 │ ⚙️ METHODS (The Behavioral Engines / Action Tools)     │
 │  • def send_text()                                     │
 │  • def charge_battery()      <── What the phone DOES   │
 │  • def check_storage()                                 │
 └────────────────────────────────────────────────────────┘
```

```
 ┌──────────────────┐  Trigger Behavior  ┌─────────────────┐
 │   CURRENT STATE  │ ─────────────────► │ METHOD BEHAVIOR │
 │ (Attribute Data) │                    │  (Action Code)  │
 └──────────────────┘                    └─────────────────┘
           ▲                                      │
           │         Calculates Changes           │
           └──────────────────────────────────────┘
                    Updates to a NEW STATE
```
1. The user triggers a method's **Behavior** (e.g., calling `.charge_battery()`). 
2. The method logic reads the current **State** attribute (e.g., `battery_pct = 82`). 
3. The behavior calculates the power increase and updates the attribute box, transitioning the object to a **New State** (e.g., `battery_pct = 100`).

---
## 🛠️ Practice Playground
Run this advanced simulation script inside your vault sandbox to watch Python dynamically manufacture two independent, self-contained transaction accounts from a single custom Class blueprint:

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
___
# 🎯 Challenge 18: The Cloud Infrastructure Capsule
### 📜 Business Context & Requirements
Our dev-ops infrastructure team needs a clean, modular way to manage cloud servers. Instead of tracking loose variable strings and detached functions across the workspace, you must architect a master object blueprint (Class) that tracks a server's **State** and houses its own **Behavior** tools.

Write a single Python script that implements these exact architectural steps:
1. **🧱 The Master Blueprint (Class)**: Define a custom Class named **`CloudServer`**.
2. **⚙️ The State Configuration Machine**: Inside the class capsule, define a configuration method named **`boot_instance(self, server_name, server_ip)`**. Inside this tool, initialize two internal **attributes** (states):
   - Save the `server_name` into an attribute called `self.name`.
   - Save the `server_ip` into an attribute called `self.ip`.
   - Initialize a third, hardcoded starting attribute named `self.status` and set its starting state string value to `"OFFLINE"`.
3. **⚙️ The Behavioral Engines (Methods)**: Inside the class capsule, define two action methods:
   - **`start_server(self)`**: This behavior must flip the internal state attribute `self.status` to `"ONLINE"`, and print a log: `"[SYSTEM] Server [Name] is spinning up online via IP [IP]..."` .
   - **`check_heartbeat(self)`**: This behavior must inspect the current state values and print a system status line: `"[HEARTBEAT] Instance: [Name] | Status: [Status]"`.
4. **🏭 Running the Factory (Instantiating Objects)**: Outside the class block (the open baseline workspace):
   - Manufacture a real, independent object capsule instance named **`production_server`** from your `CloudServer` blueprint.
   - Call `.boot_instance()` on it, passing it the arguments: `"PROD-CLUSTER-01"` and `"192.168.10.1"`.
5. **🏃 Executing System Behaviors**: 
   - Run a heartbeat check on your production server object first.
   - Fire up the server using your start engine method.
   - Run a final heartbeat check to verify that your method's behavior successfully altered the internal state attribute of your object in computer RAM!
### 💻 Write Your Code Here
```python



```

###### ⏭️ Next Lesson
[**Module 2 — Lesson 19: Constructor Instance Control**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%202%20-%20Advanced%20Systems%20Architecture%2F19-constructor-instance-control)