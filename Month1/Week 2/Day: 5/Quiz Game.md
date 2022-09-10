# Quiz Game
``` python
print("Welcome to my Computer Quiz")
Playing=input("Do You Want To Play? (yes or No) ")

if Playing.lower() != "yes":
    print("Exited!!")
    quit()

else:
    print("Okay! Let's Play :)")

Score=0
Anwser = input("Q1: What Does CPU Stands For? ")

if Anwser.lower() == "central processing unit":
    print("Correct ")
    Score+=1

else:
    print("oops Wrong Anwser")

Anwser = input("Q2: What Does GUI stands for?  ")

if Anwser.lower() == "graphical user interface":
    print("Correct ")
    Score += 1

else:
    print("oops Wrong Anwser")

Anwser = input("Q3: What does RAM stands for? ")

if Anwser.lower() == "random access memory":
    print("Correct ")
    Score += 1

else:
    print("oops Wrong Anwser")

Anwser = input("Q4: What does PSU stands for? ")

if Anwser.lower() == "power supply":
    print("Correct ")
    Score += 1

else:
    print("oops Wrong Anwser")

print("Your Score is: "+str(Score))
print("You got "+ str((Score / 4) *100)+ "%")
```
