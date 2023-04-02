# Factors-of-a-number-using-Java


Factors of a number using Java
Find the Factors of a Number in Java
Given an integer number as the input, the objective is to Find all the factors of a Number. Therefore, we’ll write a code to Find the Factors of a Number in Java Language.

Example
Input : 10
Output : 1, 2, 5
find factorial of number using java
Find the Factors of a Number in Java Language
Given an integer input, the objective is to find all the factors of a given integer input but the number itself.

To do so we’ll use loops to iterate through the range from 2 to the number itself and check whether there are any factors within the range. To do so, we’ll use loops to iterate through the range and check if each number is a factor of the number or not.

Once we find that the number is divisible by any number we’ll append it to the factors list or simply print the factors along the way. Here are a few methods to Find the Factors of a Number in Java Language,

Method 1: Using Range as [ 2, number ]
Method 2: Using Range as [ 2, number/2]
Method 3: Using Range as [2, Sqrt( number ) ]
Method 4: Using Range as [2, Sqrt( number ) ] Updated
Method 5: Update for negative numbers
We’ll discuss the above-mentioned methods in detail in the upcoming sections.

Factors of a NumberIn Java
Method 1: Using Range as [ 1, number ]
Take the input of num
Iterate from 1 to num using a for loop as i iterator
Check any given ‘i’ with if it perfectly divides num i.e. num % i == 0
Java Code
Run
public class Main
 {
      public static void main(String[] args) {

      int num = 10;

     System.out.println( "Factors of " + num + " are " );

     // finding and printing factors b/w 1 to num
     for(int i = 1; i <= num; i++)
     {
         if(num % i == 0)
             System.out.println(i + " "); 
     }

      }
 }
// Time Complexity : O(n) 
// Auxiliary Space : O(1)
Output
1 2 5 10
Method 2: Using Range as [ 1, number/2 ]
Since all divisors for any number can be found in the range 1 to num/2 we need to iterate between [ 1, number/2 ]

Take the input of num
Iterate from 1 to num/2 using a for loop as i iterator
Check any given ‘i’ with if it perfectly divides num i.e. num % i == 0
Java Code
Run
class Main
{
    public static void main (String[]args)
    {

        int num = 100;
        getFactors (num);
    }

    static void getFactors (int num)
    {

        for (int i = 1; i <= (num/2); i++)
        {
            if (num % i == 0)
            {
                System.out.print(i + " ");
            }
        }
		// print thenumber itself too
		System.out.print(num);
    }
}
// Time Complexity : O(n) 
// Auxiliary Space : O(1)
// This method is better than previous method, even though the time complexity is the same
// it runs half lesser loop than previous method
// ran for loop num times, however, this runs num/2 times
Output
1 2 4 5 10 20 25 50 100
While loop in C
Related Pages
Factorial of a number

Power of a number

Factor of a number

Finding Prime Factors of a number

Strong number

Perfect number

Method 3: Using Range as [ 1,  Sqrt( number )]
Check the output for finding the divisors of 100: 1, 2, 3, 4, 5, 10, 20, 25, 50

All divisors come in pairs (1, 100), (2, 50), (4, 25), (5, 20), (10, 10)
If you multiple any pair the result will be 100 e.g. : 2 * 50 = 100 or 4 * 25 = 100
If the first pair is ‘i’ then we can find the other pair by doing num/i
All Divisors come in pairs
We can find all smaller pairs by running loop only till √num

Then the larger pair can be found by doing num/i
Note
Just be careful that 10, pair for 10 is 10 again. But, we need to print 10 once

This will happen for all divisors that are square root of number as √100 = 10
Take the input of num
Iterate from 1 to √num using a for loop as i iterator
Check any given ‘i’ with if it perfectly divides num i.e. num % i == 0
If i ==num/i then just print i
else print both i and num/i
Java Code
Run
class Main{

    public static void main(String[] args){
        
        int num = 100;
        getFactors (num);
    }

    static void getFactors (int n)
    {
        for(int i = 1; i <= Math.sqrt(n); ++i)
        {
            if (n % i == 0){
                // If both pair of factors are equal then we just print
                // once, example for 100 : (a, b) : (10, 10)
                // 10 should be printed just once
                if(i == n / i)
                    System.out.print(i + ", ");

                    // else print both the pairs
                else
                    System.out.print(i + ", " + n/i + ", ");
            }
        }
    }
}
// Time Complexity : O(sqrt(N))
// Space Complexity : O(1)
Output
1, 100, 2, 50, 4, 25, 5, 20, 10, 
Method 4: Using Range as [ 1,  Sqrt( number )]  (Update)
The above program doesn’t print divisors in ascending order and prints them in jumbled order. This can be fixed in the program below –

Run
class Main
{
  public static void main (String[]args)
  {

    int num = 100;
      getFactors (num);
  }

  static void getFactors (int num)
  {

     
    // Same i used in other for loop
    int i;
    // to avoid double printing
    boolean flag = false;
    
    for(i = 1; i <= Math.sqrt(num); i++)
    {
        if (num % i == 0)
            System.out.print(i + " ");

        // To avoid double printing of equal pairs 
        // Example (10,10) we only want to print once 
        if(i == num/i) 
            flag = true; 
    } 

    // if flag is true then we had double pairs like (10,10) 
    // we should do i-- so as not to do double printing of pair divisor 
    // doing i -=2 rather than i-- as in previous for loop we exited 
    // with i++, example, i = 10 became 11 and we need to start with 9 
    // so as to ignore 10 as its a double pair 
    if(flag)
        i -= 2; 

    // printing pairs 
    for(; i >= 1; i--)
    {
        if (num % i == 0)
            System.out.print(num/i + " ");
    } 
  }
}
// Time Complexity : O(sqrt(N))
// Space Complexity : O(1)
Output
1 2 5 10 20 25 50 100
Method 5: For negative numbers
Negative numbers are unique cases for them both positive and negative divisors will be their example –

Factors of -100 are: -100 -50 -25 -20 -10 -5 -4 -2 -1 1 2 4 5 10 20 25 50 100

Below program takes care of it

Run
class Main {

    public static void main(String[] args) {

        // negative number
        int num = -100;
        System.out.print("Factors of " + num + " are: ");

        // Loop runs between -100 to 100 skipping 0
        for(int i = num; i <= Math.abs(num); ++i) {

            // we must skip 0 as iteration
            if(i == 0) {
                continue;
            }
            else {
                if (num % i == 0) {
                    System.out.print(i + " ");
                }
            }
        }
    }
}
// Time complexity : O(N)
// Space complexity : O(1)
Output
Factors of -100 are: -100 -50 -25 -20 -10 -5 -4 -2 -1 1 2 4 5 10 20 25 50 100 
