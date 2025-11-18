# Ex.No: 11 Planning – Block World Problem
**DATE:** 23.9.2025  
**REGISTER NUMBER:** 212222060255 

## AIM:
To find the sequence of plan for Block word problem using PDDL

## Algorithm:
Step 1 : Start the program  
Step 2 : Create a domain for Block world Problem  
Step 3 : Create a domain by specifying predicates clear, on table, on, arm-empty, holding  
Step 4 : Specify the actions pickup, putdown, stack and un-stack in Block world problem  
Step 5 : In pickup action, Robot arm pick the block on table. Precondition is Block is on table and no other block on specified block and arm-hand empty  
Step 6 : In putdown action, Robot arm place the block on table. Precondition is robot-arm holding the block  
Step 7 : In un-stack action, Robot arm pick the block on some block. Precondition is Block is on another block and no other block on specified block and arm-hand empty  
Step 8 : In stack action, Robot arm place the block on under block. Precondition is Block holded by robot arm and no other block on under block  
Step 9 : Define a problem for block world problem  
Step 10 : Obtain the plan for given problem  

---

## Program:

### domain.pddl
```pddl
(define (domain blocksworld) 
(:requirements :strips :equality) 
(:predicates (clear ?x) 
 (on-table ?x) 
 (arm-empty) 
 (holding ?x) 
 (on ?x ?y)) 

(:action pickup 
 :parameters (?ob) 
 :precondition (and (clear ?ob) (on-table ?ob) (arm-empty)) 
 :effect (and (holding ?ob) (not (clear ?ob)) (not (on-table ?ob)) 
 (not (arm-empty)))) 

(:action putdown 
 :parameters (?ob) 
 :precondition (and (holding ?ob)) 
 :effect (and (clear ?ob) (arm-empty) (on-table ?ob) 
 (not (holding ?ob)))) 

(:action stack 
 :parameters (?ob ?underob) 
 :precondition (and (clear ?underob) (holding ?ob)) 
 :effect (and (arm-empty) (clear ?ob) (on ?ob ?underob) 
 (not (clear ?underob)) (not (holding ?ob)))) 

(:action unstack 
 :parameters (?ob ?underob) 
 :precondition (and (on ?ob ?underob) (clear ?ob) (arm-empty)) 
 :effect (and (holding ?ob) (clear ?underob) 
 (not (on ?ob ?underob)) (not (clear ?ob)) (not (arm-empty)))))
 ```
 
## Input

### Problem 1: `Problem.pddl`
```pddl
(define (problem pb1) 
 (:domain blocksworld) 
 (:objects a b) 
 (:init (on-table a) (on-table b) (clear a) (clear b) (arm-empty)) 
 (:goal (and (on a b))))
```
### Problem 2: `Problem1.pddl`
```
(define (problem pb3) 
 (:domain blocksworld) 
 (:objects a b c) 
 (:init (on-table a) (on-table b) (on-table c) 
        (clear a) (clear b) (clear c) (arm-empty)) 
 (:goal (and (on a b) (on b c))))

```
## Output/Plan:
# Problem 1:

<img width="400" height="669" alt="image" src="https://github.com/user-attachments/assets/96c379e9-fa20-43d1-abe3-424e19722d0f" />
<img width="447" height="685" alt="image" src="https://github.com/user-attachments/assets/f6fd3ac2-2285-48fd-9e40-503d0c3377c2" />

## Result:
Thus the plan was found for the initial and goal state of block world problem.
