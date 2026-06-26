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

---
## What is the difference between Deep Copy and Shallow Copy?
|Feature|Shallow Copy|Deep Copy|
|---|---|---|
|Definition|Copies top-level properties; nested objects are still referenced|Completely clones the object and all nested sub-objects|
|Nested Elements|Original and copy share the same memory addresses for nested data|Original and copy have entirely distinct memory addresses|
|Effect of changes|Modifying nested elements in the copy changes the original|Modifying the copy does not affect the original|
|Performance|Faster and more memory-efficient|Slower and more resource intensive|

### Shallow Copy
```
import copy
a = [[1,2],[3,4]]
b = copy.copy(a)
```
- If alter a nested list or dict, it will change the original. 
### Deep copy
```
import copy
a = [[1,2],[3,4]]
b = copy.deepcopy(a)
```

---
## What is Exception Handling
- A programming mechanism that prevents an application from crashing when an error occurs during runtime.
- Instead of halting execution, the program catches the error, manages it gracefully and continues running the remaining code.
### Core Python Syntax
-  `try` : Holds the risky code that might raise an error.
-  `except`: Catches and handles specific error if they occur.
-  `else`: Runs only if the `try` block executes with zero error.
-  `finally`: Runs always, whether an error occurred or not.
### Example
```
def divide_num(a,b):
  try:
    result = a/b
  except ZeroDivisionError:
    print("Error: You cannot divide by Zero!")
    result = None
  else:
    print("Division successful")
  finally:
    print("Execution complete")
  return result
divide_num(10,0)
```
### Difference between Syntax Errors and Exceptions
- Syntax Error: Found by parser before the code runs. The program cannot start.
- Exceptions: Found during execution. The syntax is perfect, but an environmental or logical issue stops the script.
### Why is except Exception: better than a bare except:
- A bare `except:` catches absolutely everything, including system exits like `SystemExit` or `KeyboardInterrupt`. This makes it incredibly difficult for a user to force-stop a broken script.
- Using `except Exception:` only catches standard application errors, leaving system-level commands functional.
### What is the purpose of the raise keyword
- `raise` is used to intentionally trigger an exception when specific businees logic is violated.
  ```
  if user_age < 18:
    raise ValueError("User must be an adult to register")
  ```

---
## What are *args and **Kwargs
- These functions allows a function to accept a variable number of arguments, making the code flexible and dynamic. They are used when we don't know in advance how many arguments a user might pass into the function.
- `*args`: Collects extra positional arguments as a tuple.
  - Used when we want to pass an arbitary number of positional arguments to a function.
    ```
    def sum_numbers(*args):
      print(args) #It packs arguments into a tuple
      return sum(args)
    # Call with 3 arguments
    print(sum_numbers(1,2,3)) #Output:(1,2,3) then 6
    # Call with 5 arguments
    print(sum_numbers(10,20,30,40,50)) #Output: then 150
    ```
- `**kwargs`: Collects extra keyword arguments as a dictionary.
  - Used when want to pass an arbitary number of named/keyword arguments.
    ```
    def introduce_user(**kwargs):
      print(kwargs) # packs arguments into a dictionary
      for key, value in kwargs.items():
        print(f"{key}: {value}")
    introduce_user(name="Alice", role="Developer", location="New York")
    # Outputs: {'name':'Alice'}
    ```
### Combining both
- A strict specific order must be followed to use both the arguments together in a single function
  1. Standard formal arguments
  2. *args
  3. **kwargs
  ```
  def master_function(standard_arg, *args, **kwargs):
    print(f"standard:{standard_arg}")
    print(f"Args:{args}")
    print(f"Kwargs:{kwargs}")
  master_function("First", 2, 3, 4, role="Admin",active=True)
  # Output:
  # Standard: First
  # Args: (2, 3, 4)
  # Kwargs: {'role': 'Admin', 'active': True}
  ```
### What is the purpose of a single * in a function definition without a varaible name?
  - It forces all subsequent arguments to be passed as keyword-only arguments.
  - `def client(name, *, premium=False):` means `premium` must be called like `client("Alice", premium=True)` calling `client("Alice", True)` will fail.
### Can we use * and ** to unpack data outside of function arguments?
- Yes, can use them to merge lists or dictionaries easily.
  ```
  list1 = [1, 2]
  list2 = [*list1, 3, 4] # [1, 2, 3, 4]

  dict1 = {'a':1}
  dict2 = {**dict1, 'b':2} # {'a' : 1, 'b' : 2}
  ```

---
## What is Object-Oriented Programming(OOP)
- It is a programming paradigm that organizes software design around data, or objects, rather than functions and logic.
- An object is a self-contained component that combines both data (attributes) and behavior (methods).
- Class: Blueprint, template or recipe. It defines what data the object will hold and what it can do.
- Object: The actual instance created from blueprint.
```
# The Class (Blueprint)
class Car:
    def __init__(self, brand, model):
        self.brand = brand  # Attribute
        self.model = model  # Attribute
    def drive(self):  # Method
        return f"The {self.brand} {self.model} is driving."

# The Objects (Instances)
car1 = Car("Tesla", "Model 3")
car2 = Car("Ford", "Mustang")
print(car1.drive())  # The Tesla Model 3 is driving.
```
### 4 pillars of OOP
1. Encapsulation (Data Hiding)
  - Bundling data and methods together inside a class and restricting direct access to some components.
  - Python uses underscores to suggest or enfore privacy. A single underscore `_variable` is a convention for private data. A double underscore `__variable` activates name mangling to make it harder to access from outside.
  - Think encapsulation as a capsule pill protecting the medicine inside from the outer environment.
    ```
    class BankAccount:
      def __init__(self):
        self.__balance = 0
    ```
2. Inheritance (Code Reuse)
  - Allowing a new class(child/subclass) to adopt the attributes and methods of an existing class(parent/superclass).
  - Can pass the parent class into the child class definition.
    ```
    class Animal:
      def speak(self):
        print("Animal Sound")
    class Dog(Animal):
      pass

    d = Dog()
    d.speak() 
    ```
3. Polymorphism (Many Forms)
  - Allowing different classes to have methods with exact same name but different behaviors.
  - Python uses 'duck typing'. If two different classes both have a `speak()` method, Python will execute the correct one depending on the object passed.
    ```
    class Dog:
      def sound(self):
        print("Bark")
    Class Cat:
      def sound(self):
        print("Meow")
    ```
4. Abstraction (Hiding Complexity)
  - Hiding internal complex implementation details and showing only the essential features to the user.
  - Python uses built-in `abc`(Abstract Base Classes) module to create abstract classes that cannot be instantiated directly, forcing child classes to implement specific methods.
  - Think Abstraction as we know how to drive a car by using the steering whell and pedals (interface), but we need not to understand how the internal combustion engine works (implementation).
    ```
    from abc import ABC, abstractmethod
    class Vehicle(ABC):
      @abstractmethod
      def start(self):
        pass
    ```
### What is the purpose of self in Python classes?
`self` represents the specific instance of the class that is currently calling the method. It binds the attributes to that specific object. It is not a Python Keyword, just a universally accepted naming convention.
### Difference between Class Method and Static Method?
|Class|Static|
|---|---|
|`@classmethod`: It receives the class(`cls`) as first argument. It can modify class state that applies across all instances.|`@staticmethod`: Receives no implicit first argument(neither `self` nor `cls`). It behaves like a normal function but sits inside the class namespace for logical grouping.|
```
# Example of @classmethod
class ExampleClass:
  class_variable = "Shared Data"

  @classmethod
  def my_class_method(cls, argument):
    # cls refers to ExampleClass, Not an instance of it
    print(f"Accessing:{cls.class_variable}")
    print(f"Argument passed:{argument}")

# calling the class method directly without creating an object
ExampleClass.my_class_method("Hello World")
```
---
## What is the difference between Module and Package
|Features|Module|Package|
|---|---|---|
|Physical form|A single `.py` file|A directory (folder) containing `.py` files|
|Purpose|Groups related functions, classes, variables|Groups related modules together into a hierarchy|
|Initialization|Not required|Traditionally requires an `__init__.py` file|
|Import Syntax|`import module_name`|`from package_name import module_name`|

Examples:
MODULE
```
math_utils.py
```
PACKAGE
```
project/
|
|-- __init__.py
|-- module1.py
|-- module2.py
```
### What is the purpose of __init__.py file?
It executes automatically when a package or a module inside it is imported. It is used to initialize package-level variables, set up configurations or control what gets exposed to the user when they run `from package import *` using the `__all__` list.
### Are __init__.py files still mandatory in modern Python?
No, not since Python 3.3. Python 3.3 introduced Namespace packages, which allow Python to recognize a folder as a package without an `__init__.py` file. However, it is still standard industry practice to include them for Regular packages to clearly state design intent and handle initialization logic.
### What is the difference between a built-in module and third-party library?
Built-in modules come pre-installed with Python (the Standard Library `math`, `os`, `sys`). Third-party libraries (`requests`, `numpy`) must be downloaded using a package manager like `pip` before they can be imported.

---
## What is the difference between Remove(), Pop(), Del()?
|Method/Statement|How it Identifies the Item|What it returns|Modifies Original List?|
|---|---|---|---|
|`list.remove(value)`|By value|`none`|Yes|
|`list.pop(index)`|By index(its position)|The removed item|Yes|
|`del list[index]`|By index(or slices)|Nothing|Yes|
### What is the time complexity (Big O) of these operations?
- `remove(value)`: O(n). Python must search the list from left to right to find the matching value.
- `pop()` Last item: O(1). Removing the final element takes constant time. 
- `pop(index) / del list[index]`: O(n). When you remove an item from the middle of a list, Python must shift all subsequent elements one position to the left in memory.
### How to safely remove all occurrences of an item from a list?
- When using `for` loop with `.remove()` which skips elements as the list shortens.
  ```
  items = [1, 2, 3, 2, 4, 2]
  # keeps everything that is NOT 2
  filtered_items = [x for x in items if x != 2]
  print(filtered_items) #Output: [1, 3, 4]
  ```

---
## What is generator?
- Special type of function that returns an iterator object.
- Instead of computing and returning all values at once(like a standard function with a `return` statement), a generator yields values one at a time, on demand, using the `yield` keyword.
### Core Concept: return vs yield
- `return`: Terminates the function entirely and sends back the final result. The function's local state is destroyed.
- `yield`: Pauses the function, saves its entire internal state and sends a value back to the caller. The next time the function is called, it resumes exactly where it left off.
  ```
  def std_countdown(n):
    result = []
    while n > 0:
      result.append(n)
      n -= 1
    return result

  def gen_countdown(n):
    while n > 0:
      yield n
      n -= 1
  #using the generator
  counter = gen_countdown(3)
  print(next(counter)) # Output: 3(pause here)
  print(next(counter)) # Output: 2(resumes and pause)
  print(next(counter)) # Output: 1(resumes and pause)
  print(next(counter)) -> raises StopIteration error because Loop ended
  ```
### Why use generators
- Normal function reads all 10 million rows into a list first. This can cause an Out of Memory(OOM) error and crash the application.
- A generator reads one row at a time, processes it, drops it and moves to the next. The memory footprint remains completely flat regardless of how large the dataset is.
### Generator expression
Just like list comprehension, which uses `[]`, generator expression uses `()`
```
squares_list = [x**2 for x in range(1000000)] #List comprehension
squares_gen = (x**2 for x in range(1000000)) #Generator expression

print(squares_list.sizeof()) # Massive size in bytes
print(squares_gen.sizeof()) # Tiny, constant size in bytes
```
### What happens when a generator runs out of items?
Python automatically raises a built-in `StopIteration` exception. When use a `for` loop over a generator, the loop handles this exception behind the scenes to stop executing smoothly.
### Can a generator function have a return statement?
Yes, in Python3, `return` statement can be included inside a generator. Doing so terminates the generator and raises a `StopIteration` exception, where the returned value becomes the error message payload.
### Difference between Iterators & Generators
|Feature|Iterator|Generator|
|---|---|---|
|How it's created|Created by implementing a class with specific dunder methods|Created by writing a function that uses the `yied` keyword|
|Protocol Implementation|Must explicitly define `__iter__()` and `__next__()`|Python automatically implements `__iter__()` and `__next__()`|
|State Tracking|Must manually track and update internal variables(state)|Python handles state tracking and execution pausing automatically|
|Code complexity|Requires more boilerplate code and class structures|Highly concise, readable and compact|
### What is the relationship between an Iterable, an Iterator and a Generator?
- Iterable: Any object can loop over (e.g., a list, String or Tuple). It has an `__iter__()` method that return an iterator.
- Iterator: An object with a `__next__()` method that fetched values one by one.
- Generator: A specific kind of iterator built using a function and `yield`.
### When should we use a custom iterator class instead of a Generator function?
Must use a custom iterator class when complex object-oriented behavior such as adding extra custom methods, maintaining shared attributes across instances or when need the ability to easily reset or modify the internal state of the stream from the outside.

---
## Decorators
- A design pattern that allows you to modify or extend the behavior of a function or class without permanently changing its actual source code.
- It is simply a function that takes another function as an argument, adds some functionality and returns as modified function.
### Basic Decorator syntax
- Python uses the `@` symbol to apply a decorator to a function.
  ```
  # define the decorator function
  def my_decorator(func):
    def wrapper():
      print("Something is happening BEFORE the function is called")
      func()
      print("Something is happening AFTER the function is called")
    return wrapper

  @my_decorator
  def say_hello():
    print("Hello")

  say_hello()

  #Output
  # Something is happening BEFORE the function is called.
  # Hello!
  # Something is happening AFTER the function is called.
  ```
### Decorating functions that Accept arguments
- If the function being decorated accepts inputs, the inner `wrapper` function inside your decorator must use `*args` and `**kwargs` so it can accept any arbitrary arguments.
  ```
  def log_decorator(func):
    def wrapper(*args, **kwargs):
        print(f"Running function '{func.__name__}' with arguments {args}")
        result = func(*args, **kwargs)
        print(f"Function '{func.__name__}' finished execution.")
        return result
    return wrapper

  @log_decorator
  def greet(name, age):
    return f"Hi {name}, you are {age} years old."

  print(greet("Alice", 28))
  ```
### Real-world use cases
- Why to use a decorator in a real project?
  - Logging: Tracking when specific functions are called and with what parameters.
  - Authentication/Authorization: Checking if a user is logged in before allowing them to access a specific route or view(common in Flask/Django).
  - Caching/Memorization: Storing the results of expensive function calls so they don't run twice with the same inputs.
  - Timing: Measuring how long a function takes to execute for performance profiling.
### Can I chain multiple decorators together?
Yes. Can stack them on top of each other. They execute in order from top to bottom.
```
@decorator_one
@decorator_two
def my_func():
    pass
```
---
## Multithreading
- A programming technique that allows a single CPU core to execute multiple tasks(threads) concurrently by rapidly switching between them.
### Core paradox in Python: The GIL(Global Interpreter Lock)
- GIL constraint: Python has a strict security lock called the GIL. It ensures that only one thread can execute Python code at any given moment, even if the computer has 8 or 16 CPU cores.
- Concurrency illusion: Instead of running truly in parallel, Python threads constantly pause and take turns on a single CPU core. It happens so fast that it looks parallel to the human eye.
### When to use Multithreading (I/O bound tasks)
- Because of GIL, multithreading will not speed up heavy mathematical calculations(CPU-Bound tasks).
- However, it is highly effective for I/O bound tasks where the program spends most of its time waiting for external networks or hardware.
- Good Use Cases
    - Web scraping
    - Downloading multiple files simultaneously
    - Reading and writing large numbers of files to a hard drive
    - Making API requests to external databases.
```
import threading
import time

def worker_task(name, delay):
    print(f"Worker {name} started.")
    time.sleep(delay)  # Simulating a network or file delay
    print(f"Worker {name} finished after {delay}s.")

# Create the threads
thread1 = threading.Thread(target=worker_task, args=("A", 2))
thread2 = threading.Thread(target=worker_task, args=("B", 4))

# Start execution (they run concurrently)
thread1.start()
thread2.start()

# Wait for both threads to completely finish before moving forward
thread1.join()
thread2.join()

print("All threads finished. Moving back to main program!")
```
### What is the difference between Multithreading and Multiprocessing?
- Multithreading: Shares the exact same memory space. It is lightweight but restricted by the GIL. Best for I/O bound tasks.
- Multiprocessing: Spawns entirely separate instances of Python, each with its own memory space and its own GIL. It allows true parallel execution across multiple CPU cores. Best for CPU bound tasks(e.g., video rendering, machine learning training, heavy math).
### Race condition
- Occurs when two or more threads try to modify the exact same shared variable at the same time. Because their execution order is unpredictable, the final data can become corrupted.
- Solution: Use a `threading.Lock()`. A lock forces a thread to wait its turn before modifying shared data.
  ```
  lock = threading.Lock()

  with lock:
      # Only one thread can enter this block at a time
      shared_counter += 1 
  ```
