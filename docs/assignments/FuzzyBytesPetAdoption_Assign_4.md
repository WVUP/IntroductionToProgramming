# Fuzzy Bytes Pet Adoption - Module 3 Assignment
Includes content from [Appendix I: Static Variables and Methods](../app1_StaticVariablesAndMethods.md).

> **NOTE:** This assignment is setting up the framework to utilize user input. The new methods in the FuzzyBytesPetAdoption class will be partially complete, and this is ok. We will revisit these methods in later assignments.


## Dog Class
1.	Add a static, class-level variable called *totalDogs* (int) and initialize it to 0.

2.	In each constructor (default and overloaded) increment the *totalDogs* variable by 1.

3.	Create a getter only for the *totalDogs* variable.

4.	Update your setters to include data validation. No numerical variables set should be a negative number, and no String variables set should be empty.

## Cat Class
1.	Add a static, class-level variable called *totalCats* (int) and initialize it to 0.

2.	In each constructor (default and overloaded) increment the *totalCats* variable by 1.

3.	Create a getter only for the *totalCats* variable.

4.	Update your setters to include data validation. No numerical variables set should be a negative number, and no String variables set should be empty. 


## Bird Class
1.	Add a static, class-level variable called *totalBirds* (int) and initialize it to 0. 

2.	In each constructor (default and overloaded) increment the *totalBirds* variable by 1.

3.	Create a getter only for the *totalBirds* variable.

4.	Update your setters to include data validation. No numerical variables set should be a negative number, and no String variables set should be empty. 


## FuzzyBytesPetAdoption Class
1.	Update the *totalRevenue* instance variable and make it a static, class-level variable.

2.	Declare an instance for each of these classes: Dog, Cat, Bird. (Do not initialize these within the default constructor, if you do, this will cause an unwanted side effect with the *totalDogs*, *totalCats*, and *totalBirds* static counters. Number 3 of the assignment will complete initialization through a separate method)

3.	Create a new method called *testData()* that takes in no parameters and does not return anything. In this method, place the following statements. These statements will initialize your variables and create test data for you to use in your application. Call this method at the end of your default constructor. 

```java
 dog = new Dog(“Sparky”, 3, “German Shepherd”, 60.5, true, “Protective”, false, false);
 cat = new Cat(“Snowball”, 2, “Ragdoll”, true, true, “Long”, false);
 bird = new Bird(“Chirp”, 5, “Parakeet”, 11.5, true, 15, false);
```

4.	In the *adoptDog()*, *adoptCat()* and *adoptBird()* methods, add a parameter that brings in the name of the pet the user wants to adopt. Check to see if the pet’s name matches a pet at the center and if the pet has not been adopted. If the pet is available, mark it as adopted, add the adoption fee to the *totalRevenue* variable, and confirm the adoption by displaying the pet's name and the adoption fee with a message of congratulations to the user. If the pet has already been adopted or the name does not match, apologize to the user and inform them that the pet is not available for adoption. For example, if the user wants to adopt the dog named "Max" and Max has not been adopted, the *totalRevenue* amount will increase from $0 to $35.50, the adopted status will be set to true, and you will display a message confirming Max's adoption with the $35.50 adoption fee.

5.	Create a method called *applicationMenuOptions()* that takes in no parameters and does not return anything. Print the following information to the terminal. 

<caption><strong>Console Output:</strong></caption>

```
 Please select a numeric option from the menu.
	1 – View Available Dogs
	2 – View Available Cats
	3 – View Available Birds
	4 – View Adoption Fees
	5 – Process an Adoption
	6 – View all Pets
	7 – Help
	8 – Exit
```

6.	Create a method called *open()* that takes in no parameters and does not return anything. The method should perform the following tasks: 
- Call the *welcomeMessage()* and *applicationMenuOptions()* methods. 
- Create a `switch` statement that uses an int called *option*. We will modify this int variable in a later assignment. For now, declare this as a local, temporary int and pass it in through the `switch` statement.

7.	Create a case for each menu option listed in the *applicationMenuOptions()* terminal text, and include the following:
- For cases 1, 2, 3, 5, 6, and 7 print a message to the terminal that the option has been selected. An example is shown below. 

<caption><strong>Console Output:</strong></caption>

```
 You have selected “View Available Dogs”
 ```

- For case 4, call the *displayAdoptionFees()* method. 
- For case 8, print a message to the terminal thanking the user for visiting. 
- If none of the numeric options 1-8 are selected, use the default case to display "Please select a numeric option from 1 to 8.” An example is shown below. 

<caption><strong>Console Output:</strong></caption>

```
 Please select a numeric option from 1 to 8
```