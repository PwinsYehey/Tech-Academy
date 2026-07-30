---
tags:
  - python/cheat-sheet
  - operators
links:
  - "[[01-variables-and-data-types]]"
  - "[[03-intergers-and-floats]]"
  - "[[04-booleans-and-logic]]"
  - "[[06-Conditional-Statements]]"
date_created: 2026-07-30
---
# Operators
 
 operators are **special symbols or keywords** used to perform operations on variables and values. 

**Code Anatomy**:
```
		     Expression
       ┌───────────────────────┐
	   │       5  +  3         │
       └───────┬──┴──┬─────────┘
               │  │  │
       ┌───────┘  │  └───────┐
       ▼          ▼          ▼
   ┌───────┐ ┌──────────┐ ┌───────┐
   │Operand│ │ Operator │ │Operand│
   │  (5)  │ │   (+)    │ │  (3)  │
   └───────┘ └──────────┘ └───────┘
```
* **Expression**: Any legal **combination of values, variables, and operators** that evaluates to a final single value.
- **Operator**: The symbol performing the action (`+`) that executes specific calculation.
- **Operand**: The data being manipulated (`5` and `3`) that are fed into the operator.
___
## Operators Categories
### Arithmetic Operators
Used to perform standard mathematical calculations.

| Operator | Action                 | Example Code | Result                               |
| :------- | :--------------------- | :----------- | :----------------------------------- |
| `+`      | **Addition**           | `10 + 5`     | `15`                                 |
| `-`      | **Subtraction**        | `10 - 5`     | `5`                                  |
| `*`      | **Multiplication**     | `10 * 5`     | `50`                                 |
| `/`      | **True Division**      | `10 / 3`     | `3.333333333333333` (Always a float) |
| `//`     | **Floor Division**     | `10 // 3`    | `3` (Forcefully rounds down)         |
| `%`      | **Modulo** (Remainder) | `10 % 3`     | `1` (The leftover amount)            |
| `**`     | **Exponent** (Power)   | `2 ** 3`     | `8` (2³)                             |
___
### Assignment Operators
Used to assign values to variables, often shortcutting a mathematical operation.

| Operator | Meaning                     | Equivalent To | Example (`x = 10`) | Result            |
| -------- | --------------------------- | ------------- | ------------------ | ----------------- |
| `=`      | **Assign**                  | `x = 5`       | `x = 5`            | `x` becomes `5`   |
| `+=`     | **Add and assign**          | `x = x + 5`   | `x += 5`           | `x` becomes `15`  |
| `-=`     | **Subtract and assign**     | `x = x - 5`   | `x -= 5`           | `x` becomes `5`   |
| `*=`     | **Multiply and assign**     | `x = x * 5`   | `x *= 5`           | `x` becomes `50`  |
| `/=`     | **Divide and assign**       | `x = x / 2`   | `x /= 2`           | `x` becomes `5.0` |
| `//=`    | **Floor divide and assign** | `x = x // 3`  | `x //= 3`          | `x` becomes `3`   |
| `%=`     | **Modulo and assign**       | `x = x % 3`   | `x %= 3`           | `x` becomes `1`   |
| `**=`    | **Exponent and assign**     | `x = x ** 2`  | `x **= 2`          | `x` becomes `100` |
___
### Comparison (Relational) Operators
Used compare two values and always return a Boolean result: `True` or `False`.

| Operator | Meaning                      | Example Code | Result  |
| :------- | :--------------------------- | :----------- | :------ |
| `==`     | **Equal to**                 | `5 == 5`     | `True`  |
| `!=`     | **Not equal to**             | `5 != 3`     | `True`  |
| `>`      | **Greater than**             | `5 > 10`     | `False` |
| `<`      | **Less than**                | `5 < 10`     | `True`  |
| `>=`     | **Greater than or equal to** | `5 >= 5`     | `True`  |
| `<=`     | **Less than or equal to**    | `4 <= 3`     | `False` |
___
### Logical Operators
Used to combine multiple conditional statements.

| Operator | Meaning         | Condition for `True`                  | Example Code          | Result  |
| -------- | --------------- | ------------------------------------- | --------------------- | ------- |
| `and`    | **Logical AND** | If **both** statements are true       | `(5 > 3) and (4 > 2)` | `True`  |
| `or`     | **Logical OR**  | If **at least one** statement is true | `(5 > 3) or (1 > 2)`  | `True`  |
| `not`    | **Logical NOT** | **Reverses** the result               | `not(5 > 3)`          | `False` |
