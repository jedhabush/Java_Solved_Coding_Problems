## Instructions about the Kata

Given an array of integers.

Return an array, where the first element is the count of positives numbers and the second element is sum of negative numbers. 0 is neither positive nor negative.

If the input is an empty array or is null, return an empty array.

Example <br/>
For input [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15], you should return [10, -65].


## Solution

```java
public class Kata
{
    public static int[] countPositivesSumNegatives(int[] input)
    {
      
      int totalNegativeNums = 0;
      int totalPositiveNums =0;
      
        int[] empty = {};
        int[] arrNull = null;
      
        if(input == arrNull || input.length ==0 ){
            return empty;
        }
      
      for(int i =0; i< input.length; i++){
        
        if(input[i] >=1){
          totalPositiveNums++;
        }
        else if(input[i] <0){
          totalNegativeNums+=input[i];
        }
      }
      
      int[] result = {totalPositiveNums, totalNegativeNums};
        return result; //return an array with count of positives and sum of negatives
    }
}
```
