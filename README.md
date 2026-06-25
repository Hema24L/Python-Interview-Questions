# Python-Interview-Questions
Python is one of the most widely used programming languages in software development, data science, AI, automation and cybersecurity. Interviewers often assess candidates on Python fundamentals, object-oriented programming(OOP), data structures, exception handling, file operations, and advanced concepts.

---
## What is Python?
Python is a high-level interpreted, object-oriented and dynamically typed programming languaged created by Guido Van Rossum in 1991.
### Features
- Easy to learn and read
- Open-source
- Cross-platform
- Large standard library
- Supports multiple programming paradigms
- Automatic memory management

---
## Advantages and Disadvantages of Python
|Advantages|Disadvantages|
|---|---|
|Simple syntax|Slower than complied languages|
|Rapid development|Higher memory consumption|
|Large community support|Not ideal for mobile application development|
|Extensive libraries and frameworks||
|Platform independent||
|Supports automation and scripting||

---
## Difference between List and Tuple
|Features|List|Tuple|
|---|---|---|
|Mutable|Yes|No|
|Syntax|[]|()|
|Performance|Slower|Faster|
|Memory|More|Less|
### Example
``` bash
my_list = [1,2,3]
my_list.append(4) #Allowed
```

```bash
my_tuple = (1,2,3)
my_tuple.append(4) #Error
```

---
## Difference between == and is
Example 1:
```
a = [1,2]
b = [1,2]

print(a==b) #True
print(a is b) #False
```
The reason `==` is true because it checks whether values are equal and `is` is false because it checks whether two variables points to the same memory location(identity).

Example 2:
```
x = 100
y = 100
if x is y:
  print(id(x) == id(y)) #True(Same memory address)
```
- The above is True because Python optimizes memory for performance using Integer Caching and String Interning. When created certain identical values, Python does not make new object. It reuses old one.
- Small Integers(-5 to 256): Python pre-loads these numbers into memory when it starts up. Any variable assigned to 10 points to the exact same shared object.
- Short Strings: Simple strings(without spaces or special characters) are automatically reused.
- Mutable Objects(Lists, Dicts): These are never optimized or shared. They will always return `False` with `is`, even inside an `if` statement.

---
## What are Python Data Types
### Numeric
```
int
```
  - Signed whole numbers of unlimited length
  - Used in Loop counters, index positions and discrete counts.
  - Used for exact arithmetic without decimal rounding errors.
```
float
```
  - Real numbers represented with a decimal point.
  - Used in Financial calculations, scientific data & measurements.
  - Used for continuous values and fractional data.
```
complex
```
  - Numbers written with a real part and an imaginary part(`a + bi`).
### Sequence
```
list
```
  - Mutable, ordered collections of items.
  - Used in data pipelines, dynamic arrays.
  - It allows frequent updating, removing of elements.
```
tuple
```
  - Immutable, ordered collections of items.
  - Used in DB records, function return values, fixed configurations.
  - Protects data from accidental changes, uses less memory.
```
range
```
  - Immutable sequence of numbers generated on demand.
  - Used in controlling `for` loops and iterating specific number of times.
  - Highly memory efficient because it calculates numbers only when needed.
```
str
```
  - Immutable sequence of Unicode characters(text).
  - Used in User interface, file paths and text processing.
  - Standardises human-readable data representation and manipulation.
### Mapping
```
dict
```
  - Unordered collections of key-value pairs where keys must be unique.
  - Used in JSON data, user profiles, quick lookup tables.
  - Provides lightning-fast data retrieval by mapping keys directly to values.
### Set
```
set
```
  - Mutable, unordered collections of unique elements.
  - Used in Deduplicating list and mathematical operations(unions, intersections).
  - Eliminates duplicated automatically and provides fast membership checking.
```
frozenset
```
  - Immutable version of a standard set.
  - Used in Dictionary keys or elements inside another set.
  - Safe to use as a key because its content cannot change.
### Boolean
```
bool
```
  - A logical type that represents only `True` or `False`.
  - Used in conditional statements(`if/else`) and loop termination conditions.
  - Controls the execution flow and logic of programs.

---
## What is Dictionary
A Dictionary stores data as key-value pairs.
```
student = {
  'name': "John",
  'age': 22
}
```
### Features
- Mutable
- Unordered (insertion ordered in modern Python)
- Fast lookup using keys

---
## What is List Comprehension
### Traditional
```
squares = []
for i in range(5):
  squares.append(i*i)
```
### List Comprehension
```
squares = [i*i for i in range(5)]
#[0, 1, 4, 9, 16]
```
  - It runs faster than a standard loop because Python optimizes the creation loop behind the scenes.
  - Used in Data filtering, Data transformation, quick math operations on sequences.

---
## What is Lambda Function
- An anonymous functions that can take any number of arguments but can only have one single expression.
- Instead of using `def`, define it using `lambda`. It is short, one-time operation where defining full function would be overkill.
### Syntax
```
lambda arguments: expression
```
### Example
Standard way:
```
def add_five(x):
  return x + 5
print(add_five(5)) #Output:10
```
Lambda way:
```
add_five = lambda x: x + 5
print(add_five(5)) #Output:10
```
- It saves from writing multiple lines of bolierplate code for simple logic.
- Perfect for functions only need to use once in the entire program.
- It can be passed as an argument inside higher-order functions like map(), filter(), sorted().
  ```
  num = [1,2,3,4,5,6]
  even_num = list(filter(lambda x: x % 2 == 0, numbers))
  print(even_num) #Output:[2,4,6]
  ```
  ### Comparison between def & lambda
  |Feature|`def`|`lambda`|
  |---|---|---|
  |Name|Named(Explicitly defined)|Anonymous(nameless)|
  |Structure|Can have multiple lines of code|Limited to a single expression|
  |Return|Required explicit `return` statement|Automatically returns the expression value|
  |Docstrings|Supports documentation strings `"""doc"""`|Does not support docstrings|
  |Lifespan|Reusable anywhere in code|Usually used once|
  |Debugging|Error tracebacks show the function name|Tracebacks only show `<lambda>`|
  |Best used for|Complex logic, loops, larger code blocks|Quick data transformations, sorting, filtering|

