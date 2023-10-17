# TASK 3 MySQL Database Operations with Python

Your task is to write a Python program that accomplishes the following:
First create a database , table and add these column ‘student_id’, ‘first_name’, ‘last_name’,
‘age’, ‘grade’.
Connects to your MySQL database with python.
Inserts a new student record into the "students" table with the following details:
First Name: "Alice"
Last Name: "Smith"
Age: 18
Grade: 95.5
Updates the grade of the student with the first name "Alice" to 97.0.
Deletes the student with the last name "Smith."
Fetches and displays all student records from the "students" table

# CREATING THE TABLE  AND CONNECTING WITH THE DATABASE DB1


```python
import mysql.connector
mydb=mysql.connector.connect(host="localhost",port="3306",user="root",password="admin@123")
cur=mydb.Cursor()
#CREATING DATABASE AS DB1
cur.execute("CREATE DATABASE db1")
```


```python
mydb=mysql.connector.connect(host="localhost",user="root",password="root",database="db1")
cur=mydb.Cursor()
s="CREATE TABLE students(student_id int(4), first_name varchar(20), last_name varchar(20), age int(4), grade float(5,2))"
cur.execute(s)
```

# INSERTING A NEW STUDENT RECORD


```python
cur=mydb.Cursor()
s="INSERT INTO students(student_id,first_name,last_name,age,grade) VALUES (1,'Alice','Smith',18,95.5)"
cur.execute(s)
mybd.commit()
```

# UPDATING


```python
cur=mydb.Cursor()
s="UPDATE students SET grade=97.0 WHERE first_name='Alice'"
cur.execute(s)
mydb.commit()
```

# DELETING 


```python
cur=mydb.Cursor()
s="DELETE from students WHERE last_name='Smith'"
cur.execute=(s)
mydb.commit()
```

# FETCHING AND DISPLAYING THE TABLE 


```python
s="SELECT * from students"
cur.execute(s)
data=cur.fetchall()
for d in data:
    print(d)
```
