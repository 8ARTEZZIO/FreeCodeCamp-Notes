# What. Is Recursion?
## Recursion is a **method** that **calls itself** and is conditioned on some **stop parameter**.

| Pros | Cons |
| -------- | -------- |
| 1. Brides the gap between elegance and complexity | 1. Slowness due to CPU overhead|
|2. Reduces the need for complex loops and auxiliary data structures|2. Can lead to out of memory errors / stack overflow exceptions|
|3. Can reduce time complexity easily with **memoization**|3. Can be unnecessarily complex if poorly constructed|
|4. Works really well with recursive structures like trees and graphs||

### Call Stack.

```javascript
// Expected output = "hello my friends."
public String A() {
    return "hello " + B();
}

public String B() {
    return "my " + C();
}

public String C() {
    return "friends.";
}
```

### String Reversal.

```javascript
public String reverseString(String input) {
    // What is the base case?
    if (input.equals("")) {
        return "";
    }
    // What is the smallest amount of work I can do in each iteration?
    return reverseString(input.substring(1)) + input.charAt(0);
}
```

### Palindrome.

```javascript
public static boolean isPalindrome(String input) {
    // Define the base-case / stopping condition
    if (input.length() == 0 || input.length() == 1) {
        return true;
    }

    // Do some work to shrink the problem space
    is (input.charAt(0) == input.charAt(input.length() - 1)) {
        return isPalindrome(input.substring(1, input.length() - 1));
    }

    // Additional base-case to handle non-palindromes
    return false;
  }
```

# Recursion with numbers.

## Decimal To Binary.

```javascript
public static String findBinary(int decimal, String result) {
    if (decimal == 0)
        return result;

    result = decimal % 2 + result;
    return findBinary(decimal / 2, result);
  }
```

## Sum of Natural Numbers.

```javascript
public static int recursiveSummation(int inputNumber) {
    if (inputNumber <= 1)
        return inputNumber;
    return inputNumber + recursiveSummation(inputNumber - 1);
}
```

## Divide & Conquer.

1. Divide problem into several smaller subproblems.                                Normally, the subproblems are similar to the original
2. Conquer the subproblems by solving them recursively                             Base case: solve small enough problems by brute force
3. Combine the solutions to get a solution to the subproblems                      And finally a solution to the original problem
4. Divide and Conquer algorithms are normally recursive

### Binary Search.

```javascript
public static int binarySearch(int[] A, int left, int right, int x) {
    if (left > right) {
        return -1;
    }
    int mid = (left + right) / 2;

    if (x == A[mid]) {
        return mid;
    }

    if (x < A[mid]) {
        return binarySearch(A, left, mid - 1, x);
    }

    return binary Search(A, mid + 1, right, x);
}
```

### Fibonacci (Non-Optimized)

```javascript
public static long fib(long n) {
    if ((n==0) || (n==1))
        return n;
    else
        return fib(n-1) + fib(n-2);
}
```

### Merge Sort.

```javascript
public class MergeSrot {
    public static void main(String[] args) {
        int[] data = new int[]{-5, 20, 10, 3, 2, 0}
        mergeSort(data, 0, data.length - 1);
        System.out.println("stop");
    }

    public static void mergeSort(int[], int start, int end) {
        if (start < end) {
            int mid = (start + end) / 2;
            mergeSort(data, start, mid)
            mergeSort(data, mid + 1, end);
            merge(data, start, mid, end);
        }
    }

    public static void merge(int[] data, int start, int mid, int end) {
        // build temp array to avoid modifying the original contents
        int[] temp = new int[end - start + 1];

        int i = start, j = mid + 1, k = 0;

        // while both sub-array have values, then try and merge them in sorted order
        while (i <= mid && j <= end) {
            if (data[i] <= data[j]) {
                temp[k] = data[i];
                i++;
                k++;
            } else {
                temp[k] = data[j];
                k++;
                j++;
            }
        }

        // Add the rest of the values from the left sub-array into the result
        while (i <= mid) {
            temp[k] = data[i];
            k++; i++;
        }

        while (j <= end) {
            temp[k] = data[j];
            k++; j++;
        }

        for (i = start; i <= end; i++) {
            data[i] = temp[i - start];
        }     
}
```
# Linked Lists.

## Linked List Reversal.
