## EX 1 Display Operator Precedence in the Postfix Expression
## AIM:
To write a Java program to find and display the priority of operators in the given postfix expression.

## Algorithm
1. Start the program.
2. Define a function priority() that returns the precedence value of operators.
3. Initialize the postfix expression as a string.
4. Traverse the expression character by character.
5. For each operator, call priority() to get its precedence.
6. Display the operator along with its precedence level.
7. End.

## Program :
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

public class OperatorPriority {

    public static int priority(char op) {
        switch (op) {
            case '+':
                return 2;
            case '/':
            case '*':
                return 3;
            case '|':
                return 1;
            default:
                return -1;
        }
    }

    public static void main(String[] args) {

        String expression = "100 200 + 2 / 5 * 7|";

        for (int i = 0; i < expression.length(); i++) {
            char ch = expression.charAt(i);

            if (ch == '+' || ch == '/' || ch == '*' || ch == '|') {
                int pr = priority(ch);
                System.out.print(ch + " ----> ");

                switch (pr) {
                    case 1:
                        System.out.println("Lowest Priority");
                        break;
                    case 2:
                        System.out.println("Second Lowest Priority");
                        break;
                    case 3:
                        System.out.println("Second Highest Priority");
                        break;
                    default:
                        System.out.println("Unknown Priority");
                }
            }
        }
    }
}
```

## Output:

![image](https://github.com/user-attachments/assets/36fea1ca-9c5a-4d6b-8909-cb4b9d90e3e5)


## Result:
Thus, the Java program to find and display the priority of operators in the given postfix expression is successfully implemented.
