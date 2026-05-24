# 实现厄拉多塞筛在给定范围内生成素数的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-implement-sieve-of-eratosthenes-to-generate-prime-numbers-between-given-range/](https://www.geeksforgeeks.org/java-program-to-implement-sieve-of-eratosthenes-to-generate-prime-numbers-between-given-range/)

一个能被 1 整除的数，或者一个因子为 1 的数，其本身称为质数。当 `n` 小于 1000 万左右时，厄拉多塞筛是寻找所有小于 `n` 的素数的最有效方法之一。

## 例：

```java
Input : from = 1, to = 20
Output: 2 3 5 7 11 13 17 19

Input : from = 4, to = 15
Output: 5 7 11 13
```

## A. 天真的方法：

1.  定义一个名为 `isprime(int n)` 的函数，用于检查一个数是否为素数。
2.  从 `from` 循环到 `to`。
3.  内部循环，检查 `i` 是否为素数，然后打印 `i` 的值。

下面是上述方法的实现：

### Java

```java
// Java Program to Generate Prime
// Numbers Between Given Range
class GFG {
    public static boolean isprime(int n)
    {
        if (n == 1)
            return false;

        for (int i = 2; i <= Math.sqrt(n); i++)

            // Check if a number has factors
            // its not prime and return 0
            if (n % i == 0)
                return false;

        // Check if a number dont
        // have any factore
        // its prime and return 1
        return true;
    }
    public static void main(String[] args)
    {

        // Suppose we want to print
        // prime no.  from 1 to 20
        int from = 1, to = 20, k = 0;
        for (int i = from; i <= to; i++)
            if (isprime(i))
                System.out.print(" " + i);
    }
}
```

### 输出

```java
 2 3 5 7 11 13 17 19
```

**时间复杂度:** `O(n^3/2)`

## B. 厄拉多塞筛：

最初，假设从 0 到 `n` 的每个数字都是质数，将每个数字的数组值指定为 1。然后，通过将数组中的值从 1 更改为 0 来删除每个非质数，最后，只打印数组值为 1 的那些数，即质数。

**方法:**

1.  创建一个数组。
2.  输入 `n` 到数组，并为每个元素填充 1。
3.  设置 `a[0]=0` 和 `a[1]=0`，因为我们知道 0 和 1 不是质数。
4.  假设第一个数字（2）是质数，删除 2 的倍数（因为 2 的倍数将是非质数）。
5.  继续步骤 3 直到 `sqrt(n)`。
6.  打印未被划掉的数（即值为 1 的数）。

下面是上述方法的实现：

### Java

```java
// Java Program to Implement
// Sieve of eratosthenes
// to Generate Prime Numbers
// Between Given Range
import java.util.*;
class GFG {

    public static void main(String[] args)
    {
        int from = 1, to = 20, i;
        boolean[] a = new boolean[to + 1];
        Arrays.fill(a, true);

        // 0 and 1 are not prime
        a[0] = false;
        a[1] = false;
        for (i = 2; i <= Math.sqrt(to); i++)

            // Check if number is prime
            if (a[i])
                for (int j = i * i; j <= to; j += i) {
                    a[j] = false;
                }
        for (i = from; i <= to; i++) {

            // Printing only prime numbers
            if (a[i])
                System.out.print(" " + i);
        }
    }
}
```

### 输出

**时间复杂度:** `O(n log(log n))`