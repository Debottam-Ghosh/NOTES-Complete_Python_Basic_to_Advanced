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

<br>

## **Functions used in sequences**
| Function      | Purpose                        | Example                | Output     |
| ------------- | ------------------------------ | ---------------------- | ---------- |
| `range()`     | Generate a sequence of numbers | `range(5)`             | `0 to 4`   |
| `enumerate()` | Get index and value in a loop  | `enumerate(['a','b'])` | `(0, 'a')` |
| `zip()`       | Combine iterables element-wise | `zip([1,2],[3,4])`     | `(1,3)...` |

<br>

## **Math & Logic**
| Function  | Purpose                     | Example           | Output |
| --------- | --------------------------- | ----------------- | ------ |
| `abs()`   | Absolute value              | `abs(-7)`         | `7`    |
| `round()` | Round a number              | `round(3.567, 2)` | `3.57` |
| `pow()`   | Power                       | `pow(2, 3)`       | `8`    |
| `min()`   | Smallest value              | `min(1, 5, -2)`   | `-2`   |
| `max()`   | Largest value               | `max(1, 5, -2)`   | `5`    |
| `sum()`   | Sum of elements in **iterable** | `sum([1, 2, 3])`  | `6`    |

<br>

## **Data Structure Utilities**
| Function     | Purpose                  | Example                 | Output          |
| ------------ | ------------------------ | ----------------------- | --------------- |
| `len()`      | Length of **iterable**       | `len("hello")`          | `5`             |
| `sorted()`   | Return a sorted list     | `sorted([3,1,2])`       | `[1,2,3]`       |
| `reversed()` | Return reversed iterator | `list(reversed("abc"))` | `['c','b','a']` |
| `list()`     | Convert to list          | `list("abc")`           | `['a','b','c']` |
| `set()`      | Convert to set (unique)  | `set([1,1,2])`          | `{1,2}`         |
| `dict()`     | Create dictionary        | `dict(a=1, b=2)`        | `{'a':1,'b':2}` |

<br>

## **Evaluation and Introspection**
| Function       | Purpose                       | Example              | Output            |
| -------------- | ----------------------------- | -------------------- | ----------------- |
| `type()`       | Get type of a variable        | `type(3.14)`         | `<class 'float'>` |
| `id()`         | Get memory address            | `id(x)`              | (int)             |
| `isinstance()` | Check object type             | `isinstance(3, int)` | `True`            |
| `eval()`       | Evaluate string as expression | `eval("2+3")`        | `5`               |
| `input()`      | Get user input                | `input("Name: ")`    | (user input)      |

<br>

## **Others**
| Function  | Purpose                          | Example            |
| --------- | -------------------------------- | ------------------ |
| `help()`  | Show documentation/help          | `help(str)`        |
| `dir()`   | List object’s attributes/methods | `dir([])`          |
| `print()` | Output to screen                 | `print("Hello")`   |
| `open()`  | Open a file                      | `open("file.txt")` |
