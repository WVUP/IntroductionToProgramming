# Fuzzy Bytes Pet Adoption - Module 6 Assignment

Includes content from [Appendix III: Scanner](../app3_Scanner.md).

## FuzzyBytesPetAdoption Class

1.	Modify the *open()* method. Create a local Scanner variable.

    - After displaying the menu options, use the Scanner variable to bring in the end user's numerical menu selection and save it to the option variable.
    - Pass this response into the existing `switch` statement.
    - Repeat the process of prompting the end user for a response, getting their response, and passing it into the `switch` statement until they choose the option to exit the application.

2.	Create a *printHelp()* method that displays the following information:

    <caption><strong>Console Output:</strong></caption>

    ``` 
     Please select the number that corresponds with a menu option.
     Type 1 to view a list of dogs that are available for adoption
     Type 2 to view a list of cats that are available for adoption
     Type 3 to view a list of birds that are available for adoption
     Type 4 to view the adoption fee for different types of animals 
     Type 5 to adopt an available pet
     Type 6 to view all pets even those no longer available for adoption
     Type 7 to view the help menu
     Type 8 to quit 
    ```

3.	Modify case 7 ("Help") and the `default` case in the `switch` statement in the *open()* method.

    - Replace the existing print statements with a call to the *printHelp()* method.

4.	Create a new method called *displayAllPets()* that does not use any parameters and does not return anything. In this method you will:

    - Display the following header: “----------Pet Inventory----------"
    - Use a for-each loop to iterate through *petData* (Hint: *petData* is a 2D array, so each iteration gives you one row/pet)
    - For each pet, print out the Name, Type, Breed/Species, and Status with appropriate labels
    - Add a blank line between each pet for readability

    <caption><strong>Example Console Output:</strong></caption>

    ``` 
     ----------Pet Inventory----------
     Name: Sparky
     Type: Dog
     Breed/Species: German Shepherd
     Status: Available
     
     Name: Snowball
     ...
    ```

5.	Create a new method called *displayInventorySummary()* that does not bring in any parameters and does not return anything. In this method you will:

    - Declare a local variable called *adoptedCount* initialize this variable to 0.
    - Declare a local variable called *availableCount* initialize this variable to 0.
    - Use a `for` loop to loop through the *petData* 2D array and if the status of the pet is “Adopted” increment *adoptedCount* by one otherwise increment *availableCount* by one. 
    - Declare a local variable called *totalPets* and initialize this variable to the sum of each pet’s total count. (Hint: You created an instance variable and accessor method in each pet class in a previous module that is helpful here.)
    - Display the following header: “----------Inventory Summary----------"
    - Print out the total number of pets ever placed in the system, the total number of pets that have been adopted, and the total number of pets that are currently available.
    
    <caption><strong>Example Console Output:</strong></caption>

    ``` 
     ----------Inventory Summary----------
     Total number of pets that have come through the adoption center: 3
     Total number of pets that have been adopted: 1
     Total number of pets that are currently available for adoption: 2
    ```

6.	Modify case 6 ("View all pets") in the `switch` statement in the *open()* method.

    - Replace the existing print statements with a call to the *displayAllPets()* and *displayInventorySummary()* methods.

7.	Modify the *adoptDog()*, *adoptCat()*, and *adoptBird()* methods to return a boolean value.

8.	Create three new methods called *checkDogAvailability()*, *checkCatAvailablility()*, and *checkBirdAvailability()* these methods will not bring in any parameters and will return a boolean value. In each method do the following:

    - Check to see if the status of the pet is “Available”, if it is return true, otherwise return false. 

9.	Modify the *printAdoptionOptions()* method to return a String value and bring in the end user's response to the existing prompt using a local Scanner object.

    - If the response equals “Dog” and there are dogs available for adoption, call the *viewAvailableDogs()* method.
    - If the response equals “Cat” and there are cats available for adoption, call the *viewAvailableCats()* method.
    - If the response equals “Bird” and there are birds available for adoption, call the *viewAvailableBirds()* method.
    - For all other responses, display “That type of pet is unavailable. Please try again.” In the terminal.
    - Repeat the process of prompting the end user for a response, getting their response, and evaluating it in a condition until they choose a valid option.

10.	Modify the *processAdoption()* method to use a Scanner and a `do-while` loop to allow the user to adopt pets until they do not want to adopt any more pets or there are no pets left to adopt. 

    - Create a local Scanner variable.
    - Declare and initialize a local variable called *totalFees* (double) to track fees for all adoptions.
    - Declare and initialize a local variable counter to count the number of pets being adopted called *petsAdoptedThisVisit* (int)
    - Declare and initialize a local variable for user responses called *response* (String)

    Use a `do-while` loop to allow customers to adopt multiple pets in a single visit. Within the loop:

    - Verify that there are pets available for adoption. If there are no pets available for adoption, tell the user "Sorry! There are no more pets available for adoption." and break out of the loop.  
    - Declare a string variable called *petType* and initialize it with the value returned from the *printAdoptionOptions()* method. 
    - Tell the user to "Enter the name of the pet you want to adopt: " and store this in a local variable called *petName* (String).
    - Declare a local boolean variable called *adoptionSuccessful* and initialize it to false.
    - Check to see if the *petType* variable matches the corresponding pet (dog, cat, or bird). If it does match:

        - Make a call to the appropriate adoption method (*adoptDog()*, *adoptCat()*, or *adoptBird()*) passing in the petName and assigning it to the *adoptionSuccessful* variable. 
        - If the adoption is successful:
    
            - Add the corresponding adoption fee to the *totalFees* variable 
            - Increment the *petsAdoptedThisVisit* variable by one.
    
    - Create an inner `do-while` loop to validate user input. Before the loop, declare a local boolean variable called *validResponse*. Within the inner loop:

        - Ask the user the question “Would you like to adopt another pet? (yes/no)” 
        - Save the users input to the *response* variable.
        - Check to see if the user’s input is indeed “yes” or “no.” If it is then set the *validResponse* variable to true, otherwise print off a message to the terminal telling the user their response is invalid and they need to enter either yes or no. 

    - After both `do-while` loops end, display a summary of the transaction by printing a transaction summary header, the number of pets adopted this visit, and the total fees due. 

    <caption><strong>Example Console Output:</strong></caption>

    ``` 
     ----------Transaction Summary----------
     Pets adopted this visit: 3
     Total adoption fees due: $76.25 
    ```

11.	Modify case 5 ("Adopt a pet") in the `switch` statement in the *open()* method.

    - Replace the existing print statements with a call to the *processAdoption()* method.
