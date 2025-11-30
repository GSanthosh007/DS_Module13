## Ex2 Conversion of the Infix Expression into Postfix Expression
## AIM:
To write a Java program to convert the infix expression into postfix form using a stack by following operator precedence and associativity rules.

## Algorithm
1. Start the program.
2. Initialize a stack for operators.
3. Define a function priority() to assign precedence values to operators.
4. Traverse each character in the infix expression:
   a. If it is an operand, print it.
   b. If it is '(', push it onto the stack.
   c. If it is ')', pop and print until '(' is encountered.
   d. If it is an operator:
       - Pop and print operators from stack having higher or equal priority.
       - Push current operator onto stack.
5. After processing the entire expression, pop and print all remaining operators.
6. End.

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

import java.util.Stack;

public class InfixToPostfix {

    public static int priority(char x) {
        switch (x) {
            case ')': return 0;
            case '&':
            case '|': return 1;
            case '+':
            case '-': return 2;
            case '*':
            case '/':
            case '%': return 3;
            case '^': return 4;
            default: return 0;
        }
    }

    public static void infixToPostfix(String exp) {
        Stack<Character> stack = new Stack<>();

        for (int i = 0; i < exp.length(); i++) {
            char ch = exp.charAt(i);

            if (Character.isLetterOrDigit(ch)) {
                System.out.print(ch + " ");
            }
            else if (ch == '(') {
                stack.push(ch);
            }
            else if (ch == ')') {
                while (!stack.isEmpty() && stack.peek() != '(') {
                    System.out.print(stack.pop() + " ");
                }
                stack.pop();
            }
            else {
                while (!stack.isEmpty() && priority(stack.peek()) >= priority(ch)) {
                    System.out.print(stack.pop() + " ");
                }
                stack.push(ch);
            }
        }

        while (!stack.isEmpty()) {
            System.out.print(stack.pop() + " ");
        }
    }

    public static void main(String[] args) {
        String exp = "2*3%(2-1)+5|3";
        infixToPostfix(exp);
    }
}
```

## Output:

![image](https://github.com/user-attachments/assets/75926b46-584f-400b-8686-3f3534561757)


## Result:
Thus, the Java program to convert the infix expression into postfix form using stack and operator precedence has been successfully implemented.
