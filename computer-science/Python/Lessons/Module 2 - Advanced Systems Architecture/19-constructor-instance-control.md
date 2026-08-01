---
tags:
  - python/advanced
  - oop
  - constructor
links:
  - "[[18-intro-to-oop]]"
date_created: 2026-08-01
---
# Constructor Instance Control (`__init__` and `self`)

The **Constructor Engine** is a specialized, automatic initialization method that runs behind the scenes the exact millisecond a new object is manufactured from a class template. 

In Python, this engine is written as the double-underscore method **`__init__`** (short for initialization).
___
## ⚙️ The Core Purpose of `__init__`
Without a constructor, an object is born completely blank. You would have to write separate configuration lines for every single object you create. 

The `__init__` method solves this by acting as the **mandatory intake gate**. It forces your script to hand over the starting state data (like usernames, prices, or IPs) right at birth, ensuring no object ever sits in memory unconfigured.

```text
Procedural Object Creation: (Two manual steps) 
	1. obj = Class()
	2. obj.boot_data(args)  
  
Constructor Automation: (One secure step)
	1. obj = Class(args)
```
---
## 🕵️ Unlocking the Mystery of `self`
The keyword **`self`** is the single most critical concept to master in Object-Oriented Programming. 

When you are inside a class blueprint writing code, you don't know what name the future user will give the individual objects (they could name the variable `prince_house`, `alex_house`, or `beach_cabin`). 

The word `self` acts as a **temporary universal placeholder that means "This Exact Object Capsule Right Here."**
*   **`self.owner = owner_name`**: Tells Python: *"Take the text string argument passed into the intake gate and carve a custom memory slot for it named `owner` inside whatever specific object instance is currently being generated right now ."*
*   **Binding the Data**: Writing `self.variable_name` binds that variable directly to that specific object's capsule hull, making it instantly accessible across every other method inside that class.

```python
class House:
    def __init__(self, owner_name):
        # 'self' means: "The specific house currently being born right now"
        self.owner = owner_name 

# =====================================================================
# 🏭 RUNNING THE CODES (Instantiating Real Objects)
# =====================================================================

# 🏠 House 1 is born! 
prince_house = House("Prince")
# Python goes inside the blueprint, sees 'self.owner', and secretly translates it to:
# prince_house.owner = "Prince"

# 🏠 House 2 is born!
alex_house = House("Alex")
# Python goes inside the blueprint, sees 'self.owner', and secretly translates it to:
# alex_house.owner = "Alex"
```

---
## 🩻 Code Anatomy of a Constructor
Let's look at how parameters pass through the intake gate and map straight to your internal instance memory slots:

```text
               Intake Parameter Slots
                 ┌──────┴──────┐
  def __init__(self, size_input, color_input):
                 │       │           │
                 │       ▼           ▼
         self.size  = size_input  
         self.color = color_input
           ▲    ▲
           │    └─ Memory Slot Labels inside the capsule
           └────── "This specific object instance"
```
---
## 🛠️ Practice Playground
Run this database configuration script inside your vault sandbox to watch the `__init__` engine automatically capture and secure custom attributes right at the moment of birth [💡]:

```python
class DatabaseConnection:
    # ⚙️ THE CONSTRUCTOR ENGINE: Runs automatically on creation!
    def __init__(self, target_db, port_number):
        print(f"🛠️ [__init__ Engine] Manufacturing fresh database capsule...")
        self.db_name = target_db          # Bind parameter to unique instance attribute
        self.port = port_number           # Bind second parameter
        self.connection_status = "CLOSED" # Establish a default starting state
        
    def open_port(self):
        self.connection_status = "OPEN"
        print(f"📡 Port {self.port} to database '{self.db_name}' is now safely {self.connection_status}.\n")

# =====================================================================
# INTERCEPTING BIRTH (Passing arguments DIRECTLY into the Class name)
# =====================================================================

# Notice we pass data directly inside the Class parentheses! This calls __init__ instantly.
db_prod = DatabaseConnection("production_vault", 5432)
db_test = DatabaseConnection("sandbox_playground", 8080)

# Execute behavior actions on our distinct, separate capsules
db_prod.open_port()
db_test.open_port()
```
___
# 🎫 Challenge 19 JIRA TICKET: SEC-8891 — Network Firewall Security Constructor Automation

| Ticket Attributes | Value                                          |
| :---------------- | :--------------------------------------------- |
| **Epic Link**     | Core Network Security Infrastructure (Phase 6) |
| **Assignee**      | Junior Systems Architect (Prince_Skywalker)    |
| **Reporter**      | Lead Security Officer                          |
| **Priority**      | 🔴 High (Deployment Blocker)                   |
| **Status**        | In Development / Sandbox Lab Testing           |

---
### 📋 1. Business Context & Problem Statement
Our network engineering team is deploying security clusters. In the old system, junior developers built empty firewall objects and forgot to run the manual configuration step, leaving connection ports wide open to brute-force attacks. 

To fix this security vulnerability, you must rewrite the infrastructure blueprint using an **atomic `__init__` constructor gate**. No firewall capsule can be manufactured in computer memory unless its targeted port number and rule settings are hard-locked straight through the parental intake gate at birth.

### 🏗️ 2. Architectural System Requirements
Write a single, unified Python script that implements these exact 4 engineering steps:

#### 🟢 Task 1: Construct the Master Template (Class with Constructor)
Define a custom Class named **`NetworkFirewall`**. Inside its capsule walls, implement the automated **`__init__` constructor engine**:
- It must accept two entry parameter slots: `self`, `port_number`, and `rule_type` (e.g., `"ALLOW"` or `"BLOCK"`).
- **Data Binding**: Bind `port_number` to an instance attribute called `self.port`.
- **Data Binding**: Bind `rule_type` to an instance attribute called `self.rule`.
- **Default Starting State**: Initialize a third attribute named `self.active_status` and hardcode its starting state string value to `"OFFLINE"`.

#### 🟢 Task 2: Implement Multiple Behavior Engines (Methods)
Inside the class capsule, define two action methods that can read and mutate your internal state data:
1. **`activate_firewall(self)`**: This behavior must update your `self.active_status` variable box to `"SHIELD_ONLINE"`, and print a secure log line: `"[FIREWALL] System active. Guarding Port [Port] under rule protocol: [Rule]!"`.
2. **`inspect_node(self)`**: This behavior must read your current state variables and print a status readout line: `"[AUDIT] Port Node: [Port] | Status: [Status] | Protocol: [Rule]"`.

#### 🟢 Task 3: Execute Atomic Factory Birth (One Secure Step)
Outside the class block (the open baseline workspace), pass your real data arguments (`args`) **directly inside the Class parentheses** at birth:
- Manufacture an independent object instance named **`web_firewall`** by passing the arguments `80` and `"BLOCK"`.
- Manufacture a completely separate, independent object instance named **`ssh_firewall`** by passing the arguments `22` and `"ALLOW"`.

#### 🟢 Task 4: Run System Testing Pipelines
Execute your method behaviors back-to-back on your isolated capsules:
- Run an inspection audit on **both** firewall objects first to verify their offline states.
- Activate the `web_firewall` capsule object to flip its internal state light switch.
- Run a final audit check on **both** firewalls to prove to the security team that activating the web capsule did *not* affect or change the memory states of the ssh capsule!
### 💻 Production Code Sandbox Workspace
```python



```

###### ⏭️ Next Lesson
[**Module 2 — Lesson 20: Object Attributes & Methods**](obsidian://open?vault=Tech-Academy&file=computer-science%2FPython%2FLessons%2FModule%202%20-%20Advanced%20Systems%20Architecture%2F20-object-attributes-and-methods)