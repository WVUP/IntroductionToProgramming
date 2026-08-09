# Yummy Bytes Bakery - Module 3 Assignment

## Cookie Class
1.	Create getters for all variables in the Cookie class.

2.	Create setters for all variables in the Cookie class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Replace `<COOKIE NAME>` with the capitalized version of the value held in name, and `<#>` for the numerical value held in each respective variable.

<caption><strong>Console Output:</strong></caption>

```
Name: <COOKIE NAME>
    Flour: <#> cups
    Sugar: <#> cups
    Butter: <#> sticks
    Nuts: <#> bags
    Chocolate Chips: <#> bags
```



## Muffin Class
1.	Create getters for all variables in the Muffin class.

2.	Create setters for all variables in the Muffin class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Replace `<MUFFIN NAME>` with the capitalized version of the value held in name, and `<#>` for the numerical value held in each respective variable.

<caption><strong>Console Output:</strong></caption>

```
Name: <MUFFIN NAME>
    Flour: <#> cups
    Baking Powder: <#> tsp
    Salt: <#> tsp
    Sugar: <#> cups
    Eggs: <#>
    Milk: <#> cups
    Vegetable Oil: <#> cups
```


##  Doughnut Class
1.	Create getters for all variables in the Doughnut class.

2.	Create setters for all variables in the Doughnut class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Replace `<DOUGHNUT NAME>` with the capitalized version of the value held in name, and `<#>` for the numerical value held in each respective variable.

<caption><strong>Console Output:</strong></caption>

```
Name: <DOUGHNUT NAME>
    Milk: <#> cups
    Yeast: <#> packets
    Sugar: <#> cups
    Eggs: <#>
    Butter: <#> sticks
    Flour: <#> cups
```	

## YummyBytesBakery Class
1.	Add the following variable. 
- *register* (double)

2.	Initialize the register variable to 100.00

3.	Add a getter and setter for the register variable.

4.	Create a method called *welcomeMessage()* that does not use parameters or returns any values. The method should display the following output in the terminal.

<caption><strong>Console Output:</strong></caption>

```
Hello! Welcome to Yummy Bytes Bakery!
We sell an array of various pastries and other desserts.
```

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

<caption><strong>Console Output:</strong></caption>

```
What type of pastry would you like to order?
    Cookie
    Doughnut
    Muffin
```