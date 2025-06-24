# Chapter 3: Data Types

<br>
<br>

## Definition
A data type defines the kind of value a variable holds. Python is **dynamically typed**, so you don’t need to declare types explicitly. 

---

## Types of Data
Python stores **3 types** of data:
| Type      | Example            
| --------- | ------------------------------------------- |
| **Basic**     | `int`, `float`, `complex`, `boolean`, `string`
| **Container**   | `list`, `tuple`, `sets`, `dictionary`
| **User-defined** | `class`

- **`int`:** 5, -6, 0, etc. `[range: 1e308 i.e., $10^{308}$]`
- **`float`:** 1.5, -2.6, 0, 5, 5.6997456, etc.   `[range: 1.7e308 i.e., $1.7*10^{308}$]`
- **`complex`:** 1+5j, 6, 8j, 2.5+6.2j etc.
- **`boolean`:** True, False
- **`string`:** "Python", "I love coding", '122', """India"""
- **`list`:** [1, 'coding', True]   `[list is same thing as array in other language!]`
- **`tuple`:** (1, 'coding', True)
- **`sets`:** {1, 'coding', True}
- **`dictionary`:** {'Name': 'Debottam', 'Age': 24, 'Married': False

---

## To know the datatype of a variable, we use `type()`
```bash
type(1)
```
`int`

```bash
type([1,2,'code'])
```
`list`

```bash
type(5.6 + 9j)
```
`complex`

