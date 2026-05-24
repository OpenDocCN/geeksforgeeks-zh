# `BigIntegerMath.isPowerOfTwo()` 函数 | Guava | Java

> 原文：[https://www.geeksforgeeks.org/bigintegermath-ispoweroftwo-function-guava-java/](https://www.geeksforgeeks.org/bigintegermath-ispoweroftwo-function-guava-java/)

如果 `x` 代表 2 的幂，则 [Guava 的 `BigIntegerMath` 类](https://www.geeksforgeeks.org/bigintegermath-class-guava-java/)的方法 `isPowerOfTwo(BigInteger x)` 返回 `true`。

**语法：**

```java
public static boolean isPowerOfTwo(BigInteger x)
```

**参数：** 该方法以 `BigInteger` `x` 作为待检参数。
**返回值：** 如果 `x` 是 2 的幂，这个方法返回 `true`。

以下示例说明了 `BigIntegerMath.isPowerOfTwo()` 方法：

**示例 1：**

```java
// Java code to show implementation of
// isPowerOfTwo(BigInteger x) method of
// Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger a1 = BigInteger.valueOf(63);

        // Using isPowerOfTwo(BigInteger x) method
        // of Guava's BigIntegerMath class
        if (BigIntegerMath.isPowerOfTwo(a1))
            System.out.println(a1 + " is power of 2");
        else
            System.out.println(a1 + " is not power of 2");

        BigInteger a2 = BigInteger.valueOf(1024);

        // Using isPowerOfTwo(BigInteger x) method
        // of Guava's BigIntegerMath class
        if (BigIntegerMath.isPowerOfTwo(a2))
            System.out.println(a2 + " is power of 2");
        else
            System.out.println(a2 + " is not power of 2");
    }
}
```

**Output:**

```java
63 is not power of 2
1024 is power of 2
```

**示例 2：**

```java
// Java code to show implementation of
// isPowerOfTwo(BigInteger x) method of
// Guava's BigIntegerMath class

import java.math.*;
import com.google.common.math.BigIntegerMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        BigInteger a1 = BigInteger.valueOf(1);

        // Using isPowerOfTwo(BigInteger x) method
        // of Guava's BigIntegerMath class
        if (BigIntegerMath.isPowerOfTwo(a1))
            System.out.println(a1 + " is power of 2");
        else
            System.out.println(a1 + " is not power of 2");

        BigInteger a2 = BigInteger.valueOf(567);

        // Using isPowerOfTwo(BigInteger x) method
        // of Guava's BigIntegerMath class
        if (BigIntegerMath.isPowerOfTwo(a2))
            System.out.println(a2 + " is power of 2");
        else
            System.out.println(a2 + " is not power of 2");
    }
}
```

**Output:**

```java
1 is power of 2
567 is not power of 2
```

**参考：** [https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#isPowerOfTwo-java.math.BigInteger-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/math/BigIntegerMath.html#isPowerOfTwo-java.math.BigInteger-)