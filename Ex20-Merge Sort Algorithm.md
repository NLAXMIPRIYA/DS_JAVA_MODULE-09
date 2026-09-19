# Ex20 Sorting an Array using Merge Sort Algorithm

## DATE: 19-09-2026

## AIM:
To design a Java program that sorts a given array of integers in ascending order using the Merge Sort algorithm without using built-in sorting functions, achieving O(n log n) time complexity.

## Algorithm

1. Read the number of elements and the elements of the array.
2. Divide the array into two halves recursively until each subarray contains one element.
3. Compare the elements of the two sorted halves and merge them in ascending order.
4. Continue merging the subarrays until the complete array is sorted.
5. Display the sorted array.

## Program:

```java
/*
Program to sort a given array of integers in ascending order
using the Merge Sort algorithm without using built-in sorting functions.
Developed by: N Laxmi Priya
RegisterNumber: 212225040196
*/

import java.util.*;

public class Main {

    // Function to merge two sorted parts
    static void merge(int[] arr, int left, int mid, int right) {

        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] L = new int[n1];
        int[] R = new int[n2];

        for (int i = 0; i < n1; i++) {
            L[i] = arr[left + i];
        }

        for (int j = 0; j < n2; j++) {
            R[j] = arr[mid + 1 + j];
        }

        int i = 0;
        int j = 0;
        int k = left;

        // Merge the two arrays
        while (i < n1 && j < n2) {

            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }

            k++;
        }

        // Copy remaining elements of L
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements of R
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    // Function to perform Merge Sort
    static void mergeSort(int[] arr, int left, int right) {

        if (left < right) {

            int mid = left + (right - left) / 2;

            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            merge(arr, left, mid, right);
        }
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();

        int[] arr = new int[n];

        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        mergeSort(arr, 0, n - 1);

        System.out.println("Sorted array:");

        for (int i = 0; i < n; i++) {
            System.out.print(arr[i] + " ");
        }
    }
}
```

## Output:

<img width="377" height="213" alt="image" src="https://github.com/user-attachments/assets/22ad55d3-58af-434b-a041-fc161e2cbfbb" />


## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
