
## Instructions about the Kata

Middle Earth is about to go to war. The forces of good will have many battles with the forces of evil. Different races will certainly be involved. Each race has a certain **worth** when battling against others. On the side of good we have the following races, with their associated **worth**:

- Hobbits: 1 <br/>
- Men: 2 <br/> 
- Elves: 3 <br/>
- Dwarves: 3 <br/>
- Eagles: 4 <br/>
- Wizards: 10 <br/>
On the side of evil we have: <br/>

- Orcs: 1 <br/>
- Men: 2 <br/>
- Wargs: 2 <br/>
- Goblins: 2 <br/>
- Uruk Hai: 3 <br/>
- Trolls: 5 <br/>
- Wizards: 10 <br/>


Although weather, location, supplies and valor play a part in any battle, if you add up the worth of the side of good and compare it with the worth of the side of evil, the side with the larger worth will tend to win.

Thus, given the count of each of the races on the side of good, followed by the count of each of the races on the side of evil, determine which side wins.

***Input***:
The function will be given two parameters. Each parameter will be a string of multiple integers separated by a single space. Each string will contain the count of each race on the side of good and evil.

The first parameter will contain the count of each race on the side of good in the following order:

- Hobbits, Men, Elves, Dwarves, Eagles, Wizards.

The second parameter will contain the count of each race on the side of evil in the following order:

- Orcs, Men, Wargs, Goblins, Uruk Hai, Trolls, Wizards.


All values are non-negative integers. The resulting sum of the worth for each side will not exceed the limit of a 32-bit integer.

***Output***:
```java
Return "Battle Result: Good triumphs over Evil" 
if good wins, "Battle Result: Evil eradicates all trace of Good" if evil wins, 
or "Battle Result: No victor on this battle field" if it ends in a tie.
```
 
**Link to the kata** <br/>
[GoodVsEvil](https://www.codewars.com/kata/52761ee4cffbc69732000738/java)

## Solution

```java
public class GoodVsEvil {
  public static String battle(String goodAmounts, String evilAmounts) {
    
        //Establish the good and evil worth array
        int[] goodWorth = {1,2,3,3,4,10};
        int[] evilWorth = {1,2,2,2,3,5,10};

        //Split the string of nums to an array
        String[] arrayStrGood = goodAmounts.split(" ");
        String[] arrayStrEvil = evilAmounts.split(" ");

        //Establish the initial value to hold the sum
        int sumOfGood =0;
        int sumOfEvil = 0;


        // for loop to process the good army
        for (int i = 0; i < arrayStrGood.length; i++) {
            // Convert each string num to int
            int strNumToIntGood = Integer.parseInt(arrayStrGood[i]);

            sumOfGood+=strNumToIntGood * goodWorth[i];

        }

        // for loop to process the evil army
        for (int i = 0; i < arrayStrEvil.length; i++) {
            // Convert each string num to int
            int strNumToIntEvil = Integer.parseInt(arrayStrEvil[i]);

            sumOfEvil+=strNumToIntEvil * evilWorth[i];

        }


        // Establish the logic and return the result
          return sumOfGood > sumOfEvil ?  "Battle Result: Good triumphs over Evil" :
                sumOfEvil > sumOfGood ? "Battle Result: Evil eradicates all trace of Good" :
                                    "Battle Result: No victor on this battle field";
  }
```
