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
curschool.execute("INSERT INTO student (StudentID, name, marks) VALUES (5,'Sherlock',50);")

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
mymarks=float(input("Enter marks: "))

# We now replaces the fixed VALUES in the INSERT query with the variables, mysid, myname, and mymarks.
# To do this, we use the DB-API’s parameter substitution. We put a ? as a placeholder wherever we want to use a value.
# Then give a tuple of values as the second argument to the cursor’s execute() method:
'''
curschool.execute("INSERT INTO student (StudentID, name, marks) VALUES (?,?,?);", (mysid,myname,mymarks))

# We now commit the changes:
MySchool.commit()
```

<br>
<br>

### Error Handling
In Python, there are (at least) two distinguishable kinds of errors: **syntax errors** and **exceptions**.
<br>
Error handling in Python is done through the use of exceptions that are caught in try blocks and handled in except blocks.

Let us look at an example of how this is used. The following code not only accepts user input and adds a new record but also displays a message if the operation was successful or not.

```bash
import sqlite3
MySchool=sqlite3.connect('schooltest.db')
        
mysid= int(input("Enter ID: "))
myname=input("Enter name: ")
mymarks=float(input("Enter marks: "))
        
#try block to catch exceptions
try:
    curschool=MySchool.cursor()
    curschool.execute("INSERT INTO student (StudentID, name, marks) VALUES (?,?,?)", (mysid, myname, mymarks))
    MySchool.commit()
    print ("One record added successfully.")
    
#except block to handle exceptions    
except:
    print ("Error in operation.")
    MySchool.rollback()
        
MySchool.close()
```
###### The connection class defines the commit() and rollback() methods. Changes in the database are finalized only if the execute() method runs successfully by commit() method. Otherwise, any changes are undone by the rollback() method. You can try this yourself by saving this code as a .py file and executing it.

<br>
<br>

### Retrieving New Record
There are two prominent methods as per DB-API standard to retrieve one or more record. The below two methods are used:

<br>

**1. fetchone()**
This method fetches the next available record from the result set. It is a tuple consisting of values of each column of the fetched record. The Following code snippet retrieves and prints one record at a time till the result set is exhausted.

```bash
import sqlite3
MySchool=sqlite3.connect('schooltest.db')
            
sql="SELECT * from student;"
            
curschool=MySchool.cursor()
curschool.execute(sql)
while True:
    record=curschool.fetchone()
    if record==None:
        break
    print (record)
```

<br>

**2. fetchall()**
This method fetches all the remaining records in the form of a list of tuples. Each tuple corresponds to one record and contains values of each column in the table. The following code snippet fetches all records and prints them one at a time by using the 'for' statement.

```bash
import sqlite3
MySchool=sqlite3.connect('schooltest.db')
    
sql="SELECT * from student;"
            
curschool=MySchool.cursor()
curschool.execute(sql)
    
result=curschool.fetchall()
for record in result:
   print (record)
```

<br>
<br>

### How to Update a Record?
```bash
import sqlite3

# Connect to database
MySchool = sqlite3.connect('schooltest.db')

# Get name input
nm = input("Enter name: ")

# Use parameterized query to avoid SQL injection
sql = "SELECT * FROM student WHERE name = ?"
curschool = MySchool.cursor()
curschool.execute(sql, (nm,))
record = curschool.fetchone()
print(record)

# Get new marks and update
m = float(input("Enter new marks: "))
sql = "UPDATE student SET marks = ? WHERE name = ?"

try:
    curschool.execute(sql, (m, nm))
    MySchool.commit()
    print("Record updated successfully")
except Exception as e:
    print("Error in update operation:", e)
    MySchool.rollback()

# Close connection (optional, but good practice)
MySchool.close()
```










