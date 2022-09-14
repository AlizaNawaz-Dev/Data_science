# Python Modules And Packages:
### Modules: 
-  Python code that can be **imported** inside another Python Program.  
-  Functionality is divided into smaller chunks that can be used seperately by importing that specific file.
-  Module can contain the following elements:
   -  Definitions and implementation of classes
   -  Variables.
   -  Functions that can be used inside another program.
### Creating Modules:
- To create a module we have to save the code in a file with the file extension **“.py”**.
- FileName: **Info_Module.py**
``` python
class Choclate:
    def __init__(self, name, category):                     
        self.name = name                                   
        self.category =category

    def update_category(self,new_category):
        print("Updated category Is:")
        self.category = new_category
```
### Using Modules:
- **import** keyword is used with required filename.  

    ``` python
    import Info_Module.py
    ```
### Packages:
- A Python package usually consists of **several modules**.  
- Physically a package is a folder containing modules by which they may be **referenced.**  
- A package folder usually contains one file named **__init__.py**.
- 

