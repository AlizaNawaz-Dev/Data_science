# Loops:  
There are basically two type of loops in python.    
### 1: While:  
- Repeating action until specific condition is met.   
#### Syntax:  
Initializer  
**while** condition **:**   
(indentation)  expression  
### 2: For:  
- Repeating action for specific known number of iterations(Times).  
#### Syntax:
**for** obj **in** sequence **:**  
(indentation)   expression 
### Example:To print square n lines, one corresponding to each.  
```python
n=int(input())
for i in range(n) :
    if n<20:
        print(i*i)
```
# Functions :  
- Helps to break our program into smaller chunks.   
- Helps to avoid repetition.  
- Makes the code reusable.  
- How to Write basic Function:  
1- Define header.    
2- Write Functionality.  
3- Return variable.  
4- Call function and store it in a new variable.  
5-print that variable.  
### Example: Whether a year is leap or not. 
```python

def is_leap(year):               #Header of function
    if year % 400 == 0:         
        return True
    if year % 100 == 0:         #Functionality
        return False
    if year % 4 == 0:
        return True
    return False

year = int(input())
print(is_leap(year))            #Function Call
```  
## DocStrings:  
- Provides documentation for function(tells what the function does)  
- Written after the header of function.  
- Written in """ """ marks.  
- As docstring for above function is:    
``` python
""" Provides information whether a year is leap or not"""
```


