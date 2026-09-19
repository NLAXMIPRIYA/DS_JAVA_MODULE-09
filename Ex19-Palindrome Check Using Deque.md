# Ex19 Palindrome Check Using Deque

## DATE: 19-09-2026

## AIM:

To design a Java program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm

1. Start and read the given message as a string.
2. Remove all non-alphanumeric characters and convert the remaining characters to lowercase.
3. Insert each character of the cleaned string into a deque.
4. Remove and compare characters from the front and rear of the deque until the deque becomes empty or a mismatch is found.
5. Stop and display whether the given message is a palindrome or not.

## Program:

```java
/*
Program to check whether a given message is a palindrome by removing
all non-alphanumeric characters and using a deque.
Developed by: N Laxmi Priya
RegisterNumber: 212225040196
*/

import java.util.*;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        String message = sc.nextLine();

        // Remove non-alphanumeric characters
        // and convert to lowercase
        String cleaned = message.replaceAll("[^a-zA-Z0-9]", "")
                                .toLowerCase();

        // Create deque
        Deque<Character> deque = new ArrayDeque<>();

        // Add characters to deque
        for (int i = 0; i < cleaned.length(); i++) {
            deque.addLast(cleaned.charAt(i));
        }

        boolean palindrome = true;

        // Compare characters from both ends
        while (deque.size() > 1) {

            char first = deque.removeFirst();
            char last = deque.removeLast();

            if (first != last) {
                palindrome = false;
                break;
            }
        }

        if (palindrome) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a Palindrome");
        }
    }
}
```

## Output:

<img width="379" height="314" alt="image" src="https://github.com/user-attachments/assets/5385a884-d2a9-4177-8b5d-ddb1da6cca5d" />


## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
