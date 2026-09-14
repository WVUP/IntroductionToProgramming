# Appendix IV: Enumerated Types

***Enumerated types***, or enums, are a specialized class responsible for defining a set of constant values. These are typically used for restricting what values can be set for a defined variable. The values allowed are usually ones that are not likely to be changed on a regular basis. Examples of this would include the days of week, the months in the year, and cardinal directions. Other examples would include locations for a manufacturing company or marketing regions.


# Enumerated Type Creation
To create an enumerated type, we will create a new class. This time, instead of using the keyword class in the definition, we will use the keyword enum.

```java
 public enum Major
 {
	...
 }
```

While you can add this declaration within another class file, creating it as a separate entity will allow you to use it independently of a class.

Inside of this enum class we will state what our constant values will be. The naming convention for enum values are in all caps, similar to constant variable names. For this example, we will add a few college majors and an "undecided" option for brand new students.

```java
 public enum Major
 {
	ACCOUNTING, COMPSCI, NURSING, UNDECIDED
 }
```

One thing to notice with this declaration is that the values do not end with a semicolon. Since we are only listing the possible values that the Major enumerated type can hold, the semicolon is optional. However, it is good practice to use a semicolon after this statement.


## Declaring and Using an Enumerated Type in Other Classes

The enum that we created, Major, can be used as a data type. If we wanted to use it in the Student class, we’ll declare the variable, *studentMajor*, as a Major data type along with the student’s first and last name.

```java
 public class Student
 {
	private String firstName;
	private String lastName;
	private Major studentMajor; //Enum as a data type
 }
```

Next, we will include it in the Student constructor. When you use an enum in any statement outside of the enum class, you need to use the enum name and one of the constant values you’ve created. In our case, we will set every student with an "undecided" major.

```java
 public Student(String firstName, String lastName)
 {
	this.firstName = firstName;
	this.lastName = lastName;
	this.studentMajor = Major.UNDECIDED; //Assigning an enum value
 }
```

Using enums as a return type and a parameter is no different than any other data type.

```java
 public Major getMajor() //Enum as a return type
 {
	return studentMajor;
 }

 public void setMajor(Major newMajor) //Enum as a parameter type
 {
	this.studentMajor = newMajor;
 }
```

The one caveat to this is what you need to pass in as the parameter value. If you were to update the student’s major to Computer Science, you would pass in the enumerated type and its constant value, COMPSCI. The reason why you would use the enum.value format is to tell the compiler what the COMPSCI value belongs to.

```java
 setMajor(Major.COMPSCI);
```

Enums can also be used in condition statements. Below is a method that prints a statement to the terminal based on the student’s major. Again, just like with assignment statements, you’ll need to state what enum you are using along with the constant value you want to use.
    
```java
 public void majorChoiceFeedback()
 {
    if (studentMajor == Major.UNDECIDED)
    {
        System.out.println("We have several majors to choose from.");
    }
    else if (studentMajor == Major.COMPSCI)
    {
        System.out.println("Excellent choice!");
    }
    else if (studentMajor == Major.ACCOUNTING)
    {
        System.out.println("CPAs are always needed!");
    }
    else if (studentMajor == Major.NURSING)
    {
        System.out.println("Thank you for caring about others!");
    }
 }
```

Below is the same example written as a switch statement. This type of structure would be useful if you were to use enums as user commands in a console-based application.

```java
 public void majorChoiceFeedback()
 {
 	switch(studentMajor)
    {
        case Major.UNDECIDED:
            System.out.println("We have several majors to choose from.");
            break;
        case Major.COMPSCI:
            System.out.println("Excellent choice!");
            break;
        case Major.ACCOUNTING:
            System.out.println("CPAs are always needed!");
            break;
        case Major.NURSING:
            System.out.println("Thank you for caring about others!");
            break;
    }
 }
```

# Expanded Enumerated Type

You can also give each of your enumerated values additional pieces of data associated with it. For example, if I wanted to add a course designation for each of the majors, I can add a String field within the enum class to assign it to.

Using the same enum class as before, we are going to set up our designation field. To start with, we are going to add our new field *courseInitials*. Then, we will add the new values to our existing enums. Once we start adding additional values to our enums we must end the enum declaration with a semicolon as shown on line 3.

```java
 public enum Major
 {
	ACCOUNTING("acct"), COMPSCI("cs"), NURSING("nurs"), UNDECIDED("???");

	private String courseInitials;
 }
```

Next, we need to add a constructor to the enumerated class. This constructor will have a single parameter that brings in a String (lines 7-10). The constructor does not have a visibility modifier with it, but for enumerated classes, the visibility is assumed to be private.

```java
 public enum Major
 {
    ACCOUNTING("acct"), COMPSCI("cs"), NURSING("nurs"), UNDECIDED("???");

    private String courseInitials;

    Major(String courseInitials)
    {
        this.courseInitials = courseInitials;
    }
 }
```


The modifications that we made on line 3 are calling the Major enum constructor. When the enums are created, the attached String is added as that enum’s *courseInitials*. When the ACCOUNTING enum is created, its *courseInitials* field is assigned "acct".

We can also create a *toString()* method that returns the String value of *courseInitials* (lines 12-15).

```java
 public enum Major
 {
    ACCOUNTING("acct"), COMPSCI("cs"), NURSING("nurs"), UNDECIDED("???");

    private String courseInitials;

    Major(String courseInitials)
    {
        this.courseInitials = courseInitials;
    }

    public String toString()
    {
        return courseInitials;
    }
 }
```


# Summary
Enumerated types define a set of fixed constants. They function as data types in your classes, making enums versatile for structuring and organizing fixed data in applications.
