#
# Chapter 16: OOP
<br>
<br>

## What is OOP?
Object Oriented Programming (OOP) is a programming paradigm based on objects which bundle data and functions that operate on that data.

<br>

## Key Concepts
| Concept         | Description                                |
| --------------- | ------------------------------------------ |
| **Class**       | A blueprint for creating objects.          |
| **Object**      | An instance of a class.                    |
| **Constructor** | `__init__()` method to initialize objects. |
| **Attribute**   | Variable associated with an object.        |
| **Method**      | Function associated with an object.        |
| **Self**        | Refers to the current object.              |.

<br>

## Example
```bash
class Person:
    def __init__(self, name, age):
        self.name = name  # attribute
        self.age = age

    def greet(self):       # method
        print(f"Hi, I'm {self.name} and I'm {self.age} years old.")

p1 = Person("Alice", 25)
p1.greet()
```
```Hi, I'm Alice and I'm 25 years old.```
<br>

## Magic Methods (or Dunder Methods)
| Method                   | Purpose                                   | Example Usage     |
| ------------------------ | ----------------------------------------- | ----------------- |
| `__init__`               | Constructor (object initialization)       | `obj = MyClass()` |
| `__str__`                | User-friendly string (`print(obj)`)       | `"2x² + 3x - 1"`  |
| `__repr__`               | Developer-friendly string (`repr(obj)`)   | `repr(obj)`       |
| `__len__`                | Length of object                          | `len(obj)`        |
| `__eq__`                 | Equality comparison (`==`)                | `obj1 == obj2`    |
| `__ne__`                 | Inequality comparison (`!=`)              | `obj1 != obj2`    |
| `__add__`                | Overload `+` operator                     | `obj1 + obj2`     |
| `__sub__`                | Overload `-` operator                     | `obj1 - obj2`     |
| `__mul__`                | Overload `*` operator                     | `obj1 * obj2`     |
| `__truediv__`            | Overload `/` operator                     | `obj1 / obj2`     |
| `__floordiv__`           | Overload `//` operator                    | `obj1 // obj2`    |
| `__mod__`                | Overload `%` operator                     | `obj1 % obj2`     |
| `__pow__`                | Overload `**` operator                    | `obj ** 2`        |
| `__getitem__`            | Indexing support                          | `obj[2]`          |
| `__setitem__`            | Support assignment to indexed items       | `obj[2] = value`  |
| `__iter__`               | Make object iterable                      | `for i in obj:`   |
| `__next__`               | Support iteration                         | `next(obj)`       |
| `__contains__`           | Check for membership (`in`)               | `x in obj`        |
| `__call__`               | Make object callable like a function      | `obj()`           |
| `__bool__`               | Truth value testing (`bool(obj)`)         | `if obj:`         |
| `__lt__`                 | Less than (`<`)                           | `obj1 < obj2`     |
| `__le__`                 | Less than or equal (`<=`)                 | `obj1 <= obj2`    |
| `__gt__`                 | Greater than (`>`)                        | `obj1 > obj2`     |
| `__ge__`                 | Greater than or equal (`>=`)              | `obj1 >= obj2`    |
| `__hash__`               | Make object hashable (used in sets/dicts) | `hash(obj)`       |
| `__enter__` / `__exit__` | Context manager support (`with`)          | `with obj:`       |
<br>

## Creating a Class Function
```bash
from math import gcd

class Fraction:
    def __init__(self, numerator, denominator):
        if denominator == 0:
            raise ValueError("Denominator cannot be zero.")
        self.num = numerator
        self.den = denominator
        self.simplify()

    # How the class object will look like to users <-- MUST RETURN A STRING
    def __str__(self):
        if self.den==1:
            return f"{self.num}"
        else:
            return f"{self.num}/{self.den}"

    # How the class object will look like to Developers
    def __repr__(self):
        return self.__str__()
        
    def simplify(self):
        common = gcd(self.num, self.den)
        self.num //= common
        self.den //= common

    # What will be the result of a+b
    def __add__(self, other):
        new_num = self.num * other.den + other.num * self.den
        new_den = self.den * other.den
        return Fraction(new_num, new_den)

    # What will be the result of a-b
    def __sub__(self, other):
        new_num = self.num * other.den - other.num * self.den
        new_den = self.den * other.den
        return Fraction(new_num, new_den)

    # What will be the result of a*b
    def __mul__(self, other):
        new_num = self.num * other.num
        new_den = self.den * other.den
        return Fraction(new_num, new_den)

    # What will be the result of a/b
    def __truediv__(self, other):
        new_num = self.num * other.den
        new_den = self.den * other.num
        return Fraction(new_num, new_den)
```

<br>

## Instance Variable?
An instance variable is a **variable that belongs to an object** of a class.
- Each object has its own copy of the instance variables.
- They are defined inside the class using `self`.

### Defined where?
In most cases, inside \_\_init__(), like:
```bash
self.variable_name = value
```
### Example
```bash
class Dog:
    def __init__(self, name, breed):
        self.name = name          # instance variable
        self.breed = breed        # instance variable

dog1 = Dog("Bruno", "Labrador")
dog2 = Dog("Max", "Beagle")

print(dog1.name)   
print(dog2.name)  
```
`Bruno`
`Max`
- dog1 and dog2 each have their own: `name` and `breed`
- These are instance-specific. Changing one doesn’t affect the other


#


## Static Variable
A static variable (also called a class variable) is a variable that is **shared among all instances** of a class.
- It is not specific to any one object.
- It is defined at the class level, outside any method.
### Example:
```bash
class Dog:
    species = "Canine"   # Static / Class variable

    def __init__(self, name):
        self.name = name  # Instance variable

d1 = Dog("Bruno")
d2 = Dog("Tommy")

print(d1.species)  # Canine
print(d2.species)  # Canine

Dog.species = "Dog"  # Changing the static variable

print(d1.species)  # Dog
print(d2.species)  # Dog
```
`Canine`
`Canine`
`Dog`
`Dog`
<br>

### **Static vs Instance Variables**
| Feature       | Static Variable (`class var`) | Instance Variable (`self.var`)    |
| ------------- | ----------------------------- | --------------------------------- |
| Belongs to    | Class                         | Object (instance)                 |
| Defined using | Directly in class body        | Inside `__init__` with `self`     |
| Shared?       | Yes, by all instances         | No, each object gets its own copy |
| Accessed via  | `ClassName.var`               | Only `self.var`                   |
<br> 

### Another Useful Use Case: Counting Instances
```bash
class Dog:
    count = 0  # Static variable

    def __init__(self, name):
        self.name = name
        Dog.count += 1

d1 = Dog("Bruno")
d2 = Dog("Tommy")

print(Dog.count)
```
`2`
#
## Encapsulation
Encapsulation refers to hiding internal data and restricting direct access to some of the object's components. This is typically done by making variables private and providing public `getter` and `setter` methods to access and modify them.
<br>

### Real-Life Analogy
Think of a capsule — it contains medicine inside it, but you can’t see or touch the actual medicine. You take the capsule. The internal content is hidden, but the result (effect) is accessible.
<br>

## Example
```bash
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.__balance = balance  # private variable

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

    def get_balance(self):
        return self.__balance

    def set_balance(self, new):
        if isinstance(new, int) and new > 0:
            self.__balance = new
        else:
            print("Not Allowed!")
```

- Here, `__balance` is encapsulated — it can't be accessed directly.
- Access is only possible through methods like get_balance(), set_balance(), deposit(), and withdraw().


###

### Access Levels in Encapsulation:
| Modifier  | Syntax Example | Access Level                            |
| --------- | -------------- | --------------------------------------- |
| Public    | `self.name`    | Accessible everywhere                   |
| Protected | `self._name`   | By convention: internal use or subclass |
| Private   | `self.__name`  | Name mangling to restrict access        |
###
**NOTE:** In Python, private variables are not truly private but are name-mangled to discourage direct access.

#### **Name Mangling:**
- Name mangling is a mechanism Python uses to protect private variables in classes by internally changing their names. It helps avoid accidental access or modification of private attributes from outside the class.
###
#### **Example:**
```bash
class MyClass:
    def __init__(self):
        self.__secret = "Hidden Info"
```
#### Even though __secret looks private, Python actually renames it behind the scenes to `_MyClass__secret`So, you can't access it directly like this:
```bash
obj = MyClass()
print(obj.__secret)     # ❌AttributeError
```
#### But you can still (though you shouldn’t) access it using the mangled name:
```bash
print(obj._MyClass__secret)   # Outputs: Hidden Info
```
- #### This doesn’t make it truly private — just "harder to access" accidentally. It's more like a convention + technical barrier for safety.
#
## Types of Class Relationships
### 1. Aggregation (HAS-A)
- One class contains another class as a part.
- Represents: A "has-a" relationship.
```bash
class Engine:
    def start(self):
        print("Engine starts")

class Car:
    def __init__(self):
        self.engine = Engine()  # Car HAS-A Engine

    def drive(self):
        self.engine.start()
        print("Car drives")
c=Car()
c.drive()
```
`Engine starts`
<br>
`Car drives`



