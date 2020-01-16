# Recursion-Practice
Complete the Recursion.java program with the implementation of at least 2 of the methods below
1. Triangle Pattern
  public static void triangle(int m, int n)
  // Precondition: m <= n
  // Postcondition: The method has printed a pattern of 2*(n-m+1) lines
  // to the standard output. The first line contains m asterisks, the next 
  // line contains m+1 asterisks, and so on up to a line with n asterisks.
  // Then the pattern is repeated backwards, going n back down to m.
  /* Example output:
     triangle(3, 5) will print this:
     ***
     ****
     *****
     *****
     ****
     ***
  */
Hint: Only one of the arguments changes in the recursive call. Which one?
2. Section Numbers
  public static void numbers(String prefix, int levels)
The method prints output consisting of the String prefix followed by "section numbers" of the form 1.1., 1.2., 1.3., and so on. The levels argument determines how may levels the section numbers have. For example, if levels is 2, then the section numbers have the form x.y. If levels is 3, then section numbers have the form x.y.z. The digits permitted in each level are always '1' through '9'. As an example, if prefix is the string "THERBLIG" and levels is 2, then the method would start by printing:
THERBLIG1.1.
THERBLIG1.2.
THERBLIG1.3.
and end by printing:
THERBLIG9.7.
THERBLIG9.8.
THERBLIG9.9.
The stopping case occurs when levels reaches zero (in which case the prefix is printed once by itself followed by nothing else).
The Java String class has many manipulation methods, but you'll need only the ability to make a new string which consists of prefix followed by another character (such as '1') and a period ('.'). If s is the String that you want to create and c is the digit character (such as '1'), then the following statement will correctly form s:

  s = prefix + c + '.';
This new String s can be passed as a parameter to recursive calls of the method.
3. A Teddy Bear Picnic

This question involves a game with teddy bears. The game starts when I give you some bears. You can then give back some bears, but you must follow these rules (where n is the number of bears that you have):

If n is even, then you may give back exactly n/2 bears.
If n is divisible by 3 or 4, then you may multiply the last two digits of n and give back this many bears. (By the way, the last digit of n is n%10, and the next-to-last digit is ((n%100)/10).
If n is divisible by 5, then you may give back exactly 42 bears.
The goal of the game is to end up with EXACTLY 42 bears.
For example, suppose that you start with 250 bears. Then you could make these moves:

--Start with 250 bears.
--Since 250 is divisible by 5, you may return 42 of the bears, leaving you with 208 bears.
--Since 208 is even, you may return half of the bears, leaving you with 104 bears.
--Since 104 is even, you may return half of the bears, leaving you with 52 bears.
--Since 52 is divisible by 4, you may multiply the last two digits (resulting in 10) and return these 10 bears. This leaves you with 42 bears.
--You have reached the goal!
Write a recursive method to meet this specification:

   public static boolean bears(int n)
   // Postcondition: A true return value means that it is possible to win
   // the bear game by starting with n bears. A false return value means that
   // it is not possible to win the bear game by starting with n bears.
   // Examples:
   //   bear(250) is true (as shown above)
   //   bear(42) is true
   //   bear(84) is true
   //   bear(53) is false
   //   bear(41) is false
Hint: To test whether n is even, use the expression ((n % 2) == 0).
4. A Fractal Pattern

Examine this pattern of asterisks and blanks, and write a recursive method that can generate patterns such as this:
*
* * 
  *
* * * *
    *
    * *
      *
* * * * * * * *
        *
        * *
          *
        * * * *
            *
            * *
              *
With recursive thinking, the method needs only seven or eight lines of code (including two recursive calls). Your method should look like this:
  public static void pattern(int n, int i)
  // Precondition: n is a power of 2 greater than zero.
  // Postcondition: A pattern based on the above example has been
  // printed. The longest line of the pattern has
  // n stars beginning in column i of the output. For example,
  // The above pattern is produced by the call pattern(8, 0).
Hints: You do not need to check the precondition. Think about how the pattern is a fractal. Can you find two smaller versions of the pattern within the large pattern? Here is some code that may be useful within your method:
  // A loop to print exactly i spaces:
  for (k = 0; k < i; k++) System.out.print(" ");
  // A loop to print n asterisks, each one followed by a space:
  for (k = 0; k < n; k++) System.out.print("* ");
5. A Pattern of Letters
  public static void letters(char c)
  // Precondition: c is one of the characters 'A' through 'Z'.
  // Postcondition: The method has printed a pattern of letters
  // as follows:
  // 1. If the parameter c is 'A', then the output is 'A'.
  // 2. For other values of c, the output consists of three parts:
  //    -- the output for the previous letter (c-1);
  //    -- followed by the letter c itself;
  //    -- followed by a second copy of the output for the previous letter.
  // There is no '\n' printed at the end of the output.
  /* Example output:
     letters('D') will print this to cout:
     ABACABADABACABA
  */
6. One Binary Number

Write a method with this specification:
  public static void binaryPrint(int n)
The number n is non-negative. The method prints the value of n as a BINARY number. If n is zero, then a single zero is printed; otherwise no leading zeros are printed in the output. The '\n' character is NOT printed at the end of the output.
EXAMPLES:
  n=0  Output:0
  n=4  Output:100
  n=27 Output:11011
NOTE: Your recursive implementation must not use any local variables.
7. Sequence of Binary Numbers

Write a method with this specification:
  public static void numbers(String prefix, int k);
The number k is non-negative. The argument called prefix is a String of 0's and 1's. The method prints a sequence of binary numbers. Each output number consists of the prefix followed by a suffix of exactly k more binary digits (0's or 1's). All possible combinations of the prefix and some k-digit suffix are printed. As an example, if prefix is the string "00101" and levels is 2, then the method would print the prefix followed by the 4 possible suffixes shown here:
0010100
0010101
0010110
0010111
The stopping case occurs when k reaches zero (in which case the prefix is printed once by itself followed by nothing else).
