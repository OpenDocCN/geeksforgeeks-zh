# 寻找前 N 个偶数索引的斐波那契数列的和的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-find-sum-of-fibonacci-series-numbers-of-first-n-even-indexes/](https://www.geeksforgeeks.org/java-program-to-find-sum-of-fibonacci-series-numbers-of-first-n-even-indexes/)

对于给定的正整数 `N`，目的是求 `F2+F4+F6+……+F2n` 直到 `N` 个数的值。其中 `Fi` 表示第 `i` 个斐波那契数。

斐波那契数列是下面给出的整数序列中的数字。

```java
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ……
```

**示例:**

```java
Input: n = 4
Output: 33
N = 4, So here the fibonacci series will be produced from 0th term till 8th term:
0, 1, 1, 2, 3, 5, 8, 13, 21
Sum of numbers at even indexes = 0 + 1 + 3 + 8 + 21 = 33.

Input: n = 7
Output: 609
0 + 1 + 3 + 8 + 21 + 55 + 144 + 377 = 609.
```

## 方法 1:

找出 `2n` 之前的所有斐波那契数，只将偶数指数相加。

```java
// Java Program to find even sum of
// fibonacci Series Till number N
import java.io.*;

class geeksforgeeks {

    // Computing the value of first fibonacci series
    // and storing the sum of even indexed numbers
    static int Fib_Even_Sum(int N)
    {
        if (N <= 0)
            return 0;

        int fib[] = new int[2 * N + 1];
        fib[0] = 0;
        fib[1] = 1;

        // Initializing the sum
        int s = 0;

        // Adding remaining numbers
        for (int j = 2; j <= 2 * N; j++) {
            fib[j] = fib[j - 1] + fib[j - 2];

            // Only considering even indexes
            if (j % 2 == 0)
                s += fib[j];
        }

        return s;
    }

    // The Driver code
    public static void main(String[] args)
    {
        int N = 11;

        // Prints the sum of even-indexed numbers
        System.out.println(
            "Even sum of fibonacci series till number " + N
            + " is: " + +Fib_Even_Sum(N));
    }
}
```

**Output**

```java
Even sum of fibonacci series till number 11 is: 28656
```

**时间复杂度:** `O(n)`

## 方法 2:

可以清楚地看到，这样就可以得到所需的总和:
`2(F2+F4+F6+……+F2n)` = `(F1+F2+F3+F4+……+F2n)`

现在，如果我们把 `2n` 而不是 `n` 放在这里给出的公式中，就可以得到第一项。

因此 `F1+F2+F3+F4+……+F2n` = `F2n+2–1`。

如果我们在这里给出的公式中用 `2n` 代替 `n`，也可以找到第二项

因此，`F1–F2+F3–F4+……-F2n` = `1+(-1)2n+1F2n-1` = `1–F2n-1`。

例如，`2(f2+f4+f6+...+f2n)` = `f2n+2–1–1+f2n-1` = `f2n+2+f2n-1` - 2

任务是只找到 `F2n+1` -1。

下面是上述方法的实现:

```java
// Java Program to find even indexed
// Fibonacci Sum in O(Log n) time.

class GFG {

    static int MAX = 1000;

    // Create an array for memoization
    static int f[] = new int[MAX];

    // Returns n'th Fibonacci number
    // using table f[]
    static int fib(int n)
    {
        // Base cases
        if (n == 0) {
            return 0;
        }
        if (n == 1 || n == 2) {
            return (f[n] = 1);
        }

        // If fib(n) is already computed
        if (f[n] == 1) {
            return f[n];
        }

        int k = (n % 2 == 1) ? (n + 1) / 2 : n / 2;

        // Applying above formula [Note value n&1 is 1
        // if n is odd, else 0].
        f[n] = (n % 2 == 1)
                   ? (fib(k) * fib(k)
                      + fib(k - 1) * fib(k - 1))
                   : (2 * fib(k - 1) + fib(k)) * fib(k);

        return f[n];
    }

    // Computes value of even-indexed Fibonacci Sum
    static int calculateEvenSum(int n)
    {
        return (fib(2 * n + 1) - 1);
    }

    // Driver program to test above function
    public static void main(String[] args)
    {
        // Get n
        int n = 11;

        // Find the alternating sum
        System.out.println(
            "Even indexed Fibonacci Sum upto " + n
            + " terms: " + calculateEvenSum(n));
    }
}
```

**Output**

```java
Even indexed Fibonacci Sum upto 8 terms: 1596
```

**时间复杂度:** `O(对数 n)`