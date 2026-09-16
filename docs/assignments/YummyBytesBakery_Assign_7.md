# Yummy Bytes Bakery - Module 7 Assignment

Includes content from [Appendix IV: Enumterated Types](../app4_EnumeratedTypes.md).

## DietaryOption Enum

1.	Create a new enumerated type called DietaryOption which represents dietary options for desserts baked and sold at Yummy Bytes Bakery.

2.	Add the following enum values and aliases:

    - V("Vegan")
    - GF("Gluten Free")
    - SF("Sugar Free")
    - RF("Reduced Fat")
    - NONE("Regular")

3.	Declare a String variable called *type*. This will hold the alias associated with each enum value.

4.	In the DietaryOption overloaded constructor, initialize the *type* variable with the value being brought in through the parameter.

5.	Create a method called *getType()* that has no parameters and returns a String value. In this method, return the value held in the *type* variable.


## Cookie Class

1.	Add the following instance variable:

    - *dietaryType* (DietaryOption)
	
2.	Update the default constructor to set the *dietaryType* variable to null.

3.	Update the overloaded constructor to bring in a value for *dietaryType* as assign accordingly.

4.	Add a getter and setter for *dietaryType*.


## Muffin Class

1.	Add the following instance variable:

    - *dietaryType* (DietaryOption)
	
2.	Update the default constructor to set the *dietaryType* variable to null.

3.	Update the overloaded constructor to bring in a value for *dietaryType* as assign accordingly.

4.	Add a getter and setter for *dietaryType*.


##  Doughnut Class

1.	Add the following instance variable:

    - *dietaryType* (DietaryOption)
	
2.	Update the default constructor to set the *dietaryType* variable to null.

3.	Update the overloaded constructor to bring in a value for *dietaryType* as assign accordingly.

4.	Add a getter and setter for *dietaryType*.


## YummyBytesBakery Class

1.	Add the following instance variables:

    - *cookieRecipes* (ArrayList of Cookie)
    - *doughnutRecipes* (ArrayList of Doughnut)
    - *muffinRecipes* (ArrayList of Muffin)
    - *cookieMenu* (Hashmap with a String key and Cookie value)
    - *doughnutMenu* (Hashmap with a String key and Doughnut value)
    - *muffinMenu* (Hashmap with a String key and Muffin value)

2.	Initialize the newly added variables in the default constructor.

3.	Create three new methods called *createCookieMenu()*, *createMuffinMenu()*, and *createDoughnutMenu()*. These methods do not have parameters or return any values. In each of these methods, do the following:

    - Declare local variables of the appropriate type (e.g. *createCookieMenu()* uses Cookie data type, etc.) and initialize them by providing data similar to what was used for the *testData()* method. Be sure to include various entries for the pastry's DietaryOptions to be used for testing methods later in the assignment.
    - Insert these local instances into the appropriate pastry menu HashMap where the name of your pastry is the key, and the local instance is the value.
    - Insert the same local instances into the pastry's recipe ArrayList.

4.	Create three new methods called *printCookieMenu()*, *printMuffinMenu()*, and *printDoughnutMenu()*. In these methods, do the following:

    - Print a header for the menu (e.g. "Doughnut Menu:")
    - Loop through each key in the appropriate pastry menu HashMap.

        - For each key, display the pastry's name. Example output is shown below.
	
    <figure><figcaption>Console Output:</figcaption><pre>
    Doughnut Menu
        Boston Creme
        Cinnamon Sugar
        Apple Fritter
    </pre></figure>
	
5.	Update the *open()* method to call *printCookieMenu()*, *printMuffinMenu()*, and *printDoughnutMenu()* for cases 1, 2, and 3, respectively.
	
6.	Update the *printOrderCookies()*, *printOrderDoughnuts()*, and *printOrderMuffins()* methods. After capturing what type of pastry the end user wants to order, check to see if the appropriate pastry menu has that option available.

    - If that option is available, continue on to ask how many pastries they wish to order. This should already be set up from prior assignments.
    - If the option is not available, notify the end user that their selection is not available and try again.
	
7.	Create four new methods called *printVeganPastries()*, *printGlutenFreePastries()*, *printSugarFreePastries()*, and *printReducedFatPastries()*. All four methods do not bring in any additional data or return any values. In each of these methods, do the following:

    - Display the data stored in the type variable of the appropriate DietaryOption enum. For example, in the *printVeganPastries()* method, print the type associated with the *VEGAN* DietaryOption enum.
    - Display a header for the pastry type (i.e. Cookie)
    - For every entry in the pastry's recipe ArrayList, display the pastry's name only if the recipe has a matching DietaryOption.
    - Repeat the previous two steps for muffins and doughnuts. An example output of the vegan pastry options is shown below.
	
    <figure><figcaption>Console Output:</figcaption><pre>
    Vegan
        Cookies
        - Oatmeal Raisin
        Muffins
        - Blueberry
        - Raspberry
        Doughnuts
        - Chocolate
    </pre></figure>


8.	Add the following method calls to the open() method's case 4 ("See Dietary Options")
    - *printVeganPastries()*
    - *printGlutenFreePastries()*
    - *printSugarFreePastries()*
    - *printReducedFatPastries()*



