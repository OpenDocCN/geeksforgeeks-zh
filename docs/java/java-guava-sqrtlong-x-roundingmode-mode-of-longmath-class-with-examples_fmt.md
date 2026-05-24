# Java 番石榴：`LongMath` 类的 `sqrt(long x, RoundingMode mode)` 方法（带示例）

> 原文：[https://www.geeksforgeeks.org/java-guava-sqrtlong-x-roundingmode-mode-of-longmath-class-with-examples/](https://www.geeksforgeeks.org/java-guava-sqrtlong-x-roundingmode-mode-of-longmath-class-with-examples/)

番石榴 [`LongMath`](https://www.geeksforgeeks.org/longmath-class-guava-java/) 类的方法 `sqrt(long x, RoundingMode mode)` 接受两个参数，根据第二个参数指定的舍入模式计算第一个参数舍入后的平方根。

## 语法

```java
public static long sqrt(long x, RoundingMode mode)
```

## 参数

这个方法取两个参数：

*   `x`：需要计算平方根的 `long` 值。
*   `mode`：执行舍入操作所依据的舍入模式。

## 返回值

该方法返回 `x` 的平方根，按照指定的舍入方式进行舍入。

## 异常

此方法抛出以下异常：

*   `IllegalArgumentException`：如果 `x < 0`。
*   `ArithmeticException`：如果 `mode` 是 `UNNECESSARY` 模式，但 `sqrt(x)` 不是整数。

## 枚举舍入模式

| 枚举常数 | 描述 |
| :--- | :--- |
| `CEILING` | 舍入模式向正无穷大舍入。 |
| `DOWN` | 舍入模式为向零舍入。 |
| `FLOOR` | 舍入模式为向负无穷大舍入。 |
| `HALF_DOWN` | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下舍入为 `DOWN`。 |
| `HALF_EVEN` | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下，向偶数邻居舍入。 |
| `HALF_UP` | 取整模式为向“最近邻居”取整，除非两个邻居等距，在这种情况下取整。 |
| `UNNECESSARY` | 舍入模式断言请求的操作有确切的结果，因此没有舍入的必要。 |
| `UP` | 取整模式为远离零取整。 |

下面给出了一些例子，以便更好地理解实现：

## 示例 1

```java
// Java code to show implementation of
// sqrt(long x, RoundingMode mode) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        long x1 = 524;

        // Using sqrt(long x, RoundingMode mode)
        // method of Guava's LongMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the nearest neighbor unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        long ans1
            = LongMath.sqrt(x1,
                            RoundingMode.HALF_EVEN);

        System.out.println("Square root of " + x1
                           + " is : " + ans1);

        long x2 = 316;

        // Using sqrt(long x, RoundingMode mode)
        // method of Guava's LongMath class
        // The RoundingMode FLOOR rounds towards
        // negative infinity.
        long ans2
            = LongMath.sqrt(x2,
                            RoundingMode.FLOOR);

        System.out.println("Square root of " + x2
                           + " is : " + ans2);
    }
}
```

**输出：**

```java
Square root of 524 is : 23
Square root of 316 is : 17
```

## 示例 2

```java
// Java code to show implementation of
// sqrt(long x, RoundingMode mode) method
// of Guava's LongMath class

import java.math.RoundingMode;
import com.google.common.math.LongMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int x = -65;

        try {
            // Using sqrt(long x, RoundingMode mode)
            // method of Guava's LongMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the nearest neighbor unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.

            // This should throw "IllegalArgumentException"
            // as x < 0
            long ans1 = LongMath.sqrt(x,
                                      RoundingMode.HALF_EVEN);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出：**

```java
java.lang.IllegalArgumentException: x (-65) must be >= 0
```

**参考：**[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#sqrt-long-java.math.RoundingMode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/LongMath.html#sqrt-long-java.math.RoundingMode-)