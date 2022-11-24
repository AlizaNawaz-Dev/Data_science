
## Advanced Mysql:

➠ **FORMAT():**

-  Formats a value (**date/time** values and **number** values) with the specified format.  
-  Let's say to convert salary to **two decimal digit** we can provide value (like 2) and number will be **limited** to two after point.  
```SQL

   FORMAT(salary,2)                    # 10987.32
```
➠ **CONCAT():**

- Adds two or more strings together.  
``` SQL
   CONCAT('$',FORMAT(salary,2))        # $10987.32
```

- When we perform aggregate functions or any sort of calculation on database tabels they only **exsist in system's memory**.  
- Tabels in the database are **not affected by changes** made through queries.   
- In order to store that information in our database we can create a new table and add that information accordingly.  

### Alternative to Above:

- When we create a table and insert calculated information into table this is only for **viewing** means we are unable to modify/update or perform further operations.  - That table will be **static** new changes made in database tabels won't effect this static table.
- So alternatively we can use **VIEW** it will be same as table but will also be updated when related information will change.   
- 
