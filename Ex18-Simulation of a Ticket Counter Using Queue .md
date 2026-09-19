# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)

## DATE: 19-09-2026

## AIM:

To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.

## Algorithm

1. Start and create a queue using a linked list with `front` and `rear` pointers.
2. Read the number of customers and insert each customer into the queue using the `enqueue` operation.
3. Remove customers from the front of the queue using the `dequeue` operation.
4. Display each customer as they are served, maintaining the FIFO order.
5. Stop the program after all customers have been served.

## Program:

```java
/*
Program to simulate the functioning of a ticket counter that operates
on a First-In-First-Out (FIFO) basis using a linked list.
Developed by: N Laxmi Priya
RegisterNumber: 212225040196
*/

import java.util.Scanner;

public class Main {

    // Node class
    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    // Queue class
    static class Queue {
        Node front;
        Node rear;

        // Add customer to the queue
        void enqueue(int data) {

            Node newNode = new Node(data);

            if (rear == null) {
                front = rear = newNode;
            } else {
                rear.next = newNode;
                rear = newNode;
            }
        }

        // Remove customer from the queue
        int dequeue() {

            if (front == null) {
                return -1;
            }

            int value = front.data;
            front = front.next;

            if (front == null) {
                rear = null;
            }

            return value;
        }

        // Check whether queue is empty
        boolean isEmpty() {
            return front == null;
        }
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        Queue queue = new Queue();

        int n = sc.nextInt();

        // Add customers to the queue
        for (int i = 0; i < n; i++) {
            int customer = sc.nextInt();
            queue.enqueue(customer);
        }

        System.out.println("Customers served:");

        // Serve customers in FIFO order
        while (!queue.isEmpty()) {
            System.out.println("Customer " + queue.dequeue());
        }
    }
}terNumber:  
*/
```

## Output:

<img width="373" height="218" alt="image" src="https://github.com/user-attachments/assets/46bd7ce5-98b1-4ec1-b240-016a32c47edb" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
