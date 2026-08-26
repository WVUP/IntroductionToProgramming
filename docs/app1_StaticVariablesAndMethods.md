# Appendix 1: Static Variables and Methods
Classes consist of fields and methods. When an instance of a class is created, that instance gets its own copy of those fields and methods. This means different instances of the same class will have the same fields, but they can have their own unique values. Take a Person class as an example. Assume it has three fields: a first name, a last name, and a birthday.

```java
 import java.util.date;
  
 public class Person
 {
 	private String firstName;
 	private String lastName;
 	private Date birthday;
  
  	// constructors, getters and setters, etc.
 }
 ```

If there were two different instances of Person, one for John Doe and one for Jane Doe, each instance would have their own value for each of the three fields. These two would have different values for *firstName*, different copies of the same value for *lastName*, and likely different values for the birthday field. If the *lastName* field of the Jane Doe instance was changed, say to Smith, it would not change the value stored in the John Doe instance’s *lastName* field. This concept is included in encapsulation, and it applies to methods as well.

Not everything is tied to an object instance. Static fields and methods are associated with the class itself rather than an instance of the class. This means they can be accessed without creating an instance of the class.


# Static Fields
Static fields, also known as class variables, are shared across all instances of a class, meaning there is one copy that all instances share. If one instance changes a static field, the new value is changed for all other instances as well.

Static fields are declared using the `static` keyword and are initialized only once. They need to be `public`, unlike instance fields. They are ideal for storing data that should be common to all instances, such as configuration settings, counters, or known constants. Static fields can be accessed using the class name, without the need for an object instance. One good example that already exists in Java is the value of pi (π), which is in the Math class.  This static field is declared in the Math class like this:

```java
 /**
 * The most accurate approximation to the mathematical constant pi:
 * 3.141592653589793. This is the ratio of a circle's diameter
 * to its circumference.
 */
 public static final double PI = 3.141592653589793; 
 ``` 

In this case the value is also declared as a constant because it never changes. Because of this, it makes sense to have one copy of the value that all math equations can share.  Static fields are a great solution to this situation. 

Accessing a static field is done using the class itself, instead of an instance variable.  Printing the value of π would look like this:

```java
 System.out.print(Math.PI);
```

This would print on the screen the value 3.141592653589793, which is what π is assigned in the class. This value can also be used in other equations where needed by referencing Math.PI instead of typing out the value over and over each time.

Initializing a static field is typically done when the field is declared, as shown above with Math.PI. This is the simplest and most straightforward approach. Remember, static fields exist at the class level so they cannot work with instance fields or instance methods.

Another approach for more complex initialization is to use a static initialization block. Think of this like a constructor, but only for static fields in a class. Complex logic using `if/else`, calculations, or calling other static methods can be used in this block. An example of this is shown below.

```java
 public class Course
 {
    public static final int MAX_SEATS_AVAILABLE;

    static
    {
        MAX_SEATS_AVAILABLE = 20;
    }
 }
```

# Static Methods
Static methods, like static fields, are methods that belong to the class rather than any instance. They are also declared using the `static` keyword, should be `public`, and are also called using the class name. Static methods can access static fields, but cannot access instance variables directly.

Static methods can be called without creating an instance of the class. For example, *Math.sqrt(4)* is a call to a static method of the Math class passing in a value of 4 in this case.  Static methods can only access static fields or method parameters directly and cannot use instance variables or methods unless they are passed as parameters.

Declaring a static method is like an instance method, but with the keyword `static` added.  Here is the definition of the *sqrt()* static method in the Math class for an example: 

```java
 /**
   * Take a square root. If the argument is NaN or negative, the
   * result is NaN; if the argument is positive infinity, the result
   * is positive infinity; and if the result is either zero, the 
   * result is the same. This is accurate within the limits of
	  * doubles.
   *
   * For a cube root, use cbrt. For other roots, use
   * pow(a, 1 / rootNumber).
   *
   * @param a the numeric argument
   * @return the square root of the argument
   * @see cbrt(double)
   * @see pow(double, double)
   */
  public static double sqrt(double a)
  {
     return VMMath.sqrt(a);
  }
```

Static methods, like *sqrt()* are often used for utility or helper functions that do not require any object state. Probably the most important static method though is the *main()* method in Java.  The *main()* method is static because it serves as the starting point of the application and needs to be callable without creating an instance of a class. It’s the classic Chicken or the Egg problem, how would you create an instance of a class to call *main()* without already being in an instance of another class! Declaring the *main()* method as static is a neat workaround to this conundrum. 




# Static Method Restrictions
Because static methods exist at the class level and not the instance level, they cannot use the `this` keyword since they are not associated with any instance. Also, they cannot directly access non-static fields or methods, although these may be passed as parameters when they are called. 


# Summary
Remember, static fields and methods are shared across all instances of a class. If you need to reference a single, consistent value, such as π, or if you want to create a method that does not rely on the contents of an instance, a static field or method may be the best approach. 
