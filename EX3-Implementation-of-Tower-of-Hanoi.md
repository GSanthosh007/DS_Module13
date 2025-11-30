## EX3 Implementation of Tower of Hanoi
## AIM:
To write a Java program to implement the Tower of Hanoi using recursion.

## Algorithm:
```
Start the program.
Read the number of disks.
Define a recursive function toh(n, source, destination, auxiliary)
If n == 1, print the move and return.
Recursively move n-1 disks from source → auxiliary using destination.
Move the nth disk from source → destination.
Recursively move n-1 disks from auxiliary → destination using source.
Call the recursive function.
End the program.
```

## Program:
```
Program to implement Tower of Hanoi
Developed by: Santhosh G
RegisterNumber: 212223240152


import java.util.Scanner;

public class TowerOfHanoi {

    public static void toh(int n, char source, char dest, char aux) {
        if (n == 1) {
            System.out.println(source + " to " + dest);
            return;
        }
        toh(n - 1, source, aux, dest);
        System.out.println(source + " to " + dest);
        toh(n - 1, aux, dest, source);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter number of disks: ");
        int n = sc.nextInt();

        System.out.println("The moves involved are:");
        toh(n, 'A', 'C', 'B');  // A = source, C = destination, B = auxiliary

        sc.close();
    }
}
```

## Output:
![image](https://github.com/user-attachments/assets/43f8950e-3ddf-4b3f-9736-cbdf804d7abc)

## Result:
Thus, the Java program to implement the Tower of Hanoi using recursion has been successfully executed.
