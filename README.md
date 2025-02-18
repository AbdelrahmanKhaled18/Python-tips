# Python Problem-Solving Guide

## Introduction
This README provides a structured approach to Python problem-solving for technical interviews. It covers essential Python syntax, data structures, algorithms, and coding patterns commonly encountered in coding challenges.

## Table of Contents
1. Variables and Data Types
2. Control Flow (Loops & Conditions)
3. Functions and Scope
4. Data Structures (Lists, Tuples, Sets, Dictionaries)
5. Algorithms for Problem-Solving
6. Recursion and Dynamic Programming
7. File Handling
8. Exception Handling
9. Object-Oriented Programming (OOP)
10. Important Built-in Functions

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

## 5. Algorithms for Problem-Solving

### Sorting Algorithms
```python
arr = [3, 1, 4, 1, 5]
arr.sort()
print(arr)  # Output: [1, 1, 3, 4, 5]
```

### Searching Algorithms
```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

---

## 6. Recursion and Dynamic Programming

### Recursion Example: Factorial
```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

### Memoization Example: Fibonacci
```python
memo = {}
def fib(n):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fib(n - 1) + fib(n - 2)
    return memo[n]
```

---

## 7. File Handling

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

## 8. Exception Handling

```python
try:
    num = int("abc")
except ValueError:
    print("Invalid input!")
finally:
    print("Execution completed")
```

---

## 9. Object-Oriented Programming (OOP)

### Class and Object Example
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



## 10. Important Built-in Functions

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

### `reversed()` - Reverse an iterable
```python
numbers = [1, 2, 3, 4]
print(list(reversed(numbers)))  # Output: [4, 3, 2, 1]
```

### `sorted()` - Sort an iterable
```python
numbers = [3, 1, 4, 1, 5]
print(sorted(numbers))  # Output: [1, 1, 3, 4, 5]
```

### `all()` - Check if all elements are True
```python
print(all([True, True, False]))  # Output: False
print(all([1, 2, 3]))  # Output: True
```

### `any()` - Check if any element is True
```python
print(any([False, False, True]))  # Output: True
print(any([0, 0, 0]))  # Output: False
```

### `round()` - Round a number
```python
print(round(3.14159, 2))  # Output: 3.14
```

### `abs()` - Get the absolute value of a number
```python
print(abs(-10))  # Output: 10
```

### `divmod()` - Get quotient and remainder
```python
print(divmod(10, 3))  # Output: (3, 1)
```

### `ord()` and `chr()` - Convert between characters and ASCII values
```python
print(ord('A'))  # Output: 65
print(chr(65))  # Output: 'A'
```

### `eval()` - Evaluate a string expression
```python
expr = "3 + 5"
print(eval(expr))  # Output: 8
```

### `format()` - Format strings
```python
print("{:.2f}".format(3.14159))  # Output: '3.14'
```

### `enumerate()` - Add index to an iterable
```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
```

### `isinstance()` - Check data type
```python
print(isinstance(10, int))  # Output: True
print(isinstance("hello", str))  # Output: True
```

### `hex()`, `bin()`, `oct()` - Convert numbers to different bases
```python
print(hex(255))  # Output: '0xff'
print(bin(10))  # Output: '0b1010'
print(oct(8))  # Output: '0o10'
```



## Conclusion

This guide serves as a foundational reference for Python problem-solving in coding interviews. Keep practicing and refining your approach to master competitive programming!
