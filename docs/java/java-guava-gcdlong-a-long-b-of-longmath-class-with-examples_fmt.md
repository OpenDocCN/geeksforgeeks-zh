# Java 番石榴 LongMath 类 gcd(long a, long b) 方法详解

> 原文：[https://www.geeksforgeeks.org/java-guava-gcdlong-a-long-b-of-longmath-class-with-examples/](https://www.geeksforgeeks.org/java-guava-gcdlong-a-long-b-of-longmath-class-with-examples/)

番石榴 [`LongMath`](https://www.geeksforgeeks.org/longmath-class-guava-java/) 类的方法 `gcd(long a, long b)` 返回两个参数 `a` 和 `b` 的最大公约数。

## 语法

```java
public static long gcd(long a, long b)
```

## 参数

该方法接受要找到 GCD 的 `long` 类型的两个参数 `a` 和 `b`。

## 返回类型

该方法返回最大正 `long` 值，该值将传递给函数的两个参数相除。

## 异常

如果 `a` 为负或者 `b` 为负，则方法 `gcd(long a, long b)` 抛出 `IllegalArgumentException`。

## 注意

如果 `a` 和 `b` 都为零，则方法返回零。

## 例 1

```java
// Java code to show implementation of
// gcd(long a, long b) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long a1 = 14;
        long b1 = 70;

        // Using gcd(long a, long b) method
        // of Guava's LongMath class
        long ans1 = LongMath.gcd(a1, b1);

        System.out.println("GCD of " + a1
                           + " and " + b1
                           + " is " + ans1);

        long a2 = 23;
        long b2 = 15;

        // Using gcd(long a, long b) method
        // of Guava's LongMath class
        long ans2 = LongMath.gcd(a2, b2);

        System.out.println("GCD of " + a2
                           + " and " + b2
                           + " is " + ans2);
    }
}
```

## 输出

```java
GCD of 14 and 70 is 14
GCD of 23 and 15 is 1
```

## 例 2

```java
// Java code to show implementation of
// gcd(long a, long b) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long a = -5;
        long b = 15;

        try {
            // Using gcd(long a, long b) method
            // of Guava's LongMath class
            // This should throw "IllegalArgumentException"
            // as a < 0
            long ans = LongMath.gcd(a, b);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 输出

```java
java.lang.IllegalArgumentException: a (-5) must be >= 0
```

## 参考

[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#gcd-long-long-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#gcd-long-long-)