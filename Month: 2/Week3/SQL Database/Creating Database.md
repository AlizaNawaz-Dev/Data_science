# Creating Table:
- After creating database we can create table inside our database to store information.  
- Query for creating table **student** having columns (student_id as primary key,student_name,student_major).
```  SQL 
CREATE TABLE student ( 
 
                    student_id INT PRIMARY KEY, 
                    student_name VARCHAR (20), 
                    student_major VARCHAR  (20) 
                    );
DESCRIBE student;
```

### Deleting Table:
``` SQL
DROP TABLE student;
```

### Modifying Table:
``` SQL
ALTER TABLE student ADD gpa DECIMAL(4,6);
```

- Deleting specific column from table.  

``` SQL 
ALTER TABLE student DROP column gpa;
```

# Inserting Data:
- Inserting student's information into table **student**.    
``` SQL
INSERT INTO student VALUES(1 , 'Ali', 'CS');
```
- In order to check whether information is **inserted successfully or not** we can use this query.  
``` SQL 
SELECT * FROM student;
```
-The above query will show all information stored in table **student**.  

- If we have a situation where we don't have complete information about student we can modify insert query **by specifying column names **as follows.  
``` SQL
INSERT INTO student(student_id,student_name) VALUES(2,'Alisha');
```
- We can drop column name of our choice incase we don't have information about it.  

### Constrains:  

⊛ **NOT NULL:** Enforces a column to NOT accept NULL values.   

⊛ **UNIQUE:** Ensures that all values in a column are different.  

⊛ **DEFAULT:** Used to set a default value for a column.  
```SQL
student_major VARCHAR  (20) DEFAULT 'UnDecided';
```

⊛ **AUTO_INCREMENT:** Allows a unique number to be generated automatically when a new record is inserted into a table.  


# Deleting Data:

# Updating Data:
- Query to update a major name based on a condition keyword **WHERE** is used to **impose condition **in query.  
``` SQL
UPDATE student SET major= 'BIO'
               WHERE major='BIOLOGY'
```
