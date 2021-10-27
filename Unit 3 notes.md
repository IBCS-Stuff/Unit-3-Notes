# Unit 3 Notes



## Console Input
 - Input, despite being necessary for most useful programs, 
is pretty complicated
 - Java has numerous methods for getting input from a bunch 
of different sources
 - keyboard, local files, web pages, network resources, 
etc.
 - For now, we will focus on one simple method for reading 
input from the keyboard


The simplest way to read input from the keyboard is to use a 
Scanner and the predefined stream `System.in`

```
Just below the package line:
package myProject;
import java.util.*;  or import java.util.Scanner;
Then the code goes in main:
Scanner keyboard = new Scanner(System.in);
```

Once you’ve done this, you can read a line of input using the 
nextLine method and store the result in a String

`String input = keyboard.nextLine();`

To read an int, use nextInt:
`int x = keyboard.nextInt();`

Look up Scanner in the Java API for more useful methods


## Parameters

Say we wanted to print this:
```
**********
*****
**************
**
```
 - Think about how to define methods for this...

we could do this:
```
public static void lineOf10 
{
    for(int i = 0; i < 10; i++) 
    {
        System.out.print("*"); 
    }
    System.out.println();
}
public static void lineOf5 
{
    for(int i = 0; i < 5; i++) 
    {
        System.out.print("*"); 
    }
    System.out.println();
}
public static void lineOf14 
{
    for(int i = 0; i < 14; i++) 
    {
        System.out.print("*"); 
    }
    System.out.println();
}
```

 - In many cases, we need or want additional information 
for our methods
 - For example, when we want to do almost the exact same 
thing
 - We can get this information using parameters
 - Parameters are closely related to arguments
  - When defining the function, we have parameters or formal 
arguments
 - When calling a function, we have actual arguments, or 
simply arguments
 - In reality, we will often use these terms interchangibly

 - We add parameters to our methods by specifying the 
types and names in the prototype
```
public static void printProduct(int a, 
int b)
```
 - Parameter declarations have the same rules as variable 
declarations
 - Parameters have the same scope as local variables
 - Once we have declared parameters, we can use them 
in the method body
 - The parameters will take the values specified by the 
argument each time the method is called

example:
```
public static void printSum(int a, int b) 
{
System.out.println(a + b);
}
public static void hasOddLength(String str) 
{
System.out.println(str.length() % 2 != 0);
}
```
When calling a method, you must provide the correct 
number and type of arguments:

```
public static void main(String[] args) 
{ 
Scanner kb = new Scanner(System.in);
System.out.print(“Enter a string: ”);
String input = kb.nextLine();
  System.out.println("Is the length of that 
odd?");
hasOddLength(input);
}
public static void hasOddLength(String str) { 
... }
```

 - Overloading: two or methods with the same name, but with 
different unique parameters (count of parameters, and 
data types)
 - Examples:
 - public static void drawbox()   //uses default 
sizes
  public static void drawbox(int a)  // draws a 
square box
 - public static void drawbox (int a, int b) // 
draws a rectangle

## Return Values

 - Parameters allow the caller to give information to 
the callee
 - To go the other way around, we use return values
 - A return value is a value that is the result of a 
method call
 -  At the call site, the method call evaluates to the return 
value


We've seen this already:
```
String str = "Hello!";
String short = str.substring(1, 3);
```
 - substring returns a value (namely, the chunk 
of the string we asked for)
 - When a method returns a value, we must do 
something with that value
 - Store it in a variable, pass it as a parameter, print it 
out, etc.
 - If we don't, the value is simply lost

## The Math Class

 - The Math class in the Java Class Library includes a 
bunch of methods that return values
• `Math.abs()` - absolute value
• `Math.pow()` - exponentiation
• `Math.max()`, `Math.min()` - maximum and minimum
• `Math.sin()`, `Math.cos()`, `Math.tan()` - trig functions
• `Math.toRadians()` to convert from degrees
• Etc.
 - When  you use these, remember to save the return 
values


## About Libraries

 - Libraries are useful collections of objects (and 
their state/methods) and methods that are either 
freely available, or for-purchase
 - math, io, others are installed with Java
 - others can be added to your project
 - The programmer then gets to use these already-
implement objects and methods, rather than write 
them from scratch for each new project

#### Methods that return values

To declare a method that returns a value, make 
two changes:
• Declare the return type instead of using void in the 
prototype
o e.g. public static int add(int x, int y) 
• Add one (or more) return statements to the code
 - A method with a non-void return type MUST 
ALWAYS return a value


```
public static double fahrToCels(double fahr) 
{
double cels = (5.0 / 9.0) * (fahr - 32);
return cels;
}
public static String cutFirstAndLast(String str) 
{
String trimmed = str.substring(1, str.length() - 1);
return trimmed;
}
// can return the expression directly
public static double hypotenuse(int leg1, int leg2) 
{
return Math.sqrt(leg1 * leg1 + leg2 * leg2);
}
```





