# Java Guava `LongMath.isPowerOfTwo(long x)` 方法示例

> 原文：[https://www.geeksforgeeks.org/java-guava-ispoweroftwolong-x-of-longmath-class-with-examples/](https://www.geeksforgeeks.org/java-guava-ispoweroftwolong-x-of-longmath-class-with-examples/)

Guava [`LongMath`](https://www.geeksforgeeks.org/longmath-class-guava-java/) 类的 `isPowerOfTwo(long x)` 方法用于检查一个数是否是二的幂。它接受要检查的数字作为参数，并根据该数字是否为 2 的幂返回布尔值 `true` 或 `false`。

## 语法
```java
public static boolean isPowerOfTwo(long x)
```

## 参数
该方法接受一个 `long` 类型的单参数 `x`，检查其是否为二的幂。

## 返回值
该方法返回一个 `boolean` 值。如果 `x` 代表 2 的幂，则返回 `true`，如果 `x` 不代表 2 的幂，则返回 `false`。

## 异常
该方法不抛出任何异常。

## 注意
这与 `Long.bitCount(x) == 1` 不同，因为 `Long.bitCount(Long.MIN_VALUE) == 1`，但 `Long.MIN_VALUE` 不是 2 的幂。

## 示例 1
```java
// Java code to show implementation of
// isPowerOfTwo(long x) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long n1 = 52;

        // Using isPowerOfTwo(long x) method
        // of Guava's LongMath class
        if (LongMath.isPowerOfTwo(n1))
            System.out.println(n1
                               + " is power of 2");
        else
            System.out.println(n1
                               + " is not power of 2");

        long n2 = 4;

        // Using isPowerOfTwo(long x) method
        // of Guava's LongMath class
        if (LongMath.isPowerOfTwo(n2))
            System.out.println(n2
                               + " is power of 2");
        else
            System.out.println(n2
                               + " is not power of 2");
    }
}
```

## 输出
```
52 is not power of 2
4 is power of 2
```

## 示例 2
```java
// Java code to show implementation of
// isPowerOfTwo(long x) method of Guava's
// LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long n1 = 256;

        // Using isPowerOfTwo(long x) method
        // of Guava's LongMath class
        if (LongMath.isPowerOfTwo(n1))
            System.out.println(n1
                               + " is power of 2");
        else
            System.out.println(n1
                               + " is not power of 2");

        long n2 = 4096;

        // Using isPowerOfTwo(long x) method
        // of Guava's LongMath class
        if (LongMath.isPowerOfTwo(n2))
            System.out.println(n2
                               + " is power of 2");
        else
            System.out.println(n2
                               + " is not power of 2");
    }
}
```

## 输出
```
256 is power of 2
4096 is power of 2
```

## 参考
[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#isPowerOfTwo-long-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#isPowerOfTwo-long-)