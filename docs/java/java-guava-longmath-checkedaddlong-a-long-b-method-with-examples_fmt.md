# Java Guava LongMath.checkedAdd(long a, long b)方法详解

> 原文：[https://www.geeksforgeeks.org/java-guava-longmath-checkedaddlong-a-long-b-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longmath-checkedaddlong-a-long-b-method-with-examples/)

`checkedAdd(long a, long b)` 是 Guava [`LongMath`](https://www.geeksforgeeks.org/intmath-class-guava-java/) 类的一种方法，它接受两个参数 `a` 和 `b`，并返回它们的和。

## 方法签名

```java
public static long checkedAdd(long a, long b)
```

## 参数说明

该方法接受两个 `long` 值 `a` 和 `b` 并计算它们的和。

## 返回值

该方法返回传递给它的 `long` 值之和，前提是不溢出。

## 异常

如果总和（即 `a + b`）在有符号 `long` 算术中溢出，则 `checkedAdd(long a, long b)` 方法会抛出 `ArithmeticException`。

## 示例

下面的例子说明了上述方法的实现：

### 示例 1

```java
// Java code to show implementation of
// checkedAdd(long a, long b) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long a1 = 25;
        long b1 = 36;

        // Using checkedAdd(long a, long b)
        // method of Guava's LongMath class
        long ans1 = LongMath.checkedAdd(a1, b1);

        System.out.println("Sum of " + a1 + " and "
                           + b1 + " is: " + ans1);

        long a2 = 150;
        long b2 = 667;

        // Using checkedAdd(long a, long b)
        // method of Guava's LongMath class
        long ans2 = LongMath.checkedAdd(a2, b2);

        System.out.println("Sum of " + a2 + " and "
                           + b2 + " is: " + ans2);
    }
}
```

**输出：**

```java
Sum of 25 and 36 is: 61
Sum of 150 and 667 is: 817
```

### 示例 2

```java
// Java code to show implementation of
// checkedAdd(long a, long b) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    static long findDiff(long a, long b)
    {
        try {

            // Using checkedAdd(long a, long b) method
            // of Guava's LongMath class
            // This should throw "ArithmeticException"
            // as the sum overflows in signed
            // long arithmetic
            long ans = LongMath.checkedAdd(a, b);

            // Return the answer
            return ans;
        }
        catch (Exception e) {
            System.out.println(e);
            return -1;
        }
    }

    // Driver code
    public static void main(String args[])
    {
        long a = Long.MIN_VALUE;
        long b = 452;

        try {

            // Function calling
            findDiff(a, b);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.lang.ArithmeticException: overflow
```

## 参考

[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#checkedAdd-long-long-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#checkedAdd-long-long-)