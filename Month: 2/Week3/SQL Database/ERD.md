## Nested Queries:

- When we use multiple **SELECT** statments to get specific peice of information.  

- IN keyword is used to nest queries.  
``` SQL
SELECT student.student_name,student.student_id 

FROM student 

WHERE student_id IN(SELECT finance.id 
                    FROM finance
                    WHERE finance.status = 'paid');

```
- Above query will give **names and ids** of students who have paid their fee challan.  

## Deleting entries from DB:
- There are certain conditions imposed while deleting information that is linked to another table in DB (haveing foreign keys).  
- These conditions are **ON DELETE SET NULL** and **ON DELETE SET CASCADE**.  
  
◼ **ON DELETE SET NULL**: Sets a foreign key in the **child table to Null** if the corresponding record in the parent table is deleted.  

◼ **ON DELETE SET CASCADE**: Delete the rows from the **child table automatically,** when the rows from the parent table are deleted.  
