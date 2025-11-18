# Ex.No: 10 Logic Programming – Simple queries from facts and rules
**DATE:** 20.09.2025  
**REGISTER NUMBER:** 212222060077  

## AIM:
To write a prolog program to find the answer of query.

## Algorithm:
Step 1: Start the program  
Step 2: Convert the sentence into First order Logic  
Step 3: Convert the sentence into Horn clause form  
Step 4: Add rules and predicates in a program  
Step 5: Pass the query to program  
Step 6: Prolog interpreter shows the output and return answer  
Step 8: Stop the program  

---

## Task 1:

Construct the FOL representation for the following sentences:

1. John likes all kinds of food  
2. Apples are food  
3. Chicken is a food  
4. Sue eats everything Bill eats  
5. Bill eats peanuts  

Convert into clause form and prove that John like Apple by using Prolog.

### Program:

```prolog
likes(john,X):- 
 food(X). 
eats(bill,X):- 
 eats(sue,X). 
eats(Y,X):- 
 food(X). 
eats(bill,peanuts). 
food(apple). 
food(chicken). 
food(peanuts).
```
## Output:
<img width="539" height="407" alt="image" src="https://github.com/user-attachments/assets/38452398-e011-46d3-988a-7b2de611127c" />

Task 2:
Consider the following facts and represent them in predicate form:

Steve likes easy courses.
Science courses are hard.
All the courses in Have fun department are easy
BK301 is Have fun department course.
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”

Program:
```prolog
likes(steve,X):- 
 easycourse(X). 
hard(sciencecourse). 
easycourse(X):- 
 course(X,dept(havefun)). 
course(bk301,dept(havefun)).
```
## Output:
<img width="415" height="63" alt="image" src="https://github.com/user-attachments/assets/ac958d22-0c64-447b-bab2-32958f87a75b" />


## Result:
Thus the prolog programs were executed successfully and the answer of query was found.

