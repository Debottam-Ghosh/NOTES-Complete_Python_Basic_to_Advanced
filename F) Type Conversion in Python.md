# Chapter 6: Type Conversion in Python

<br>
<br>

## Definition
In python, we can convert a datatype to some other datatype very easily **until it is valid**

#### We can easily change the datatype of `5` from `int` to `str`
```bash
# First store x as int
x = 5
print(type(x))

# Convert the datatype to str
x = str(x)
print(type(x))
```
`<class 'int'>`
`<class 'str'>`

#### But we cannot change the datatype of `Five` from `str` to `int`

```bash
# First store x as int
x = 'Five'
print(type(x))

# Convert the datatype to str
x = int(x)
print(type(x))
```
`<class 'str'>`
`ValueError: invalid literal for int() with base 10: 'Five'`

## Some More Useful Examples
```bash
x = 'Hello'
list(x)
```
`['H', 'e', 'l', 'l', 'o']`

```bash
x = 4.7
int(x)
```
`4`

**NOTE:** Type Conversion is a temporary action until you store the converted varaible

```bash
x = 5
str(x)  #changing the dtype to str
type(x) #but the dtype remains the same (check output)
```
`int`

```bash
x = 5
x = str(x) #changing dtype to 'str' and also string that
type(x)  #Now the dtype will remain 'str' (check output)
```
`str`

---

## **Tricky Sawal**
### What will be the output?
```bash
x = True + 2
print(x)
print(type(x))
```
#### The output will be:
```bash
3
<class 'int'>
```
#### This is because python takes `True` as `1` and `False` as `0`. <br>So the output of `False + 5` will be `5`

---

## Taking Input From Users
```bash
Name = input("Enter your name: ")
```
`Enter your name: ___________________________`

#### But there is one problem. `By default`, python stores all inputs as `str`
```bash
Num_1 = input("Enter the 1st number: ")
Num_2 = input("Enter the 2nd number: ")
print(Num_1 + Num_2)
```
`Enter 1st number: 5`
<br>
`Enter 2nd number: 6`
<br>
Output: `56`

#### To fix this, we have to convert the datatype to `int`
```bash
Num_1 = int(input("Enter the 1st number: "))
Num_2 = int(input("Enter the 2nd number: "))
print(Num_1 + Num_2)
```
`Enter 1st number: 5`
<br>
`Enter 2nd number: 6`
<br>
Output: `11`







