## **PRINT() FUNCTION**

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

### General Syntax:
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

```bash
```

```bash
```
