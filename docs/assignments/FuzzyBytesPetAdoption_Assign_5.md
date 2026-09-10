# Fuzzy Bytes Pet Adoption - Module 3 Assignment

**NOTE:** At this point only one of each type of animal is being used and this is ok. In a later module, the assignment will have the code be refactored to include multiples of each animal. 

## FuzzyBytesPetAdoption Class
1.	Create a method called *processAdoption()*. Add 2 String parameters, one that brings in the type of pet the user wants to adopt and one that brings in the name of the pet the user wants to adopt.   If the pet type is “Dog”, then call the *adoptDog()* method passing in the name parameter.  If the pet type is “Cat”, then call the *adoptCat()* method passing in the name parameter. Otherwise, If the pet type is “Bird”, then call the *adoptBird()* method passing in the name parameter. 

2.	Create the following 2D array instance variable using the included data type:
    - *petData* (String)

3.	Initialize the *petData* variable in the default constructor. This variable will have 12 elements using 3 rows x 4 columns. Make sure to leave the call to *testData()* as the last item in the default constructor. Otherwise, you will get an error regarding NullPointerExceptions.

4.	In the *testData()* method, initialize the petData 2D array with information from the Dog, Cat, and Bird objects.

    Row:
    - Row 0: Dog Information
    - Row 1: Cat Information
    - Row 2: Bird Information


    For each pet, assign the appropriate values to each Column:
    - Column 0: pet name, use appropriate accessor methods
    - Column 1: pet type, Hard code values appropriately “Dog”, “Cat”, or “Bird”
    - Column 2: pet breed/species, use appropriate accessor methods
    - Column 3: adoption status, use appropriate accessor methods within a ternary operator to check if the pet is adopted; if true, set to "Adopted", if false, set to "Available"

    For Example: 
    - *petData[0][0]* will contain the dog’s name.
    - *petData[1][0]* will contain the cat’s name.
    - *petData[2][0]* will contain the bird’s name.  

5.	Update the *adoptDog()*, *adoptCat()*, and *adoptBird()* methods to change the corresponding adoption status to “Adopted” in the 2D array after the *isAdopted* variable is set to true.  

6.	Create three methods called *displayAvailableDogs()*, *displayAvailableCats()*, and *displayAvailableBirds()* that do not bring in or return any values. In these methods if a pet is available for adoption print a header, then print the information that corresponds with the values stored in the 2D array, otherwise print a statement saying there are no available pets of this type for adoption. An example output for *displayAvailableDogs()* should look like this if a dog is available:

    <caption><strong>Console Output:</strong></caption>

    ```
     ==AVAILABLE FOR ADOPTION==
     Name: Sparky
     Type: Dog
     Breed: German Shepherd
    ```

    An example output for *displayAvailableDogs()* when no dogs are available:

    <caption><strong>Console Output:</strong></caption>

    ```
     Sorry! There are currently no dogs available for adoption. 
    ```

7.	Update the switch statement in the open() method. Replace the print statements in    Cases 1,2, and 3 with calls to their corresponding displayAvailableDogs(), displayAvailableCats(), and displayAvailableBirds() methods. 
