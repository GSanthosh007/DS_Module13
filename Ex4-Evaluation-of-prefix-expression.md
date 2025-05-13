# Ex4 Evaluation of prefix expression
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
```
1. Start
2.Initialize an empty stack s with a variable top for tracking the stack index.
3.Define a push() function to add an element to the stack.
4.Define a pop() function to remove and return the top element from the stack.
5.In evalprefix(), loop through the given prefix expression from right to left.
6.For each character, if it’s an operator (+, *), pop two operands from the stack, perform the operation, and push the result.
7.If it's a digit, convert it to an integer and push it onto the stack; finally, print the result after the loop ends.
8.End

```  

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: Stephen raj Y
RegisterNumber:  212223230217
*/
#include <stdio.h>
#include <ctype.h>
#include <string.h>

int stack[20];
int top = -1;

void push(int x) {
    stack[++top] = x;
}

int pop() {
    return stack[top--];
}

void evalprefix(char *symbol) {
    int num, n1, n2, n3;
    int len = strlen(symbol);


    for (int i = len - 1; i >= 0; i--) {
        if (isdigit(symbol[i])) {
            num = symbol[i] - 48; 
            push(num);
        } else {
            n1 = pop();
            n2 = pop();

            switch (symbol[i]) {
                case '+':
                    n3 = n2 + n1;
                    break;
                case '-':
                    n3 = n1 - n2;
                    break;
                case '*':
                    n3 = n1 * n2;
                    break;
                case '/':
                    n3 = n1 / n2;
                    break;
            }
            push(n3);
        }
    }
    printf("%d\n", pop()); 
}
```

## Output:

![image](https://github.com/user-attachments/assets/98c230d3-2e9c-4157-ad37-40519e5219cd)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
