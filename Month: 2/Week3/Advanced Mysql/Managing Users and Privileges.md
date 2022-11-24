# Managing Users and Privileges: 

### Creating User Account:
```SQL
create user my_user identified by 'password';
create user my_admin identified by 'password';
```
⦿ Granting all privileges to admin account.   
``` SQL
GRANT ALL
ON my_students.*
to my_admin;
```
⦿ Granting selected privileges to user account.   
``` SQL
GRANT SELECT , UPDATE , DELETE ,INSERT
ON my_students.*
to my_user;
```

⦿ To see what kind of permissions an account possess
``` SQL
show grants for my_admin;
show grants for my_user;
```
⦿ Revoking(cancelling) grants from user.  
``` SQL
REVOKE SELECT , UPDATE , DELETE ,INSERT
ON my_students.*
FROM my_user;
```
- when we want to restric user account to view specific information.  
- To do this we can specify **ON** argument like for which specific table we are granting permission to user.  
```SQL
GRANT SELECT
ON my_student.cs_students          # cs_students is view in DB not an actual table.
TO my_user;
```
- Above query will allow **my_user** account to view **cs_students** information only from my_student DB.  

⦿ Reseting Password.  
```SQL
SET password for my_user = password('myNewPassword');
```
⦿ Deleting  Account.  
- Revoking privileges and dropping account are different because revoking simply means limiting or canceing some permissions.  
- While dropping account will completely remove access to that account. 
```SQL
DROP user my_user;
```
