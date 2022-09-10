# Object-Oriented-Programing(OOP):  
Based on concept of objects that can contain **data**.  
OOP is based on object and classes.  
## Class:
- It's a **blueprint** for objects.   
- Outlines possible states and behaviors.  
- Class is an abstract template of what object can contain.  
## Object:
- We use class to create an object.  
- It consists of **State + behavior**.  
- ### State:     
- Properties of an object. ( size, colour, model) .    
- ### Behavior:  
- The tasks that an object performs(person can walk,speak,cook)  .  

- Attributes in python are represented by **variables**.  
- **State <--> Attributes** (In python state information is contained in attributes).  
- **Behavior <--> Method** (Behaviors information in method/function).  
- Object is Concrete representaion of class.  
## type():  
- By using type(class_name) function we can find class of any object.  
```python
type(mystery)                             #output:__main__.employee
```
# Creating Class:
## Syntax: 
***class*** classname **:**  
(indented)Statments(attributes,methods)  
### Object creation:   
obj_name= classname()  
``` python
class Choclate:
  pass
C1 = choclate()
```
- As above defined class is not performing any functionality so we can create methods to perform any action.
- Methods in class are same as regular python function having one exception.  
- Every method will have **self** as it's first argument in method definition.  
### Syntax:  
**def** name(**self**, param1) **:**  
(indented)statments  
Create object:   
Obj=name **()**  
Call class method through this obj  
Obj.name("aliza")   value is passed.  
- self is not needed in method call.  
 ***Then why we need self in every method definition?***  
- To call attributes and methods from within the class definition when object is not created yet.  
- Also **self** helps us to refer different objects like when C1 is called , self will take its values and return data accordingly for different objects.  
### constructor:
```python
 def __init__(self,name,price):
  self.name=name
  self.price=price
```
- As this method is constructor so it can be automatically invoked whenever we create an object.    
- We can also create our own methods and can invoke them whenever required(custom methods).  
```python
class Choclate:
    def __init__(self, name, category):                     # constructor
        self.name = name                                    # will refer to information of each object individually.
        self.category =category

    def update_category(self,new_category):
        print("Updated category Is:")
        self.category = new_category

C1 =Choclate ("Kit-Kat", "Milky")
print(C1.name,C1.category)                                   #output:Kit-Kat Milky

C2 =Choclate ("Dairy-Milk", "Dark")
print(C2.name,C2.category)                                   #output:Dairy-Milk Dark

C1.update_category("DARK")                                   #output:Updated category Is:
print(C1.category)                                           #       DARK


C2.update_category("MILKY")                                 #output:Updated category Is:
print(C2.category)                                          #       MILKY

```

- Rather then using variables we can also use different data structures.  
### lists:
- ***Syntax***
Choclates=[Choclates(pass arguments),
          Choclates(pass arguments)]  
``` python
Choclates=[Choclates("Dairy-Milk", "Dark"),
           Choclate ("Dairy-Milk", "Dark")]
```
***Static Method***:
- Not attached to any individual object.  
- Invoked on class itself.  
- They dont have parameters in function definition.  
- They are invoked usig class name.  
- classname.method()  
```python
class Choclates:
  def Info():
    print("Choclate Class")
Choclates.Info()                                          #output:Choclate Class
```
- There are also three principles in oop
### Encapsulation:
- Wrapping up of data under a single unit.  
- It is a protective shield that prevents the data from being accessed by the code outside.  
- Prevent the accidental modification of data.  
- ***Private variables*** are used to prevent modification.In python we can private variables using '_'(underscore).   
```python
class Choclate:
    def __init__(self):
        self._name = "Kit-Kat"                                            # Protected member

class Candy(Choclate):
    def __init__(self):
        Choclate.__init__(self)                                          # Calling constructor of Base class
        print("member of base class: ",self._name)

        self._name = "Galaxy"                                             # Modify the protected variable
        print("modified protected member outside class: ",self._name)

obj1 = Candy()
obj2 = Choclate()

print("protected member of obj1: ", obj1._name)                          # Calling protected member
print("protected member of obj2: ", obj2._name)
```
### Inheritance:
- When a class derives from another class.  
- Child class can access all information of parent class including methods attributes.  
- provides the reusability of a code.(we dont have to rewrite code over and over having same functionality).  
- In python we can inherit class like this.  
- ***Class DerivedClass(BaseClass):***  
```python
class Choclate:
     def __init__(self, name,category):
        self.name = name
        self.category=category

    def update_category(self, new_category):
        print("Updated category Is:")
        self.category = new_category
        
class Candy(Choclate):
    def __init__(self, name):
        self.name = name
        
Obj1= Candy("Kit-kat",)
Obj1.update_category("Dark")              #Accessing method of parent class
print(Obj1.category)                      #output:Updated category Is:
                                                  Dark
```
### Polymorphism:
- Methods in the child class that have the same name as the methods in the parent class.  
```python
class Choclate:
    def info(self):
        print("This is Choclate class method!!")

    def Category(self,category):
        self.category=category

class Candy(Choclate):
    def info(self):
        print("This is Candy class method!!")

obj1=Choclate()
obj2=Candy()
obj1.info()                               #output:This is Choclate class method!!
obj2.info()                               #output:This is Candy class method!!


```
