# Chapter 4: variables & Literals

<br>
<br>

## Variables
Variables are used to store data and we declare a varible when we don't know what the value will be in future or we want our users to give inputs.

## Important Features of Python Variables

#### **It's dynamically typed**
Unlike some other languages, Python doesn't require explicit declaration of variable types. If we type `x=5` and `y='Red'`, automatically `x` and `y` will be typed as `int` and `str` respectively.

#### **It's dynamically bound**
In Python, when you write:
```bash
x = 10
x = "hello"
```
Python binds `x` to an integer object first, and then later binds it to a string object. **No type is fixed**. The binding happens when the line is executed, not before.

## **Special Syantax**
### Declare multiple variales in a single line:
```bash
# METHOD 1: MOST FREQUENTLY USED
a,b,c = 5,'Red',1.67
print(a)
print(b)
print(c)
```
`5`
`Red`
`1.67`

```bash
# METHOD 2:
a=5; b='Red'; c='1.67'
print(a)
print(b)
print(c)
```
`5`
`Red`
`1.67`

```bash
# METHOD 3:
a=b=4;c='Red'
print(a)
print(b)
print(c)
```
`4`
`4`
`Red`

---

## Literals
A literal is a **fixed** value you directly write in your code. It represents **constant data**.

### Example:
```bash
x = 10      # 10 is a literal
name = "Bob"  # "Bob" is a string literal
```
### Types of Literals
#### **1. Numeric Literals:** Used for numbers
| Type    | Example        |
| ------- | -------------- |
| Integer | `100`, `-7`    |
| Float   | `3.14`, `-0.5` |
| Complex | `2 + 3j`       |

#### **2. String Literals:** Text enclosed in single, double, or triple quotes
```bash
"Hello"
'Python'
'''Multi-line
string'''
```
#### **3. Boolean Literals:** Used in logic/conditions
```bash
True
False
```
#### **4. Special Literal:** `None`
Represents no value, often used to `declare a variable` or as a placeholder.
```bash
x = None
```





