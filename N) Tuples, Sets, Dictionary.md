#
# Chapter 14: Tuples, Sets, Dictionary

<br>
<br>

# Tuples
An example of a tuple: `(1,2,3)`
- Tuples are **immutable**, i.e., adding or deleting elements is not allowed.
- So we can say **tuples are read-only datatypes**.
- All other functionalities work similarly on tuples just like lists.

#

## Sets
An example of a set: `{1,2,3}`
### 4 Rules of Sets
1. Sets do not contain duplicate objects.
2. Sets do not allow indexing/ slicing.
3. Sets cannot contain any mutable objects.
4. Set is itself a mutable datatype. So by rule 3, set cannot conatin a set.
<br>

### **Creating an empty set:**
- To create an empty set, use`S = set()`
- You CANNOT create an empty set by `S = {}` as this creates an empty dictionary instead.

#

## Dictionary
A dictionary is an unordered, mutable collection of key-value pairs.
<br>

```bash
my_dict = {"name": "Alice", "age": 25}
```

### Key Features
- Keys must be unique and immutable (e.g., strings, numbers, tuples).
- Values can be any type and duplicated.
- Dictionary overall is a mutable datatype
- Dictionary has no indexing (i.e., `my_dict[1]` will not work)
- Python 3.7+ maintains insertion order.

<br>

### Nested Dictionary
```bash
student = {"name": "Bob", "marks": {"math": 90, "eng": 85}}}
```

<br>

### Accessing Dictionary
**Dictionar can be accessed through keys:**
```bash
my_dict['name']           #'Alice'
my_dict['Alice']          #Error
student['marks']['eng']   #85
```
<br>

### **Common Operations**
| **Operation**       | **Description**                          | **Example**              | **Output**                         |
| ------------------- | ---------------------------------------- | ------------------------ | ---------------------------------- |
| Create              | Creates a dictionary                     | `d = {"a": 1, "b": 2}`   | `{'a': 1, 'b': 2}`                 |
| Access value        | Returns value for key `"a"`              | `d["a"]`                 | `1`                                |
| Modify/Add value    | Adds or updates key `"c"` with value `3` | `d["c"] = 3`             | `{'a': 1, 'b': 2, 'c': 3}`         |
| Delete key          | Removes key `"a"`                        | `del d["a"]`             | `{'b': 2, 'c': 3}`                 |
| Check key existence | Returns `True` if key exists             | `"a" in d`               | `True`                             |
| Get with default    | Returns value or `0` if key not found    | `d.get("x", 0)`          | `0`                                |
| Keys                | Returns all keys                         | `d.keys()`               | `dict_keys(['a', 'b'])`            |
| Values              | Returns all values                       | `d.values()`             | `dict_values([1, 2])`              |
| Items               | Returns key-value pairs                  | `d.items()`              | `dict_items([('a', 1), ('b', 2)])` |
| Clear all           | Empties the dictionary                   | `d.clear()`              | `{}`                               |
| Copy                | Creates a shallow copy                   | `d2 = d.copy()`          | `d2` is a separate copy            |
| Merge dictionaries  | Adds keys from `d2` to `d1`              | `d1.update(d2)`          | `d1` now includes `d2` keys        |
| Loop through        | Iterates over key-value pairs            | `for k, v in d.items():` | `a 1`<br>`b 2`                     |

