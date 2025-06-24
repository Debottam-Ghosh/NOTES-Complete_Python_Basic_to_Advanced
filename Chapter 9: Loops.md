# Chapter 9: Loops

<br>
<br>

## Definition
Loops are used to repeat a block of code multiple times. 

## Types of Loops
There are two types of loops in python:
<br>
**1. While** 
<br>
**2. For**

---

## While Loop
Repeats the code as long as a condition is True.
### Syntax:
```bash
while condition:
    # code block
```

### Simple Example:
```bash
x = 3
while x > 0:
    print(x)
    x -= 1
```
`3`
<br>
`2`
<br>
`1`

### Making Table of any number using while loop
```bash
n = int(input("Enter a number: "))

print(f"\nLET'S LEARN THE TABLE OF {n} TODAY!")   #Headline

i = 1
while i<11:
    print(n,'*',i,'=',n*i)
    i+=1
```
`Enter a number: _____5_____`
```
LET'S LEARN THE TABLE OF 5 TODAY!
5 * 1 = 5
5 * 2 = 10
5 * 3 = 15
5 * 4 = 20
5 * 5 = 25
5 * 6 = 30
5 * 7 = 35
5 * 8 = 40
5 * 9 = 45
5 * 10 = 50
```

---
## For Loop
Used to iterate over **sequences**. <br> Example of Sequences:
#### 1. Range function
- `range(6)`: 0,1,2,3,4,5 &nbsp;&nbsp;&nbsp;(starts from 0 by default)
- `range(3,8)`: 3,4,5,6,7
- `range(5,16,3)`: 5,8,11,14
#### 2. String
#### 3. List
#### 4. Tuple
#### 5. Sets
#### 6. Dictionary

### **Syntax:**
```bash
for item in sequence:
    # code block
```


### Simple Examples
<br>

**1. Range Function:**
```
for i in range(7):
    print(i,end=" ")
```
`0 1 2 3 4 5 6 `

**2. String:**
```
for i in 'Python':
    print(i,end=" ")
```
`P y t h o n`

**3. Tuple:**
```
for i in (3,5,7,10):
    print(i,end=" ")
```
`3 5 7 10`

**4. List:**
```
for i in [1,3,9]:
    print(i,end=" ")
```
`1 3 9 `

---

## Loop Control Statements
| Statement  | Meaning                   | Example Use               |
| ---------- | ------------------------- | ------------------------- |
| `break`    | Exit the loop immediately | `if i == 3: break`        |
| `continue` | Skip to next iteration    | `if i % 2 == 0: continue` |
| `pass`     | Do nothing (placeholder)  | `if i == 2: pass`         |

<br>

### 1. `break` — Exit the loop completely
- Used to terminate a loop when a condition is met.
- It immediately exits the loop, even if the loop condition is still True.

#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Example:**
```bash
for i in range(5):
    if i == 3:
        break
    print(i, end=' ' )
```
 **Output:** `0 1 2` (Stops the loop when i == 3)

 <br>

 ### 2. `continue` — Skip the current iteration
- Skips the current loop iteration and jumps to the next one.
- The loop doesn’t stop, just avoids executing the rest of the code for that iteration.

#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Example:**
```bash
for i in range(5):
    if i == 3:
        continue
    print(i, end=' ' )
```
**Output:** `0 1 2 4 5` (Skips printing for i == 3)

<br> 

### 3. `pass` — Do nothing (placeholder)
- It’s a null statement — does nothing at all..
- Used as a placeholder for code you’ll write later (like inside an empty function, loop, or condition).
#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Example:**
```bash
for i in range(5):
    if i == 3:
        pass
    print(i, end=' ' )
```
**Output:** `0 1 2 3 4 5` (Just passed i == 3, doing nothing)

<br>

### **Examples with `break`,`continue`,`pass`**
```
for i in range(10,20):
    print('\n',i, end=' ')
    if(i==13):
        continue
        print('- continue',end=' ')
    elif(i==16):
        pass
        print('- pass',end=' ')
    elif(i==19):
        break
        print('- break',end=' ')
```
**Output:**
```
 10 
 11 
 12 
 13 
 14 
 15 
 16 - pass 
 17 
 18 
 19
```

**Explanation:**
- At `i==13`, printing is skipped as `continue` skips everything after it for that iteration.
- At `i==16`, printing happened as `pass` does nothing
- At `i==19`, the loop breaks due to `break`

---

## Nested Loop for Pattern Printing
Nested loops are often used to print patterns like this:
```bash
*
**
***
****
*****
```
The code to print the above pattern is:
```bash
# number of rows:
n = 5    #One can also take input from the user

for i in range(1,n+1):
    for j in range(i):
        print("*",end=" ")
    print("\n")
```

<br>

### When to use a `for` loop and when to use a `while` loop?
Use `for` loop when you have a clear idea about how many times the loop will be iterated. On the other hand, use a `while` loop when you don't know how many times the loop will be iterated, but all you know is a condition that needs to be satisfied to continue the loop



