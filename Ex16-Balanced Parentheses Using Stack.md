# Ex16 Check for Balanced Parentheses Using Stack

## DATE: 19-09-2026

## AIM:

To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket `(`, `{`, `[` has a corresponding and correctly ordered closing bracket `)`, `}`, `]`.

## Algorithm

1. Start and create an empty stack to store the opening brackets.
2. Read the input string and traverse each character.
3. If the character is an opening bracket `(`, `{`, `[`, push it into the stack.
4. If the character is a closing bracket, check whether it matches the top opening bracket; if not, the brackets are unbalanced.
5. After traversing the string, if the stack is empty, the brackets are balanced; otherwise, they are unbalanced.

## Program:

```java
/*
Program to verify whether the parentheses (brackets) in an input string are balanced.
Developed by: N Laxmi Priya
RegisterNumber: 212225040196
*/

import java.util.*;

public class Main {

    // Method to check balanced parentheses
    static boolean isBalanced(String str) {

        Stack<Character> stack = new Stack<>();

        for (char ch : str.toCharArray()) {

            // Push opening brackets
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            }

            // Check closing brackets
            else if (ch == ')' || ch == '}' || ch == ']') {

                if (stack.isEmpty()) {
                    return false;
                }

                char top = stack.pop();

                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }

        // Stack must be empty for balanced brackets
        return stack.isEmpty();
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        String str = sc.nextLine();

        if (isBalanced(str)) {
            System.out.println("Balanced Parentheses");
        } else {
            System.out.println("Unbalanced Parentheses");
        }
    }
}
```

## Output:

<img width="368" height="223" alt="image" src="https://github.com/user-attachments/assets/3c166577-7a12-4dab-aad7-356f0090c0c3" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
