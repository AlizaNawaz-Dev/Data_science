# Principles of OOP
There are three basic principles of oop
### 1-Encapsulation:
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
### 2-Inheritance:
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
### 3-Polymorphism:
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


