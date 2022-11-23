
# Database Design:
- Databse design is categorized into **two** main parts.  

➥ **Logical Design:**

- Logical design is more **conceptual and abstract**.   
- Or we can say designing **general layout**(like casually on paper) to get an idea of what we want.   
- To define the data **elements**and their **relationships**.  

➥ **Physical Design:**  

- To design the actual database based on the requirements gathered during the **logical data design.**  

- **DBA:**    
 ✦ who directs and performs all activities related to maintaining a successful database environment.
 
- Database administrator (DBA)**implements** the design.  

### Refrential Integrity:  

- Refers to the **relationship** between tables.  
- All references from one table to another should be **valid**.  
- In other words **foreign keys** must have corresponding attribute in the **related** table.   

### Shorthand Notation:

- Textual representation of database tables.  
- Entity(Table) gets listed first in all **capital letters**.  
- Attributes inside **paranthesis**.  
- Primary keys are **underlined** and alternatively labeled as **PK**.   
- Foreign keys are represented by **dotted line** alternatively labeled as **FK**.  
 
 ### Normalization:  
 
- The process of **organizing** data in a database.   
- To make the database more **flexible** by eliminating **redundancy** and **inconsistent** dependency.   
- Results in more tables with less attributes but tabels are more **refined.**
 
 Databsase should be normalized atleast upto third normal form.  
 
 ➜ **First Normal Form (1NF)**
 
 - An attribute of a table cannot hold multiple values. It must hold only single-valued attribute.  
 
 ➜ **Second Normal Form (2NF)**
 
 - A relation must be in first normal form.   
 - Is based on full functional dependency.  
 - Every non-primary-key attribute is fully functionally dependent on the primary key.  
 
 ➜ **Third Normal Form (3NF)**
 
 - A relation that is in First and Second Normal Form.  
 - Every non-primary attribute(column) should be dependent on it's primary key.  
 
