## What. Is Recurion?
Recursion is a **method** that **calls itself** and is conditioned on some **stop parameter**.

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
