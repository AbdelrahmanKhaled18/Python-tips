# Python Syntax and Important Functions

## Introduction
This README file provides an overview of Python syntax and essential built-in functions with explanations and sample code.

## Table of Contents
1. Variables and Data Types
2. Control Flow (Loops & Conditions)
3. Functions and Scope
4. Data Structures (Lists, Tuples, Sets, Dictionaries)
5. File Handling
6. Exception Handling
7. Object-Oriented Programming (OOP)
8. Important Built-in Functions

---

## 1. Variables and Data Types
Python supports dynamic typing, meaning variables do not need explicit declarations.

```python
x = 10          # Integer
y = 3.14        # Float
name = "John"   # String
is_active = True # Boolean
```

### Type Checking
```python
print(type(x))  # <class 'int'>
print(type(y))  # <class 'float'>
```

### Type Casting
```python
num = int("5")   # Converts string to integer
flt = float(10)   # Converts integer to float
s = str(100)      # Converts integer to string
b = bool(1)       # Converts integer to boolean
lst = list("abc") # Converts string to list
st = set([1, 2, 2, 3]) # Converts list to set
tpl = tuple([1, 2, 3]) # Converts list to tuple
d = dict([("name", "John"), ("age", 30)]) # Converts list of tuples to dictionary
```

---

## 2. Control Flow (Loops & Conditions)

### If-Else Statements
```python
num = 10
if num > 0:
    print("Positive number")
elif num < 0:
    print("Negative number")
else:
    print("Zero")
```

### Loops
**For Loop:**
```python
for i in range(5):
    print(i)  # Outputs 0 to 4
```

**While Loop:**
```python
count = 0
while count < 5:
    print(count)
    count += 1
```

### Advanced Looping
**Looping with `enumerate()`:**
```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
```

**List Comprehension with Loops:**
```python
squares = [x ** 2 for x in range(10)]
print(squares)
```

**Nested Loops:**
```python
for i in range(3):
    for j in range(2):
        print(f"i: {i}, j: {j}")
```

---

## 3. Functions and Scope

### Defining and Calling Functions
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

### Lambda Functions
```python
square = lambda x: x ** 2
print(square(5))  # Output: 25
```

---

## 4. Data Structures

### Lists
```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # Output: apple
```

### Nested Lists (2D Lists)
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(matrix[1][2])  # Output: 6
```

### Tuples (Immutable)
```python
tuple_data = (1, 2, 3)
print(tuple_data[1])  # Output: 2
```

### Sets (Unique Elements)
```python
unique_numbers = {1, 2, 3, 3}
print(unique_numbers)  # Output: {1, 2, 3}
```

### Dictionaries (Key-Value Pairs)
```python
person = {"name": "John", "age": 30}
print(person["name"])  # Output: John
```

---

## 5. File Handling

### Reading a File
```python
with open("file.txt", "r") as file:
    content = file.read()
    print(content)
```

### Writing to a File
```python
with open("file.txt", "w") as file:
    file.write("Hello, Python!")
```

---

## 6. Exception Handling
```python
try:
    num = int("abc")
except ValueError:
    print("Invalid input!")
finally:
    print("Execution completed")
```

---

## 7. Object-Oriented Programming (OOP)

### Class and Object
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hello, my name is {self.name}."

person1 = Person("Alice", 25)
print(person1.greet())
```

---

## 8. Important Built-in Functions

### `len()` - Get the length of a sequence
```python
print(len([1, 2, 3]))  # Output: 3
```

### `max()` and `min()` - Get the maximum and minimum values
```python
print(max([10, 20, 30]))  # Output: 30
print(min([10, 20, 30]))  # Output: 10
```

### `sum()` - Get the sum of elements in a list
```python
print(sum([1, 2, 3, 4]))  # Output: 10
```

### `sorted()` - Sort a list
```python
numbers = [3, 1, 4, 1, 5]
print(sorted(numbers))  # Output: [1, 1, 3, 4, 5]
```

### `map()` - Apply a function to all elements
```python
numbers = [1, 2, 3, 4]
squared = list(map(lambda x: x ** 2, numbers))
print(squared)  # Output: [1, 4, 9, 16]
```

### `filter()` - Filter elements based on a condition
```python
numbers = [1, 2, 3, 4]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print(even_numbers)  # Output: [2, 4]
```

### `zip()` - Combine multiple iterables
```python
names = ["Alice", "Bob"]
ages = [25, 30]
combined = list(zip(names, ages))
print(combined)  # Output: [('Alice', 25), ('Bob', 30)]
```

---

## Conclusion
This README provides an overview of essential Python syntax and functions. Keep practicing to master Python!

