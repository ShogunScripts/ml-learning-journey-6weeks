# 📅 Day 2 – Loops, Functions & Recursion

## 🎯 Objective
- Understand different types of loops in Python (`for`, `while`).
- Learn to define and use functions.
- Explore recursion with simple examples.

---

## 📝 Notes
### 🔁 Loops
Python has two primitive loop commands:
- `while` loops
- `for` loops


#### The `while` Loop
- With the `while` loop we can execute a set of statements as long as a condition is true.
  ```python
  #Print i as long as i is less than 6:
  i = 1
  while i < 6:
    print(i)
    i += 1
  ```


#### The `for` Loop
- A `for` loop is used for iterating over a sequence (that is either a list, a tuple, a dictionary, a set, or a string).
- This is less like the `for` keyword in other programming languages, and works more like an iterator method as found in other object-orientated programming languages.
- With the `for` loop we can execute a set of statements, once for each item in a list, tuple, set etc.
  ```python
  #Print each fruit in a fruit list:
  fruits = ["apple", "banana", "cherry"]
  for x in fruits:
    print(x)
  ```
- The `for` loop does not require an indexing variable to set beforehand.
- Even strings are iterable objects, they contain a sequence of characters:
  ```python
  #Loop through the letters in the word "banana":
  for x in "banana":
    print(x)
  ```


#### The `break` Statement
- With the break statement we can stop the loop:
  ```python
  i = 1
  while i < 6:
    print(i)
    if i == 3:
      break
    i += 1

  fruits = ["apple", "banana", "cherry"]
  for x in fruits:
    print(x)
    if x == "banana":
      break
  ```


#### The `continue` Statement
- With the `continue` statement we can stop the current iteration of the loop, and continue with the next:
  ```python
    fruits = ["apple", "banana", "cherry"]
    for x in fruits:
      if x == "banana":
        continue
      print(x)
  ```


#### The `range()` Function
- To loop through a set of code a specified number of times, we can use the `range()` function,
- The `range()` function returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and ends at a specified number.
  ```python
  for x in range(6):
    print(x)
  ```
- The `range()` function defaults to 0 as a starting value, however it is possible to specify the starting value by adding a parameter: `range(2, 6)`, which means values from 2 to 6 (but not including 6):
  ```python
  for x in range(2, 6):
    print(x)
  ```
- The `range()` function defaults to increment the sequence by 1, however it is possible to specify the increment value by adding a third parameter: `range(2, 30, 3)`:
  ```python
  for x in range(2, 30, 3):
    print(x)
  ```


#### Else in For Loop
- The `else` keyword in a `for` loop specifies a block of code to be executed when the loop is finished:
  ```python
  #Print all numbers from 0 to 5, and print a message when the loop has ended:
  for x in range(6):
    print(x)
  else:
    print("Finally finished!")
  ```


### 🔧 Functions
- A function is a block of code which only runs when it is called.
- You can pass data, known as parameters, into a function.
- A function can return data as a result.
- Defined using `def` keyword.

#### Arbitrary Arguments, *args
- If you do not know how many arguments that will be passed into your function, add a * before the parameter name in the function definition.
- This way the function will receive a tuple of arguments, and can access the items accordingly:
  ```python
  If the number of arguments is unknown, add a * before the parameter name:
  def my_function(*kids):
    print("The youngest child is " + kids[2])
  
  my_function("Emil", "Tobias", "Linus")
  ```

#### Default Parameter Value
- The following example shows how to use a default parameter value.
- If we call the function without argument, it uses the default value:
  ```python
  def my_function(country = "Norway"):
  print("I am from " + country)

  my_function("Sweden")
  my_function("India")
  my_function()
  my_function("Brazil")
  ```


### Lambda Functions
- A lambda function is a small anonymous function.
- A lambda function can take any number of arguments, but can only have one expression.
- Syntax
  ```
  lambda arguments : expression
  ```
  ```python
  #Add 10 to argument a, and return the result:
  x = lambda a : a + 10
  print(x(5))
  ```
- Lambda functions can take any number of arguments:
  ```python
  #Multiply argument a with argument b and return the result:
  x = lambda a, b : a * b
  print(x(5, 6))
  
  #Summarize argument a, b, and c and return the result:
  x = lambda a, b, c : a + b + c
  print(x(5, 6, 2))
  ```

#### Why Use Lambda Functions?
- The power of lambda is better shown when you use them as an anonymous function inside another function.
- Say you have a function definition that takes one argument, and that argument will be multiplied with an unknown number:
  ```python
  def myfunc(n):
    return lambda a : a * n
  ```
- Use that function definition to make a function that always doubles the number you send in:
  ```python
  def myfunc(n):
    return lambda a : a * n
  
  mydoubler = myfunc(2)
  
  print(mydoubler(11))
  ```
- Or, use the same function definition to make a function that always triples the number you send in:
  ```python
  def myfunc(n):
    return lambda a : a * n
  
  mytripler = myfunc(3)
  
  print(mytripler(11))
  ```
- Use lambda functions when an anonymous function is required for a short period of time.

  
### 🔄 Recursion
- A function calling itself.
- Base case & recursive step.
- Example: factorial, Fibonacci series.


### Arrays
- Python does not have built-in support for Arrays, but Python Lists can be used instead.
- However, to work with arrays in Python you will have to import a library, like the NumPy library.
- Use the `len()` method to return the length of an array (the number of elements in an array).
  ```python
  cars = ["Ford", "Volvo", "BMW"]
  x = len(cars)
  ```
- You can use the `for in` loop to loop through all the elements of an array.
  ```python
  for x in cars:
    print(x)
  ```
|  Method  |  Description  |
|----------|---------------|
| append() | Adds an element at the end of the list |
| clear() |	Removes all the elements from the list |
| copy() | Returns a copy of the list |
| count() |	Returns the number of elements with the specified value |
| extend() | Add the elements of a list (or any iterable), to the end of the current list |
| index()	| Returns the index of the first element with the specified value |
| insert() | Adds an element at the specified position |
| pop() |	Removes the element at the specified position |
| remove() | Removes the first item with the specified value |
| reverse() |	Reverses the order of the list |
| sort() | Sorts the list |

---

## 💻 Practice Exercises
1. Write a Python program to print the first 10 natural numbers using a `while` loop.  
2. Create a function that takes a list of numbers and returns their sum.  
3. Write a recursive function to calculate the factorial of a number.  
4. Write a recursive function to generate the Fibonacci sequence up to `n` terms.  

---

## ✅ Summary
- Learned how to use loops for repetition.
- Understood function definitions & arguments.
- Practiced recursion with base cases.

---

## 📂 Resources
- [W3Schools – Python While Loops](https://www.w3schools.com/python/python_while_loops.asp)  
- [W3Schools – Python For Loops](https://www.w3schools.com/python/python_for_loops.asp)
- [W3Schools – Python Functions](https://www.w3schools.com/python/python_functions.asp)
- [W3Schools – Python Lambda Functions](https://www.w3schools.com/python/python_lambda.asp)
- [W3Schools – Python Arrays](https://www.w3schools.com/python/python_arrays.asp)
- [GeeksforGeeks – Recursion](https://www.geeksforgeeks.org/recursion/)  

---

