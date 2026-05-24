# Java IntSummaryStatistics 类，带示例

> 原文: [https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/](https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/)

`IntSummaryStatistics` 类存在于 [`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中。它收集了[整数](https://www.geeksforgeeks.org/java-lang-integer-class-java/)对象，在我们处理整数流的情况下非常有用。它维护它已经处理的整数的计数、它们的总和以及各种其他统计数据。该类也可以与 `Streams` 一起使用。

它是有用的，因为它保持一个连续的总和、平均值等。因此可以用于统计数据的处理。

## 等级体系

```java
java.lang.Object
↳ java.util.IntSummaryStatistics
```

## 构造器

1.  `IntSummaryStatistics()`: 一个默认构造器，将计数和总和初始化为零，并将最大值设置为 `Integer.MIN_VALUE`，最小值设置为 `Integer.MAX_VALUE`。

**语法:**

```java
public IntSummaryStatistics()
```

2.  `IntSummaryStatistics(count, min, max, sum)`: 使用调用时传递的参数初始化各个数据成员。

**语法:**

```java
public IntSummaryStatistics(long count, int min, int max, long sum)
                     throws IllegalArgumentException
```

## 方法

1.  `accept()` – 此函数将传入的整数添加到统计数据中。

**语法:**

```java
public void accept(int value)
```

2.  `combine()`: 此功能将传递的 `IntSummaryStatistics` 对象的统计数据与当前统计数据进行合并。

**语法:**

```java
public void combine(IntSummaryStatistics other)
```

3.  `getCount()`: 此方法返回已处理的整数数量的计数。

**语法:**

```java
public final long getCount()
```

4.  `getSum()`: 此方法返回所有已处理整数的总和。

**语法:**

```java
public final long getSum()
```

5.  `getAverage()`: 此方法返回所有已处理整数的平均值。

**语法:**

```java
public final double getAverage()
```

6.  `getMin()`: 此方法返回所有已处理整数中的最小值。

**语法:**

```java
public final int getMin()
```

7.  `getMax()`: 此方法返回所有已处理整数中的最大值。

**语法:**

```java
public final int getMax()
```

8.  `toString()`: 此方法返回对象中包含的所有统计数据的字符串表示形式。

**语法:**

```java
public String toString()
```

## 示例

演示 `IntSummaryStatistics` 的实际应用。

```java
// Java program to demonstrate
// IntSummaryStatistics class

import java.util.*;

public class IntSummaryStatisticsDemo {
    public static void main(String[] args)
    {
        IntSummaryStatistics intSummaryStatistics
            = new IntSummaryStatistics();

        List<Integer> list
            = Arrays.asList(10, 20, 30, 40, 50);

        Iterator<Integer> iterator = list.listIterator();
        while (iterator.hasNext()) {
            // Add the integers to the IntSummaryStatistics object
            intSummaryStatistics.accept(iterator.next());
        }

        // Use various methods to obtain the data
        System.out.println("The count of values is "
                           + intSummaryStatistics.getCount());
        System.out.println("The average of values is "
                           + intSummaryStatistics.getAverage());
        System.out.println("The sum of values is "
                           + intSummaryStatistics.getSum());
        System.out.println("The maximum of values is "
                           + intSummaryStatistics.getMax());
        System.out.println("The minimum of values is "
                           + intSummaryStatistics.getMin());
        System.out.println("The string representation is");
        System.out.println(intSummaryStatistics.toString());
    }
}
```

**输出:**

```
The count of values is 5
The average of values is 30.0
The sum of values is 150
The maximum of values is 50
The minimum of values is 10
The string representation is
IntSummaryStatistics{count=5, sum=150, min=10, average=30.000000, max=50}
```

**参考:** [https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html)