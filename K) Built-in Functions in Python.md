# 
# Chapter 11: Built-in Functions in Python

<br>
<br>

## **Type conversions**
| Function  | Purpose            | Example         | Output  |
| --------- | ------------------ | --------------- | ------- |
| `int()`   | Convert to integer | `int("5")`      | `5`     |
| `float()` | Convert to float   | `float("3.14")` | `3.14`  |
| `str()`   | Convert to string  | `str(10)`       | `'10'`  |
| `bool()`  | Convert to boolean | `bool(0)`       | `False` |

#

## **Functions used in sequences**
| Function      | Purpose                        | Example                | Output     |
| ------------- | ------------------------------ | ---------------------- | ---------- |
| `range()`     | Generate a sequence of numbers | `range(5)`             | `0 to 4`   |
| `enumerate()` | Get index and value in a loop  | `enumerate(['a','b'])` | `(0, 'a')` |
| `zip()`       | Combine iterables element-wise | `zip([1,2],[3,4])`     | `(1,3)...` |

#

## **Math & Logic**
| Function  | Purpose                     | Example           | Output |
| --------- | --------------------------- | ----------------- | ------ |
| `abs()`   | Absolute value              | `abs(-7)`         | `7`    |
| `round()` | Round a number              | `round(3.567, 2)` | `3.57` |
| `pow()`   | Power                       | `pow(2, 3)`       | `8`    |
| `min()`   | Smallest value              | `min(1, 5, -2)`   | `-2`   |
| `max()`   | Largest value               | `max(1, 5, -2)`   | `5`    |
| `sum()`   | Sum of elements in **iterable** | `sum([1, 2, 3])`  | `6`    |

#

## **Data Structure Utilities**
| Function     | Purpose                  | Example                 | Output          |
| ------------ | ------------------------ | ----------------------- | --------------- |
| `len()`      | Length of **iterable**       | `len("hello")`          | `5`             |
| `sorted()`   | Return a sorted list     | `sorted([3,1,2])`       | `[1,2,3]`       |
| `reversed()` | Return reversed iterator | `list(reversed("abc"))` | `['c','b','a']` |
| `list()`     | Convert to list          | `list("abc")`           | `['a','b','c']` |
| `set()`      | Convert to set (unique)  | `set([1,1,2])`          | `{1,2}`         |
| `dict()`     | Create dictionary        | `dict(a=1, b=2)`        | `{'a':1,'b':2}` |

#

## **Evaluation and Introspection**
| Function       | Purpose                       | Example              | Output            |
| -------------- | ----------------------------- | -------------------- | ----------------- |
| `type()`       | Get type of a variable        | `type(3.14)`         | `<class 'float'>` |
| `id()`         | Get memory address            | `id(x)`              | (int)             |
| `isinstance()` | Check object type             | `isinstance(3, int)` | `True`            |
| `eval()`       | Evaluate string as expression | `eval("2+3")`        | `5`               |
| `input()`      | Get user input                | `input("Name: ")`    | (user input)      |

#

## **Others**
| Function  | Purpose                          | Example            |
| --------- | -------------------------------- | ------------------ |
| `help()`  | Show documentation/help          | `help(str)`        |
| `dir()`   | List object’s attributes/methods | `dir([])`          |
| `print()` | Output to screen                 | `print("Hello")`   |
| `open()`  | Open a file                      | `open("file.txt")` |

#
## **Python: Modules vs Packages vs Libraries**
| **Aspect**        | **Module**                                 | **Package**                                                    | **Library**                                                 |
| ----------------- | ------------------------------------------ | -------------------------------------------------------------- | ----------------------------------------------------------- |
| **Definition**    | A single `.py` file containing Python code | A directory with an `__init__.py` file and one or more modules | A collection of modules and packages designed for a purpose |
| **Structure**     | Single file                                | Folder with multiple files/modules                             | Bundle of packages, modules, resources, documentation       |
| **Purpose**       | Organize reusable code in one file         | Organize multiple modules together                             | Provide tools to solve a specific set of problems           |
| **Example**       | `math.py`, `random.py`                     | `numpy` (with submodules like `numpy.linalg`)                  | `Scikit-learn`, `TensorFlow`, `Keras`, `Pandas`             |
| **Import Syntax** | `import module_name`                       | `import package.module`                                        | `import library_name` or specific parts (`from X import Y`) |
| **Can Contain**   | Functions, variables, classes              | Modules, sub-packages                                          | Multiple packages and modules                               |
| **File Type**     | `.py`                                      | Directory with `__init__.py`                                   | Mix of `.py`, compiled extensions, metadata, docs, etc.     |
| **Example Use**   | `import math` → `math.sqrt(4)`             | `import os.path`                                               | `from sklearn.linear_model import LogisticRegression`       |
#
### **Summary:**
- A **module** is a basic building block.
- A **package** is a collection of modules.
- A **library** is a bigger toolkit that can contain many packages and modules for broader functionality.
# Some More Examples

## Enumerate()

```bash
l = ['a', 1, True, 'Python']
enumerate(l)    
list(enumerate(l))

#To see the enumerated list you have to use list(enumerate())
```
`[(0, 'a'), (1, 1), (2, True), (3, 'Python')]`
## zip()
```bash
l1 = ['a', 1, True, 'Python']
l2 = [False, 'coding', 5]
l3 = [1,3,5,7,9,11]
zip(l1,l2,l3)    
list(zip(l1,l2,l3))

#zip(l1,l2,l3,...) will create another list with length same as min(len(l1),len(l2),...)
#To see the zipped list you have to use `list(zipped())`
```
`[('a', False, 1), (1, 'coding', 3), (True, 5, 5)]`
## round()
```bash
print(round(3.4653433,2), end = ' ')  #round upto 2 decimal places
print(round(3.7653433), end = ' ')    #rpund to nearest integer
print(round(5))
```
`3.47 4 5`
## max()
```bash
print(max([1,3,5]),end=' ') #-----> Valid     
print(max((1,3,5)),end=' ') #-----> Valid
print(max({1,3,5}),end=' ') #-----> Valid
print(max(1,3,5),end=' ')   #-----> Valid     
print(max('A','B','c'))   #max will be determined by ASCII code
```
`5 5 5 5 c`
## sum()
```bash
print(sum([1,2,3]),end=' ') #-----> Valid
print(sum((1,2,3)),end=' ') #-----> Valid
print(sum({1,2,3}),end=' ') #-----> Valid
#print(sum(1,2,3))  #-----> Not Valid
```
`6 6 6`
