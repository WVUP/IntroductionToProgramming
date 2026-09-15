# Yummy Bytes Bakery - Module 3 Assignment

## Cookie Class
1.	Create getters for all variables in the Cookie class.

2.	Create setters for all variables in the Cookie class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Replace `<COOKIE NAME>` with the capitalized version of the value held in name, and `<#>` for the numerical value held in each respective variable.

    <figure><figcaption>Returned String Format:</figcaption><pre>
     Name: &ltCOOKIE NAME&gt
        Flour: &lt#&gt cups
        Sugar: &lt#&gt cups
        Butter: &lt#&gt sticks
        Nuts: &lt#&gt bags
        Chocolate Chips: &lt#&gt bags
    </pre></figure>



## Muffin Class
1.	Create getters for all variables in the Muffin class.

2.	Create setters for all variables in the Muffin class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Replace `<MUFFIN NAME>` with the capitalized version of the value held in name, and `<#>` for the numerical value held in each respective variable.

    <figure><figcaption>Returned String Format:</figcaption><pre>
     Name: &ltMUFFIN NAME&gt
        Flour: &lt#&gt cups
        Baking Powder: &lt#&gt tsp
        Salt: &lt#&gt tsp
        Sugar: &lt#&gt cups
        Eggs: &lt#&gt
        Milk: &lt#&gt cups
        Vegetable Oil: &lt#&gt cups
    </pre></figure>


##  Doughnut Class
1.	Create getters for all variables in the Doughnut class.

2.	Create setters for all variables in the Doughnut class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Replace `<DOUGHNUT NAME>` with the capitalized version of the value held in name, and `<#>` for the numerical value held in each respective variable.

    <figure><figcaption>Returned String Format:</figcaption><pre>
     Name: &ltDOUGHNUT NAME&gt
        Milk: &lt#&gt cups
        Yeast: &lt#&gt packets
        Sugar: &lt#&gt cups
        Eggs: &lt#&gt
        Butter: &lt#&gt sticks
        Flour: &lt#&gt cups
    </pre></figure>	

## YummyBytesBakery Class
1.	Add the following variable. 
    - *register* (double)

2.	Initialize the register variable to 100.00

3.	Add a getter and setter for the register variable.

4.	Create a method called *welcomeMessage()* that does not use parameters or returns any values. The method should display the following output in the terminal.

    <figure><figcaption>Console Output:</figcaption><pre>
     Hello! Welcome to Yummy Bytes Bakery!
     We sell an array of various pastries and other desserts.
    </pre></figure>

5.	Create three methods called *sellCookies()*, *sellMuffins()*, and *sellDoughnuts()*. Each of these brings in the number of pastries to sell. They will not return any values. The methods should perform the following tasks:

    - Set a local variable equal to the quantity from the parameter multiplied by the appropriate price constant:

        - COOKIE_PRICE for cookies
        - MUFFIN_PRICE for muffins
        - DOUGHNUT_PRICE for doughnuts
        
    - Display a concatenated message to the screen stating what the total is. Example outputs for each method call are shown below:

    ```
     sellCookies(3);     //Output: Your total is $0.75
     sellMuffins(3);      //Output: Your total is $2.25
     sellDoughnuts(3);   //Output: Your total is $4.50
    ```

6.	Create a method called *printOrderOption()* that does not use parameters or returns any values. The method should display the following output in the terminal. Use escape characters.

    <figure><figcaption>Console Output:</figcaption><pre>
     What type of pastry would you like to order?
        Cookie
        Doughnut
        Muffin
    </pre></figure>
