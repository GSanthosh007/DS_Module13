# Ex2 Conversion of the infix expression into postfix expression
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
```
1. Start the program.
2.Initialize a stack and set the top index to -1.
3.Define the push() and pop() functions to add and remove elements from the stack.
4.Define the priority() function to assign priorities to operators.
5.Traverse the expression in the IntoPost() function, handling operands, parentheses, and operators.
6.After processing the expression, pop and print any remaining operators from the stack.
7.End.
  ```

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: Stephen raj Y
RegisterNumber:  212223230217
*/
#include<stdio.h>
#include<ctype.h>

char stack[100];
int top = -1;

void push(char x)
{
   top++;
   stack[top]=x;
}

char pop()
{
     return stack[top--];
}
int priority(char x)
{
    if(x==')')
    return 0;
    if(x=='&'||x=='|')
    return 1;
    if(x=='+'||x=='-')
    return 2;
    if(x=='*'||x=='/'||x=='%')
    return 3;
    if(x=='^')
    return 4;
    return 0;
}
char IntoPost(char *exp)
{
    char *symbol,x;
    symbol=exp;
    while(*symbol!='\0')
    {
        if(isalnum(*symbol))
        
        printf("%c ",*symbol);
        
        else if(*symbol=='(')
        
        push(*symbol);
        else if(*symbol==')')
        {
            while((x=pop())!='(')
            printf("%c ",x);
        }
        else
        {
            while(priority(stack[top])>=priority(*symbol))
            printf("%c ",pop());
            push(*symbol);
        }
        symbol++;   
}
while(top != -1)
    {
       printf("%c ",pop());
    }
    return 0;
}
int main()
{
    char exp[100]="2*3%(2-1)+5|3";
    IntoPost(exp);
    return 1;
}
```

## Output:

![image](https://github.com/user-attachments/assets/75926b46-584f-400b-8686-3f3534561757)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
