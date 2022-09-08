## Basics:
### 1-Hello World
***print():***  
print function is used to print anything written inside round paranthesis().  
**Example:**  
``` python  
print("Hello, World.")
print("I Love Choclates")
```  
### 2-Variable and Types
**Variables:**  
- Are used for storing elements/objects to perform further operations.  
- In python there's no need to declare variables(define DataType).  
**Syntax:** variable name= value  
- By using this variable name we can perform any operation on it.  
**Example:**  (Marks of different subjects are added here using variable_name(that contain their values))  
``` python  
Marks_1= 70
Marks_2= 80
Marks_3= 60

Obtained= Marks_1+Marks_2+Marks_3
print(Obtained)                   #output:210

Percentage=Obtained/300*100
print(Percentage)                 #output:70.0
```

**Data Types:**  
- We can find datatype of any object  using  type(object_name) 
- By default datatype is considered String.
#### 1- Numbers:
- It can be either integer or floating point.
- We can also cast(convert) float to int 
``` python  
Marks = 70        
Percentage = 12.3 
Percentage = float(12.3)          # This will print 12 after typecasting

print(percentage)
```  

- type(Marks)                        
- It will give type **int** in console.
- (#) symbol is used in python for writing comments in code(to make it understandable).
#### 2- Strings: 
- Sequence of characters.  
- Can be defined using single ' ' or double "" quotes. 
- Double quotes are preffered because when apostrophes(') are used in string they might be confusing (because same symbol will be used for termination of string)  
``` python  
Information  = "Data science uses scientific methods or processes"  
print(Information)
```  
- We can also concatenate(join) strings by using + symbol
``` python   
First_Name = "Aliza"
Last_Name = "Nawaz"

Name=First_Name+" " +Last_Name
print(Name)                       #output:Aliza Nawaz
```
#### 3- Boolean:
- Boolean when there's some condition either something can be true or false.   
- Capitalization is important here (True,False)  
**Example:**  
``` python  
State= True
```
### 3-Lists:
- Used to name collection of values.  
- Can contain any type of objects.    
- Used to store multiple elements.  
- List itself is also a type in python.  
**Syntax:** list_name=[variable/value,variable/value,variable/value,]
``` python 
Choclates=["Kit-Kat","Bounty","Dairy-Milk"]
print(Choclates)                            #output:['Kit-Kat', 'Bounty', 'Dairy-Milk']
```
- We can also use a list as an element in list. 
``` python 
Choclates=["Kit-Kat","Bounty","Dairy-Milk"]
Information = [150,450,40,Choclates]

print(Information)                         #output:[150, 450, 40, ['Kit-Kat', 'Bounty', 'Dairy-Milk']]
```

