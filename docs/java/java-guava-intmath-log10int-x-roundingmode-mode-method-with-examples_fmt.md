# Java 番石榴 | `IntMath.log10(int x, RoundingMode mode)` 方法带示例

> 原文: [https://www.geeksforgeeks.org/java-guava-intmath-log10int-x-roundingmode-mode-method-with-examples/](https://www.geeksforgeeks.org/java-guava-intmath-log10int-x-roundingmode-mode-method-with-examples/)

番石榴 [`IntMath` 类](https://www.geeksforgeeks.org/intmath-class-guava-java/)的 `log10(int x, RoundingMode mode)` 方法接受两个参数，并根据第二个参数指定的舍入方式计算第一个参数舍入后的基数-10 对数值。

## 语法

```java
public static int log10(int x, RoundingMode mode)
```

## 参数

该方法取 2 个参数:

*   `x` 是要查找对数的 `int` 值。
*   `mode` 是指定的舍入模式。

## 返回值

该方法返回 `x` 的以 10 为底的对数，根据指定的舍入方式进行舍入。

## 异常

此方法抛出以下异常:

*   **`IllegalArgumentException`**: 如果 `x < 0`。
*   **`ArithmeticException`**: 如果模式是 `UNNECESSARY`，但 `x` 不是 10 的幂。

### 枚举舍入模式

| 枚举常数 | 描述 |
| --- | --- |
| `CEILING` | 舍入模式向正无穷大舍入。 |
| `DOWN` | 舍入模式为向零舍入。 |
| `FLOOR` | 舍入模式为向负无穷大舍入。 |
| `HALF_DOWN` | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下舍入为 `DOWN`。 |
| `HALF_EVEN` | 舍入模式为向“最近邻居”舍入，除非两个邻居等距，在这种情况下，向偶数邻居舍入。 |
| `HALF_UP` | 取整模式为向“最近邻居”取整，除非两个邻居等距，在这种情况下取整。 |
| `UNNECESSARY` | 舍入模式断言请求的操作有确切的结果，因此没有舍入的必要。 |
| `UP` | 取整模式为远离零取整。 |

下面给出了一些例子，以便更好地理解实现:

## 示例 1

```java
// Java code to show implementation of
// log10(int x, RoundingMode mode) method
// of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    // Driver code
    public static void main(String args[])
    {
        int a1 = 10000;

        // Using log10(int x, RoundingMode mode)
        // method of Guava's IntMath class
        // The RoundingMode HALF_EVEN rounds towards
        // the "nearest neighbor" unless both neighbors
        // are equidistant, in which case, round towards
        // the even neighbor.
        System.out.println(
            IntMath.log10(a1,
                          RoundingMode.HALF_EVEN));

        int a2 = 15;

        // Using log10(int x, RoundingMode mode)
        // method of Guava's IntMath class
        // The RoundingMode HALF_DOWN rounds towards
        // "nearest neighbor" unless both neighbors
        // are equidistant, in which case round down.
        System.out.println(
            IntMath.log10(a2,
                          RoundingMode.HALF_DOWN));
    }
}
```

输出:

```java

```

## 示例 2

```java
// Java code to show implementation of
// log10(int x, RoundingMode mode) method
// of Guava's IntMath class
import java.math.RoundingMode;
import com.google.common.math.IntMath;

class GFG {

    static int findlog10(int x, RoundingMode mode)
    {
        try {
            // Using log10(int x, RoundingMode mode)
            // method of Guava's IntMath class
            // The RoundingMode HALF_EVEN rounds towards
            // the "nearest neighbor" unless both neighbors
            // are equidistant, in which case, round towards
            // the even neighbor.
            // This should throw "IllegalArgumentException"
            // as x <= 0
            int ans = IntMath.log10(x, mode);

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
        int x = -152;

        try {

            // Function calling
            findlog10(x, RoundingMode.HALF_EVEN);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

输出:

```java
java.lang.IllegalArgumentException: x (-152) must be > 0
```

## 参考

[https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#log10-int-java.math.RoundingMode-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/math/IntMath.html#log10-int-java.math.RoundingMode-)