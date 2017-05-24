# CS 1632 - Software Quality Assurance
Summer Semester 2017 - Exercise 1

For this exercise, your group will determine a test plan for the simple simulator GoatGoatCar, based on the requirements listed.  There are several known defects in the software; you will need to find and report on at least two.  Additionally, a traceability matrix showing the mapping of test cases to requirements is required.  

There should be 10 test cases altogether.

Each requirement should have AT LEAST one test case associated with it, and each test should have EXACTLY ONE requirement associated with it.  This can easily be checked via a traceability matrix (which you should also deliver).  Note that some test cases may actually test several requirements.  You should specify the one that the test case fits best - that is, what are you really trying to test with this test case?

Test cases should mention all necessary preconditions, execution steps, and postconditions.

It is expected that you actually execute the test plan in order to find the defects, along with some exploratory testing to determine how the system works and where defects might lie.  There are AT LEAST three defects.  Full credit will be given only to those who properly find and describe at least three.  While you are not expected to find *all* of the defects, a reasonable test plan should definitely find at least two.  This is an intentionally target-rich environment.

You should EMAIL me the completed test plan.  This must be in to me by the next class, although I highly recommend you work on it in class.

You may ask me any questions on writing a test plan during class.

Remember the correct format for test cases -

```
	IDENTIFIER:
	TEST CASE: 
	PRECONDITIONS:
	EXECUTION STEPS:
	POSTCONDITIONS:
```

The IDENTIFIER is some value which will UNIQUELY specify the test case.  It can be a number, word or any other mnemonic (e.g. TEST-INVALID-TIMES, TEST-LOW-NUM-TIMES, etc.).

Remember the correct format for defects -

```
	 SUMMARY:
	 DESCRIPTION:
	 REPRODUCTION STEPS:
	 EXPECTED BEHAVIOR:
	 OBSERVED BEHAVIOR:
```

Other attributes of a defect (e.g., SEVERITY or IMPACT) are not necessary.  The test case which found the defect should be listed as part of the DESCRIPTION.

## Grading

```
Attendance - 0.5 point
Test cases - 1.0 point
Defects (2) - 0.5 point
Total: 2 points

You may get partial credit for any part except for attendance.
```

## GoatGoatCar
GoatGoatCar is going to be our way of determining the correct answer to the "Monty Hall Problem" (https://en.wikipedia.org/wiki/Monty_Hall_problem).  The Monty Hall Problem can be summarized as follows:

_Assume you are on a game show with three closed doors.  Behind one door is a car (which you want), and behind the other two doors are goats (which you do not want - if you do want a goat, I implore you to research how difficult goat tending is).  You pick one door, which you hope has the car behind it.  The game show host - who knows where the car is, and so will not open that door - opens up one of the two doors you did not select.  Behind that door is, of course, a goat._

_The question: is the optimal strategy to switch doors to the remaining closed door, to stay with the door you've already selected, or does it not matter?_

Our program will attempt to find the solution the worst possible way - by brute force.  It will simulate a large number of these decisions and give a summary at the end of what percentage of the time switching would give you the "good item" and what percentage of the time staying would have won you the "bad" item.

The program will accept four arguments, in this order:

* __"Good" option__ - This will be the item that the player actually wants (e.g., a car).

* __"Bad" option__ - This will be the item that the player does not want (e.g., a goat)

* __Num Times__ - This is the number of rounds that will be simulated.

* __Num Threads__ - This will be the number of threads that the simulation runs in

Example command to execute.  This will use "car" as the good choice, "goat" as the bad choice, 10001 as the number of rounds to simulate, and it will do it on four threads.

```
$ java -jar GoatGoatCar.jar car goat 10001 4
```

GoatGoatCar.jar is available in this directory.  

The requirements are listed in the file requirements.md in this directory.

