# Functions:
- There are number of functions in SQL we can use in our queries to to access and manage databases according to our requirements.  

🔘 **COUNT():** Returns the number of rows either based on a condition, or without a condition.  
```SQL
SELECT COUNT(student_id) FROM student
                         WHERE student_major='CS';
```

🔘 **AVG():** Calculate the average value of a numeric column.  
```SQL
SELECT AVG(gpa) FROM student; 
```

🔘 **SUM():**  Return the sum of a group of values.  
```SQL
SELECT SUM(marks) FROM student;
```
🔘 **GROUP BY**: Groups rows that have the same values,often used with aggregate functions(SUM,COUNT,AVG).   
```SQL
SELECT COUNT(gpa), gpa FROM student
                  GROUP BY gpa;
```
