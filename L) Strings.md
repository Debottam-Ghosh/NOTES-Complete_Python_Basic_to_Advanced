# Chapter 12: Strings

<br>
<br>

String is a datatype in Python. In most of the programming languages that build applications have string as a datatype (e.g, Python, Java, C++)

<br>

## Declaration of a String
```bash
# Single Line
str1 = 'Hello world'
str2 = "Hello world"
str3 = '''Hello world'''

# Multi Line
str4 = '''I am Debottam.
I love coding.
I am learning python.'''

print(str1)
print(str2)
print(str3)
print(str4)
```

## Accessing Substring from a String
<br>

### 1. Indexing:
There are two types of **indexing** in python:
1. Positive Indexing
2. Negative Indexing

```bash
str1 = "Hello World"

# POSITIVE INDEXING
print(str1[0], end = ', ')        #-------> 0TH INDEXED CHARACTER
print(str1[1], end = ', ')        #-------> 1ST INDEXED CHARACTER
print(str1[2], end = ', ')        #-------> 2ND INDEXED CHARACTER
print('...', end = ' ')    
print(str1[10], end = ', ')       #-------> 10TH INDEXED CHARACTER
#print(str1[11],end = ' ')        #------> INVALID: OUT OF RANGE

print(' ')

# NEGATIVE INDEXING
print(str1[-1], end = ', ')        #-------> LAST CHARACTER
print(str1[-2], end = ', ')        #-------> 2ND LAST CHARACTER
print(str1[-3], end = ', ')        #-------> 3RD LAST CHARACTER
print('...', end = ' ')    
print(str1[-11], end = ', ')       #-------> 9TH LAST CHARACTER
#print(str1[-12],end = '  ')        #------> INVALID: OUT OF RANGE
```
`H, e, l, ... d,`
`d, l, r, ... H,`

### 2. Slicing:
```bash
str1 = "Hello World"

print(str1[2:7])             #------> 2ND TO 6TH INDEXED CHARACTERS:         `llo W`
print(str1[3:])              #------> 3RD INDEXED ONWARDS CHARACTERS:        `lo World`
print(str1[:8])              #------> UPTO 8TH INDEXED CHARACTERS:           `Hello Wo`
print(str1[:])               #------> ALL CHARACTERS:                        `Hello World`
print("")
print(str1[-5:-2])          #------> 5TH LAST TO 3RD LAST CHARACTERS:        `Wor`
print(str1[-3:])            #------> 3RD LAST ONWARDS CHARACTERS:            `rld`
print(str1[:-5])            #------> UPTO 6TH LAST CHARACTERS:               `Hello `
print("")
print(str1[2:9:3])          #------> 2ND TO 8TH INDEXED CHARACTERS with step=3:            `l r`
print(str1[-2:-9:-1])       #------> 2ND LAST TO 8TH LAST INDEXED CHARACTERS IN REVERSE:    lroW ol`
```
<br>

### Reverse Using Slicing:
```bash
str1 = "Hello World"
print(str1[::-1])
```
`dlroW olleH`
<br>

### **Editing a String**
String is `immutable` which means you cannot change a string. <br> QFor example:
```bash
str1 = 'Hello'
str1[2] = 'X' 
```
#### This will throw an error


<br>
<br>

## Operators in Strings

### **Arithmatic Operators:**

#### 1. Concatenation
```bash
s1 = 'Hello'
s2 = 'World'
s3 = 'Code'
s1 + s2 + s3
```
**Output:** `HelloWorldCode`
<br>

#### 2. Repetition
```bash
s = 'Hello'
s1*3
```
**Output:** `HelloHelloHello`
