#
# Chapter 15: Functions

<br>
<br>

## What is a Function?
A function is a block of reusable code that performs a specific task.
#
## Types of Functions
- Built-in functions: print(), len(), type(), etc.
- User-defined functions: Functions you define using def.
- Lambda (anonymous) functions: Short, unnamed functions.
#
## Syntax (for user-defined function)
```bash
def function_name(parameters):
    """docstring (optional)"""
    # code block
    return value  # optional (in case of no return value, the function will return None)
```
#
## **Types of Arguments in Python Functions***
Python supports 5 main types of arguments in functions:
### **1. Positional Arguments:** Passed in the same order as parameters
```bash
def power(n1,n2):
    x = n1**n2
    return x
power(2,3)
#Output will be 8 (i.e., 2^3) (NOT 3^2)
```
<br>

### **2. Keyword Arguments:** Pass arguments using parameter names, regardless of order.

```bash
def power(n1,n2):
    x = n1**n2
    return x
power(n2=2,n1=3)
#Output will be 9 (i.e., 3^2 here as we explicitly mention that)
```
#### Remember that keyword arguments override positional arguments
<br>

### **3. Default Arguments:** Provide a default value if no argument is passed
```bash
def power(n1=1,n2=1):
    x = n1**n2
    return x
power(2,3) #Output will be 8 (n1=2, n2=3)
power(2) #Output will be 2 (n1=2, n2=1 (default)) 
power(n2=3) #Output will be 1 (n1=1(default), n2=3) 
```
<br>

### **4. Variable-Length Arguments (\*args)**
- Used when the number of positional arguments is unknown.
- Treated as a tuple.
```bash
def add(*nums):
    print(sum(nums))

add(1, 2, 3)
# Output: 6
```
<br>

### **5. Keyword Variable-Length Arguments (\*\*kwargs)**
- #### Used when the number of keyword arguments is unknown.
- #### Treated as a dictionary.
```bash
def show_info(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

show_info(name="Anu", age=22)
# Output: 
# name: Anu
# age: 22
```

---

## **Nested Functions**
- A nested function is a function defined inside another function.
- It can access variables from the enclosing (outer) function scope.
#
### **Examples:**
```bash
def outer(x):
    def inner(y):
        return x + y
    return inner     #Since function is an object so you use inner instead of inner()

outer(5)(3)  #Output is 8
```

---

## **Recursion in Python**
- Recursion is a technique where a function calls itself to solve a problem by breaking it down into smaller sub-problems.
- Recursion uses `STACK` data structure
#
### **Basic Structure**
```bash
def recursive_function():
    if base_condition:
        return result
    else:
        return recursive_function()
```
#
### **Example – Factorial**
```bash
def fact(n):
    if n==0 or n==1:
        return 1
    else:
        return n*fact(n-1)
```

----

## **Lambda Function**
- A lambda function is a small, anonymous function defined using the lambda keyword.
- Ideally written in a line.
- It can have any number of arguments but only one expression.
#
### **Syntax**
```bash
lambda arguments: expression
```
#
### **Basic Example**
```bash
cube = lambda x:x**3
print(cube(2))  #Output is 8
```
#
### **Multiple Arguments**
```bash
add = lambda a, b: a + b
print(add(3, 4))   # Output: 7
```
#
### **Built-in Functional Tools in Python**
| Function   | Purpose                          | Returns                    |
| ---------- | -------------------------------- | -------------------------- |
| `map()`    | Transforms each item             | `map` object (iterable)    |
| `filter()` | Filters items based on condition | `filter` object (iterable) |
| `reduce()` | Reduces items to a single value  | Single value               |

**Note:** `reduce()` is in the functools module → `from functools import reduce`
#
### **1. map(function, iterable)**
#### Applies a function to each element of an iterable.
```bash
nums = [1, 2, 3, 4]
squares = list(map(lambda x: x**2, nums))
print(squares)  # Output: [1, 4, 9, 16]
```
#
### **2. filter(function, iterable)**
#### Filters elements that return True for the given function.
```bash
nums = [1, 2, 3, 4, 5, 6]
evens = list(filter(lambda x: x % 2 == 0, nums))
print(evens)  # Output: [2, 4, 6]
```
#
### **3. reduce(function, iterable)**
#### Applies a function cumulatively to reduce the iterable to a single value.
```bash
from functools import reduce

nums = [1, 2, 3, 4]
product = reduce(lambda x, y: x * y, nums)
print(product)  # Output: 24
```
#
### **Summary**
| Function   | Example Code                         | Output      | When to Use                    |
| ---------- | ------------------------------------ | ----------- | -------------------------------|
| `map()`    | `map(lambda x: x+1, [1,2,3])`        | `[2, 3, 4]` | To transform each item         |
| `filter()` | `filter(lambda x: x>2, [1,2,3,4])`   | `[3, 4]`    | To select specific items       |
| `reduce()` | `reduce(lambda x,y: x+y, [1,2,3,4])` | `10`        | To combine all items into one  |

---

## **List Comprehension**
### **What is it?**
#### A shorter syntax for creating a new list from an existing iterable.
### **Syntax**
```bash
[expression for item in iterable if condition]
```
### **Examples**
#### A. Basic:
```bash
squares = [x**2 for x in range(5)]
print(squares)  # Output: [0, 1, 4, 9, 16]
```
#
#### B. With Conditions:
```bash
even_nums = [x for x in range(10) if x % 2 == 0]
print(even_nums)  # Output: [0, 2, 4, 6, 8]
```
#
#### C. Nested Loops:
```bash
pairs = [(x, y) for x in range(2) for y in range(3)]
print(pairs)  # Output: [(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2)]
```

---

## **Dictionary Comprehension**

### **What is it?**
#### A similar concise syntax to create dictionaries.

### **Syntax**
```bash
{key_expr: value_expr for item in iterable if condition}
```
#
### **Examples**
#### A. Basic:
```bash
even_squares = {x: x**2 for x in range(6) if x % 2 == 0}
print(even_squares)  # Output: {0: 0, 2: 4, 4: 16}
```
#
#### B. With Conditions:
```bash
even_squares = {x: x**2 for x in range(6) if x % 2 == 0}
print(even_squares)  # Output: {0: 0, 2: 4, 4: 16}
```
