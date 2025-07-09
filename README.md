# Python Problem-Solving & Syntax Guide

## Introduction

This README provides a comprehensive, structured approach to Python problem-solving, syntax, and best practices for technical interviews and real-world development. It covers essential and advanced Python syntax, data structures, algorithms, coding patterns, standard libraries, and tips commonly encountered in coding challenges and professional work.

## Table of Contents

1. [Variables, Data Types, and Type Hints](#1-variables-data-types-and-type-hints)
2. [Operators](#2-operators)
3. [Control Flow (Conditions, Loops, Comprehensions, Pattern Matching)](#3-control-flow-conditions-loops-comprehensions-pattern-matching)
4. [Functions (def, lambda, *args, **kwargs, decorators, docstrings, recursion)](#4-functions)
5. [Data Structures (Lists, Tuples, Sets, Dicts, Collections)](#5-data-structures)
6. [String Manipulation](#6-string-manipulation)
7. [Modules, Imports, and Environments](#7-modules-imports-and-environments)
8. [File and OS Operations](#8-file-and-os-operations)
9. [Exception and Error Handling](#9-exception-and-error-handling)
10. [Object-Oriented Programming (OOP)](#10-object-oriented-programming-oop)
11. [Iterators and Generators](#11-iterators-and-generators)
12. [Async Programming (async/await)](#12-async-programming-asyncawait)
13. [Important Built-in Functions](#13-important-built-in-functions)
14. [Useful Python Libraries for Interviews](#14-useful-python-libraries-for-interviews)
15. [Modern Python Features (3.8+)](#15-modern-python-features-38)
16. [Tips, Idioms, and Common Pitfalls](#16-tips-idioms-and-common-pitfalls)
17. [Resources & Further Reading](#17-resources--further-reading)
18. [Conclusion](#18-conclusion)

---

## 1. Variables, Data Types, and Type Hints

Python supports dynamic typing, meaning variables do not need explicit declarations. You can also use type hints for clarity and static analysis.

### Variable Assignment and Naming

```python
# Assigning variables (no need to declare type)
x = 10          # Integer assignment
y = 3.14        # Float assignment
name = "John"   # String assignment
is_active = True # Boolean assignment

# Variable naming conventions
snake_case = 1      # Preferred for variables and functions
CamelCase = 2       # Used for class names
CONSTANT_VALUE = 42 # By convention, constants are all uppercase

# Multiple assignment
x, y, z = 1, 2, 3   # Assign multiple variables at once
a = b = c = 0       # Assign the same value to multiple variables

# Swapping variables (Pythonic way)
a, b = b, a

# Unpacking sequences
lst = [1, 2, 3]
x, y, z = lst  # x=1, y=2, z=3

# Extended unpacking (Python 3+)
first, *middle, last = [1, 2, 3, 4, 5]  # first=1, middle=[2,3,4], last=5
```

### Data Types

```python
# Basic data types
integer_var: int = 42
float_var: float = 3.1415
string_var: str = "Hello"
bool_var: bool = False

# NoneType (represents the absence of a value)
none_var: None = None

# Complex numbers
complex_var: complex = 2 + 3j

# Type checking
print(type(integer_var))  # <class 'int'>
print(type(float_var))    # <class 'float'>
print(type(string_var))   # <class 'str'>
print(type(bool_var))     # <class 'bool'>
print(type(none_var))     # <class 'NoneType'>
print(type(complex_var))  # <class 'complex'>
```

### Type Hints (Type Annotations)

```python
# Function with type hints
def greet(name: str) -> str:
    return f"Hello, {name}!"

# Variable type hints (Python 3.6+)
age: int = 30
height: float = 1.75
is_student: bool = True

# List, Tuple, Set, Dict type hints (Python 3.9+ syntax)
my_list: list[int] = [1, 2, 3]
my_tuple: tuple[str, int] = ("Alice", 25)
my_set: set[str] = {"apple", "banana"}
my_dict: dict[str, int] = {"a": 1, "b": 2}

# For older Python versions, use typing module
from typing import List, Tuple, Set, Dict
my_list2: List[int] = [1, 2, 3]
my_tuple2: Tuple[str, int] = ("Bob", 30)
my_set2: Set[str] = {"cat", "dog"}
my_dict2: Dict[str, int] = {"x": 10, "y": 20}
```

### Type Casting

```python
# Convert between types
num = int("5")      # Converts string to integer
flt = float(10)     # Converts integer to float
s = str(100)        # Converts integer to string
b = bool(1)         # Converts integer to boolean (0 is False, others are True)
lst = list("abc")   # Converts string to list of characters
st = set([1, 2, 2, 3]) # Converts list to set (removes duplicates)
tpl = tuple([1, 2, 3]) # Converts list to tuple
d = dict([("name", "John"), ("age", 30)]) # Converts list of tuples to dictionary
```

### Constants

```python
# Python does not have true constants, but by convention, use ALL_CAPS
PI = 3.14159
GRAVITY = 9.8

# You can use typing.Final (Python 3.8+) to indicate a constant
from typing import Final
MAX_SIZE: Final = 100
```

---

## 2. Operators

Python provides a variety of operators for performing operations on variables and values. These include arithmetic, comparison, logical, assignment, bitwise, identity, and membership operators.

### Arithmetic Operators
```python
# Arithmetic Operators
x = 10
y = 3
print(x + y)  # Addition: 13
print(x - y)  # Subtraction: 7
print(x * y)  # Multiplication: 30
print(x / y)  # Division (float): 3.333...
print(x // y) # Floor division: 3 (quotient without remainder)
print(x % y)  # Modulus: 1 (remainder)
print(x ** y) # Exponentiation: 1000 (10^3)
```

### Comparison Operators
```python
# Comparison Operators (return True or False)
a = 5
b = 7
print(a == b)   # Equal: False
print(a != b)   # Not equal: True
print(a > b)    # Greater than: False
print(a < b)    # Less than: True
print(a >= b)   # Greater than or equal: False
print(a <= b)   # Less than or equal: True
```

### Logical Operators
```python
# Logical Operators (used with boolean values)
x = True
y = False
print(x and y)  # Logical AND: False
print(x or y)   # Logical OR: True
print(not x)    # Logical NOT: False
```

### Assignment Operators
```python
# Assignment Operators
n = 10
n += 2   # n = n + 2 -> 12
n -= 3   # n = n - 3 -> 9
n *= 4   # n = n * 4 -> 36
n /= 6   # n = n / 6 -> 6.0
n //= 2  # n = n // 2 -> 3.0
n %= 2   # n = n % 2 -> 1.0
n **= 3  # n = n ** 3 -> 1.0
```

### Bitwise Operators
```python
# Bitwise Operators (operate on binary representations)
a = 5      # 0b0101
b = 3      # 0b0011
print(a & b)   # AND: 1 (0b0001)
print(a | b)   # OR: 7 (0b0111)
print(a ^ b)   # XOR: 6 (0b0110)
print(~a)      # NOT: -6 (inverts all bits)
print(a << 1)  # Left shift: 10 (0b1010)
print(a >> 1)  # Right shift: 2 (0b0010)
```

### Identity Operators
```python
# Identity Operators (check if two variables refer to the same object)
x = [1, 2, 3]
y = x
z = [1, 2, 3]
print(x is y)      # True (same object in memory)
print(x is z)      # False (different objects, same content)
print(x is not z)  # True
```

### Membership Operators
```python
# Membership Operators (check for membership in a sequence)
fruits = ["apple", "banana", "cherry"]
print("banana" in fruits)      # True
print("orange" not in fruits)  # True
```

---

## 3. Control Flow (Conditions, Loops, Comprehensions, Pattern Matching)

Python provides several ways to control the flow of your program, including conditional statements, loops, comprehensions, and pattern matching (Python 3.10+).

### If, Elif, Else Statements
```python
num = 10
if num > 0:
    print("Positive number")  # Executes if condition is True
elif num < 0:
    print("Negative number")  # Executes if previous condition is False and this is True
else:
    print("Zero")             # Executes if all above conditions are False
```

### Match-Case (Pattern Matching, Python 3.10+)
```python
def http_status(code):
    match code:
        case 200:
            return "OK"
        case 404:
            return "Not Found"
        case _:
            return "Unknown"

print(http_status(200))  # Output: OK
```

### For Loops
```python
# Iterate over a sequence (list, tuple, string, etc.)
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Iterate with index using enumerate
for index, fruit in enumerate(fruits):
    print(index, fruit)

# Iterate over a range of numbers
for i in range(5):
    print(i)  # Prints 0 to 4
```

### While Loops
```python
count = 0
while count < 5:
    print(count)
    count += 1  # Increment to avoid infinite loop
```

### Loop Control Statements
```python
for i in range(5):
    if i == 2:
        continue  # Skip the rest of the loop for i==2
    if i == 4:
        break     # Exit the loop when i==4
    print(i)

# 'pass' is a no-op statement (does nothing, used as a placeholder)
for i in range(3):
    pass  # Useful when code is required syntactically but nothing needs to be done
```

### Nested Loops
```python
for i in range(2):
    for j in range(3):
        print(f"i: {i}, j: {j}")
```

### List Comprehensions
```python
# Create a list of squares from 0 to 9
squares = [x ** 2 for x in range(10)]

# With condition (only even squares)
even_squares = [x ** 2 for x in range(10) if x % 2 == 0]
```

### Dictionary Comprehensions
```python
# Create a dictionary mapping numbers to their squares
dict_squares = {x: x ** 2 for x in range(5)}
```

### Set Comprehensions
```python
# Create a set of unique first letters
words = ["apple", "banana", "cherry", "avocado"]
first_letters = {word[0] for word in words}
```

### Generator Comprehensions
```python
# Create a generator for squares (memory efficient)
square_gen = (x ** 2 for x in range(10))
print(next(square_gen))  # Get the next value
```

---

## 4. Functions (def, lambda, *args, **kwargs, decorators, docstrings, recursion)

Functions are reusable blocks of code that perform a specific task. Python supports first-class functions, meaning functions can be assigned to variables, passed as arguments, and returned from other functions.

### Defining Functions
```python
def greet(name):
    """Return a greeting string for the given name."""
    return f"Hello, {name}!"  # Return statement

print(greet("Alice"))  # Output: Hello, Alice!
```

### Function Parameters and Return Values
```python
def add(a, b):
    return a + b  # Returns the sum of a and b

result = add(2, 3)  # result = 5
```

### Default Arguments
```python
def power(base, exponent=2):
    return base ** exponent  # If exponent not provided, defaults to 2

print(power(3))      # 9 (3^2)
print(power(3, 3))   # 27 (3^3)
```

### Variable-Length Arguments (*args, **kwargs)
```python
def print_args(*args):
    # *args collects extra positional arguments as a tuple
    print(args)

def print_kwargs(**kwargs):
    # **kwargs collects extra keyword arguments as a dictionary
    print(kwargs)

print_args(1, 2, 3)  # (1, 2, 3)
print_kwargs(a=1, b=2)  # {'a': 1, 'b': 2}
```

### Lambda (Anonymous) Functions
```python
# Lambda functions are small, anonymous functions
square = lambda x: x ** 2  # Equivalent to: def square(x): return x ** 2
print(square(5))  # Output: 25

# Useful for short, throwaway functions (e.g., with map, filter, sorted)
nums = [1, 2, 3, 4]
squared = list(map(lambda x: x ** 2, nums))  # [1, 4, 9, 16]
```

### Docstrings
```python
def multiply(a, b):
    """Multiply two numbers and return the result."""
    return a * b

print(multiply.__doc__)  # Prints the docstring
```

### Recursion
```python
def factorial(n):
    """Return the factorial of n (n!)."""
    if n == 0:
        return 1
    return n * factorial(n - 1)  # Recursive call

print(factorial(5))  # Output: 120
```

### Decorators
```python
# Decorators are functions that modify the behavior of other functions

def my_decorator(func):
    def wrapper(*args, **kwargs):
        print("Before function call")
        result = func(*args, **kwargs)
        print("After function call")
        return result
    return wrapper

@my_decorator  # Apply the decorator
def say_hello():
    print("Hello!")

say_hello()
# Output:
# Before function call
# Hello!
# After function call
```

### Best Practices
- Use descriptive function and parameter names.
- Write docstrings for all public functions.
- Avoid mutable default arguments (use None and set inside the function).
- Keep functions short and focused on a single task.

---

## 5. Data Structures (Lists, Tuples, Sets, Dicts, Collections)

Python provides several built-in data structures, each with unique properties and use cases.

### Lists
```python
# Lists are ordered, mutable sequences
fruits = ["apple", "banana", "cherry"]
print(fruits[0])         # Access by index (first element)
fruits.append("date")   # Add to end
fruits.insert(1, "kiwi")# Insert at index 1
fruits.remove("banana") # Remove by value
last = fruits.pop()      # Remove and return last item
print(fruits)

# List slicing
numbers = [0, 1, 2, 3, 4, 5]
print(numbers[1:4])      # [1, 2, 3] (start inclusive, end exclusive)
print(numbers[::-1])     # Reverse the list
```

### Nested Lists (2D Lists)
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
print(matrix[1][2])  # Access element in row 2, column 3 (6)
```

### Tuples
```python
# Tuples are ordered, immutable sequences
tuple_data = (1, 2, 3)
print(tuple_data[1])
# Single-element tuple: (value,)
single = (42,)
```

### Sets
```python
# Sets are unordered collections of unique elements
unique_numbers = {1, 2, 3, 3}
print(unique_numbers)  # {1, 2, 3}
unique_numbers.add(4)
unique_numbers.discard(2)
print(2 in unique_numbers)  # False
```

### Dictionaries
```python
# Dictionaries are key-value pairs (unordered in <3.7, insertion-ordered in 3.7+)
person = {"name": "John", "age": 30}
print(person["name"])         # Access value by key
person["city"] = "London"     # Add new key-value pair
person["age"] = 31            # Update value
print(person.keys())           # Get all keys
print(person.values())         # Get all values
print(person.items())          # Get all key-value pairs
```

### Dictionary Methods
```python
# Safe access with get (returns None or default if key not found)
print(person.get("country", "Unknown"))
# Remove a key
person.pop("city")
```

### Comprehensions
```python
# List comprehension
squares = [x**2 for x in range(5)]
# Set comprehension
evens = {x for x in range(10) if x % 2 == 0}
# Dict comprehension
squares_dict = {x: x**2 for x in range(5)}
```

### Collections Module
```python
from collections import Counter, defaultdict, deque, namedtuple, OrderedDict

# Counter: counts occurrences
d = Counter("aabbc")  # {'a': 2, 'b': 2, 'c': 1}

# defaultdict: provides default values for missing keys
default = defaultdict(int)
default["missing"] += 1  # default value is 0, so result is 1

# deque: double-ended queue (fast appends/pops from both ends)
dq = deque([1, 2, 3])
dq.appendleft(0)
dq.append(4)
dq.pop()
dq.popleft()

# namedtuple: tuple with named fields
Point = namedtuple("Point", ["x", "y"])
p = Point(1, 2)
print(p.x, p.y)

# OrderedDict: remembers insertion order (like dict in 3.7+)
od = OrderedDict()
od["a"] = 1
od["b"] = 2
```

### Mutability Table
| Type      | Ordered | Mutable | Example         |
|-----------|---------|---------|----------------|
| list      | Yes     | Yes     | [1, 2, 3]      |
| tuple     | Yes     | No      | (1, 2, 3)      |
| set       | No      | Yes     | {1, 2, 3}      |
| dict      | Yes*    | Yes     | {"a": 1}       |

---

## 6. String Manipulation

Strings are immutable sequences of Unicode characters. Python provides many ways to manipulate and format strings.

### Creating and Using Strings
```python
s = "hello world"  # Double or single quotes are both valid
s2 = 'Python is fun!'
multiline = """This is
a multiline string."""
```

### Indexing and Slicing
```python
text = "abcdefg"
print(text[0])      # 'a' (first character)
print(text[-1])     # 'g' (last character)
print(text[1:4])    # 'bcd' (slice from index 1 to 3)
print(text[::-1])   # 'gfedcba' (reverse string)
```

### String Immutability
```python
# Strings cannot be changed in place
s = "hello"
# s[0] = 'H'  # This would raise an error
s = 'H' + s[1:]  # Create a new string instead
```

### Common String Methods
```python
s = "  hello, Python!  "
print(s.strip())         # Remove leading/trailing whitespace
print(s.lower())         # Convert to lowercase
print(s.upper())         # Convert to uppercase
print(s.replace("Python", "World"))  # Replace substring
print(s.split(","))     # Split into list by comma
print(s.find("Python")) # Find substring index (returns -1 if not found)
print(s.startswith("  h")) # Check prefix
print(s.endswith("!  "))  # Check suffix
```

### String Formatting
```python
name = "Alice"
age = 30
# Old style
print("%s is %d years old" % (name, age))
# str.format method
print("{} is {} years old".format(name, age))
# f-strings (Python 3.6+)
print(f"{name} is {age} years old")
```

### Joining and Splitting
```python
chars = ['a', 'b', 'c']
joined = "".join(chars)  # 'abc'
print(joined)
words = "one two three".split()  # ['one', 'two', 'three']
print(words)
```

### Bytes and Encoding
```python
# Bytes are immutable sequences of bytes (not characters)
b = b"hello"  # Bytes literal
# Encoding and decoding
utf8_bytes = "hello".encode("utf-8")  # String to bytes
text = utf8_bytes.decode("utf-8")      # Bytes to string
```

### Regular Expressions (regex)
```python
import re
pattern = r"\d+"  # One or more digits
result = re.findall(pattern, "abc123def456")  # ['123', '456']
# Search for a pattern
match = re.search(r"Python", "hello Python world")
if match:
    print("Found!", match.group())
```

---

## 7. Modules, Imports, and Environments

Modules and packages help organize code. Python also supports virtual environments for dependency management.

### Importing Modules
```python
import math  # Import the whole module
print(math.sqrt(16))  # Use module_name.function

from datetime import datetime  # Import specific class/function
print(datetime.now())

import numpy as np  # Import with alias
print(np.array([1, 2, 3]))
```

### from ... import ...
```python
from math import pi, sin  # Import specific names
def area_of_circle(r):
    return pi * r ** 2
```

### The __name__ Variable
```python
# Every Python module has a __name__ variable
# If run as a script, __name__ == "__main__"
if __name__ == "__main__":
    print("This script is being run directly.")
else:
    print("This script is being imported.")
```

### Packages and __init__.py
- A package is a directory with an `__init__.py` file (can be empty).
- Import modules from packages using dot notation: `from mypackage import mymodule`.

### Virtual Environments
```bash
# Create a virtual environment (venv)
python -m venv venv
# Activate (Windows)
venv\Scripts\activate
# Activate (Unix/macOS)
source venv/bin/activate
# Deactivate
deactivate
```

### Installing Packages with pip
```bash
pip install requests
pip install numpy==1.24.0  # Specify version
```

### requirements.txt
- List dependencies in a `requirements.txt` file:
  ```
  requests
  numpy==1.24.0
  ```
- Install all dependencies:
  ```bash
  pip install -r requirements.txt
  ```

### Best Practices
- Use virtual environments for every project.
- Pin package versions for reproducibility.
- Avoid `from module import *` (namespace pollution).
- Organize code into modules and packages for clarity.

---

## 8. File and OS Operations

Python provides powerful tools for file I/O and interacting with the operating system.

### Reading and Writing Files
```python
# Read entire file
with open("file.txt", "r") as file:  # 'r' = read mode
    content = file.read()  # Read all contents as a string
    print(content)

# Write to a file (overwrites existing content)
with open("file.txt", "w") as file:  # 'w' = write mode
    file.write("Hello, Python!")

# Append to a file
with open("file.txt", "a") as file:  # 'a' = append mode
    file.write("\nAppended line.")

# Read file line by line
with open("file.txt", "r") as file:
    for line in file:
        print(line.strip())
```

### File Modes
- 'r': Read (default)
- 'w': Write (truncate file)
- 'a': Append
- 'b': Binary mode (e.g., 'rb', 'wb')
- 'x': Create (fail if exists)

### Context Managers
```python
# Custom context manager using 'with'
class ManagedFile:
    def __init__(self, filename):
        self.filename = filename
    def __enter__(self):
        self.file = open(self.filename, 'w')
        return self.file
    def __exit__(self, exc_type, exc_val, exc_tb):
        self.file.close()

with ManagedFile('test.txt') as f:
    f.write('Hello from context manager!')
```

### pathlib (Modern File Paths)
```python
from pathlib import Path
p = Path('file.txt')
print(p.exists())
print(p.read_text())
```

### os and sys Modules
```python
import os
print(os.getcwd())           # Current working directory
print(os.listdir('.'))       # List files in current directory
os.rename('file.txt', 'newfile.txt')  # Rename file
os.remove('newfile.txt')     # Delete file

import sys
print(sys.version)           # Python version
print(sys.argv)              # Command-line arguments
```

### glob (Pattern Matching for Files)
```python
import glob
print(glob.glob('*.txt'))    # List all .txt files in current directory
```

---

## 9. Exception and Error Handling

Python uses exceptions to handle errors gracefully. You can catch, raise, and define custom exceptions.

### Basic try/except
```python
try:
    num = int("abc")  # Raises ValueError
except ValueError:
    print("Invalid input!")
```

### Multiple except Blocks
```python
try:
    x = 1 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
except Exception as e:
    print(f"Other error: {e}")
```

### else and finally
```python
try:
    num = int("123")
except ValueError:
    print("Invalid input!")
else:
    print("Conversion successful!")  # Runs if no exception
finally:
    print("Execution completed")     # Always runs
```

### Catching Multiple Exceptions
```python
try:
    # Some code that may raise ValueError or TypeError
    pass
except (ValueError, TypeError) as e:
    print(f"Caught error: {e}")
```

### Raising Exceptions
```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("b cannot be zero!")
    return a / b
```

### Custom Exceptions
```python
class MyError(Exception):
    pass

try:
    raise MyError("Something went wrong!")
except MyError as e:
    print(e)
```

### Assertions
```python
x = 10
assert x > 0, "x must be positive"  # Raises AssertionError if condition is False
```

### Warnings
```python
import warnings
warnings.warn("This is a warning!")
```

### Best Practices
- Catch only exceptions you expect and can handle.
- Use specific exception types, not bare `except:`.
- Clean up resources in `finally` or use context managers.
- Use assertions for debugging, not for data validation in production.

---

## 10. Object-Oriented Programming (OOP)

OOP allows you to model real-world entities using classes and objects. Python supports inheritance, encapsulation, and polymorphism.

### Defining Classes and Creating Objects
```python
class Person:
    def __init__(self, name, age):  # Constructor
        self.name = name            # Instance attribute
        self.age = age

    def greet(self):                # Instance method
        return f"Hello, my name is {self.name}."

person1 = Person("Alice", 25)
print(person1.greet())  # Output: Hello, my name is Alice.
```

### Inheritance
```python
class Student(Person):  # Inherit from Person
    def __init__(self, name, age, student_id):
        super().__init__(name, age)  # Call parent constructor
        self.student_id = student_id

    def greet(self):  # Override method
        return f"Hi, I'm {self.name}, student #{self.student_id}."

s = Student("Bob", 20, "S123")
print(s.greet())
```

### Dunder (Magic) Methods
```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __add__(self, other):  # v1 + v2
        return Vector(self.x + other.x, self.y + other.y)
    def __repr__(self):        # print(v)
        return f"Vector({self.x}, {self.y})"

v1 = Vector(1, 2)
v2 = Vector(3, 4)
print(v1 + v2)  # Vector(4, 6)
```

### Class and Static Methods
```python
class MyClass:
    count = 0  # Class attribute (shared by all instances)

    @classmethod
    def increment_count(cls):
        cls.count += 1

    @staticmethod
    def say_hello():
        print("Hello from static method!")

MyClass.increment_count()
MyClass.say_hello()
```

### Properties (Getters/Setters)
```python
class Celsius:
    def __init__(self, temperature=0):
        self._temperature = temperature
    @property
    def temperature(self):
        return self._temperature
    @temperature.setter
    def temperature(self, value):
        if value < -273.15:
            raise ValueError("Temperature below absolute zero!")
        self._temperature = value

c = Celsius()
c.temperature = 25
print(c.temperature)
```

### Dataclasses (Python 3.7+)
```python
from dataclasses import dataclass
@dataclass
class Point:
    x: int
    y: int

p = Point(1, 2)
print(p)
```

---

## 11. Iterators and Generators

Iterators and generators provide a way to iterate over data efficiently, especially for large or infinite sequences.

### Iterators
```python
# Any object with __iter__() and __next__() is an iterator
my_list = [1, 2, 3]
my_iter = iter(my_list)  # Get iterator from iterable
print(next(my_iter))     # 1
print(next(my_iter))     # 2
print(next(my_iter))     # 3
# next(my_iter) would raise StopIteration
```

### Custom Iterator
```python
class CountDown:
    def __init__(self, start):
        self.current = start
    def __iter__(self):
        return self
    def __next__(self):
        if self.current <= 0:
            raise StopIteration
        val = self.current
        self.current -= 1
        return val

for num in CountDown(3):
    print(num)  # 3, 2, 1
```

### Generators (Functions with yield)
```python
def my_generator():
    yield 1
    yield 2
    yield 3

gen = my_generator()
print(next(gen))  # 1
print(next(gen))  # 2
print(next(gen))  # 3
```

### Generator Expressions
```python
# Like list comprehensions, but with ()
squares = (x ** 2 for x in range(5))
for sq in squares:
    print(sq)
```

### Why Use Generators?
- Memory efficient (generate items on the fly)
- Useful for large data, pipelines, or infinite sequences

---

## 12. Async Programming (async/await)

Async programming allows you to write concurrent code using the async/await syntax, useful for I/O-bound tasks.

### Basic async/await
```python
import asyncio

async def fetch_data():
    print("Fetching data...")
    await asyncio.sleep(1)  # Simulate async I/O
    print("Data fetched!")

async def main():
    await fetch_data()

asyncio.run(main())  # Run the async program
```

### Running Multiple Coroutines
```python
import asyncio

async def task(name, delay):
    await asyncio.sleep(delay)
    print(f"Task {name} done!")

async def main():
    await asyncio.gather(
        task("A", 1),
        task("B", 2),
    )

asyncio.run(main())
```

### async for and async with
```python
import asyncio

class AsyncCounter:
    def __init__(self, limit):
        self.limit = limit
        self.count = 0
    def __aiter__(self):
        return self
    async def __anext__(self):
        if self.count >= self.limit:
            raise StopAsyncIteration
        await asyncio.sleep(0.1)
        self.count += 1
        return self.count

async def main():
    async for num in AsyncCounter(3):
        print(num)

asyncio.run(main())
```

---

## 13. Important Built-in Functions

Python provides many built-in functions for common tasks. Here are some of the most useful, grouped by category:

### Numeric Functions
```python
print(abs(-10))         # Absolute value: 10
print(round(3.14159, 2)) # Round to 2 decimal places: 3.14
print(divmod(10, 3))   # (Quotient, remainder): (3, 1)
print(pow(2, 3))       # 2^3 = 8
```

### Sequence and Collection Functions
```python
lst = [1, 2, 3, 4]
print(len(lst))         # Length: 4
print(max(lst))         # Maximum: 4
print(min(lst))         # Minimum: 1
print(sum(lst))         # Sum: 10
print(sorted([3, 1, 4, 1, 5]))  # [1, 1, 3, 4, 5]
print(list(reversed(lst)))       # [4, 3, 2, 1]
print(list(zip(['a', 'b'], [1, 2])))  # [('a', 1), ('b', 2)]
```

### Functional Programming
```python
nums = [1, 2, 3, 4]
print(list(map(lambda x: x**2, nums)))  # [1, 4, 9, 16]
print(list(filter(lambda x: x % 2 == 0, nums)))  # [2, 4]
print(all([True, True, False]))  # False (all elements True?)
print(any([False, False, True])) # True (any element True?)
```

### Type and Conversion Functions
```python
print(isinstance(10, int))  # True
print(type(3.14))           # <class 'float'>
print(str(100))             # '100'
print(int('5'))             # 5
print(float('3.14'))        # 3.14
print(list('abc'))          # ['a', 'b', 'c']
print(dict([('a', 1), ('b', 2)]))  # {'a': 1, 'b': 2}
```

### Character and Encoding Functions
```python
print(ord('A'))   # 65 (ASCII value)
print(chr(65))    # 'A' (character from ASCII)
print(hex(255))   # '0xff'
print(bin(10))    # '0b1010'
print(oct(8))     # '0o10'
```

### Evaluation and Formatting
```python
print(eval("3 + 5"))           # 8 (evaluate string as expression)
print("{:.2f}".format(3.14159)) # '3.14' (format float)
```

---

## 14. Useful Python Libraries for Interviews

Python's standard library and a few external libraries are extremely useful for coding interviews and real-world tasks.

### collections
```python
from collections import Counter, defaultdict, deque, namedtuple, OrderedDict

# Counter: count occurrences
d = Counter("aabbc")  # {'a': 2, 'b': 2, 'c': 1}

# defaultdict: default values for missing keys
default = defaultdict(int)
default["missing"] += 1  # default value is 0, so result is 1

# deque: double-ended queue
dq = deque([1, 2, 3])
dq.appendleft(0)
dq.append(4)
dq.pop()
dq.popleft()

# namedtuple: tuple with named fields
Point = namedtuple("Point", ["x", "y"])
p = Point(1, 2)
print(p.x, p.y)

# OrderedDict: remembers insertion order
od = OrderedDict()
od["a"] = 1
od["b"] = 2
```

### heapq (Heap queue algorithms)
```python
import heapq
nums = [5, 1, 3]
heapq.heapify(nums)         # Transform list into a heap
print(heapq.heappop(nums))  # Pop the smallest item: 1
heapq.heappush(nums, 2)     # Push new item
```

### itertools (Iterator building blocks)
```python
from itertools import permutations, combinations, product, groupby
print(list(permutations([1, 2, 3])))  # All possible orderings
print(list(combinations([1, 2, 3], 2)))  # All pairs
print(list(product([1, 2], ['a', 'b']))) # Cartesian product
```

### functools (Higher-order functions)
```python
from functools import lru_cache, reduce, partial

@lru_cache(maxsize=128)
def fib(n):
    if n < 2:
        return n
    return fib(n-1) + fib(n-2)

print(fib(10))

print(reduce(lambda x, y: x + y, [1, 2, 3, 4]))  # 10
```

### bisect (Binary search)
```python
import bisect
lst = [1, 3, 4, 7]
print(bisect.bisect_left(lst, 4))  # 2 (index to insert 4)
bisect.insort(lst, 5)              # Insert 5 in order
print(lst)
```

### math and random
```python
import math, random
print(math.gcd(12, 18))    # 6
print(math.isclose(0.1+0.2, 0.3))  # True (floating point comparison)
print(random.randint(1, 10))       # Random int between 1 and 10
print(random.choice(['a', 'b', 'c']))
```

### datetime
```python
from datetime import datetime, timedelta
now = datetime.now()
print(now)
print(now + timedelta(days=7))  # One week later
```

### re (Regular expressions)
```python
import re
pattern = r"\d+"
print(re.findall(pattern, "abc123def456"))  # ['123', '456']
```

### json and csv
```python
import json, csv
# JSON
obj = {"a": 1, "b": 2}
s = json.dumps(obj)  # Serialize to string
print(json.loads(s)) # Deserialize
# CSV
with open("data.csv", "w", newline="") as f:
    writer = csv.writer(f)
    writer.writerow(["name", "age"])
    writer.writerow(["Alice", 30])
```

### argparse (Command-line arguments)
```python
import argparse
parser = argparse.ArgumentParser()
parser.add_argument('--name')
args = parser.parse_args(['--name', 'Alice'])
print(args.name)
```

### logging
```python
import logging
logging.basicConfig(level=logging.INFO)
logging.info("This is an info message.")
```

### unittest and pytest (Testing)
```python
import unittest
class TestAdd(unittest.TestCase):
    def test_add(self):
        self.assertEqual(1 + 2, 3)

# pytest: use assert directly in test functions
# def test_add():
#     assert 1 + 2 == 3
```

### requests (HTTP for external APIs)
```python
import requests
response = requests.get('https://api.github.com')
print(response.status_code)
```

---

## 15. Modern Python Features (3.8+)

Python continues to evolve with new features. Here are some highlights from recent versions:

### Walrus Operator (:=, Python 3.8+)
```python
# Assignment expressions allow assignment inside expressions
if (n := 10) > 5:
    print(f"n is {n}")
```

### Positional-Only Parameters (Python 3.8+)
```python
def add(a, b, /, c):
    return a + b + c
# a and b must be positional, c can be keyword
print(add(1, 2, 3))
# print(add(a=1, b=2, c=3))  # TypeError
```

### f-string Debugging (Python 3.8+)
```python
x = 42
print(f"{x=}")  # Prints: x=42
```

### Type Hint Improvements (Python 3.9+)
```python
# Built-in generic types (no need for typing.List, etc.)
nums: list[int] = [1, 2, 3]
```

### Pattern Matching (match-case, Python 3.10+)
```python
def http_status(code):
    match code:
        case 200:
            return "OK"
        case 404:
            return "Not Found"
        case _:
            return "Unknown"
print(http_status(200))
```

### Structural Pattern Matching (Python 3.10+)
```python
def process_point(pt):
    match pt:
        case (0, 0):
            return "Origin"
        case (0, y):
            return f"Y={y} axis"
        case (x, 0):
            return f"X={x} axis"
        case (x, y):
            return f"Point ({x}, {y})"
print(process_point((0, 5)))
```

### dataclasses (Python 3.7+)
```python
from dataclasses import dataclass
@dataclass
class Point:
    x: int
    y: int
p = Point(1, 2)
print(p)
```

### Enums (Python 3.4+)
```python
from enum import Enum
class Color(Enum):
    RED = 1
    GREEN = 2
    BLUE = 3
print(Color.RED)
```

---

## 16. Tips, Idioms, and Common Pitfalls

### Best Practices
- Follow [PEP8](https://www.python.org/dev/peps/pep-0008/) for code style (indentation, naming, spacing).
- Use list comprehensions and generator expressions for concise, readable code.
- Prefer 'with' for file/resource management (context managers).
- Use virtual environments for project isolation.
- Write docstrings for all public modules, classes, and functions.
- Avoid using mutable default arguments in functions.
- Use exceptions for error handling, not return codes.

### Common Pitfalls
```python
# Mutable default arguments
def append_to_list(lst=[]):
    lst.append(1)
    return lst
print(append_to_list()) # [1]
print(append_to_list()) # [1, 1]  # Problem: same list reused!

# Correct way:
def append_to_list_safe(lst=None):
    if lst is None:
        lst = []
    lst.append(1)
    return lst
```

### Idiomatic Python ("Pythonic" Code)
```python
# Swapping values
x, y = 1, 2
x, y = y, x

# Looping with index and value
for i, value in enumerate(['a', 'b', 'c']):
    print(i, value)

# Unpacking
first, *middle, last = [1, 2, 3, 4, 5]

# Use 'in' for membership
d = {'a': 1, 'b': 2}
if 'a' in d:
    print('Key exists!')

# Use 'get' for safe dict access
value = d.get('c', 0)  # 0 if 'c' not in d
```

### Zen of Python
```python
import this  # Prints the Zen of Python (guiding principles)
```

### Interview Tips
- Practice writing code on a whiteboard or in a plain text editor.
- Read the problem carefully and clarify requirements.
- Use built-in data structures and libraries to save time.
- Write clean, readable code with comments.
- Test edge cases and handle errors gracefully.

---

## 17. Resources & Further Reading

- [Python.org Documentation](https://docs.python.org/3/)
- [PEP8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/)
- [Real Python Tutorials](https://realpython.com/)
- [Corey Schafer's YouTube Channel](https://www.youtube.com/c/CoreySchafer)
- [Dive Into Python 3](https://diveintopython3.net/)
- [LeetCode Python Problems](https://leetcode.com/problemset/all/?difficulty=All&status=All&tags=python)
- [Hitchhiker’s Guide to Python](https://docs.python-guide.org/)
- [PyPI - Python Package Index](https://pypi.org/)
- [Python Patterns](https://github.com/faif/python-patterns)
- [Awesome Python](https://awesome-python.com/)

---

## 18. Conclusion

This guide provides a comprehensive foundation for Python syntax, problem-solving, and best practices. Mastering these concepts will prepare you for technical interviews and real-world development. Remember to keep practicing, stay updated with new Python features, and write clean, readable, and efficient code. Happy coding!

