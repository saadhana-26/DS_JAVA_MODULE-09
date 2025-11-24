# Ex19 Palindrome Check Using Deque
## DATE:23/11/25
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Start the program.
2. Read an input string from the user.
3. Remove all non-alphanumeric characters from the string.
4. Convert all characters to lowercase for uniform comparison.
5. Create a deque (double-ended queue).
6. Insert each character of the cleaned string into the deque.
7. If all pairs match, the string is a palindrome.
8. Display the result.
  

## Program:

/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: SAADHANA L
RegisterNumber:  212224060224
*/
~~~
import java.util.*;

public class PalindromeChecker {
    
    public static boolean isPalindrome(String message) {
        // Convert to lowercase and remove non-alphanumeric characters
        message = message.toLowerCase().replaceAll("[^a-z0-9]", "");
        
        Deque<Character> deque = new ArrayDeque<>();
        
        // Add all characters to the deque
        for (char c : message.toCharArray()) {
            deque.addLast(c);
        }
        
        // Compare characters from both ends
        while (deque.size() > 1) {
            if (deque.pollFirst() != deque.pollLast()) {
                return false;  // Mismatch found
            }
        }
        
        return true;  // All characters matched
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        //System.out.println("Enter a message:");
        String input = scanner.nextLine();

        if (isPalindrome(input)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a palindrome");
        }

        scanner.close();
    }
}
~~~

## Output:

<img width="384" height="136" alt="image" src="https://github.com/user-attachments/assets/380a1e14-1106-4584-aa8e-434d767f68ff" />


## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
