# [Simple Elevator](https://www.codewars.com/kata/simple-elevator)

Write a function that mimics the behavior of a safe elevator.  It will travel from where it is, to the floor for the button pressed _if_ the button is valid.

simple_elevator : Function
* Args: 2
  1. _Number_: the floor the elevator is on - (0 <= floor <= 3)
  2. _String_: the floor the elevator should go to - ["0","1","2","3"]
* Return: _Number_ --> -3 <= n <= 3
  * Return value indicates how many floors the elevator has traveled
* Behavior: This function will move from it's starting location to it's finishing location, returning the number of floors moved. It is a safe elevator. In case any argument is invalid, it will stay in place to avoid injuring the occupants.

'''js
// copy of your polished solution for easy reference.
'''


### Index
* [Input Analysis](#input-analysis)
* [Solution Explanation](#solution-explanation)
* [Constraints](#constraints)
* [Resource Estimation](#resource-estimation)
* [Scaffolding](#scaffolding)
* [Language Features](#language-features)
* [Bugs & Challenges](#bugs-challenges) 
* [Use Cases](#use-cases)
* [Learning Journal](#learning-journal)

---

## Input Analysis

What can we measure, analyze or do to incoming args:
* Types of arguments
  * If it's string, is it empty
  * Do math to them if they're numbers
  * Convert types
  * Range of number (<, >, ==, ...)
    * Exclude or include accordingly
* Compare to known valid inputs

Classifications:
* Validity & Invalidity
  * Valid floor, invalid button
  * ... all 4 combinations
* Floor is higher than button
* Floor is lower than button
* Floor is same as button
* Button is a string, but not in the list
* Floor is a number, but is not in the range
* Floor is a number, but has a decimal 
  * Decimal is 0
  * Decimal is not 0
* No second argument is passed in
* More than two args are passed in
* Number starts with too many 0's
* (noticed this one after failing tests):
  * Inputs whose difference is a valid output, but are not valid themselves.


I wrote a case or two for each bullet point.  In writing my tests I noticed the "floor is not a number" case was incomplete and added two sub-cases.

[TOP](#index)

___

## Solution Explanation


Since there are very few allowable inputs, we'll just do an exhaustive check to see if the arguments are valid.  Then we'll do the subtraction if they are.



[TOP](#index)

---

## Constraints

We will solve it twice:
1. With a pure function, unconstrained
2. With an object. 
  * Testing will be trickier
  * The specs will change

[TOP](#index)

___


## Resource Estimation

didn't do this 


[TOP](#index)

___

## Scaffolding

[Scaffolding Gist](https://gist.github.com/colevandersWands/db24816532b371c27abe682380f5dca2)

We had a heated discussion about the use of '==' & '===' for comparing numbers to the similar string (ie. 4 & "4").  

We defaulted our return value to 0.

[TOP](#index)

___


## Language Features

Nothing fancy.  If's, for's, '===' and a Number conversion.


[TOP](#index)

---

## Challenges & Bugs

What particular challenges & bugs did you come across when you were filling in your scaffolding?

Were they logic bugs? Language bugs? 

Did you have trouble keeping track of which part of the challenge you were solving?

[TOP](#index)

___

## Use Cases

List 5+ use cases for your solution.  They can be stand-alone, part of an application, or impractical.  Your use cases can be overly complicated, or very basic. What's important is that you come up with as many and as diverse use cases as possible.


[TOP](#index)

---

## Learning Journal

Things I learned studying this problem:
* !! we failed the test case s_e(6, "3") !!  
  * This showed us that our strategy is bad, we will accept many arguments that return a valid output but are invalid inputs.
  * This class of arguments: any numbers such that (floor - button = valid output), but floor or button are invalid inputs.


New vocabulary:


Things I struggled with:


Lessons to apply for next time:



[TOP](#index)

___
___
### <a href="http://elewa.education/blog" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/34921062-506450ae-f97d-11e7-875f-6feeb26ad72d.png" width="100" height="40"/></a>

