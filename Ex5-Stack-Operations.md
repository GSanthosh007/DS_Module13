Ex5 Stack Operations
AIM

To write a Java program to perform push and pop operations of a stack for use in infix-to-postfix conversion.

Algorithm
1. Initialize top as -1 and declare stack as a character array.
2. For push operation:
      - Increment top.
      - Store the character in stack[top].
3. For pop operation:
      - If top is -1, return a special value (e.g., '\0') indicating underflow.
      - Otherwise, return stack[top] and decrement top.

Program
```
/*
Program to perform push and pop operations of the stack
Developed by: Santhosh G
Register Number: 212223240152
*/

class CharStack {
    private char[] stack = new char[100];
    private int top = -1;

    // Push operation
    public void push(char x) {
        stack[++top] = x;
    }

    // Pop operation
    public char pop() {
        if (top == -1) {
            return '\0';   // Indicates stack underflow
        } else {
            return stack[top--];
        }
    }
}

public class StackOperations {
    public static void main(String[] args) {
        CharStack s = new CharStack();

        // Example push
        s.push('A');
        s.push('B');
        s.push('C');

        // Example pop
        System.out.println("Popped element: " + s.pop()); // Output: C
        System.out.println("Popped element: " + s.pop()); // Output: B
    }
}
```

Output

![image](https://github.com/user-attachments/assets/a38787c7-b24a-4ad8-9f06-16c5b428d6b5)

Result

Thus, the Java program to perform push and pop operations of the stack for infix-to-postfix conversion is implemented successfully.
