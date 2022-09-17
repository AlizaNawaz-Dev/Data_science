# Rock ,Paper and Scissor
##  1- Random Module:
- Returns a random number between the **given range**.  
- Creates pseudo-random numbers(these are not truly random).  

   - **random.randint() :** method is used to generate random integers between the given range.  
   
##  2- Lower():
-  Built-in Python method  used for string handling.  
-  It takes no arguments.  
-  From the given string **lower()** converts each uppercase character to lowercase.  
  
#### in:
- To check if a value is present in given Datastructure.  
-  To iterate through a sequence in a for loop.  
``` python
import random

User_score=0
Computer_score=0
options= ["rock","paper","scissor"]

while True:

    User_input=input("Type Rock,paper,Scissor and Q to quit: ").lower()
    if User_input== "q":
        break

    if User_input not in options:
        continue
        
    Random_number=random.randint(0,2)
    Computer_pick= options[Random_number]
    print("Computer Picked",Computer_pick)

    if User_input == "Rock" and Computer_pick== "Scissor":
        print("You Won")
        User_score+=1

    elif User_input == "paper" and Computer_pick== "Rock":
        print("You Won")
        User_score+=1

    elif User_input == "Scissor" and Computer_pick== "Paper":
        print("You Won")
        User_score+=1
        
    else:
        print("You Lost !!")
        Computer_score+=1
        
print("You Won",User_score,"Times")
print("Computer Won",Computer_score,"Times")
print("Good-Bye")
```
