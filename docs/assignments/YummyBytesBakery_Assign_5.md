# Yummy Bytes Bakery - Module 4 Assignment

## YummyBytesBakery Class
1.	Create the following 2D array instance variables using the included data types:
    - *cookieCase* (Cookie)
    - *muffinCase* (Muffin)
    - *doughnutCase* (Doughnut)

2.	Initialize these variables in the default constructor. Each variable should have a total of 12 elements (Example: 3 rows x 4 columns, 4x3, 2x6. Your choice.) Make sure to leave the call to *testData()* as the last item in the default constructor. Otherwise, you will get an error regarding NullPointerExceptions.

3.	Create three methods called *fillCookieCase()*, *fillMuffinCase()*, and *fillDoughnutCase()*. These will be responsible for filling their respective 2D arrays. Each brings in an instance of their corresponding class:
    - Cookie for *fillCookieCase()*
    - Muffin for *fillMuffinCase()*
    - Doughnut for *fillDoughnutCase()*
	
	Then, assign every element in the appropriate 2D array to the object passed in
    - *cookieCase[][]* for cookies
    - *muffinCase[][]* for muffins
    - *doughnutCase[][]* for doughnuts

4.	In the *testData()* method, call the *fillCookieCase()*, *fillMuffinCase()*, and *fillDoughnutCase()* methods passing in the cookie, muffin, and doughnut instance variables.

5.	Create three methods called *printCookieCase()*, *printMuffinCase()*, and *printDoughnutCase()* that do not bring in or return values. In these methods, print a header then print the name (*getName()*) of all elements of their respective arrays as a numbered list. An example output for *printCookieCase()* should look like this:

    <caption><strong>Console Output:</strong></caption>

    ```
     ==COOKIE CASE==
     1) Chocolate Chip
     2) Chocolate Chip
     3) Chocolate Chip
     4) Chocolate Chip
     5) Chocolate Chip
     6) Chocolate Chip
     7) Chocolate Chip
     8) Chocolate Chip
     9) Chocolate Chip
     10) Chocolate Chip
     11) Chocolate Chip
     12) Chocolate Chip
    ```

6.	Update the switch statement in the *open()* method. Replace the print statement for case 6 (“Show display case”) from the previous assignment with calls to the *printCookieCase()*, *printMuffinCase()*, and *printDoughnutCase()* methods.
