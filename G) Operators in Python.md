# Chapter 7: Operators in Python

<br>
<br>

In python programming language, there are 7 different operators. 
## **1. Arithmetic Operators**
#### Used for numeric calculations:
| Operator | Description         | Example  | Result |
| -------- | ------------------- | -------- | ------ |
| `+`      | Addition            | `5 + 2`  | `7`    |
| `-`      | Subtraction         | `5 - 2`  | `3`    |
| `*`      | Multiplication      | `5 * 2`  | `10`   |
| `/`      | Division (float)    | `5 / 2`  | `2.5`  |
| `//`     | Floor Division      | `5 // 2` | `2`    |
| `%`      | Modulus (remainder) | `5 % 2`  | `1`    |
| `**`     | Exponentiation      | `2 ** 3` | `8`    |

---

### **2. Comparison Operators (Relational)**
#### Used to compare values:
| Operator | Meaning          | Example  | Result  |
| -------- | ---------------- | -------- | ------- |
| `==`     | Equal to         | `5 == 5` | `True`  |
| `!=`     | Not equal to     | `5 != 2` | `True`  |
| `>`      | Greater than     | `5 > 3`  | `True`  |
| `<`      | Less than        | `2 < 3`  | `True`  |
| `>=`     | Greater or equal | `5 >= 5` | `True`  |
| `<=`     | Less or equal    | `4 <= 2` | `False` |

---

### **3. Assignment Operators**
#### Used to assign values to variables:
| Operator | Meaning                 | Example   |
| -------- | ----------------------- | --------- |
| `=`      | Assign                  | `x = 5`   |
| `+=`     | Add and assign          | `x += 3`  |
| `-=`     | Subtract and assign     | `x -= 2`  |
| `*=`     | Multiply and assign     | `x *= 4`  |
| `/=`     | Divide and assign       | `x /= 2`  |
| `//=`    | Floor divide and assign | `x //= 2` |
| `%=`     | Modulus and assign      | `x %= 2`  |
| `**=`    | Power and assign        | `x **= 2` |

---

### **4. Logical Operators**
#### Used with boolean values (`True` / `False`):

| Operator | Description                  | Example          | Result  |
| -------- | ---------------------------- | ---------------- | ------- |
| `and`    | True if both are True        | `True and False` | `False` |
| `or`     | True if at least one is True | `True or False`  | `True`  |
| `not`    | Negates the value            | `not True`       | `False` |

---

## **5. Bitwise Operators**
#### Operate at the binary level:

| Operator | Meaning      | Example         | 
| -------- | ------------ | --------------- | 
| `&`      | AND          | `5 & 3` → `1`   | 
| `\|`      | OR           | `5 \| 3`→`7`     |
| `^`      | XOR          | `5 ^ 3` → `6`   |  
| `~`      | NOT (invert) | `~5`    → `-6`  |  
| `<<`     | Left shift   | `5 << 1` → `10` |  
| `>>`     | Right shift  | `5 >> 1` → `2`  |  

---

### **6. Membership Operators**
#### Test for presence in a sequence:
| Operator | Description  | Example                     |
| -------- | ------------ | --------------------------- |
| `in`     | Present?     | `'a' in 'cat'` → `True`     |
| `not in` | Not present? | `5 not in [1,2,3]` → `True` |

---

### **7. Identity Operators**
#### Compare object identity (not just value):
| Operator | Description      | Example      |
| -------- | ---------------- | ------------ |
| `is`     | Same object?     | `x is y`     |
| `is not` | Not same object? | `x is not y` |


##### For Example:
```bash
a = 'Hello World'
b = 'Hello World'
print(a is y)
```
**Output:**```False``` because a and b are not same identity (although they store same value) as they are not stored in the same memory

