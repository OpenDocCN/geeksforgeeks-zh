# BigIntegerMath binomial() 函数 | Guava | Java

> 原文：[https://www.geeksforgeeks.org/bigintegermath-binomial-function-guava-java/](https://www.geeksforgeeks.org/bigintegermath-binomial-function-guava-java/)

Guava 的 `BigIntegerMath` 类的 `binomial(int n, int k)` 方法返回 `n` 选择 `k`，也称为 `n` 和 `k` 的二项式系数，即

```java
n! / (k! (n - k)!)
```

## 语法

```java
public static BigInteger binomial(int n, int k)
```

## 参数

该方法取以下参数：

*   `n`：二项式展开的基数。
*   `k`：二项式展开的幂。

## 返回值

该方法返回 `n` 和 `k` 的二项式系数。

## 异常

如果 `n < 0`，`k < 0` 或 `k > n`，此方法抛出 `IllegalArgumentException`。

## 注意

结果可以占用多达 `O(k log n)` 的空间。

## 示例

以下示例说明了 `BigIntegerMath.binomial()` 方法：

### 示例 1

```java
// Java code to show implementation of
// binomial(int n, int k) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int n = 5;
        int k = 2;

        // Using binomial(int n, int k) method of
        // Guava's BigIntegerMath class
        BigInteger ans = BigIntegerMath.binomial(n, k);

        System.out.println("Binomial Coefficient of "
                           + n + " & " + k
                           + " is: " + ans);

        int n1 = 15;
        int k1 = 9;

        // Using binomial(int n, int k) method of
        // Guava's BigIntegerMath class
        BigInteger ans1 = BigIntegerMath.binomial(n1, k1);

        System.out.println("Binomial Coefficient of "
                           + n1 + " & " + k1
                           + " is: " + ans1);
    }
}
```

**输出：**

```java
Binomial Coefficient of 5 & 2 is: 10
Binomial Coefficient of 15 & 9 is: 5005
```

### 示例 2

```java
// Java code to show implementation of
// binomial(int n, int k) method
// of Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {

        try {
            int n = 5;
            int k = 7;

            // Using binomial(int n, int k) method of
            // Guava's BigIntegerMath class
            // This should raise "IllegalArgumentException"
            // as k > n
            BigInteger ans = BigIntegerMath.binomial(n, k);

            System.out.println("Binomial Coefficient of"
                               + n + " & " + k
                               + " is: " + ans);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出：**

```java
Exception: java.lang.IllegalArgumentException: k (7) > n (5)
```

## 参考

[https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#binomial-int-int-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#binomial-int-int-)