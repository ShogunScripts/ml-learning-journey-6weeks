# 📅 Day 1 – Python basics (variables, datatypes, operators, conditionals)

## 🎯 Objective
- Revise Python fundamentals: variables, data types, operators & conditional statements.  
- Understand conditional statements (`if`, `elif`, `else`) and their use in decision making.  
- Practice writing simple programs using these concepts.

---

## 📖 Notes
### Variables
- Variables are containers for storing data values.
- Python has no command for declaring a variable. A variable is created the moment you first assign a value to it.
- Variables do not need to be declared with any particular type, and can even change type after they have been set.
  ```
  x = 4       # x is of type int
  x = "Sally" # x is now of type str
  print(x)
  ```
- Python allows you to assign values to multiple variables in one line:
  ```
  x, y, z = "Orange", "Banana", "Cherry"
  print(x)
  print(y)
  print(z)
  ```

---
      
### Datatypes
- Variables can store data of different types, and different types can do different things.
- Python has the following data types built-in by default, in these categories:

  | Category       | Types                         |
  |----------------|-------------------------------|
  | Text Type      | `str`                           |
  | Numeric Types  | `int`, `float`, `complex`           |
  | Sequence Types | `list`, `tuple`, `range`            |
  | Mapping Type   | `dict`                          |
  | Set Types      | `set`, `frozenset`                |
  | Boolean Type   | `bool`                          |
  | Binary Types   | `bytes`, `bytearray`, `memoryview`  |
  | None Type      | `NoneType`                      |

---

### Operators
- Operators are used to perform operations on variables and values.

Python Identity Operators
- Identity operators are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location:

  | Operator	 | Description	| Example	|
  |------------|--------------|---------|
  | `is` |	Returns True if both variables are the same object | `x is y`	|
  | `is not`	| Returns True if both variables are not the same object	| `x is not y` |

Python Membership Operators
- Membership operators are used to test if a sequence is presented in an object:

  | Operator	 | Description	| Example	|
  |------------|--------------|---------|
  | `in`  |	Returns True if a sequence with the specified value is present in the object |	`x in y`	|
  | `not in` |	Returns True if a sequence with the specified value is not present in the object	| `x not in y` |

---

### Conditionals
If statements
- An "if statement" is written by using the `if` keyword.
  ```
  a = 33
  b = 200
  if b > a:
    print("b is greater than a")
  ```

Indentation
- Python relies on indentation (whitespace at the beginning of a line) to define scope in the code. Other programming languages often use curly-brackets for this purpose.
  ```
  #If statement, without indentation (will raise an error):
  a = 33
  b = 200
  if b > a:
  print("b is greater than a") # you will get an error
  ```

Elif
- The `elif` keyword is Python's way of saying "if the previous conditions were not true, then try this condition".
  ```
  a = 33
  b = 33
  if b > a:
    print("b is greater than a")
  elif b == a:
    print("a and b are equal")
  ```

Else
- The `else` keyword catches anything which isn't caught by the preceding conditions.
  ```
  a = 33
  b = 33
  if b > a:
    print("b is greater than a")
  elif b == a:
    print("b and a are equal")
  else :
    print("a is greater than b")
  ```

Short Hand If
- If you have only one statement to execute, you can put it on the same line as the `if` statement.
  ```
  if a > b: print("a is greater than b")
  ```

Short Hand If ... Else
- If you have only one statement to execute, one for `if`, and one for `else`, you can put it all on the same line:
  ```
  a = 3
  b = 220
  print("A") if a > b else print("B")
  ```
- You can also have multiple else statements on the same line:
  ```
  a = 330
  b = 330
  print("A") if a > b else print("=") if a == b else print("B")
  ```

AND, OR, NOT
- The `and`, `or` & `not` keywords are logical operators, and are used to combine conditional statements:
  ```
  a = 200
  b = 33
  c = 500
  if a > b and c > a:
    print("Both conditions are True")
  
  if a > b or a > c:
    print("At least one of the conditions is True")
  
  if not a > b:
    print("a is NOT greater than b")
  ```

The pass Statement
- `if` statements cannot be empty, but if you for some reason have an `if` statement with no content, put in the `pass` statement to avoid getting an error.
  ```
  a = 33
  b = 200
  
  if b > a:
    pass
  ```


Python Match
- The `match` statement is used to perform different actions based on different conditions.
- Instead of writing many `if..else` statements, you can use the `match` statement.
- The `match` statement selects one of many code blocks to be executed.
- Use the pipe character `|` as an or operator in the case evaluation to check for more than one value match in one case
- Use the underscore character `_` as the last case (default case) value if you want a code block to execute when there are not other matches.
- You can add `if` statements in the case evaluation as an extra condition-check.
  ```
  month = 5
  day = 4
  match day:
    case 1 | 2 | 3 | 4 | 5 if month == 4:
      print("A weekday in April")
    case 1 | 2 | 3 | 4 | 5 if month == 5:
      print("A weekday in May")
    case _:
      print("No match")
  ```

---

## 🔗 References
- [W3School Python Tutorials](https://www.w3schools.com/python/default.asp)
