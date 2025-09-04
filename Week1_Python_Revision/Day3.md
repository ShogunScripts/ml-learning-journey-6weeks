# 📅 Day 3 – Data Structures (lists, tuples, dicts, sets)

## 🎯 Objective
- Understand Python data structures (list, tuple, set, dict).
- Learn when to use each data structure.
- Practice basic operations and manipulations.

---

## 📝 Notes
### 📖 Key Concepts
There are four collection data types in the Python programming language:
  - ***List*** is a collection which is ordered and changeable. Allows duplicate members.
  - ***Tuple*** is a collection which is ordered and unchangeable. Allows duplicate members.
  - ***Set*** is a collection which is unordered, unchangeable^, and unindexed. No duplicate members.
  - ***Dictionary*** is a collection which is ordered^^ and changeable. No duplicate members.

    Notes:
    - ^Set items are unchangeable, but you can remove and/or add items whenever you like.
    - ^^As of Python version 3.7, dictionaries are ordered. In Python 3.6 and earlier, dictionaries are unordered.

    
### 1. List (`list`)
- Lists are used to store multiple items in a single variable.
- List items are ordered, mutable (can change), and allow duplicate values.
- Lists are created using square brackets:
  ```python
  fruits = ["apple", "banana", "cherry"]
  fruits.append("orange")   # add item
  fruits.remove("banana")   # remove item
  print(fruits[0])          # access by index
  print(len(fruits))        # determine how many items a list has
  ```
- To determine how many items a list has, use the `len()` function.
- A list can contain different data types:
  ```python
  list1 = ["abc", 34, True, 40, "male"]
  ```
- From Python's perspective, lists are defined as objects with the data type `list`:
  ```python
  list1 = ["abc", 34, True, 40, "male"]
  print(type(list1))
  ```
  ```
  #Output:
  <class 'list'>
  ```
- It is also possible to use the `list()` constructor when creating a new list.
  ```python
  thislist = list(("apple", "banana", "cherry")) # note the double round-brackets
  print(thislist)
  ```
- Methods to delete from a list:
  ```python
  # 1. Delete by index using 'del'
  numbers1 = [10, 20, 30, 40]
  del numbers1[1]  # deletes element at index 1
  print("After del at index 1:", numbers1)  # [10, 30, 40]
  
  # 2. Delete by index using .pop() (also returns the removed element)
  numbers2 = [10, 20, 30, 40]
  removed = numbers2.pop(2)  # removes element at index 2
  print("After pop at index 2:", numbers2, "| Removed:", removed)  # [10, 20, 40], Removed: 30
  
  # 3. Delete by value using .remove() (removes first occurrence)
  numbers3 = [10, 20, 30, 20, 40]
  numbers3.remove(20)  # removes the first occurrence of 20
  print("After remove(20):", numbers3)  # [10, 30, 20, 40]
  
  # 4. Delete a slice (multiple elements at once)
  numbers4 = [10, 20, 30, 40, 50]
  numbers4[1:3] = []  # removes elements at index 1 and 2
  print("After slicing [1:3]:", numbers4)  # [10, 40, 50]
  
  ```


### 2. Tuples (`tuple`)
- Tuples are used to store multiple items in a single variable.
- A tuple is a collection which is ordered and unchangeable and allow duplicate values.
- Tuples are written with round brackets.
  ```python
  thistuple = ("apple", "banana", "cherry", "apple", "cherry")
  print(thistuple)
  print(len(thistuple))
  ```
- To create a tuple with only one item, you have to add a comma after the item, otherwise Python will not recognize it as a tuple.
  ```python
  thistuple = ("apple",)
  print(type(thistuple))
  
  #NOT a tuple
  thistuple = ("apple")
  print(type(thistuple))
  ```
- A tuple can contain different data types
  ```python
  tuple1 = ("abc", 34, True, 40, "male")
  ```
- From Python's perspective, tuples are defined as objects with the data type `tuple`:
  ```python
  tuple1 = ("abc", 34, True, 40, "male")
  print(type(tuple1))
  ```
  ```
  #Output:
  <class 'tuple'>
  ```
- It is also possible to use the `tuple()` constructor to make a tuple.
  ```python
  thistuple = tuple(("apple", "banana", "cherry")) # note the double round-brackets
  print(thistuple)
  ```
- Methods to delete from a tuple:
  ```python
  # Original tuple
  t = (1, 2, 3, 4)
  print("Original tuple:", t)
  
  # 1. Delete the entire tuple
  t1 = (1, 2, 3, 4)
  del t1
  # t1 is now deleted (uncommenting the next line would raise an error)
  # print(t1)
  
  # 2. Delete an element by converting to list, then back to tuple
  t2 = (1, 2, 3, 4)
  temp = list(t2)
  del temp[1]   # remove element at index 1
  t2 = tuple(temp)
  print("After deleting index 1 (via list):", t2)
  
  # 3. Create a new tuple without the element (using slicing)
  t3 = (1, 2, 3, 4)
  t3 = t3[:1] + t3[2:]  # remove element at index 1
  print("After deleting index 1 (via slicing):", t3)
  ```


### 3. Sets (`set`)
- Sets are used to store multiple items in a single variable.
- A set is a collection which is unordered, unchangeable^, and unindexed.
  ^ Note: Set items are unchangeable, but you can remove items and add new items.
- Sets are written with curly brackets.
  ```python
  thisset = {"apple", "banana", "cherry"}
  print(thisset)
  ```
- Set items are unordered, unchangeable, and do not allow duplicate values.
- Unordered means that the items in a set do not have a defined order.
- Set items can appear in a different order every time you use them, and cannot be referred to by index or key.
- Note: The values `True` and `1` & `False` and `0` are considered the same value respectively in sets, and are treated as duplicates:
  ```python
  thisset = {"apple", "banana", "cherry", "apple", True, False, 1, 2, 0}     #set cannot contain duplicate values
  print(thisset)
  ```
  ```
  #Output:
  {False, True, 2, 'apple', 'cherry', 'banana'}
  ```
- To determine how many items a set has, use the `len()` function.
- A set can contain different data types.
  ```python
  set1 = {"abc", 34, True, 40, "male"}
  print(type(set1))
  ```
  ```
  #Output:
  <class 'set'>
  ```
- It is also possible to use the `set()` constructor to make a set.
  ```python
  thisset = set(("apple", "banana", "cherry")) # note the double round-brackets
  print(thisset)
  ```
- To delete an item from set :
  ```python
  myset = {"apple", "banana", "cherry"}

  # 1. remove() → removes item, raises error if not found
  myset.remove("banana")
  
  # 2. discard() → removes item, does nothing if not found
  myset.discard("orange")  # no error
  
  # 3. pop() → removes and returns a random item (since sets are unordered)
  item = myset.pop()
  print("Popped:", item)
  
  # 4. clear() → removes all items
  myset.clear()
  print(myset)  # set()
  ```
  

### 4. Dictionaries (`dict`)
- Dictionaries are used to store data values in key:value pairs.
- A dictionary is a collection which is ordered^, changeable and do not allow duplicates.
  ^Notes: As of Python version 3.7, dictionaries are ordered. In Python 3.6 and earlier, dictionaries are unordered.
- Dictionaries are written with curly brackets, and have keys and values:
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
  }
  print(thisdict)
  ```
- Dictionary items are ordered, changeable, and do not allow duplicates.
- Dictionary items are presented in key:value pairs, and can be referred to by using the key name.
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964
  }
  print(thisdict["brand"])
  ```
- Dictionaries are changeable, meaning that we can change, add or remove items after the dictionary has been created.
- Dictionaries cannot have two items with the same key:
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964,
    "year": 2020
  }
  print(thisdict)
  ```
  ```
  #Output:
  {'brand': 'Ford', 'model': 'Mustang', 'year': 2020}
  ```
- To determine how many items a dictionary has, use the `len()` function.
  ```python
  thisdict = {
    "brand": "Ford",
    "model": "Mustang",
    "year": 1964,
    "year": 2020
  }
  print(len(thisdict))
  ```
  ```
  #Output:
  3
  ```
- The values in dictionary items can be of any data type.
- From Python's perspective, dictionaries are defined as objects with the data type `dict`:
  ```python
  thisdict = {
    "brand": "Ford",
    "electric": False,
    "year": 1964,
    "colors": ["red", "white", "blue"]
  }
  ```
  ```
  #Output:
  <class 'dict'>
  ```
- It is also possible to use the `dict()` constructor to make a dictionary.
  ```python
  thisdict = dict(name = "John", age = 36, country = "Norway")
  print(thisdict)
  ```
- To delete a key-value pair in a dictionary:
  ```python
  thisdict = {
    "brand": "Ford",
    "electric": False,
    "year": 1964,
    "colors": ["red", "white", "blue"]
  }

  del thisdict['year']

  print(thisdict)
  ```

---

## 💻 Practice Exercises
1. Create a list of numbers and find the maximum.
   ```python
   numbers = [1,71, 12, 43, 59, 10, 6, 33]
   print(max(numbers))
   ```
2. Write a tuple of 5 elements and access the last two.
   ```python
   fruits = ("watermelon","grapes","coconut","papaya","pineapple","orange")
   print(fruits[-2:])
   print(fruits[-1:-3:-1]
   #Slicing in Python works left to right, meaning the start index must come before the stop index when using the default step `1`. If you really want to slice backwards, you need a negative `step` (i.e. `-1`) parameter
   ```
3. Convert a list with duplicate values into a set.
   ```python
   list1 = ["apple", "orange", "mango", "apple", "kiwi", "orange"]
   set1 = set((list1))
   print(set1)
   ```
4. Create a dictionary of student names and marks.
   ```python
   students = {
     'Rahul' : 56,
     "Manish" : 94,
     "Vinit" : 82
   }
   print(students)
   ```
5. Word frequency counter using `dict`
   ```python
   sample = "The quick brown fox jumps over the lazy dog. The dog barked, but the fox ran away quickly. Both the fox and the dog were very clever animals."

   for ch in ',.!?':
     sample = sample.replace(ch,"")

   words = sample.lower().split()
   wordDictionary = dict()

   for x in words:
     if x in wordDictionary:
       wordDictionary[x] = wordDictionary[x] + 1
     else:
       wordDictionary[x] = 1

   print(wordDictionary)
   ```
---

## 📂 Resources
- [W3Schools – Python Lists](https://www.w3schools.com/python/python_lists.asp)
- [W3Schools – Python Tuples](https://www.w3schools.com/python/python_tuples.asp)
- [W3Schools – Python Sets](https://www.w3schools.com/python/python_sets.asp)
- [W3Schools – Python Dictionaries](https://www.w3schools.com/python/python_dictionaries.asp)


---
