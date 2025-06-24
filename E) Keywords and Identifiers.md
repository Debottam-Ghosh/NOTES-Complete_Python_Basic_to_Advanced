# Chapter 5: Keywords and Identifiers

<br>
<br>

## Keywords
There are **33 keywords** in python. You should not use those as your variable names as these have special meanings and they are reserved by the program.

## Complete List of Keywords
```bash
import keyword
print(keyword.kwlist)
```
`['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']`

---

## Identifiers
Identifiers are names you create for:
- Variables
- Functions
- Classes
- Modules, etc.

## Examples
```bash
name = "Alice"         # 'name' is an identifier
def greet(): ...       # 'greet' is an identifier
class Student: ...     # 'Student' is an identifier
```

## Vaild Indentifiers Rules:
- Must start with a letter (`A–Z`, `a–z`) or underscore `_`
- Can contain letters, digits, and underscores
- Cannot be a Python keyword
- Case-sensitive (`Name ≠ name`)

| **Valid Identifiers**   | **Invalid Identifiers**   |
| ----------------------- | ------------------------- |
| `name`                  | `1name`                   |
| `user_name`             | `user-name`               |
| `_temp`                 | `@temp`                   |
| `MAX_VALUE`             | `my var`                  |
| `x`                     | `for`                     |
| `age25`                 | `25age`                   |
| `data_123`              | `def`                     |
| `name_`                 | `print()`                 |
| `value2temp`            | `import*`                 |




