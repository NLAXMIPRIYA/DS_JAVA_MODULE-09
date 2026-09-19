# Ex17 Reversing a String Using Stack Data Structure

## DATE: 19-09-2026

## AIM:

To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm

1. Start and read the input string.
2. Create an empty stack to store the characters of the string.
3. Traverse the string and push each character into the stack.
4. Pop each character from the stack and append it to the result string.
5. Stop and display the reversed string.

## Program:

```java
/*
Program to reverse an input string using a stack.
Developed by: N Laxmi Priya
RegisterNumber: 212225040196
*/

import java.util.*;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        String str = sc.nextLine();

        Stack<Character> stack = new Stack<>();

        // Push each character into the stack
        for (int i = 0; i < str.length(); i++) {
            stack.push(str.charAt(i));
        }

        String reversed = "";

        // Pop characters to reverse the string
        while (!stack.isEmpty()) {
            reversed = reversed + stack.pop();
        }

        System.out.println("Reversed String: " + reversed);
    }
}
```

## Output:

<img width="386" height="166" alt="image" src="https://github.com/user-attachments/assets/a2f85ffe-aae4-4060-9156-3b0e3d931b26" />


## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
