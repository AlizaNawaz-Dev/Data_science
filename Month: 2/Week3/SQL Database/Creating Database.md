# Creating Table:
- After creating database we can create table inside our database to store information.  
- Query for creating table **student** having columns (student_id as primary key,student_name,student_major).
```  SQL 
CREATE TABLE student ( 
 
                    student_id INT PRIMARY KEY, 
                    student_name VARCHAR (20), 
                    student_major VARCHAR  (20) 
                    )
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
