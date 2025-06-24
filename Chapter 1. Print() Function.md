# Chapter 1. Print() Function

<br>
<br>

## Definition of `print()` in Python
The print() function in Python is a built-in function used to output data to the console (standard output).

---

## Examples
```bash
#print a string
print("I am learning python")
```
`I am learning python`

```bash
#print any datatype
print(4+5)
```
`9`

```bash
#print multiple objects in one line
print("I love coading", 1+2, True)
```
`I love coading" 3 True`

```bash
#print multiple lines
print("I am a data scientist")
print(5+6)
print(False)
```
`I am a data scientist`
`11`
`False`

---

## General Syntax:
```bash
print(\*objects, sep=' ', end='\n', file=sys.stdout, flush=False)`
```

| Parameter  | Description                                      | Default          |
| ---------- | ------------------------------------------------ | ---------------- |
| `*objects` | One or more objects to print (comma-separated)   | Required         |
| `sep`      | String inserted between objects                  | `' '` (space)    |
| `end`      | String appended after the last object            | `'\n'` (newline) |
| `file`     | A file-like object (stream) where output is sent | `sys.stdout`     |
| `flush`    | If `True`, forcibly flush the output buffer      | `False`          |


```bash
#Basic print
print("Hello", "World") 
```
`Hello World`

```bash
#Custom Separator
print("2025", "06", "03", sep="-")
```
`2025-06-03`

```bash
#Custom End
print("Loading...", end=' ')
print("100%")
```
`Loading... 100%`

```bash
#printing to a file
print("print this to a file", file=open("output.txt","w"))
```

---

## **Force Flush=True**
```bash
# Without flush=True
import time

print("Loading...", end=" ")
time.sleep(2)
print("Done!")
```
`Loading... Done!`

In some environments (like terminals with buffering or GUI apps), "Loading..." might not show up immediately because the output is buffered until a newline or the buffer fills.

```bash
# With flush=True
import time

print("Loading...", end=" ", flush='True')
time.sleep(2)
print("Done!")
```
`Loading... Done!`
##### Now, "Loading..." is shown instantly, even though there's no newline (\n), because flush=True forces the output buffer to be written immediately.

-----

## What Is Flushing?
##### Flushing means **forcing the output buffer to be written out immediately.**

##### When you use print(), Python doesn't always write directly to the screen or file right away. Instead, it stores the output temporarily in a buffer (like a waiting room) and flushes (writes out) that buffer:
- When it’s full
- When a newline (\n) is printed
- When the program ends
- Or when you manually flush

#### `flush=True` tells to python: "Don’t wait — send this output to the screen right now!”
