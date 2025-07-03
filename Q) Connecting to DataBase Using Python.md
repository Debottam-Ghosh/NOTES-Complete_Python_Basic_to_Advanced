#
# Chapter 17: Connecting to DataBase Using Python

<br>
<br>

## What is Python DB API?
The Python DB API (PEP 249) specifies **a standard way to connect to relational databases** (like MySQL, PostgreSQL, SQLite, etc.) in Python.
<br>

#### What It Is:
- A common interface all Python database modules (like sqlite3, mysql-connector-python, psycopg2) follow.
- Ensures that code written for one database can be easily adapted to another with minimal changes.


<br>

---

## Connection Methods & Creating a Database
### Key Concepts
| Component                   | Description                              |
| --------------------------- | ---------------------------------------- |
| `connect()`                 | Establishes a connection to the database |
| `cursor()`                  | An object to execute SQL queries         |
| `execute()`                 | Runs SQL statements                      |
| `fetchone()` / `fetchall()` | Retrieves query results                  |
| `commit()`                  | Saves (commits) changes                  |
| `rollback()`                | Reverts changes if an error occurs       |
| `close()`                   | Closes connection or cursor              |

<br>
<br>

### Creating a database from Python 
```bash
import sqlite3
MySchool=sqlite3.connect('schooltest.db')
curschool=MySchool.cursor()
curschool.execute('''CREATE TABLE student (
    StudentID INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT (20) NOT NULL,
    age INTEGER,
    marks REAL);''')
MySchool.close() 
```

<br>
<br>

### Inserting New Record
**Example 1: Inserting pre decided values in the table**
```bash
# Assuming that the database MySchool is created and contains the table student, we start by creating a connection:
import sqlite3
MySchool=sqlite3.connect('schooltest.db')
curschool=MySchool.cursor()

# To add a new record to the table, we execute the INSERT query:
curschool.execute("INSERT INTO student (StudentID, name, house, marks) VALUES (5,'Sherlock',32,50);")

# We now commit the changes to confirm them:
MySchool.commit()
```
###### The new record is added to the table. You can verify this from SQLite Studio.

<br>

**Example 2: To accept user input for the values in the table:**
```bash
# Assuming that the database MySchool is created and contains the table student, we start by creating a connection:
import sqlite3
MySchool=sqlite3.connect('schooltest.db')
curschool=MySchool.cursor()

# To accept user input, we use variables to store each of the values:
mysid= int(input("Enter ID: "))
myname=input("Enter name: ")
myhouse=int(input("Enter house: "))
mymarks=float(input("Enter marks: "))

'''
We now replaces the fixed VALUES in the INSERT query with the variables, mysid, myname, myhouse and mymarks.
To do this, we use the DB-API’s parameter substitution. We put a ? as a placeholder wherever we want to use a value and
then give a tuple of values as the second argument to the cursor’s execute() method:
'''
curschool.execute("INSERT INTO student (StudentID, name, house, marks) VALUES (?,?,?,?);", (mysid,myname,myhouse,mymarks))

# We now commit the changes:
MySchool.commit()
```





