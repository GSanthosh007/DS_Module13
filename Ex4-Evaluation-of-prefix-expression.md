Ex4 Evaluation of Prefix Expression
AIM

To write a Java program to evaluate the given prefix expression using a stack and print the result.

Algorithm
1. Start
2. Initialize an empty integer stack.
3. Read the prefix expression as a string.
4. Traverse the expression from right to left.
5. For each character:
      - If it is a digit, convert it to an integer and push it on the stack.
      - If it is an operator, pop two operands from the stack,
        perform the operation, and push the result back.
6. After traversal, the final value on the stack is the result.
7. Print the result.
8. End

Program:
```
/*
Program to evaluate the given prefix expression
Developed by: Santhosh G
Register Number: 212223240152
*/

import java.util.Stack;

public class PrefixEvaluation {

    public static int evaluatePrefix(String expr) {
        Stack<Integer> stack = new Stack<>();

        // Traverse from right to left
        for (int i = expr.length() - 1; i >= 0; i--) {
            char ch = expr.charAt(i);

            // If digit, push to stack
            if (Character.isDigit(ch)) {
                stack.push(ch - '0');
            } else {
                // Operator: pop two operands
                int n1 = stack.pop();
                int n2 = stack.pop();
                int result = 0;

                switch (ch) {
                    case '+':
                        result = n1 + n2;
                        break;
                    case '-':
                        result = n1 - n2;
                        break;
                    case '*':
                        result = n1 * n2;
                        break;
                    case '/':
                        result = n1 / n2;
                        break;
                }
                stack.push(result);
            }
        }

        return stack.pop();
    }

    public static void main(String[] args) {
        String prefix = "+9*26"; // Example prefix expression
        int result = evaluatePrefix(prefix);
        System.out.println("Result: " + result);
    }
}

Output

![image](https://github.com/user-attachments/assets/98c230d3-2e9c-4157-ad37-40519e5219cd)

Result

Thus, the Java program to evaluate the prefix expression using a stack is executed successfully.
