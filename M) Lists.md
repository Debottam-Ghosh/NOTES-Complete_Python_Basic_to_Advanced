#
# Chapter 13: Lists
<br>
<br>

## **What is a List?**
- A list is a built-in data type that holds an ordered, mutable collection of items.
- Items can be of different data types: int, str, float, bool, even another list.
```bash
my_list = [1, "hello", 3.14, True]
```
<br>

### **List vs Array**
Although list in python is very much similar to array in other languages but they have some differences:
| **Feature**       | **List**                     | **Array**                                 |
| ----------------- | ---------------------------- | ----------------------------------------- |
| **Data Types**    | Can store mixed data types   | Stores elements of the **same data type** |
| **Flexibility**   | More flexible, more features | More memory-efficient (for numbers)       |

<br>

## **How to Create a List**
```python
# Empty list
a = []

# List of numbers
nums = [1, 2, 3]

# Mixed types
mixed = [1, "hello", True]

# Nested list
nested = [[1, 2], [3, 4]]
```
<br>

## **Accessing List Elements**
```python
my_list = [10, 20, 30, 40]

# Indexing
print(my_list[0])     # 10
print(my_list[-1])    # 40

# Slicing
print(my_list[1:3])   # [20, 30]
print(my_list[:2])    # [10, 20]

my_list_nested = [[1,2],3,[4,5]]
print(my_list_nested[2][1])  # 5
```
<br>

## **Editing List Elements**
```python
my_list[1] = 25
print(my_list)  # [10, 25, 30, 40]
```
<br>

## **Adding Elements** (assume `a=[1,2,3,4]`)
| **Method**     | **Description**                     | **Example**         | **Output (`a` after execution)** |
| -------------- | ----------------------------------- | ------------------- | -------------------------------- |
| `append(x)`    | Adds `x` to the end                 | `a.append(5)`       | `[1, 2, 3, 4, 5]`                |
| `insert(i, x)` | Inserts `x` at index `i`            | `a.insert(1, 'hi')` | `[1, 'hi', 2, 3, 4]`             |
| `extend(lst)`  | Adds all elements from another list | `a.extend([6, 7])`  | `[1, 2, 3, 4, 6, 7]`             |

<br>

## **Deleting Elements** (assume `a=[1,2,3,4]`)
| **Method**  | **Description**                     | **Example**   | **Output (`a` after execution)** |
| ----------- | ----------------------------------- | ------------- | -------------------------------- |
| `remove(x)` | Removes **first occurrence** of `x` | `a.remove(2)` | `[1, 3, 4]`                      |
| `pop(i)`    | Removes and returns element at `i`  | `a.pop(1)`    | `[1, 3, 4]` (returns `2`)        |
| `del a[i]`  | Deletes element at index `i`        | `del a[0]`    | `[2, 3, 4]`                      |
| `clear()`   | Removes all elements                | `a.clear()`   | `[]`                             |

<br>

## **Common List Operations**
| **Operation** | **Example**       | **Result**           |
| ------------- | ----------------- | -------------------- |
| Concatenation | `[1, 2] + [3, 4]` | `[1, 2, 3, 4]`       |
| Repetition    | `[1, 2] * 3`      | `[1, 2, 1, 2, 1, 2]` |
| Membership    | `3 in [1, 2, 3]`  | `True`               |
| Length        | `len([1, 2, 3])`  | `3`                  |
| Iteration     | `for i in list:`  | Loop through items   |

<br>

## **Useful Built-in List Functions**
| **Function/Method** | **Purpose**                                   | **Example**                  | **Output**             |
| ------------------- | --------------------------------------------- | ---------------------------- | ---------------------- |
| `len()`             | Number of elements                            | `len([1, 2, 3])`             | `3`                    |
| `sum()`             | Sum of numeric list                           | `sum([1, 2, 3])`             | `6`                    |
| `max()` / `min()`   | Largest / smallest value                      | `max([4, 2, 9])`             | `9`                    |
| `list()`            | Converts to list                              | `list("abc")`                | `['a', 'b', 'c']`      |
| `sorted()`          | Returns sorted list (doesn't change original) | `sorted([3, 1, 2])`          | `[1, 2, 3]`            |
| `reversed()`        | Returns a reverse iterator                    | `list(reversed([1, 2, 3]))`  | `[3, 2, 1]`            |
| `enumerate()`       | Returns index-item pairs                      | `list(enumerate(['a','b']))` | `[(0, 'a'), (1, 'b')]` |

<br>

## **Looping Through a List**
```python
fruits = ['apple', 'banana', 'cherry']

for fruit in fruits:
    print(fruit, end=' ')
    
print('')
# With index
for i, fruit in enumerate(fruits):
    print(i, fruit, end=' ')
```
`apple banana cherry`
`0 apple 1 banana 2 cherry`
#
## Coding Task
### Remove the duplicates from a given list
```python
l = [1,3,2,4,1,5,2,4,1,2,5]
L = []
for i in l:
    if i not in L:
        L.append(i)
L
```

`[1, 3, 2, 4, 5]`
