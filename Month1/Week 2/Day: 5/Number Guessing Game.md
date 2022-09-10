# Number Guessing Game
``` python
# Guessing Number
import random

top_of_range=input("Type a Number: ")
Guesses=0

if top_of_range.isdigit():
    top_of_range=int(top_of_range)

    if top_of_range <=0:
        print("Please Enter number greater then zero.")
        quit()
        
else:
    print("PLease enter Digit Next Time!")
    quit()

Random_number=random.randrange(0,top_of_range)

while True:
    Guesses+=1
    User_guess=input("Make a Guess: ")
    if User_guess.isdigit():
        User_guess = int(User_guess)

    else:
        print("PLease enter Digit!")
        continue

    if User_guess == Random_number:
        print("Congratulations You got it Right")
        break

    elif User_guess > Random_number:
        print("You Were Above the Number's Range")
    else:
        print("You Were Below the Number's Range")

print("You got it in",Guesses,"Guesses")

```
