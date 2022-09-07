# Basics of probability for data science
## Probability:  
It is **chance** an event will happen. It's basically the ratio of the number of ways an event can occur to the number of **possible outcomes**.  
  
```Probability = No. of ways certain event can occur / No. of possible events```  
Notionally:

***P (A) = n/N   = n (A)/n(S)***         
### Probability in daily life:
•	When we toss a coin. Expected result  means the coin can either land on the ***‘heads’*** side or ***‘tails’***.  
•	Rolling of die.  
•	Choosing a card from deck.  
•	Winning a lucky draw.  
•	There is a high chance of getting the job this year.  
#### Event:  
Events in probability can be defined as a ***set of outcomes*** of a random experiment. 
  
There are two types of an event  
- 1-  Mutually Exclusive Events:  
                                Events that cannot occur at the same time are known as ***mutually exclusive events.***  
***Example:***    
o	Tossing a coin  
- 2-  Non-Mutual Exclusive Events:  
                                Events that can occur at the same time are known as ***non-mutual exclusive events.***  
***Example:***   
o	Picking a card from deck of cards.  
### Additive rule:
    P (A or B) =P (A) +P (B)                                           Mutually Exclusive    
    P (A or B) =P (A) +P (B) −P (A and B)                              Non-Mutual  

### Multiplicative rule:  
#### Independent event:  
``` Total outcomes remain same for each experiment. ```   
***Formula:  P (A∩B) = P (A).P (B)***  
#### Dependent event:  
``` Total outcomes for each experiment reduces after each experiment.  ```  
***Formula: P (A∩B) = P (A) × P (B|A)***  
### Conditional Probability:  
Conditional probability is defined as the ***likelihood of an event*** or outcome occurring, based on the occurrence of a previous event or outcome.    
### Use in data science:  
-	Helps in analysis of frequency of past event as well as future events.  
-	Basically it really helps in predicting chances of events that can happen in future.  
-	Helps to make a clear guess or idea where to put new coming points/predictions if there are multiple options to choose from.  
