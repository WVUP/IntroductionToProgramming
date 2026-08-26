# Yummy Bytes Bakery - Module 4 Assignment

Includes content from [Appendix I: Static Variables and Methods](../app1_StaticVariablesAndMethods.md).

> **NOTE:** This assignment is setting up the framework to utilize user input. The new methods in the YummyBytesBakery class will be partially complete, and this is ok. We will revisit these methods in later assignments.

## Cookie Class
1.	Update your setters to include data validation. No ingredient set should be a negative number, and every cookie should have a name.

## Muffin Class
1.	Update your setters to include data validation. No ingredient set should be a negative number, and every cookie should have a name.

##  Doughnut Class
1.	Update your setters to include data validation. No ingredient set should be a negative number, and every cookie should have a name.

## YummyBytesBakery Class
1.	Update the *register* instance variable and make it a static, class-level variable.

2.	Declare an instance for each of these classes: Cookie, Muffin, and Doughnut. Initialize these variables in the constructor using their respective default constructors.

3.	Create a new method called *testData()* that takes in no parameters and does not return anything. In here, place the following statements. These statements will create test data for you to use in your application. Call this method in your default constructor.

```java
 cookie = new Cookie(2.5, 0.75, 1.0, 0.0, 1.0, “Chocolate Chip”);
 muffin = new Muffin(3.0, 0.5, 1.0, 1.5, 3, 1.25, 1.0, “Blueberry”);
 doughnut = new Doughnut(2.0, 1, 2.5, 3, 1.0, 3.0,“Boston Cream”); 
```

4.	In the *sellCookie()*, *sellMuffin()* and *sellDoughnut()* methods, add a parameter that brings in the amount of money a customer is willing to pay. After they state how many items they wish to buy and their total amount to pay has been calculated, check to see if the customer gave you enough money. If the customer pays the exact amount or more, add the total amount sold to the *register* variable and thank the customer for their payment. Otherwise, tell the user that they did not provide enough money. For example, if the customer pays $1.00 for a $0.75 muffin, the register’s amount will increase from $100 to $100.75. We are not worried about giving change back to the customer at this time.

5.	Create a method called *mainMenuOptions()* that takes in no parameters and does not return anything. Here, print the following information to the terminal.

<caption><strong>Console Output:</strong></caption>

```
 Please select a numeric option from the menu.
 	1 - See our cookie menu
 	2 - See our muffin menu
 	3 - See our doughnut menu
 	4 - See dietary options
 	5 - Place an order
 	6 - Show display case
 	7 - Help
 	8 - Exit
```

6.	Create a method called *open()* that takes in no parameters and does not return anything. The method should perform the following tasks:
- Call the *welcomeMessage()* and *mainMenuOptions()* methods. 
- Create a `switch` statement that uses an int called option. We will modify this int variable in a later assignment. For now, declare this as a local, temporary int and pass it in through the `switch` statement.

7.	Create a case for each menu option listed in the *mainMenuOption()* terminal text. For each case, print the option selected to the terminal. If none of those options are selected, use the default case to display “Please make a different selection.” An example is shown below. 

<caption><strong>Console Output:</strong></caption>

```
 You have selected “See our doughnut menu”
    Please make a different selection.
```
