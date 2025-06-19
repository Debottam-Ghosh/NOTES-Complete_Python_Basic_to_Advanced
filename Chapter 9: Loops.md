## Definition
Loops are used to repeat a block of code multiple times. 

## Types of Loops
There are two types of loops in python:
#### 1. `While` &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. `For`

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
`2`
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
