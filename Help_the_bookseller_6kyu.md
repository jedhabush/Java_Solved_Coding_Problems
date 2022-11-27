## Instructions about the Kata

A bookseller has lots of books classified in 26 categories labeled A, B, ... Z. Each book has a code ```c``` of 3, 4, 5 or more characters. The 1st character of a code is a capital letter which defines the book category.

In the bookseller's stocklist each code ```c``` is followed by a space and by a positive integer n (int n >= 0) which indicates the quantity of books of this code in stock.

***For example an extract of a stocklist could be:***

```
L = {"ABART 20", "CDXEF 50", "BKWRK 25", "BTSQZ 89", "DRTYM 60"}.
or
L = ["ABART 20", "CDXEF 50", "BKWRK 25", "BTSQZ 89", "DRTYM 60"] or ....
```

***You will be given a stocklist (e.g. : L) and a list of categories in capital letters e.g :***
```
M = {"A", "B", "C", "W"} 
or
M = ["A", "B", "C", "W"] or ...
```

and your task is to find all the books of L with codes belonging to each category of M and to sum their quantity according to each category.

***For the lists L and M of example you have to return the string (in Haskell/Clojure/Racket/Prolog a list of pairs):***
```
(A : 20) - (B : 114) - (C : 50) - (W : 0)
```

where A, B, C, W are the categories, 20 is the sum of the unique book of category A, 114 the sum corresponding to "BKWRK" and "BTSQZ", 50 corresponding to "CDXEF" and 0 to category 'W' since there are no code beginning with W.

If L or M are empty return string is ``` "" ``` (Clojure/Racket/Prolog should return an empty array/list instead).

***Notes:***
In the result codes and their values are in the same order as in M.
See "Samples Tests" for the return.

**Link to the kata** <br/>
[Help_the_bookseller](https://www.codewars.com/kata/54dc6f5a224c26032800005c/java)

## Solution

```java

public static String stockSummary(String[] lstOfArt, String[] lstOf1stLetter) {

        if(lstOfArt.length == 0 || lstOf1stLetter.length == 0) return "";

        // To count the total quantity
        int total = 0;
        // To produce the result string
        String result = "";

        for ( int i =0; i < lstOf1stLetter.length; i++) {
           // reset total at each iteration
           total = 0;

            for (int j = 0; j < lstOfArt.length; j++) {

                // Add total quantity if the first CharAt(0) matches then replace all non numbers else 0
                total+= lstOfArt[j].charAt(0) == (lstOf1stLetter[i].charAt(0)) ? Integer.parseInt(lstOfArt[j].replaceAll("[^0-9]" , "")) : 0;


            }

            // Construct the string
            result +=  " - (" + lstOf1stLetter[i] + " : " + total + ")";
        }

            // substring to delete the first 3 characters at each iteration
            return result.substring(3);

        }
        
 ```
