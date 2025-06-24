# 
# Chapter 12: Strings

<br>
<br>

String is a datatype in Python. In most of the programming languages that build applications have string as a datatype (e.g, Python, Java, C++)

<br>

## Declaration of a String
```bash
# Single Line
str1 = 'Hello world'
str2 = "Hello world"
str3 = '''Hello world'''

# Multi Line
str4 = '''I am Debottam.
I love coding.
I am learning python.'''

print(str1)
print(str2)
print(str3)
print(str4)
```

## Accessing Substring from a String
### 1. Indexing:
There are two types of **indexing** in python:
1. Positive Indexing
2. Negative Indexing

```bash
str1 = "Hello World"

# POSITIVE INDEXING
print(str1[0], end = ', ')        #-------> 0TH INDEXED CHARACTER
print(str1[1], end = ', ')        #-------> 1ST INDEXED CHARACTER
print(str1[2], end = ', ')        #-------> 2ND INDEXED CHARACTER
print('...', end = ' ')    
print(str1[10], end = ', ')       #-------> 10TH INDEXED CHARACTER
#print(str1[11],end = ' ')        #------> INVALID: OUT OF RANGE

print(' ')

# NEGATIVE INDEXING
print(str1[-1], end = ', ')        #-------> LAST CHARACTER
print(str1[-2], end = ', ')        #-------> 2ND LAST CHARACTER
print(str1[-3], end = ', ')        #-------> 3RD LAST CHARACTER
print('...', end = ' ')    
print(str1[-11], end = ', ')       #-------> 9TH LAST CHARACTER
#print(str1[-12],end = '  ')        #------> INVALID: OUT OF RANGE
```
`H, e, l, ... d,`
`d, l, r, ... H,`

### 2. Slicing:
```bash
str1 = "Hello World"

print(str1[2:7])             #------> 2ND TO 6TH INDEXED CHARACTERS:         `llo W`
print(str1[3:])              #------> 3RD INDEXED ONWARDS CHARACTERS:        `lo World`
print(str1[:8])              #------> UPTO 8TH INDEXED CHARACTERS:           `Hello Wo`
print(str1[:])               #------> ALL CHARACTERS:                        `Hello World`
print("")
print(str1[-5:-2])          #------> 5TH LAST TO 3RD LAST CHARACTERS:        `Wor`
print(str1[-3:])            #------> 3RD LAST ONWARDS CHARACTERS:            `rld`
print(str1[:-5])            #------> UPTO 6TH LAST CHARACTERS:               `Hello `
print("")
print(str1[2:9:3])          #------> 2ND TO 8TH INDEXED CHARACTERS with step=3:            `l r`
print(str1[-2:-9:-1])       #------> 2ND LAST TO 8TH LAST INDEXED CHARACTERS IN REVERSE:    lroW ol`
```
<br>

### Reverse Using Slicing:
```bash
str1 = "Hello World"
print(str1[::-1])
```
`dlroW olleH`
<br>

### **Editing a String**
String is `immutable` which means you cannot change a string. <br> QFor example:
```bash
str1 = 'Hello'
str1[2] = 'X' 
```
#### This will throw an error


<br>
<br>

## Operators in Strings

### **Arithmatic Operators:**

#### 1. Concatenation
```bash
s1 = 'Hello'
s2 = 'World'
s3 = 'Code'
s1 + s2 + s3
```
**Output:** `HelloWorldCode`
<br>

#### 2. Repetition
```bash
s = 'Hello'
s1*3
```
**Output:** `HelloHelloHello`
<br>

## **Relational Operators:**
```bash
"apple" == "apple"       # True
"apple" < "banana"       # True (lexicographical)
"tea" > "Tea"            # True (uppercase < lowercase)
```
<br>

## **Membership Operator**
```bash
'Hell' in 'Hello World'
```
**Output:** `True`

```bash
'h' in 'Hello'
```
**Output:** `False`
<br>

## **Loop Through String**
```bash
for i in "Hello World":
    print(i,end='-')
```
**Output:** `H-e-l-l-o- -W-o-r-l-d-`
<br>

```bash
s = 'I am coding'
for i in s[2:7]:
    print(i,end='-')
```
**Output:** `a-m- -c-o-`

<br>

# String Functions

## 1. Built-in Functions (valid for other iterables like list, tuple etc. also)
<br>

| **Function** | **Purpose**                                           | **Syntax**                                  | **Example**                     | **Output**                  |
| ------------ | ----------------------------------------------------- | ------------------------------------------- | ------------------------------- | --------------------------- |
| `sorted()`   | Returns a **new sorted list** from an iterable        | `sorted(iterable, key=None, reverse=False)` | `sorted([3, 1, 4])`             | `[1, 3, 4]`                 |
|              |                                                       |                                             | `sorted("hello")`               | `['e', 'h', 'l', 'l', 'o']` |
|              |                                                       |                                             | ✅`sorted([3,1,4], reverse=True)` | `[4, 3, 1]`                 |
| `max()`      | Returns the **largest item** in an iterable or args   | `max(iterable)` / `max(a, b, ...)`          | `max([3, 1, 5])`                | `5`                         |
|              |                                                       |                                             | `max("hello")`                  | `'o'`                       |
| `min()`      | Returns the **smallest item** in an iterable or args  | `min(iterable)` / `min(a, b, ...)`          | `min([3, 1, 5])`                | `1`                         |
|              |                                                       |                                             | `min("hello")`                  | `'e'`                       |
| `len()`      | Returns the **length (number of items)** in an object | `len(obj)`                                  | `len("hello")`                  | `5`                         |
|              |                                                       |                                             | `len([1, 2, 3, 4])`             | `4`                         |


## 2. Python String Functions (Only applicable for strings)
| **Functions**          | **Purpose**                                 | **Example**                 | **Output**        |
| ------------------- | ------------------------------------------- | --------------------------- | ----------------- |
| `str.capitalize()`  | Capitalizes first character                 | `'hello'.capitalize()`      | `'Hello'`         |
| `str.lower()`       | Converts to lowercase                       | `'Hello'.lower()`           | `'hello'`         |
| `str.upper()`       | Converts to uppercase                       | `'Hello'.upper()`           | `'HELLO'`         |
| `str.title()`       | Capitalizes each word                       | `'hello world'.title()`     | `'Hello World'`   |
| `str.swapcase()`    | Swaps uppercase to lowercase and vice versa | `'Hello'.swapcase()`        | `'hELLO'`         |
| `str.islower()`     | Checks if all characters are lowercase      | `'hello'.islower()`         | `True`            |
| `str.isupper()`     | Checks if all characters are uppercase      | `'HELLO'.isupper()`         | `True`            |
| `str.istitle()`     | Checks if title-cased                       | `'Hello World'.istitle()`   | `True`            |
| `str.isalpha()`     | Only letters?                               | `'abc'.isalpha()`           | `True`            |
| `str.isdigit()`     | Only digits?                                | `'123'.isdigit()`           | `True`            |
| `str.isalnum()`     | Letters and numbers only?                   | `'abc123'.isalnum()`        | `True`            |
| `str.isspace()`     | Only whitespace?                            | `'   '.isspace()`           | `True`            |
| `str.startswith(x)` | Starts with `x`?                            | `'hello'.startswith('he')`  | `True`            |
| `str.endswith(x)`   | Ends with `x`?                              | `'hello'.endswith('lo')`    | `True`            |
| `str.find(x)`       | First index of `x`, else -1                 | `'hello'.find('l')`         | `2`               |
| `str.rfind(x)`      | Last index of `x`, else -1                  | `'hello'.rfind('l')`        | `3`               |
| `str.index(x)`      | First index of `x`, else error              | `'hello'.index('l')`        | `2`               |
| `str.rindex(x)`     | Last index of `x`, else error               | `'hello'.rindex('l')`       | `3`               |
| `str.count(x)`      | Count of `x`                                | `'banana'.count('a')`       | `3`               |
| `str.replace(a, b)` | Replace `a` with `b`                        | `'hello'.replace('l', 'x')` | `'hexxo'`         |
| `str.strip()`       | Remove leading/trailing whitespace          | `'  hi  '.strip()`          | `'hi'`            |
| `str.lstrip()`      | Remove leading whitespace                   | `'  hi'.lstrip()`           | `'hi'`            |
| `str.rstrip()`      | Remove trailing whitespace                  | `'hi  '.rstrip()`           | `'hi'`            |
| `str.split()`       | Split by whitespace                         | `'a b c'.split()`           | `['a', 'b', 'c']` |
| `str.split(',')`    | Split by `,` or other delimiter             | `'a,b,c'.split(',')`        | `['a', 'b', 'c']` |
| `str.join(list)`    | Join list into string with separator        | `' '.join(['a', 'b', 'c'])` | `'a b c'`         |
| `str.encode()`      | Encode to bytes                             | `'hi'.encode()`             | `b'hi'`           |
| `str.format()`      | String formatting                           | `'Name: {}'.format('Ram')`  | `'Name: Ram'`     |
#
### `sort` vs `sorted`:
`sorted` is a temprary action whereas `sort` is permanent action. For example, 
```bash
L = "126435"
sorted(L)
print(L)
```
#### The output will be still `126435`. 
But
```bash
L = 126435
L.sort()
print(L)
```
#### The output will `123456`

#

### One Interesting Note
The built-in functions (i,e., the functions are used for list, sets, tuples also) are used by passing the object as an argument (e.g., `sorted("Hello")`) but the string functions use dot notation (e.g., `"Hello".upper()`)
#
### **Then How to Know What to Use?**
### ✨ Rule of Thumb:
| Ask Yourself                                                                     | Use                    |
| -------------------------------------------------------------------------------- | ---------------------- |
| Does this action **belong to the object’s type**?                                | Use `object.method()`  |
| Is this a **generic Python function** that can be applied to various data types? | Use `function(object)` |

#

## Coding Task
### Convert a string into title case without using title()
```bash
s = "how are you?"
l = s.split()
L = []
for i in l:
    j = i.capitalize()
    L.append(j)
    
S = " ".join(L)
S
```
`How Are You?`

