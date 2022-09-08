# Logical Operators:
### 1- and:  
- Returns True if both statements are true. 
``` python
Marks=70                                         #Both conditions must be true here.
print(Marks>=50 and Marks<71)                    #output:True       
```
### 2- or:
- Returns True if one of the statements is true.  
``` python
Marks=80                                          #Only one condition needs to be true.
print(Marks>=50 or Marks<71)                      #output:True       
```
### 3-not:
- Reverse the result.
 ``` python 
Marks=80                                         #What ever the condition is result will be negation.
print(not(Marks>=50 or Marks<71))                #output:False
```
# if-else:
- When we want to perform some operation that satisfies a particular condition if-else structure is used.
- in python:
### Syntax :  
**if** condition **:**  
(indented)Statments  
**else :**  
(indented)Statments  
### elif: In case of multiple conditions we can use elif multiple times.  
if condition :  
(indented)Statments  
**elif** condition **:**  
(indented)Statments  
**elif** condition **:**  
(indented)Statments    
else :  
(indented)Statments 
### Example:  
``` python
Marks=int(input()) 

if(Marks>=80 ):
  print("Your Grade is: 'A'") 
  
elif(Marks>=70 and Marks<80):
  print("Your Grade is: 'B'")
  
elif(Marks>=60 and Marks<70):
  print("Your Grade is: 'C'")
  
else:                                                   #input: 79  
  print("Your Grade is: F")                             #output:Your Grade is: 'B'  
``` 
