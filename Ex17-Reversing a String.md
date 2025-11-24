# Ex17 Reversing a String Using Stack Data Structure
## DATE:23/11/25
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1. Start the program.
2. Read the input string from the user.
3. Create an empty stack of characters.
4. Traverse the string and push each character onto the stack.
5. Pop each character from the stack and append it to a new string — this gives the reversed string.
6. Display the reversed string.
7. Stop the program.
  

## Program:

/*
Program to reverses an input string using a stack
Developed by: SAADHANA L
RegisterNumber:  212224060224
*/
~~~
import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
         Stack<Character> stack=new Stack<>();
        for(char ch:input.toCharArray())
        {
            stack.push(ch);
        }
        StringBuilder rev=new StringBuilder();
        while(!stack.isEmpty())
        {
            rev.append(stack.pop());
        }
        return rev.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String reversed = reverseString(input);
        System.out.println(reversed);

        scanner.close();
    }
}

~~~
## Output:
<img width="365" height="132" alt="image" src="https://github.com/user-attachments/assets/3eab1d1f-3265-413a-8bb0-c1502731b3bb" />



## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
