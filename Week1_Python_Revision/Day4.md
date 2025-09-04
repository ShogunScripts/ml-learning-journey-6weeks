# 📅 Day 4 – File Handling, Exceptions

## 🎯 Objective
- Learn to read and write files in Python.
- Understand exception handling with try-except-finally.
- Practice file operations and error handling.
- list comprehension & generator
---

## 📝 Notes
### 📖 Key Concepts
- `open()`, `read()`, `write()`, `close()`.
- Exception handling using `try`, `except`, `finally`.
- Common errors (FileNotFoundError, ZeroDivisionError).

### File Handling
- File handling is an important part of any web application.
- Python has several functions for creating, reading, updating, and deleting files.

#### 1. File `open()`
  - The key function for working with files in Python is the `open()` function.
  - The `open()` function takes two parameters: *filename*, and *mode*.
  - There are four different methods (modes) for opening a file:
    ```python
    "r" - Read - Default value. Opens a file for reading, error if the file does not exist

    "a" - Append - Opens a file for appending, creates the file if it does not exist
    
    "w" - Write - Opens a file for writing, creates the file if it does not exist
    
    "x" - Create - Creates the specified file, returns an error if the file exists
    ```
  - In addition you can specify if the file should be handled as binary or text mode
  ```python
  "t" - Text - Default value. Text mode
  "b" - Binary - Binary mode (e.g. images)
  ```
  - To open a file for reading it is enough to specify the name of the file:
    ```python
    f = open("demofile.txt")
    #the code above is same as
    f = open("demofile.txt","rt")
    ```
    Because `"r"` for read, and `"t"` for text are the default values, you do not need to specify them.


---

## 💻 Practice Exercises
1. Write a program to read a text file and count the words.
2. Write a program that writes user input into a file.
3. Handle a `ZeroDivisionError` gracefully.
4. Handle file not found exception.

---

## 📂 Resources
- [W3Schools – File Handling](https://www.w3schools.com/python/python_file_handling.asp)
- [GeeksforGeeks – Exception Handling](https://www.geeksforgeeks.org/python-exception-handling/)

---
