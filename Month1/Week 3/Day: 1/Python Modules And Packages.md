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
    import Info_Module
    ```
- Now by importing **Info_Module.py** we can use its all functionalities.  
- **from** keyword is used to import specific functionality from file.  
``` python
from Info_Module import update_category
```
### Packages:
- A Python package usually consists of **several modules**.  
- Physically a package is a folder containing modules by which they may be **referenced.**  
- A package folder usually contains one file named **__init__.py**.
### __init__.py:
   - Helps python to recognise folder as a package.  

### Creating Pacakge:
- Create a folder.  
- Inside folder create python file named **__init__.py**.  
- Add/Create modules.

### Using Pacakge:
- import package_name.module_name.   
- Package_name = My_Package  
- Modules_name = module_1 , module_2.  
- By using **from** keyword we can select package and then using **import** keyword we can acess our desired module.  
- We can also use **package_name.module_name** to select module from package and then further specify desired functionality.  
``` python
from My_Package import module_1
from My_Package.module_1 import update_category
```
