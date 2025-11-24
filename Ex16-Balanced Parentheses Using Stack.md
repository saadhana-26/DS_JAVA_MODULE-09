# Ex16 Check for Balanced Parentheses Using Stack
## DATE:23/11/25
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Start the program.
2. Read an input string containing parentheses/brackets.
3. Create a stack to store opening brackets.
4. Traverse each character of the string:
5. If the character is an opening bracket (, {, [, push it onto the stack.
6. Check if the stack is empty: If yes, the string is unbalanced.
7. Otherwise, pop the top element from the stack and verify if it matches the current closing bracket.
8. If the brackets do not match, the string is unbalanced.
9. After traversal:
10. If the stack is empty, the string is balanced; otherwise, it's unbalanced.
11. End the program.

## Program:

/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: SAADHANA L
RegisterNumber:  212224060224
*/
~~~
import java.util.Scanner;

public class ParenChecker {
    static class ArrayStack
    {
        private char[] data;
        private int top;
        public ArrayStack(int capacity)
        {
            data=new char[capacity];
            top=-1;
        }
        public boolean isEmpty()
        {
            return top==-1;
        }
        
        public boolean isFull()
        {
            return top==data.length-1;
        }
        public void push(char c)
        {
            if(isFull())
            {
                System.out.println("Stack overflow");
            }
            data[++top]=c;
        }
        public char pop()
        {
            if(isEmpty())
            {
                System.out.println("Stack underflow");
            }
            return data[top--];
            
            
        }
        public char peek()
        {
            if(isEmpty())
            {
                System.out.println("Stack underflow");
            }
            return data[top];
        }
    }


    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}

~~~
## Output:

<img width="363" height="130" alt="image" src="https://github.com/user-attachments/assets/7296fa18-bb6b-4884-8568-426c468638ee" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
