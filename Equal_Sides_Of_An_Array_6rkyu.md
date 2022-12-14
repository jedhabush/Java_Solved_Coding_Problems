## Instructions about the Kata

You are going to be given an array of integers. Your job is to take that array and find an index N where the sum of the integers to the left of N is equal to the sum of the integers to the right of N. If there is no index that would make this happen, return -1.

**For example:**

Let's say you are given the array {1,2,3,4,3,2,1}: <br/>
Your function will return the index 3, because at the 3rd position of the array, the sum of left side of the index ({1,2,3}) and the sum of the right side of the index ({3,2,1}) both equal 6.

**Let's look at another one.** <br/>
You are given the array {1,100,50,-51,1,1}: <br/>
Your function will return the index 1, because at the 1st position of the array, the sum of left side of the index ({1}) and the sum of the right side of the index ({50,-51,1,1}) both equal 1.

**Last one:** <br/>
You are given the array {20,10,-80,10,10,15,35} <br/>
At index 0 the left side is {} <br/>
The right side is {10,-80,10,10,15,35} <br/>
They both are equal to 0 when added. (Empty arrays are equal to 0 in this problem) <br/>
Index 0 is the place where the left side and right side are equal. <br/>

**Note:** <br/>
Please remember that in most programming/scripting languages the index of an array starts at 0.

**Input:** <br/>
An integer array of length 0 < arr < 1000. The numbers in the array can be any integer positive or negative.

**Output:** <br/>
The lowest index N where the side to the left of N is equal to the side to the right of N. If you do not find an index that fits these rules, then you will return -1.

**Note:** <br/>
If you are given an array with multiple answers, return the lowest correct index.

**Link to the kata** <br/>
[EqualSidesOfAnArray](https://www.codewars.com/kata/5679aa472b8f57fb8c000047/java)

## Solution

```java

public class Kata {
  public static int EqualSides(int[] arr) {

        for (int i = 0; i < arr.length; i++) {

            if(leftSide(arr,i) == rightSide(arr,i)){
                return i;

            }
        }

        return -1;
    }


  public static long leftSide(int[] arr , int idx){
  
        long result = 0;

        for (int i = 0; i < idx; i++) {
            result += arr[i];
        }

        return result;

    }

  public static long rightSide(int[]arr , int idx){

        long result = 0;
        
        for (int i = idx + 1; i < arr.length; i++) {
            result += arr[i];
        }

        return result;
      }
    }
    
   ```
