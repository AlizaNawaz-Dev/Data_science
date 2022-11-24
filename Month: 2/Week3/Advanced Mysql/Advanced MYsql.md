
## Advanced Mysql:

➠ **FORMAT():**

-  Formats a value (**date/time** values and **number** values) with the specified format.  
-  Let's say to convert salary to **two decimal digit** we can provide value (like 2) and number will be **limited** to two after point.  
```SQL

FORMAT(salary,2);                    # 10987.32
```
➠ **CONCAT():**

- Adds two or more strings together.  
``` SQL
CONCAT('$',FORMAT(salary,2));       # $10987.32
```

- When we perform aggregate functions or any sort of calculation on database tabels they only **exsist in system's memory**.  
- Tabels in the database are **not affected by changes** made through queries.   
- In order to store that information in our database we can create a new table and add that information accordingly.  

### Alternative to Above:

- When we create a table and insert calculated information into table this is only for **viewing** means we are unable to modify/update or perform further operations.  
- That table will be **static** new changes made in database tabels won't effect this static table.
- So alternatively we can use **VIEW** it will be same as table but will also be updated when related information will change.   
- To create view:
``` SQL
CREATE VIEW new_Info;           # new_Info is view name 
```
- We can drop/delete view in same way as we do for tabels.  
```SQL
DROP VIEW new_Info;
```

## IMPORT/EXPORT :

➝ **Export data to out file:**
- Now rather then showing data on the screen we can also store it in different file formats (CSV,textfile,spreadsheet adn sql) in our system.   
- To create csv file of data present in table:
``` SQL
SELECT * 
FROM students
INTO OUTFILE 'c:\\data\\students.csv'            # 'c:\data\students.csv' is path where we want our data to be stored.
FIELDS ENCLOSED BY '"' TERMINATED BY ',' ESCAPED BY '\\'
LINES TERMINATED BY'\r\n';
```
- Reason behind using \\ is that  \ is **delimiter**(boundary) in mysql so we use two instead of one.  


➝ **Import data from out file:**
- As we have our data stored in csv file we can load it back in our database.  
``` SQL
LOAD DATA
INFILE 'c:\\data\\students.csv'
INTO TABLE my_students.students
FIELDS ENCLOSED BY '"' TERMINATED BY ',' ESCAPED BY '\\'
LINES TERMINATED BY'\r\n';
```

## Crearing table from exsisting table:

- Let's say we want to create a new table that contains some related important information of original table.   
```SQL
CREATE TABLE cs_Students 
LIKE my_students.student;                 # This query will create a structure of table like student table without any data in it.

INSERT cs_Students 
SELECT * students_name,student_id
FROM student
WHERE major='CS';                     
```

- If we want to update a record that present in multuple tabels.  
- We create session variables using @ sybmol to do this task.   
```SQL
SET @oldstudent_id := 021;
SET @newstudent_id := 120;
```
### Transaction:

- In order to make sure that all related tabels are updated we can use transaction.  
- Transaction begins with a specific task and ends when all the tasks in the group successfully completed.  
- If any of the tasks fail, the transaction fails.  
- The COMMIT command saves all the transactions to the database
``` SQL
START TRANSACTION;
UPDATE students
SET student_id= @newstudent_id
WHERE student_id= @oldstudent_id;

UPDATE finance
SET student_id= @newstudent_id
WHERE student_id= @oldstudent_id;

COMMIT;
```
