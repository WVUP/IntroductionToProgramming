# Appendix III: Scanner

Up until this point we’ve only been able to provide information to the end user through the terminal by using the System.out class. Now, we can use the Scanner class to incorporate the end user’s input into our application.


# Declaration and Initialization
In order to utilize components of the Scanner class, we need to first import it. This statement will need to be added at the top of the class you want to use it in outside of the class definition.

```java
 import java.util.Scanner;
 
 public class SystemManagement
 {
	...
 }
```

This will allow you to incorporate public methods declared in the Scanner class without having to explicitly call it each time you use a method. We’ll have examples of both explicit and implicit calls in the following code segments.

Next, like any other class we want to use, we need to declare a variable of the Scanner class. 

```java
 private Scanner readerA; //implicit call
 private java.util.Scanner readerB; //explicit call
```

When you initialize the Scanner variable, you need to provide what the Scanner instance is "watching". In our case, since we want to use the terminal for end user input, we want to pass System.in as the parameter value. This class is in charge of all things related to terminal input. 

```java
 readerA  = new Scanner(System.in); //implicit call
 readerB = new java.util.Scanner(System.in); //explicit call
```


# Usage
Now that we have our Scanner variable declared and initialized, we can use any of its publicly declared methods. For this section we will focus on *nextInt()* and *nextLine()*. Other methods and their functionality are defined in the [Scanner class documentation](https://docs.oracle.com/en/java/javase/22/docs/api/java.base/java/util/Scanner.html).


## nextInt()
The *nextInt()* method allows you to read the user’s input as an integer as long as what is provided is in the correct format. Letters, symbols, and decimal points are not permitted and will throw an InputMismatchException.

Generally, whenever you’re using a scanner, you’re going to first print to the terminal what the user needs to provide. You’re prompting them for the information that is relevant to the application’s current process. 

```java
 System.out.println("Please provide the number of students enrolled in the course: ");
 ```

Next, use the Scanner variable reader to make an external call to the *nextInt()* method. The integer that is returned by this method will be stored in the local variable *nbrOfStudents*. Since we have already declared and initialized the Scanner variables, we’re able to use implicit method calls. Because of this, we will only use the readerA variable for the remainder of this section’s examples.

```java
 System.out.println("Please provide the number of students enrolled in the course: ");
 
 int nbrOfStudents = readerA.nextInt();
 reader.nextLine();

 System.out.println(nbrOfStudents + " students enrolled in the course");
```

When line 3 is reached, the application will pause temporarily and will idle at the terminal screen. It’s waiting for a user to type in their response. 

<figure><figcaption>Console Output:</figcaption><pre>
Please provide the number of students enrolled in the course:
<strong>></strong>
</pre></figure>



As soon as the end user provides their answer and hits ‘enter’, the *nextInt()* method will execute. It will pull the integer from the terminal and assign it to the *nbrOfStudents* variable. However, the ‘enter’ keypress used in the input statement is left behind. The use of *nextLine()* on line 4 will consume that keypress so it will not be included in the next end user input. The remainder of the code will be executed afterwards.

<figure><figcaption>Console Output:</figcaption><pre>
Please provide the number of students enrolled in the course:
<strong>> 18</strong>
18 students enrolled in the course
</pre></figure>


## nextLine()
Instead of bringing in a single value, the *nextLine()* method will bring in all input from the user as a String value. Examples of this multiple word response would be the student’s combined first and last name, the title of a course, or adding a course description.

```java
 System.out.println("Please provide the name of the course: ");
 
 String courseName = readerA.nextLine();

 System.out.println("Course name: " + courseName);
```

When the above code is executed, it will idle again on line 3 waiting for the end user’s response.

<figure><figcaption>Console Output:</figcaption><pre>
Please provide the name of the course:
<strong>></strong>
</pre></figure>


When the user submits the prompted information, the remainder of the code is executed.

<figure><figcaption>Console Output:</figcaption><pre>
Please provide the name of the course:
<strong>> Introduction to Programming</strong>
Course name: Introduction to Programming
</pre></figure>

You can also use this method if you want the user to provide commands. This, in combination with `do-while` loops, allows you to capture incorrect input and prompt the user for the correct input without risking application crashes.


```java
 boolean validAnswer = false;

 do
 {
	System.out.println("Please use one of the following commands:");
	System.out.println("ADD - Add course");
	System.out.println("UPDATE - Update course");
	System.out.println("QUIT - Exit application");

	String userResponse = readerA.nextLine();

	switch(userResponse.toUpperCase())
	{
		case "ADD":
			validAnswer = true;
			addNewCourse();
			break;
		case "UPDATE":
			validAnswer = true;
			modifyCourse();
			break;
		case "QUIT":
			System.exit(0);
			break;
		default:
			System.out.println("That is not a valid command\n");
			break;
	}
 }
 while(validAnswer == false)
```


# Summary
The Scanner class allows you to create a more interactive console-based application. You can write applications that incorporate information that is meaningful to them instead of hard-coding data for them.
