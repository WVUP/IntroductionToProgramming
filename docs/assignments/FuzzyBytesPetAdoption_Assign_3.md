# Fuzzy Bytes Pet Adoption - Module 3 Assignment

## Dog Class
1.	Create getters for all variables in the Dog class. 

2.	Create setters for all variables in the Dog class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Use escape characters for formatting. Replace `<DOG NAME>` with the capitalized version of the value held in name, replace `<#>` for the numerical values held in age and weight, and replace the other placeholders `<Breed>`, `<true/false>`, `<Personality>` with their respective variable values.

<caption><strong>Console Output:</strong></caption>

```
 Name: <DOG NAME>
    Age: <#> years
    Breed: <Breed>
    Weight: <#> lbs
    House Trained: <true/false>
    Personality: <Personality>
    Hypoallergenic: <true/false>
    Adopted: <true/false>
```

## Cat Class
1.	Create getters for all variables in the Cat class.
 
2.	Create setters for all variables in the Cat class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Use escape characters for formatting. Replace `<CAT NAME>` with the capitalized version of the value held in name, replace `<#>` for the numerical value held in age, and replace the other placeholders `<Breed>`, `<true/false>`, `<Fur length>` with their respective variable values.

<caption><strong>Console Output:</strong></caption>

```
 Name: <CAT NAME>
    Age: <#> years
    Breed: <Breed>
    Indoors Only: <true/false>
    Litter Trained: <true/false>
    Fur Length: <Fur length>
    Adopted: <true/false>
```


## Bird Class
1.	Create getters for all variables in the Bird class. 

2.	Create setters for all variables in the Bird class.

3.	Create a method called *toString()* that does not use parameters. The method should return a String with the following output. Use escape characters for formatting. Replace `<BIRD NAME>` with the capitalized version of the value held in name, replace `<#>` for the numerical values held in age, wingspan, and lifespan, and replace the other placeholders `<Species>`, and `<true/false>` with their respective variable values.

<caption><strong>Console Output:</strong></caption>

```
 Name: <BIRD NAME>
    Age: <#> years
    Species: <Species>
    Wingspan: <#> in
    Can Talk: <true/false>
    Lifespan: <#> years
    Adopted: <true/false>
```

## FuzzyBytesPetAdoption Class
1.	Add the following variable.
- *totalRevenue* (double)

2.	Initialize the *totalRevenue* variable to 0.

3.	Create a method called *welcomeMessage()* that does not use parameters or returns any values. The method should display the following output in the terminal. 

<caption><strong>Console Output:</strong></caption>

```
 Hello! Welcome to Fuzzy Bytes Pet Adoption!
 We help match loving families with wonderful pets.
```

4.	Create three methods called *adoptDog()*, *adoptCat()*, and *adoptBird()*. These methods do not bring in any parameters and will not return any values. The methods should display a concatenated message to the screen stating what the adoption fee is. Example outputs for each method call are shown below: 

```
 adoptDog(); //Output: The adoption fee for a dog is $35.50.
 adoptCat(); //Output: The adoption fee for a cat is $25.00.
 adoptBird(); //Output: The adoption fee for a bird is $15.75.
```

5.	Create a method called *displayAdoptionFees()* that does not use parameters or return any values. The method should display the following output in the terminal. Use escape characters.

<caption><strong>Console Output:</strong></caption>

```
 Adoption Fees:
    Dog adoption fee: $35.50 
    Cat adoption fee: $25.00
    Bird adoption fee: $15.75
```

**OPTIONAL:** Format the double to display two numbers after the decimal point. (**You will need to use outside sources for this**) If you choose not to format, note that the dog fee will display as $35.5 and cat fee $25.0 and this is acceptable.

6.	Create a method called *printAdoptionOptions()* that does not use parameters or returns any values. The method should display the following output in the terminal. Use escape characters.

<caption><strong>Console Output:</strong></caption>

```
 What type of pet would you like to adopt?
    Dog
    Cat
    Bird
```