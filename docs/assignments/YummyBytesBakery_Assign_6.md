# Yummy Bytes Bakery - Module 6 Assignment

Includes content from [Appendix III: Scanner](../app3_Scanner.md).

## YummyBytesBakery Class

1.	Modify the *open()* method. Create a local Scanner variable. 

    - After displaying the menu options, use the Scanner variable to bring in the end user's numerical menu selection and save it to the *option* variable.
    - Pass this response into the existing `switch` statement. 
    - Repeat the process of prompting the end user for a response, getting their response, and passing it into the `switch` statement until they choose the option to exit the application.

2.	Create a *printHelp()* method that displays the following information:

    <caption><strong>Console Output:</strong></caption>

    ```        
     Please select a number that corresponds with a menu option.
     Type 1 to see our cookie menu
     Type 2 to see our doughnut menu
     Type 3 to see our muffin menu
     Type 4 to see all dietary pastry options
     Type 5 to place an order
     Type 6 to see what's available
     Type 7 to see help menu (this menu)
     Type 8 to quit
    ```

3.	Modify case 7 ("Help") and the `default` case in the `switch` statement in the *open()* method. Replace the existing print statements with a call to the *printHelp()* method. 

4.	Modify the *sellCookies()*, *sellMuffins()*, and *sellDoughnuts()* methods. 

    - Remove the parameter that is responsible for the customer's payment. 
    - In the method, create and initialize a local Scanner variable. 
    - After calculating the total price, ask the end user how much they want to pay. 
    - Enclose the existing `if/else` statement in a `do-while` loop. 
    - Using the local Scanner variable, retrieve the customer's chosen amount to pay. 
    - If the amount they provided is enough, provide a way to exit the loop. Otherwise, tell the end user that they did not provide enough money, and repeat the request for the end user's payment amount.

5.	Create three methods called *checkCookieCaseQuantity()*, *checkMuffinCaseQuantity()*, and *checkDoughnutCaseQuantity()* that returns an int and brings in the name of a pastry through a parameter. 

    - Create a local variable called *quantity*. 
    - Starting with a *quantity* of 0, use a nested loop to iterate through each element in the appropriate 2D array:

        - *cookieCase[][]* for cookies
        - *muffinCase[][]* for muffins
        - *doughnutCase[][]* for doughnuts

    - If the element is not null and the object’s name in the element matches the name from the parameter, increase the *quantity* value by 1. 
    - Once you loop through all elements, return the value assigned to the *quantity* variable.

6.	Create three methods named *removeCookies()*, *removeMuffins()*, and *removeDoughnuts()* that brings in the number of pastries to remove and the name of the pastry to remove. 

    - Use a nested loop to iterate through the appropriate 2D array:

        - *cookieCase[][]* for cookies
        - *muffinCase[][]* for muffins
        - *doughnutCase[][]* for doughnuts

    - If the element is not null and the object’s name in the 2D array element matches the name from the parameter and the number of pastries to remove is not less than or equal to 0, decrease the number of pastries to remove by 1 and set the current element equal to null.

7.	Modify the *printCookieCase()*, *printMuffinCase()*, and *printDoughnutCase()* methods.

    - Print the contents of the 2D array utilizing a nested loop.
    - If an element in the 2D array is null, print “- - -” instead of a name.

8.	Create three methods called *printOrderCookies()*, *printOrderMuffins()*, and *printOrderDoughnuts()*. 

    - Create a local Scanner variable. 
    - In a `do-while` loop, complete the following:

        - Ask the end user "What would you like to order?". 
        - Make a call to the appropriate case display method.

            - *printCookieCase()* for cookies
            - *printMuffinCase()* for muffins
            - *printDoughnutCase()* for doughnuts

        - Using the local Scanner variable, retrieve the name of the pastry from the end user and save this in a local String variable. 
        - Ask the end user "How many would you like to order?". 
        - Using the local Scanner variable, retrieve the number of pastries the end user wishes to purchase and save this in a local int variable. 
        - If the number they provided is 1 or more, complete the following tasks: 

            - Using the appropriate quantity check method, check to see if the number of pastries the user wants to purchase is available. 

                - *checkCookieCaseQuantity()* for cookies
                - *checkMuffinCaseQuantity()* for muffins
                - *checkDoughnutCaseQuantity()* for doughnuts

            - If so, run the appropriate remove and sell methods, and provide a way to exit the do-while loop. 

                - *removeCookies()* and *sellCookies()* for cookies
                - *removeMuffins()* and *sellMuffins()* for muffins
                - *removeDoughnuts()* and *sellDoughnuts()* for doughnuts

            - If there are not enough pastries available, display "Error: There is not enough of that item to sell. Try again." 

        - If the number they provide is 0 or less, complete the following task: 

            - Display "Error: Order must contain at least 1 item." and go back to the beginning of the do-while loop and repeat the ordering process.

9.	Modify the *printOrderOption()* method to bring in the end user's response to the existing prompt. 

    - If the user's response equals "cookie", call the *printOrderCookies()* method. 
    - If the user's response equals "muffin", call the *printOrderMuffins()* method. 
    - If the user's response equals "doughnut", call the *printOrderDoughnuts()* method. 
    - For all other responses display "Pastry unavailable. Please try again." in the terminal. 
    - Repeat the process of prompting the end user for a response, getting their response, and evaluating it in a condition statement until they choose a valid option.

10.	Modify case 5 ("Place order") in the `switch` statement in the *open()* method. Replace the existing print statement with a call to the *printOrderOption()* method. 

11.	Optional: Alter the following methods to utilize loops of your choice: 

    - *fillCookieCase()* 
    - *fillMuffinCase()* 
    - *fillDoughnutCase()* 
