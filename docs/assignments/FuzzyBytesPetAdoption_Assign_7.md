# Fuzzy Bytes Pet Adoption - Module 7 Assignment

By now, you can see that the current pet adoption system would work for basic customer adoptions, but it has several design limitations that would cause problems as the application needs to grow. At this point, the main issue is that it uses hardcoded data for only three pets stored in a fixed array. This prevents the adoption center from adding more pets or expanding beyond three entries, which is not practical for real-world use.

The system also searches for pets by comparing the user’s input to a pet’s name. This approach is unreliable because multiple pets could share the same name, making them impossible for the application to distinguish from one another. It is also less efficient than using a unique numeric ID, since numeric comparisons are simpler and can guarantee uniqueness.

The fixed array structure makes the code difficult to extend. Adding new pets would require changing the core data structure. Using a dynamic collection such as an ArrayList would allow new pets to be added without rewriting the underlying design. In this module, you will be refactoring the current application and adding new code based on this knowledge.

## IdGenerator Class

1.	Create a new class called IdGenerator within this class add the following:
    - Declare a static instance variable named *nextId* (int)
    - Initialize the variable to 1. 
    - Create a static accessor method for this variable that returns *nextId* incremented by 1. (This will make it so that each Id will be unique to the pet it is assigned to)


## Dog Class

1.	Declare an instance variable called *id* (int) 

2.	Initialize the *id* variable in each constructor with a call to the static accessor method you created in the IdGenerator class. 

3.	Create an accessor method for the *id* variable.

4.	Update the *toString()* method to include the *id*. 


## Cat Class

1.	Declare an instance variable called *id* (int) 

2.	Initialize the *id* variable in each constructor with a call to the static accessor method you created in the IdGenerator class. 

3.	Create an accessor method for the *id* variable.

4.	Update the *toString()* method to include the *id*. 


## Bird Class

1.	Declare an instance variable called *id* (int) 

2.	Initialize the *id* variable in each constructor with a call to the static accessor method you created in the IdGenerator class. 

3.	Create an accessor method for the *id* variable.

4.	Update the *toString()* method to include the *id*. 





## FuzzyBytesPetAdoption Class

**NOTE:** Making the first change will cause several errors. These errors will go away as you continue to make changes, however, you should comment out the sections that are creating errors in order to test your changes as you go along. 

1.	Remove the *dog*, *cat*, *bird*, and *petData* instance variables and replace them with the following instance variables (do not forget to import packages as needed):

    - *dogs* (ArrayList<Dog>)
    - *cats* (ArrayList<Cat>)
    - *birds* (ArrayList<Bird>)

2.	Remove the initialization of the *petData* variable from the constructor and replace it with initializations of the *dogs*, *cats*, and *birds* ArrayLists. 

3.	Modify the *testData()* method to use the ArrayLists instead of the 2D array, and add at least 2 more pets to each array list. For example:

    ```java
    dogs.add(new Dog("Sparky", 3, "German Shepherd", 60.5, true, "Protective", false, false));
    dogs.add(new Dog("Luna", 2, "Golden Retriever", 55.0, true, "Friendly", false, false));
    dogs.add(new Dog("Vash", 5, "Labrador Retriever", 70.0, true, "Playful", false, false));
    ```

4.	Modify the *adoptDog()*, *adoptCat()*, and *adoptBird()* methods by completing the following:

    - Remove the String *name* parameter and replace it with int *id* 
    - Create a `for` loop in each method to loop through the corresponding animal list. Within this loop (most of the previous logic you already have created will remain the same with some subtle changes):

        - Check to see if the *id* brought in from the parameter is equal to the *id* of the pet, and that the pet has not yet been adopted. If this is true:

            - Set the pet’s *isAdopted* variable to true.
            - Assign the *totalRevenue* variable to its current amount plus the corresponding pet adoption fee. 
            - Print the congratulations and the total fee (see example). 
            - Return true. 

    - Outside of the loop:

        - Print the apology saying this pet is not available (see example).
        - Return false. 

	<figure><figcaption>Console Output (true):</figcaption><pre>
	Congratulations! You adopted Sparky!
	The adoption fee for a dog is: $35.50
    </pre></figure>

	<figure><figcaption>Console Output (false):</figcaption><pre>
	Sorry! The dog with the Id 22 is not available for adoption.
    </pre></figure>

5.	Modify the *processAdoption()* method:

    - Update the user prompt to ask for the pet’s id instead of the pet’s name. 
    - Change this line from a String variable of *petName* (`String petName = input.nextLine();`), to an int variable called *petId*. Include validation with a `while` loop so that your application gracefully handles incorrect input for this variable. 
    - Pass the *petId* variable as a parameter into the adopt methods that were previously using *petName*.  

6.	Modify the *checkDogAvailability()*, *checkCatAvailability()*, and *checkBirdAvailability()* to use for-each loops to iterate through the corresponding pet ArrayList to check if the pet is already adopted or not. 

7.	Modify the *displayAvailableDogs()*, *displayAvailableCats()*, and *displayAvailableBirds()* methods to use your choice of a for-each loop or `for` loop to iterate through the corresponding pet ArrayList to print the pet’s id, name, and breed on the available pet, or an apology message if there are no available pets. 

    <figure><figcaption>Console Output (for dogs when available):</figcaption><pre>
    ==AVAILABLE DOGS FOR ADOPTION==
    Id: 1
    Name: Sparky
    Breed: German Shepherd
    ------------------------------------------------
    Id: 2
    Name: Luna
    Breed: Golden Retriever
    ------------------------------------------------
    </pre></figure>

    <figure><figcaption>Console Output (for dogs when none are available):</figcaption><pre>
    Sorry! There are currently no dogs available for adoption. 
    </pre></figure>

8.	Modify the *displayAllPets()* method to do the following:

    - Print a header for dogs.
    - Check to see if the list of dogs is empty. 
    - If the list is empty, print a message notifying the user there are no dogs in the system. 
    - Otherwise use a for-each loop to iterate through the dogs ArrayList and print to the terminal a call to the Dog instance’s *toString()* method. 
    - Repeat these steps for cats and birds. 


<figure><figcaption>Console Output (Due to size, this example does not include all pets that you should be seeing when you have called this method):</figcaption><pre>
----------Dog Inventory----------
ID: 1
    Name: SPARKY:
    Age: 3 years
    Breed: German Shepherd
    Weight: 60.5 lbs
    House Trained: true
    Personality: Protective
    Hypoallergenic: false
    Adopted: false

----------Cat Inventory----------
ID: 4
    Name: SNOWBALL:
    Age: 2 years
    Breed: Ragdoll
    Indoor: true
    Litter Trained: true
    Fur Length: Long
    Adopted: false
</pre></figure>

9.	Modify the *displayInventorySummary()* method by completing the following:

    - Keep the *adoptedCount*, and *availableCount* variables.
    - Remove the `for` loop, and replace it with for-each loops for the dogs, cats, and birds (for a total of three for-each loops) lists. Within these for-each loops:

        - Check to see if the dog, cat, or bird is adopted

            - If they are, increment *adoptedCount* by 1
            - Otherwise, increase *availableCount* by 1. 

    - Keep the *totalPets* variable and assign it the sum of the size of each corresponding pet ArrayList. 
    - Keep the information that prints to the terminal. 

    **NOTE:** At this point you should no longer see any syntax errors. If you are still seeing errors, read back through your code and verify that you have removed or modified anything related to the 2D array. 

10.	Create 3 methods called *addDog()*, *addCat()*, and *addBird()* that bring in a parameter of the corresponding pet class. Then, take the parameter and add it to the corresponding pet ArrayList. 

11.	Go through your modified methods and make changes to your JavaDoc as needed.
