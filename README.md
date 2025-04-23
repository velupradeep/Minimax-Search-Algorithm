ExpNo 5 : Implement Simple Hill Climbing Algorithm
Name: PRADEEP V
Register Number: 212223240119
Aim:
Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration

Theory:
Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space. Feedback is provided in terms of heuristic function

Algorithm:

Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.
Loop until a solution is found or there are no new operators left to be applied in current state:
Select an operator that has not yet been applied to the current state and apply it to produce a new state
Evaluate the new state:
if it is a goal state, then return it and quit
if it is not a goal state but better than current state then make new state as current state
if it is not better than current state then continue in the loop
Steps Applied:
Step-1
Generate Random String of the length equal to the given String

Step-2
Mutate the randomized string each character at a time

Step-3
Evaluate the fitness function or Heuristic Function

Step-4:
Lopp Step -2 and Step-3 until we achieve the score to be Zero to achieve Global Minima.

PROGRAM:

import random
import string
def generate_random_solution(answer):
    l=len(answer)
    return [random.choice(string.printable) for _ in range(l)]
def evaluate(solution,answer):
    print(solution)
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        #to calculate the "difference" between two strings, character by character.
        #ord(s) - ord(t) calculates the difference between the ASCII values of the characters s and t.
         #abs() takes the absolute value of this difference to ensure that it is non-negative. This is important because the difference could be negative if s is less than t in terms of ASCII value.
         #The absolute value ensures that the difference is always positive or zero.
        diff += abs(ord(s) - ord(t))    return diff
def mutate_solution(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
def SimpleHillClimbing():
    answer="Artificial Intelligence"
    best=generate_random_solution(answer)
    best_score=evaluate(best,answer)
    while True:
       print("Score:", best_score, " Solution: ", "".join(best))  
       if best_score == 0:
           break
       new_solution = mutate_solution(list(best))
       score = evaluate(new_solution, answer)
       if score < best_score:
           best = new_solution
           best_score = score
SimpleHillClimbing()
Sample Input and Output
Sample String:
Artificial Intelligence
Output:
Score: 643 Solution : 8RzF:oG ]%;CPORRMe!zGvk
Score: 609 Solution : 8RzF:oG ]%;CPqRRMe!zGvk
Score: 604 Solution : 8RzF:oG ]%;CPqRRMe!zGqk
Score: 594 Solution : 8RzF:oG ]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
....................................................
..................................................
................................................
Score: 1 Solution : Artificial Intelligencf
Score: 1 Solution : Artificial Intelligencf
Score: 1 Solution : Artificial Intelligencf
Score: 1 Solution : Artificial Intelligencf
Score: 0 Solution : Artificial Intelligence
RESULT:
Thus the Simple Hill Climb Algorithm Implemented successfully.
