# Ex.No: 12  Planning –  Monkey Banana Problem
### DATE:  22.4.25                                                                          
### REGISTER NUMBER : 212222040171
### AIM: 
To find the sequence of plan for Monkey Banana problem using PDDL Editor.
###  Algorithm:
Step 1:  Start the program <br> 
Step 2 : Create a domain for Monkey Banana Problem. <br> 
Step 3:  Create a domain by specifying predicates. <br> 
Step 4: Specify the actions GOTO, CLIMB, PUSH-BOX, GET-KNIFE, GRAB-BANANAS in Monkey Banana problem.<br>  
Step 5:   Define a problem for Monkey Banana problem.<br> 
Step 6:  Obtain the plan for given problem.<br> 
Step 7: Stop the program.<br> 
### Program:
```
(define (domain monkey-banana)
  (:requirements :strips :typing)
  (:types location object)

  (:predicates
    (at ?agent - object ?loc - location)
    (onbox)
    (hasbanana)
    (bananaat ?loc - location)
    (boxat ?loc - location)
    (monkeyat ?loc - location)
    (monkeyonbox)
  )

  (:action move
    :parameters (?from - location ?to - location)
    :precondition (monkeyat ?from)
    :effect (and
      (not (monkeyat ?from))
      (monkeyat ?to)
    )
  )

  (:action push
    :parameters (?from - location ?to - location)
    :precondition (and
      (monkeyat ?from)
      (boxat ?from)
    )
    :effect (and
      (not (monkeyat ?from))
      (not (boxat ?from))
      (monkeyat ?to)
      (boxat ?to)
    )
  )

  (:action climbup
    :parameters (?loc - location)
    :precondition (and
      (monkeyat ?loc)
      (boxat ?loc)
    )
    :effect (monkeyonbox)
  )

  (:action climbdown
    :parameters ()
    :precondition (monkeyonbox)
    :effect (not (monkeyonbox))
  )

  (:action grasp
    :parameters (?loc - location)
    :precondition (and
      (monkeyonbox)
      (bananaat ?loc)
      (boxat ?loc)
    )
    :effect (hasbanana)
  )
)

```

```
(define (problem monkey-banana-problem)
  (:domain monkey-banana)

  (:objects
    A B C - location
  )

  (:init
    (monkeyat A)
    (boxat B)
    (bananaat C)
  )

  (:goal (hasbanana))
)

```








### Input 

### Output/Plan:
![image](https://github.com/user-attachments/assets/f99ce161-24de-4e6e-87d7-970bd40396e3)
![image](https://github.com/user-attachments/assets/49506acd-27e3-4534-975f-18efd7534d6f)
![image](https://github.com/user-attachments/assets/61bd336d-58af-42d8-8412-59ca16aa862c)
![image](https://github.com/user-attachments/assets/71d8a97e-b7bb-4f2d-9d20-e071141ca7f7)





### Result:
Thus the plan was found for the initial and goal state of given problem.
