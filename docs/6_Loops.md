# Loops

Control structures are fundamental to programming, as they enable the efficient execution of code based on specific conditions. One of the most essential control structures is the looping structure, which allows for repetitive execution of tasks based on defined parameters. Loops are highly versatile, offering the flexibility needed to adapt to various scenarios, from processing large datasets to maintaining an application until user termination.

In programming, there are several types of loops, each suited for specific use cases. This includes the while loop, which continues executing as long as a condition is met; the do-while loop, which guarantees that code runs at least once before checking the condition; and the for loop, which provides a more structured approach by combining initialization, condition-checking, and iteration in a single statement. Additionally, the for-each loop is ideal for iterating through collections of data with a predetermined end.

Loops also present challenges, such as the risk of infinite loops, where the condition never becomes false, causing the program to run indefinitely. Properly managing loop conditions and using keywords like break and continue can help control the flow of loops, allowing for early termination or skipping over iterations as needed.

## Learning Objectives

- Demonstrate how looping structures work within an application.
- Implement determinate looping structure: for-each.
- Implement indeterminate looping structures: for, while, and do-while.
- Explain how a looping structure could be applied to search for data.
- Understand how to leave indeterminate looping structures through conditions or return.

# Control Structures
The second control structure in programming is a looping structure. This allows you to repeat a series of tasks over and over again for a given amount of time. ***Loops*** give you the flexibility to adapt to the end user’s needs, whether it’s processing large data sets, or wanting to continue the execution of an application until the end user terminates it.

# while
A ***while*** loop is a looping structure that relies on a condition to determine whether or not to execute the code within the loop’s body. It’s an ***indeterminate loop***, meaning that it does not have a defined end point when it is created. The loop continues to run as long as a condition is met.

In the code segment below, we are repeating the same series of tasks over and over again. We are increasing the value of total then checking it to see if it meets a specified criteria.

```java
 int total = 0;

 if (total >= 2)
 {
  	System.out.println(“Does not meet the condition”);
 }
 else
 {
 	System.out.println(“Meets the condition”); 
 }
 total++;

 if (total >= 2)
 {
 	System.out.println(“Does not meet the condition”);
 }	
 else
 {
 	System.out.println(“Meets the condition”);
 }	
 
 total++;
 if (total >= 2)
 {
 	System.out.println(“Does not meet the condition”); 
 }
 else
 {
 	System.out.println(“Meets the condition”);
 }
 total++;
```

This is an inefficient way to handle this scenario. What we can do is isolate the repeated statements as shown below:

```java
 if (total >= 2)
 {
	System.out.println(“Does not meet the condition”);
 }
 else 
 {
	System.out.println(“Meets the condition”);
 }	
 total++;
```

Then, we can place it inside of a `while` loop. The structure of a `while` loop is similar in nature to how the first part of an if statement is set up. You provide a condition, and if that condition is met, the statements in the code block below are executed.

```java
 while (condition)
 {
	//tasks to repeat if condition is true
 }
```

Taking our original scenario, we can place our isolated statements in the `while` loop’s body.

```java
 int total = 0;

 while (condition)
 {
	if (total >= 2)
	{
		System.out.println(“Does not meet the condition”);
	}
	else
	{
 		System.out.println(“Meets the condition”);
 	}
 	total++;
 }
```


We can then update the `while` loop’s condition to repeat its tasks until the value of *total* equals 4.

```java
 int total = 0;

 while (total <= 4)
 {
	if (total >= 2)
	{
		System.out.println(“Does not meet the condition”);
	}
	else
	{
 		System.out.println(“Meets the condition”);
 	}
 	total++;
 }
```

Below is a chart of what the state of *total* is along with what the terminal output would be for each iteration of the loop.

<caption><strong>Table 6.1: total state table and associated output.</strong></caption>

| Value of total	| Terminal Output |
| ----- | -----|
| 0	| “Does not meet the condition” |
| 1	| “Does not meet the condition” |
| 2	| “Meets the condition” |
| 3	| “Meets the condition” |
| 4	| “Meets the condition” |


Once the value of *total* is 5, the `while` loop condition is no longer met, the statements within the brackets on line 4 and 14 are ignored, and the application continues its execution.

## Infinite Loop 
One thing that is bound to happen to every programmer is the accidental creation of an ***infinite loop***. This is something that is especially easy to do in `while` loops. Since the loop continues its process while a condition statement is true, you need to provide a way inside that loop to make it false. Otherwise, the loop will continue until the application is terminated.

Think of it this way. Imagine you’re on a roller coaster. In order to go around the track, you need to have tickets. For the first ride, you have 3 tickets in your hand. You meet the condition to go around the track. You get back to the station, you still meet the condition with the 3 tickets, and you go around again. And again. And again. Unless you give the station attendant a ticket either at the start of the ride, or at the end, you’ll continue to stay on that roller coaster. By giving away those tickets each time, you get to a point where you have none left. Then, the original condition of “you need tickets to ride the coaster” becomes false.

Looking at this from a syntax perspective, the code segment below is an example of an infinite loop.

```java
 int countdown = 5;

 while (countdown > 0)
 {
	System.out.println(“Hello World!”);
 }
```

There isn’t a statement within the `while` loop’s body that changes the *countdown* value. This is what’s causing the infinite loop to occur.

If we add a statement to line 6 that decrements the value of *countdown*, after “Hello World!” is printed to the terminal 5 times, the loop will end.

```java
 int countdown = 5;

 while (countdown > 0)
 {
	System.out.println(“Hello World!”);
	countdown--;
 }
```

When using loops that rely on a condition to function, make sure you have a way to get out of it.


# do-while
***do-while*** loops are similar to `while` loops. They both use conditional statements. However, `do-while` loops check the condition at the end of executing the loop’s tasks, not before.

Below is the structure of a `do-while` loop:

```java
 do
 {
	//tasks to repeat
 }
 while (condition);
```

How this will function is the tasks in the `do` block will execute. Then, the condition on line 5 will be checked. If the condition is true, it will repeat everything within the `do` block again. This process will repeat until the `while` condition is false.

This `do-while` structure is perfect when you are presenting an end user with options. You can provide them a menu to select from. If they select a valid option, the application proceeds to process their request. If they do not provide a valid answer, the `do-while` loop will display their menu options again and wait for a valid response. Below is an example of this setup:

```java
 boolean validOptionSelected = false;
 Scanner userInput = new Scanner(System.in);
 
 do
 {
 	System.out.println("Please select from the following options:");
 	System.out.println("1 - Add a new course");  
 	System.out.println("2 - Enroll a student");
 	System.out.println("3 - Exit Course Management System");

 	int userResponse = userInput.nextInt();

 	switch (userResponse)
 	{
 		case 1:
 			validOptionSelected = true;
 			createNewCourse();
 			break;
 		case 2:
 			validOptionSelected = true;
 			enrollStudent();
 			break;
 		case 3:
 			validOptionSelected = true;
 			System.exit(0);
 			break;
 		default:
 			System.out.println("That is not a valid menu option.");
 	}            
 }
 while (validOptionSelected == false);
```

When this code segment runs, the user option menu is displayed in the terminal.

<caption><strong>Console Output:</strong></caption>

```
 Please select from the following options:
 1 - Add a new course
 2 - Enroll a student
 3 - Exit Course Management System
```

The application then waits for a response from the end user. In this scenario, the end user provides the value 5.

<caption><strong>Console Output:</strong></caption>

```
 Please select from the following options:
 1 - Add a new course
 2 - Enroll a student
 3 - Exit Course Management System
 5
```

The provided value does not match any of the cases listed. The default case is triggered displaying the terminal message from line 28. 

<caption><strong>Console Output:</strong></caption>

```
 Please select from the following options:
 1 - Add a new course
 2 - Enroll a student
 3 - Exit Course Management System
 5
 That is not a valid menu option.
```

The *validOptionSelected* variable remains false, thus matching the condition statement on line 31. The loop is then executed again starting on line 6.

<caption><strong>Console Output:</strong></caption>

```
 Please select from the following options:
 1 - Add a new course
 2 - Enroll a student
 3 - Exit Course Management System
 5
 That is not a valid menu option.
 Please select from the following options:
 1 - Add a new course
 2 - Enroll a student
 3 - Exit Course Management System
```

`do-while` loops are a great alternative to `while` loops when you want to execute a task at least once before evaluating a condition.


# for
A `for` loop has the benefit of combining three loop specific statements into one header. It has a condition-based loop similar to a `while` loop. Unlike a `while` loop that relies on the programmer to remember to put in a ***post-loop action*** in the body of the loop, `for` loops have the post-loop action built into the loop header. 

The `for` loop’s header is composed of three parts: a local variable declaration, a condition, and a post-loop action. 

```java
 for (local variable; condition; post-loop action)
 {
	// tasks to repeat
 }
```

Typically, the local variable is a type of counter. The condition then uses that counter to keep track of how many times the loop needs to run. Then, the post-loop action increases or decreases the counter at the end of every loop. 

Below is the `while` loop that we used earlier in the module. Lines 1, 3, and 13 have comments showing each of the important components used in a `for` loop.

```java
 int total = 0; //This is your local variable

 while (total <= 4) //This is your condition
 {
	if (total >= 2)
	{
		System.out.println(“Does not meet the condition”);
	}
	else
	{
 		System.out.println(“Meets the condition”);
 	}
 	total++; //This is your post-loop action
 }
```

We are able to reorganize these components into a `for` loop and be able to achieve the same end result. 

```java
 for (int total = 0; total <= 4; total++)
 {
 	if (total >= 2)
 	{
 		System.out.println(“Does not meet the condition”);
 	}
 	else
	{
 		System.out.println(“Meets the condition”);
 	}
 }
```

For the first iteration, the local variable *total* is created and assigned the value 0. This portion of the `for` loop header is only executed once. *total* is then used in the condition evaluation. The condition result is true, therefore, lines 3 through 10 are processed. When the code reaches the end of the loop, the value held in *total* will be incremented. The next loop begins on line 1 again this time starting with the condition statement. 

The end result will be identical to that of the original `while` loop shown in Table 6.1.


# For-each
***For-each*** loops are classified as a ***determinate loop***, meaning that the loop has a defined end based on the data it’s processing. If a collection contains five items, the loop will execute five times processing each element as it reaches it.

The structure of a for-each loop is shown below. 

```java
 for (dataType singleElement : collection)
 {
	//Tasks to repeat
 }
```

If we were to create an array of names, we can use a for-each loop to display them to the terminal. In the for-each loop header below, you can read this as “For each individual student in the course roster”. 

```java
 String[] roster = new String[] {“John”, “Katie”, “Parker”, “Ayden”};

 for (String studentName : roster)
 {
	System.out.println(studentName.toUpperCase());
 }
```

The first time this loop executes it will check to see if an item exists in the array. It sees that there is something available and grabs the first name out of *roster*, “John”. The name is converted to upper case and displayed in the terminal. At the start of the next loop, it checks to see if there is an item next in line. There is, and it prints “Katie” in all caps. This process repeats until there is nothing left for the loop header to grab from the array. Table 6.2 shows what iteration the for-each structure is on, what item is being processed, and what output would be shown in the terminal.


<caption><strong>Table 6.2: total state table and associated output.</strong></caption>

| Iteration	| Item in List Being Processed	| Terminal Output |
| ----- | ----- | ----- |
| 1	| “John”	| “JOHN” |
| 2	| “Katie”	| “KATIE” |
| 3	| “Parker”	| “PARKER” |
| 4	| “Ayden”	| “AYDEN” |
| 5	| Nothing remains in the collection. Loop concludes and continues on with the rest of the application. | |


If you need to process everything in a collection, for-each loops work well. However, since for-each loops are created to process a collection from start to finish, use caution when implementing them for searching functionality. If you are searching for a unique instance of something, there is no reason to continue to search for it once you’ve found it.


# break and continue
The keywords ***break*** and ***continue*** allow you to modify how a loop functions and what is allowed to be processed. They give you a way to leave or skip over an iteration, respectively.

## break
Not only can `break` be used to get out of `switch` statements, it can be used to get out of loops. When the `break` keyword is reached in a loop, the loop stops and ignores everything else that needs to be processed.

Take the code segment below. We have an array of four names, and the for-each loop is pulling each name from the array and printing it to the terminal.

```java
 String[] names = new String[]{"John", "Katie", "Parker", "Ayden"};

 for(String name : names)
 {
	System.out.println(name);
 }
```

<caption><strong>Console Output:</strong></caption>

```
 John
 Katie
 Parker
 Ayden
```

Let’s alter this and say that we want to stop processing data in the names array once we come across the name “Parker”. We’ll add an `if` statement within the for-each loop that compares the current value pulled from the array to the String “Parker”. If it is a match, then we’ll use the `break` keyword. 

```java
 String[] names = new String[]{"John", "Katie", "Parker", "Ayden"};

 for(String name : names)
 {
 	if(names[index].equals("Parker"))
 	{
 		break;
 	}
 	
		System.out.println(name);
 }
```

When we run this method, the names “John” and “Katie” are retrieved from the array and used for comparison in the condition statement, which evaluates to false. The names are then printed to the terminal. When the name “Parker” is retrieved from the array and compared in the condition statement, the name is a match and the `break` keyword is executed. The for-each loop stops and continues with the rest of the application. It does not print the name “Parker” to the terminal, and the last name “Ayden” is not processed at all. The resulting output is shown below.

<caption><strong>Console Output:</strong></caption>

```
 John
 Katie
```

## continue
If you want to skip over one iteration and process the remaining data set, use `continue`. Below is the same code from the previous example, but this time we are swapping out the `break` keyword for `continue`. The names “John” and “Katie” are processed the same way as before. When the name “Parker” is reached and the `continue` keyword is executed, the for-each loop stops its current iteration and moves on to the next name in the array. “Ayden” is retrieved, evaluated, then printed to the terminal.

```java
 String[] names = new String[]{"John", "Katie", "Parker", "Ayden"};

 for(String name : names)
 {
 	if(names[index].equals("Parker"))
 	{
 		break;
 	}
 	
	System.out.println(name);
 }
```

<caption><strong>Console Output:</strong></caption>

```
 John
 Katie
 Ayden 
```

# Searching
One of the more common uses of loops in entry-level applications is iterating through data to find something. `while` loops are fantastic for this type of functionality. Since it is controlled by a condition statement, it gives you an easy way to leave your looping structure once you’ve found what you’re looking for.

Imaging you’re in a room with cabinets lining the walls. You have been asked to find a red coffee mug. How you would accomplish this task is to open up each cabinet, look at the contents inside it, and if you find the red coffee mug, you finish your search.

In this process you are looking through a collection of cabinets. You open only one of them at a time, and compare the contents to a predefined item description. If you do not find what you’re looking for, you repeat the same process for the next cabinet. Below is the pseudocode, or simplified syntax, of this.

```
 while (object has not been found)
 {
 	if(object in cabinet matches the “red coffee mug” description)
 	{
  		End my search
 	}
 	else 
  	{
 		continue my search
 	}
 }
```

If we wanted to do this for a student roster, where we want to look at each name to see if they are the person we are looking for, we would use a similar format.


```java
 boolean studentFound = false;
 String[] roster = new String[] {“John”, “Katie”, “Parker”, “Ayden”};
 int index = 0;

 while (studentFound != true)
 {
 	if(index < roster.length)
 	{
		if(roster[index].equals(“Parker”))
 		{
 			studentFound = true;
  			System.out.println(“Student has been found”);
 		}
	}
 	else if(index == roster.length)
 	{
 		break;
 	}
 
 	index++;
 }
 
 if (studentFound == false)
 {
 	System.out.println(“Student has not been found”);
 }
```

This loop uses a boolean value, often called a flag, that is being used to denote whether or not an item has been found. The loop also uses a counter variable called *index* that keeps track of what index we’re looking at in the roster array. The `while` loop condition checks the *studentFound* boolean flag. If the student has not been found, the application proceeds with the comparison statements. If the value of *index* is a valid index for the roster array, we’ll pull that value from the array at that index. We’ll then compare it to the name we’re looking for, “Parker”.  If it is a match, we’ll flip the value of the flag, stating that the student has been found, and notify the end user. If it was not a match, the *index* value is incremented, and the loop starts again on line 5. Once we increase the *index* variable to be the same as the array’s length, meaning we have no more valid indices left to use, we’ll use the `break` keyword to leave the `while` loop. Otherwise, we’ll end up with an infinite loop. If the student was never found, we’ll execute the contents of the if statement on line 25. Table 6.3 shows the state changes of the *index*, *roster*, and *studentFound* variables throughout the search function.


<caption><strong>Table 6.3: State table for student search.</strong></caption>

| Value of index	| Name Pulled From roster Array	| End Result of Inner if Statement Condition (Line 9)	| Value of studentFound| 
| ----- | ----- | ----- | ----- |
| 0	| “John”	| false	| false| 
| 1	| “Katie”	| false	| false| 
| 2	| “Parker”	| true	| true| 
| 3	| while loop does not continue. Condition is not met. if statement  outside of the while loop on line 23 does not execute as well since the student has been found.| | | 




# Summary

**Looping structures:** Allows repetitive execution of tasks.

**while Loop:** Executes as long as a condition is true, but can lead to infinite loops if the condition isn't properly managed.

**do-while Loop:** Similar to a `while` loop but guarantees that the code runs at least once before checking the condition.

**for Loop:** Combines initialization, condition-checking, and iteration in one statement, often used for scenarios where the number of iterations is known.

**For-Each Loop:** Used to iterate through collections like lists, performing actions on each element.

**break:** Modifies loop behavior by exiting a loop early.

**continue:** Modifies loop behavior by skipping an iteration.


# Key Terms

- break	
- continue	
- Determinate Loop	
- do-while	
- for
- for-each
- Indeterminate Loop	
- Infinite Loop	
- Loops	
- Post-Loop Action	
- while


# Review Questions
1.	What is a looping structure in programming, and why is it useful?
2.	Explain the concept of an infinite loop and how it can occur in a `while` loop.
3.	Can infinite loops only occur in `while` loops? If not, in what other structures can it occur and give an example of how it can occur in those structures.
4.	What is the key difference between a `while` loop and a `do-while` loop? Give an example of each.
5.	Describe the three components of a `for` loop header and their roles. Give an example of its use.
6.	What is the primary advantage of using a for-each loop over other looping structures? Give an example.
7.	How does the `break` keyword affect the execution of loops? Provide an example scenario where it would be useful.
8.	What does the `continue` keyword do within a loop? How does it differ from `break`?
9.	Why should caution be used when implementing for-each loops for search operations?
10.	In what scenarios would you prefer a `while` loop over a `for` loop, and vice versa?
