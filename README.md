# Python Problem-Solving Guide

## Introduction

This README provides a structured approach to Python problem-solving for technical interviews. It covers essential Python syntax, data structures, algorithms, and coding patterns commonly encountered in coding challenges.

## Table of Contents

1. [Variables and Data Types](#1-variables-and-data-types)
2. [Control Flow (Loops & Conditions)](#2-control-flow-loops--conditions)
3. [Functions and Scope](#3-functions-and-scope)
4. [Data Structures (Lists, Tuples, Sets, Dictionaries)](#4-data-structures)
5. [Algorithms for Problem-Solving](#5-algorithms-for-problem-solving)
6. [Recursion and Dynamic Programming](#6-recursion-and-dynamic-programming)
7. [String Manipulation](#7-string-manipulation)
8. [File Handling](#8-file-handling)
9. [Exception Handling](#9-exception-handling)
10. [Object-Oriented Programming (OOP)](#10-object-oriented-programming-oop)
11. [Important Built-in Functions](#11-important-built-in-functions)
12. [Useful Python Libraries for Interviews](#12-useful-python-libraries-for-interviews)
13. [Conclusion](#conclusion)

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

```python
# If-Else Statements
num = 10
if num > 0:
    print("Positive number")
elif num < 0:
    print("Negative number")
else:
    print("Zero")
```

```python
# For Loop
for i in range(5):
    print(i)
```

```python
# While Loop
count = 0
while count < 5:
    print(count)
    count += 1
```

```python
# Enumerate
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
```

```python
# List Comprehension
squares = [x ** 2 for x in range(10)]
print(squares)
```

```python
# Nested Loops
for i in range(3):
    for j in range(2):
        print(f"i: {i}, j: {j}")
```

---

## 3. Functions and Scope

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

```python
# Lambda Function
square = lambda x: x ** 2
print(square(5))  # Output: 25
```

---

## 4. Data Structures

```python
# List
fruits = ["apple", "banana", "cherry"]
print(fruits[0])
```

```python
# Nested List
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(matrix[1][2])
```

```python
# Tuple
tuple_data = (1, 2, 3)
print(tuple_data[1])
```

```python
# Set
unique_numbers = {1, 2, 3, 3}
print(unique_numbers)
```

```python
# Dictionary
person = {"name": "John", "age": 30}
print(person["name"])
```

---

## 5. Algorithms for Problem-Solving

```python
# Sorting
arr = [3, 1, 4, 1, 5]
arr.sort()
print(arr)
```

```python
# Binary Search
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

```python
# Two-pointer Technique
def has_pair_with_sum(arr, target):
    arr.sort()
    left, right = 0, len(arr) - 1
    while left < right:
        current_sum = arr[left] + arr[right]
        if current_sum == target:
            return True
        elif current_sum < target:
            left += 1
        else:
            right -= 1
    return False
```

---

## 6. Recursion and Dynamic Programming

```python
# Factorial (Recursion)
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

```python
# Fibonacci (Memoization)
memo = {}
def fib(n):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fib(n - 1) + fib(n - 2)
    return memo[n]
```

```python
# Fibonacci (Tabulation)
def fib_tab(n):
    if n <= 1:
        return n
    dp = [0] * (n + 1)
    dp[1] = 1
    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]
    return dp[n]
```

---

## 7. String Manipulation

```python
s = "hello world"
print(s[::-1])
print(s.split())
print("".join(['a', 'b']))
print(s.replace("world", "Python"))
```

---

## 8. File Handling

```python
# Read File
with open("file.txt", "r") as file:
    content = file.read()
    print(content)
```

```python
# Write File
with open("file.txt", "w") as file:
    file.write("Hello, Python!")
```

---

## 9. Exception Handling

```python
try:
    num = int("abc")
except ValueError:
    print("Invalid input!")
finally:
    print("Execution completed")
```

---

## 10. Object-Oriented Programming (OOP)

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

## 11. Important Built-in Functions

```python
print(len([1, 2, 3]))               # Length of a list
print(max([10, 20, 30]))           # Maximum value
print(min([10, 20, 30]))           # Minimum value
print(sum([1, 2, 3, 4]))           # Sum of elements in a list

print(list(map(lambda x: x**2, [1, 2, 3])))  # Square all elements using map
print(list(filter(lambda x: x % 2 == 0, [1, 2, 3, 4])))  # Filter even numbers

print(list(zip(["Alice", "Bob"], [25, 30])))  # Combine two lists into tuples
print(list(reversed([1, 2, 3, 4])))             # Reverse a list
print(sorted([3, 1, 4, 1, 5]))                  # Sort a list

print(all([True, True, False]))     # Returns True if all elements are True
print(any([False, False, True]))    # Returns True if at least one element is True

print(round(3.14159, 2))            # Round to 2 decimal places
print(abs(-10))                     # Absolute value
print(divmod(10, 3))                # Returns (quotient, remainder)

print(ord('A'))                     # ASCII value of character
print(chr(65))                      # Character from ASCII value
print(eval("3 + 5"))                # Evaluate a string expression
print("{:.2f}".format(3.14159))      # Format float to 2 decimal places

print(isinstance(10, int))          # Check if variable is instance of type
print(hex(255))                     # Convert to hexadecimal
print(bin(10))                      # Convert to binary
print(oct(8))                       # Convert to octal
```

---

## 12. Useful Python Libraries for Interviews

```python
# collections
from collections import Counter, defaultdict
print(Counter("aabbc"))
```

```python
# heapq
import heapq
nums = [5, 1, 3]
heapq.heapify(nums)
print(heapq.heappop(nums))
```

```python
# itertools
from itertools import permutations
print(list(permutations([1, 2, 3])))
```

