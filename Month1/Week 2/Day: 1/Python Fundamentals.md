### Taking input from user:  
#### input()  
- input() function enables to take input from user.   
- It reads the input and return string so we can typecast according to required input.
``` python
Age=input("Enter Your Age")
print(Age)
Age=int(input())                      
print(Age+3)      
```
### TypeCasting:
- We can convert any input into required datatype by using these functions.  
1- str()  (like for conversion into  string)          string(name)  
2- int()  
3-float()  
4-bool()  

### Built-in functions for Strings:  

1- replace()   
***Syntax***  
variablename.replace("what to replace","with which value")

``` python
name="Aliza Nawaz"
print(name.replace("i","ee"))            #output:Aleeza Nawaz     
```
2- upper(): convert all letters into uppercase  
***Syntax***  
varaiblename.upper()
``` python
name="Aliza Nawaz"
print(name.upper())                     #output:ALIZA NAWAZ
 
```
3- lower(): convert all letters into lowercase  
***Syntax***  
varaiblename.lower()
``` python
name="ALIZA Nawaz"
print(name.lower())                     #output:aliza nawaz
 
```
4- find():will return index of value/string if present in variable.  
***Syntax***   
varaiblename.find('value')
``` python
name="aliza nawaz"
print(name.find('i'))                   #output:2
 
```

- These methods return new string means if we again print same variable (without using function) there will be no modification.  
**Example:**    
``` python
name="Aliza Nawaz"
print(name.upper())           #output:ALIZA NAWAZ
print(name)                   #output:Aliza Nawaz
```
