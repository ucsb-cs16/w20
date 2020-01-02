---
annotatedpdfurl: /lectures/CS16_Lecture3_ann.pdf
annotatedready: true
desc: Repetition with loops 
lecture_date: 2020-01-14
num: Lecture 3
slides: /lectures/CS16_Lecture3.pdf
ready: true

---

# Control Structures: Loops

## `while` loop

A while loop is used to repeat code while some condition is true.
```c++
	while(BOOLEAN_EXPRESSION) {
		// Code to run when the BOOLEAN_EXPRESSION is true.
	}
```

Check if the BOOLEAN_EXPRESSION is true.
* If true, the statements inside the loop's block will execute.
* at the end of the loop block, go back to `while`.
* If false, the statements in the loop will not execute.
* the program execution after the loop continues.

Example usage: say we want users to enter a non-negative number.
Use a while loop, so that users must keep entering values until the boolean statement is satisfied
```c++
    while(num < 0) {
    	//keep asking user, taking in input
    }
```

## Example

```
int i = 0;
while (i < 10)
	cout << "i = " << i << endl;
	// add i++ afterwards to eliminate an infinite loop.
	// i++ → i = i + 1;
	// Remember to enclose this statement with { }
```

* Note that a single statement after a while loop (similar to an if statement) is considered part of the loop without the { }.
	* If more than one statement is part of the loop, this must be contained within the { }


The boolean statement is checked first, and the body is skipped if the requirements are met.
Once the bool statement (`num < 0`) is no longer true, i.e., the user provided a non-negative number, the loop will stop.


The `while` loop has two flavors: a usual `while` that we looked at above, and `do-while` loop, which is used when the body of the loop needs to be executed **at least once**.

## `do-while` loops

A `while` loop is used to repeat code until some condition is no longer true

```c++
	do {
		// Code
		// This code is executed once
		// and is executed again if the BOOLEAN_EXPRESSION below is true
	} while(BOOLEAN_EXPRESSION);
```

1. Execute the code in the loop
2. Check if BOOLEAN_EXPRESSION is true.
* If true, then go back to 1.
* If false, then exit the loop and resume program execution.

Note: You must have a semicolon (`;`) after the `while` statement, if you are using a `do-while` loop (no semicolon if it is just a `while`).

In all loops, remember to **update the variable controlling the loop each time** (examined in bool test), otherwise an infinite loop will occur.
After any while loop, we know that the variable being examined meets a particular condition (e.g., `num >= 0`), otherwise, we would not have exited the loop.

## Example

```
int i = 0;
do {
	cout << "i = " << i << endl;
	i++;
} while (i < 0);
```

* Outputs "i = 0" once regardless of what the BOOLEAN_EXPRESSION evaluates to.
* Change to `while (i < 10)` to print "i = [0 - 9]".


## `for` loops

The `while` and `for` loops can be interchanged, but some formats are more convenient than others in different situations.

The `for` loop is used to repeat code (usually a fixed number of times).

```c++
	for (INITIALIZATION; BOOLEAN_EXPRESSION; UPDATE) {
		// Code to run when the BOOLEAN_EXPRESSION is true.
	}
```

1. Execute the INITIALIZATION statement.
2. Check if the BOOLEAN_EXPRESSION is true.
* if true, execute code in the loop.
* THEN execute UPDATE statement.
* Go back to the BOOLEAN_EXPRESSION.
* if false, do not execute code in the loop.
* exit the loop and resume program execution.

## Example

```
for (int i = 0; i < 10; i++) {
	cout << “i = “ << i << endl;
}
```

## Nested Loops

Other loops within a loop can be defined.

## Example

```
for (int i = 0; i < 5; i++) {
	cout << “—“ << endl;
	cout << “i = “ << i << endl;
	for (int j = 0; j < 5; j++) {
		cout << “j = “ << j << endl;
	}
}
```



### Skipping and Terminating Loop Execution

`continue`
* Once a `continue` line is reached, go back to the top of the loop immediately

`break`
* Once a `break` line is reached, the program will _exit_ (break out of) the loop immediately

In both cases, the program ignores anything else in the block that comes after continue/break,
i.e., the rest of that block below the `continue`/`break` line is **not** executed

## Example

```
for (int i = 0; i < 10; i++) {
	if (i == 4)
		continue;
	if (i == 7)
		break;
	cout << “i = “ << i << endl;
}
```



# Formatting output to the terminal

* Several ways to do this.
* We can customize the `cout` function to display floating point numbers as follows:

```
cout.setf(ios::fixed);
cout.setf(ios::showpoint);
cout.precision(2); // prints two decimal spaces for floating point values.
```	

# Example: A number guessing game

```
#include <iostream>

using namespace std;

const int ANSWER = 42; // const values cannot be modified

int main(int argc, char *argv[]) {

	int input = 0;

	do {
		cout << "Guess a number between [0 - 100]: ";
		cin >> input;
		if (input == -1)
			break;
		if (input < ANSWER) {
			cout << "Too small" << endl;
			continue;
		}
		if (input > ANSWER) {
			cout << "Too big" << endl;
			continue;
		}
		if (input == ANSWER) {
			cout << "WINNER! ANSWER = " << ANSWER << endl;
			break;
		}
	} while (true);

	cout << "Thanks for playing!" << endl;
}
```


**Math Puzzle**
One of the powers of computing is being able to do a brute-force search for a solution to a problem. Trial and error works just fine for some problems. In fact, computers can be especially good at such problems. Consider this:

Horses cost $10, pigs cost $3, and rabbits are only $0.50. A farmer buys 100 animals for $100, How many of each animal did he buy?  

Write a program to do this.

Acknowledgements: Thanks to Richert Wang for the original version of these notes
