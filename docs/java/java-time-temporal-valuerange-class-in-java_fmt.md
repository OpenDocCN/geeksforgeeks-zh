# java 中的 java.time.temporal.ValueRange 类

> 原文: [https://www.geeksforgeeks.org/java-time-temporal-valuerange-class-in-java/](https://www.geeksforgeeks.org/java-time-temporal-valuerange-class-in-java/)

`ValueRange` 类捕获临时字段实例值的有效范围。给定的类提供范围的最小值和最大值。

**注意:** 可能在外部范围内有无效值。例如，一个字段可能具有有效值 1、2、3、6、7，因此具有范围“1-7”，尽管值 4 和 5 无效。

**类声明:**

```java
public final class ValueRange
extends Object
implements Serializable
```

**`ValueRange` 类从 `java.lang.Object` 类继承了以下方法:**

*   `clone()`
*   `finalize()`
*   `getClass()`
*   `notify()`
*   `notifyAll()`
*   `wait()`

**`ValueRange` 类方法:**

| 方法 | 描述 |
| --- | --- |
| `checkValidIntValue(long value, TemporalField field)` | 此方法检查指定的值是否有效并适合 `int`。 |
| `checkValidValue(long value, TemporalField field)` | 此方法检查指定的值是否有效。 |
| `equals(Object object)` | 此方法检查此范围是否等于另一个范围。 |
| `getLargestMinimum()` | 此方法获取字段可以接受的最大可能最小值。 |
| `getMaximum()` | 此方法获取字段可以接受的最大值。 |
| `getMinimum()` | 此方法获取字段可以接受的最小值。 |
| `getSmallestMaximum()` | 此方法获取字段可以接受的最小可能最大值。 |
| `hashCode()` | 此方法返回适合此范围的哈希代码。 |
| `isFixed()` | 如果值集是固定的，则此方法返回 `true`。 |
| `isIntValue()` | 此方法检查该范围内的所有值是否都符合 `int`。 |
| `isValidIntValue(long value)` | 此方法检查该值是否在有效范围内，以及该范围内的所有值是否符合 `int`。 |
| `isValidValue(long value)` | 此方法检查该值是否在有效范围内。 |
| `of(long min, long max)` | 此方法获得固定的值范围。 |
| `of(long min, long maxMin, long max)` | 此方法获取变量值范围。 |
| `of(long min, long maxMin, long minMax, long max)` | 此方法获得完全可变的值范围。 |
| `toString()` | 此方法是此范围的字符串表示形式，而不是 `null`。 |

**例 1:**

```java
// Java program to demonstrate
// ValueRange Class and its methods

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {
        // create ValueRange object
        ValueRange vRange = ValueRange.of(5555, 1000000);

        // store the minimum value that the field can take
        long minVal = vRange.getMinimum();

        // store the maximum value that the field can take
        long maxVal = vRange.getMaximum();

        // print
        System.out.println("Minimum value is: " + minVal);
        System.out.println("Maximum value is: " + maxVal);
    }
}
```

**输出**

```java
Minimum value is: 5555
Maximum value is: 1000000
```

**例 2:**

```java
// Java program to demonstrate
// ValueRange Class and its methods

import java.time.temporal.ValueRange;

public class GFG {
    public static void main(String[] args)
    {
        // create ValueRange object
        ValueRange vRange = ValueRange.of(1, 10000);

        // check value 6001 in range or not
        long value1 = vRange.checkValidValue(6001, null);

        // print
        System.out.println("Value passed: " + value1);
    }
}
```

**输出**

```java
Value passed: 6001
```