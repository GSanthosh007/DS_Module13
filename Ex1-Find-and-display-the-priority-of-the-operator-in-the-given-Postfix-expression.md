# EX 1 Display operator precedence in the infix expression.
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
```
1. Start the program.
2.Define the priority() function to return the priority of operators.
3.Initialize the string containing operators and operands.
4.Loop through each character in the string.
5.For each operator, call the priority() function to determine its priority.
6.Print the operator and its corresponding priority level.
7.End.
 ``` 

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Stephen raj Y
RegisterNumber:  212223230217
*/
#include <stdio.h>
#include<string.h>
int function(char y)
{
    switch(y)
    {
        case '+':
        return 2;
        case '/':
        return 3;
        case '*':
        return 3;
        case '|':
        return 1;
        default:
        return -1;
        
    }
    
}
int main()
{
    char expression[]="100 200 + 2 / 5 * 7|";
    char *x = expression;
    while(*x!=0)
    {
        if(*x=='+' || *x=='/'|| *x=='*'||*x=='|')
        {
            int pr = function(*x);
            printf("%c  ----> ",*x);
            switch(pr)
            {
                case 1:
                printf("Lowest Priority\n");
                break;
                case 2:
                printf("Second Lowest Priority\n");
                break;
                case 3:
                printf("Second Highest Priority\n");
                break;
                case 4:
                printf("Second Highest Priority\n");
            }
        }
        x++;
    }
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/36fea1ca-9c5a-4d6b-8909-cb4b9d90e3e5)


## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
