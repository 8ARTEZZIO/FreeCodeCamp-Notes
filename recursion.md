# What. Is Recurion?
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

## Divide & Conquer

1. Divide problem into several smaller subproblems.                                Normally, the subproblems are similar to the original
2. Conquer the subproblems by solving them recursively                             Base case: solve small enough problems by brute force
3. Combine the solutions to get a solution to the subproblems                      And finally a solution to the original problem
4. Divide and Conquer algorithms are normally recursive
