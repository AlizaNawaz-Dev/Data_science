# Managing Users and Privileges: 

### Creating User Account:
```SQL
create user my_user identified by 'password';
create user my_admin identified by 'password';
```
- Granting all privileges to admin account.   
``` SQL
GRANT ALL
ON my_students.*
to my_admin;
```
-  Granting selected privileges to user account.   
``` SQL
GRANT SELECT , UPDATE , DELETE ,INSERT
ON my_students.*
to my_user;
```

- To see what kind of permissions an account possess
``` SQL
show grants for my_admin;
show grants for my_user;
```
- Revoking(cancelling) grants from user.  
``` SQL
REVOKE SELECT , UPDATE , DELETE ,INSERT
ON my_students.*
FROM my_user;
```
