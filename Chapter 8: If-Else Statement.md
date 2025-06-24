# Chapter 8: If-Else Statement

<br>
<br>

#### Instead of brackets, Python uses indentation (`tabs`) to define code blocks in `if`, `elif`, and `else`.

## Basic Syntax
```bash
if condition:
    # Code if condition is True
elif another_condition:
    # Code if elif is True
else:
    # Code if all above are False
```

## Examples
```bash
x = 10

if x > 0:
    print("Positive number")
elif x == 0:
    print("Zero")
else:
    print("Negative number")
```
`Positive number`

## **Important Notes**
- Use elif instead of multiple if blocks when conditions are related.
- **Indentation is mandatory** – Python doesn’t use {} like other languages.

## Solve the Problem
- #### Let you want to make a login page that ask your email ID and password. The corerct email ID is `debottamghosh361@gmail.com` and the correct passoword is `1234`
- #### If the user enters correct email ID and password then `WELCOME!` will be printed.
- #### If the user enters correct email ID but an incorrect password, then print `INCORRECT PASSWORD` and ask for the passowrd once more. If it enters correct password this time, then print `IT'S CORRECT PASSWORD`. If it enters incorrect password again, print`WRONG PASSWORD`.
- #### For all other cases print `INCORRECT CREDENTIALS`.

```bash
  cor_email = 'debottamghosh361@gmail.com'
cor_pass = '1234'

email = input("Enter your email ID: ")
password = input("Enter your password: ")

if email == cor_email and password == cor_pass:
    print("WELCOME!")
elif email == cor_email and password != cor_pass:
    print("INCORRECT PASSWORD")
    password = input("Enter your password again: ")
    if password == cor_pass:
        print("IT'S CORRECT PASSWORD")
    else:
        print("WRONG PASSWORD")
else:
    print("INCORRECT CREDENTIALS")
```

## One Liner If-Else (Ternary Operator)
```bash
num = int(input("Enter a number: "))
result = "Even" if num % 2 == 0 else "Odd"   #ONE LINER IF-ELSE!
print(result)
```
