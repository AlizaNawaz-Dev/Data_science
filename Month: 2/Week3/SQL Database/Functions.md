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
SELECT COUNT(gpa), student_name FROM student
                       GROUP BY student_name;
```

🔘 **LIMIT:** Select a limited number of records.  
```SQL
SELECT student_name FROM student
                    LIMIT 5;
```
- Above query will give first five names of students.  

🔘 **ORDER BY:** Sorts the records according to given column. (by default in ascending order ).   
``` SQL
SELECT student_name FROM student
                    ORDER BY gpa;
```

🔘 **UNION:** 
- To combine the result-set of two or more SELECT statements. 
- Same number of columns should be selected from both tabels.  
- DataType should be same.  
```SQL
SELECT student_id FROM student
UNION 
SELECT feeChallan_No FROM finance;
```
🔘 **AS:** 
- We can change current column name with new name by using AS keyword.  
``` SQL
SELECT student_names AS name 
                     FROM student;
```

# WILDCARDS:
-  Search for a specified pattern in a column.
-  Wildcard characters are used with the LIKE operator.  
-  The LIKE operator is used for search.  
-  Now this pattern can be found by using two special operators.  

◼ **_**  Represents a **single** character.  

◼ **%**  Represents **zero or more**characters. 

```SQL
SELECT * FROM student
         WHERE student_major LIKE '%science%';
```
- This query will give all information about student having science in their major.  
