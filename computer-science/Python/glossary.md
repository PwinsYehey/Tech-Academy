---
tags:
  - python/vocabulary
  - core-concepts
links:
  - "[[python_roadmap]]"
date_created: 2026-07-29
---
# Computer Science & Architecture Glossary

This reference manual maps complex industry jargon to universal, developer-accurate definitions. Terms are grouped by their structural connections so you can easily compare related concepts.
___
## 🧰 Foundation Engine & Execution Core
### 📜 Script
A plain text file containing a sequence of programming instructions that an interpreter reads and executes top-to-bottom.
### 🏃 Interpreter
A software program that reads and executes your script instructions **one single line at a time** on the fly. It translates each line into machine code and runs it instantly before moving to the next line. (Python operates completely on an Interpreter program).
### 🏭 Compiler
A software program that translates your entire source code file **all at once** into raw computer machine language beforehand. It saves this translation as a permanent standalone executable file (like an `.exe` file) before the program is ever launched.
### 🔑 Keywords
Special, reserved words built into Python's native brain that possess an immutable semantic meaning (e.g., `def`, `while`, `try`, `import`, `with`). You cannot use them as variable names.
### 🛠️ Operators
Special symbols used to execute calculations or evaluations on your data (e.g., `+` for addition, `/` for division, `=` for assignment).
### 🪵 Operand
The physical data value or variable that an operator acts upon. For example, in the expression `10 + 5`, the numbers `10` and `5` are operands.
___
## 📦 Variables & Memory Lifecycle
### 📦 Variables
Labeled digital storage containers or "boxes" carved into your computer's short-term memory (RAM) that act as pointers holding and manipulating raw data values.
### 📋 Declaration
The act of announcing a variable's name and existence to a programming language interpreter. In many older languages, you must explicitly declare a variable's data type before putting data inside.
### 🏁 Initialization / Initialize
The specific act of assigning a starting data value to a variable for the very first time. In Python, declaration and initialization happen simultaneously on a single line (e.g., `x = 10`).
### 🗂️ Data Type
The official classification category assigned to a value (e.g., `int`, `str`, `bool`) that dictates to Python what kind of operations are mathematically and structurally permitted on that information.
### 🏃 Dynamic / Dynamically Typed
An environment trait where data types are checked on-the-fly during runtime execution instead of being compile-locked beforehand. Python figures out your variables' data types automatically based on what value you drop inside.
### 🔄 Type Casting (Conversion)
The process of explicitly forcing a variable to transform from its current data type category into a different one using constructor functions like `int()`, `str()`, or `float()`.
### 🏷️ Placeholder
A temporary variable slot used during automation processes to capture whatever data item is passing through the current phase of execution (like a loop variable or print string token).
___
## 🗃️ Data Collection Behaviors
### 🔢 Index
A sequential numeric address slot assigned to an item inside an ordered collection. Python indexes are zero-indexed, meaning the first element always sits at index position `0`.
### 📏 Ordered
A trait where a collection structure remembers and locks in the exact chronological sequence in which items are inserted, preventing elements from shifting around randomly.
### 🌪️ Unordered
A collection trait where items possess no set spatial layout sequence or numeric index positions. The computer shuffles the items in random memory positions to maximize lightning-fast lookup speeds.
### 🧪 Mutable
A structural trait meaning changeable. If a collection data type is mutable (like a List or Dictionary), you can dynamically add, update, or drop items from its container without re-creating the whole file.
### 🧊 Immutable
A structural trait meaning frozen or unchangeable. If a data type is immutable (like an Integer, String, or Tuple), its raw memory data cannot be modified in place. Any modification forces Python to manufacture a brand-new object behind the scenes.
### 🧳 Modifying
The dynamic programmatic action of updating, editing, adding, or deleting data values sitting inside a mutable collection container.
___
## 🏗️ Modular Architecture & Scope
### ⚙️ Function
A detached, reusable machine block of instructions that sits silently in memory until it is explicitly called by its name to execute a task.
### 🧬 Method
A specialized function that belongs explicitly to a data type or object family (e.g., `.strip()` for strings, `.get()` for dictionaries) and must be invoked using dot notation.
### 🎛️ Parameter
The temporary variable name written inside a function's blueprint definition parentheses (e.g., `def check(token):`, where `token` is the parameter slot).
### 🤝 Argument
The actual, physical data value you pass into a function container when you execute the machine line (e.g., `process_payment("abc")`, where `"abc"` is the argument).
### 🌎 Global Scope
The open, baseline workspace of a script. Any variable initialized outside of a function lives here and can be read by any other line of code in the entire file.
### 📦 Local Scope
The restricted, temporary memory capsule created inside a custom function block. Variables born here are completely invisible to the outside script and evaporate from RAM the instant the function ends.
### 🔒 Shadow Variable
A local variable created inside a function box that shares the exact same name as a global variable, causing Python to prioritize reading the local version while inside the box.
### 🧭 Namespace
A hidden "family last name" or prefix identifier that Python uses to group tools and variables together, preventing errors caused when separate modules share the exact same tool names.
### 🔂 Iteration / Iterate
The systematic process of looping or repeating a block of instructions over and over through a collection data conveyor belt.
### 🌫️ Whitespace / Indentation 
The blank structural spacing inserted at the absolute beginning of a line of code (typically 4 spaces or a Tab). In Python, indentation is a mandatory language mechanic used to define where a control flow structure (like an `if` block, `for` loop, or custom function capsule) begins and ends. Missing or misaligned whitespace triggers an instant `IndentationError` crash.
___
## 🛡️ Systems Integrity & Storage I/O
### 🚨 Exception
The official technical term for a runtime code error. It is a physical object generated by Python when a system rule is broken (e.g., `ValueError`, `KeyError`, `ZeroDivisionError`).
### 📋 Traceback
The step-by-step diagnostic log map printed on your screen when a program crashes, tracking the chronological file names and line numbers leading up to the exact point where the code fractured.
### 🫴 Fallback Value (Plan B)
A safe backup value assigned to a variable inside an `except` block to prevent the entire program from crashing when an operation fails completely.
### 🔄 Idempotency
An architectural safety concept which guarantees that no matter how many times an operation is repeated or accidentally re-submitted (like a user double-clicking a payment button), the system results remain identical without causing duplicate records or data corruption.
### 🪓 Context Manager (`with` statement)
An automated software safety guard that automatically opens, manages, and guarantees the safe shutdown or locking of a file or connection port stream the exact second its indented code block terminates.
### 💾 File I/O (Input / Output)
The structural process of exchanging data streams between temporary computer memory (RAM) and permanent hard drive storage space.
* **Input (Reading):** Pulling text *out* of the hard drive into variables.
* **Output (Writing):** Pushing variables *into* permanent files on disk.
### 📜 Ledger
 An immutable, append-only log file or record book where a program is strictly allowed to add new data rows to the very bottom, preserving an unbroken historical timeline transaction signature.
