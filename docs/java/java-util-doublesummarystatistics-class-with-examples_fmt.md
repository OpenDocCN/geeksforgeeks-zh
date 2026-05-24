# Java DoubleSummaryStatistics 类，带示例

> 原文：[https://www.geeksforgeeks.org/java-util-doublesummarystatistics-class-with-examples/](https://www.geeksforgeeks.org/java-util-doublesummarystatistics-class-with-examples/)

`DoubleSummaryStatistics` 类存在于 [`java.util`](https://www.geeksforgeeks.org/java-util-package-java/) 包中。它收集了一组 [`Double`](https://www.geeksforgeeks.org/java-lang-double-class-java/) 对象，在我们处理大量精确实数的情况下非常有用。它维护已处理的值的数量、它们的总和以及各种其他统计信息的计数。该类也可以与 [Streams](https://www.geeksforgeeks.org/stream-in-java/) 一起使用。

它是有用的，因为它保持一个连续的总和、平均值等。因此可以用于统计数据的处理。

## 等级体系

```java
java.lang.Object
↳ java.util.DoubleSummaryStatistics
```

## 构造方法

1.  `DoubleSummaryStatistics()`：一个默认构造方法，它将计数和总和初始化为零，并将最大值设置为 [`Double.NEGATIVE_INFINITY`](https://www.geeksforgeeks.org/java-lang-double-class-java/)，最小值设置为 [`Double.POSITIVE_INFINITY`](https://www.geeksforgeeks.org/java-lang-double-class-java/)。

**语法：**

```java
public DoubleSummaryStatistics()
```

## 方法

1.  `accept()`：此函数将传入的 `double` 值添加到统计数据中。

**语法：**

```java
public void accept(double value)
```

2.  `combine()`：此函数将传入的 `DoubleSummaryStatistics` 对象的统计数据与当前统计数据合并。

**语法：**

```java
public void combine(DoubleSummaryStatistics other)
```

3.  `getCount()`：此方法返回已处理的 `double` 值的计数。

**语法：**

```java
public final long getCount()
```

4.  `getSum()`：此方法返回所有已处理的 `double` 值的总和。

**语法：**

```java
public final double getSum()
```

5.  `getAverage()`：此方法返回所有已处理的 `double` 值的平均值。

**语法：**

```java
public final double getAverage()
```

6.  `getMin()`：此方法返回所有已处理的 `double` 值中的最小值。

**语法：**

```java
public final double getMin()
```

7.  `getMax()`：此方法返回所有已处理的 `double` 值中的最大值。

**语法：**

```java
public final double getMax()
```

8.  `toString()`：此方法返回对象中包含的所有统计数据的字符串表示形式。

**语法：**

```java
public String toString()
```

## 示例

以下示例演示了 `DoubleSummaryStatistics` 的实际应用。

```java
// Java program to demonstrate
// DoubleSummaryStatistics class

import java.util.*;

public class DoubleSummaryStatisticsDemo {
    public static void main(String[] args)
    {

        DoubleSummaryStatistics doubleSummaryStatistics
            = new DoubleSummaryStatistics();

        List<Double> list = new LinkedList<>();
        list.add(95.7);
        list.add(234.6767);
        list.add(243.5);
        list.add(50.0);
        list.add(45.6);
        list.add(45664.0);
        list.add(7007.777);
        list.add(5677.0);
        list.add(0.0);
        list.add(45664.7);

        Iterator<Double> iterator = list.listIterator();
        while (iterator.hasNext()) {

            // Add the doubles to the
            // DoubleSummaryStatistics object
            doubleSummaryStatistics
                .accept(iterator.next());
        }

        // Use various methods to obtain the data
        System.out.println("The count of values is "
                           + doubleSummaryStatistics
                                 .getCount());
        System.out.println("The average of values is "
                           + doubleSummaryStatistics
                                 .getAverage());
        System.out.println("The sum of values is "
                           + doubleSummaryStatistics
                                 .getSum());
        System.out.println("The maximum of values is "
                           + doubleSummaryStatistics
                                 .getMax());
        System.out.println("The minimum of values is "
                           + doubleSummaryStatistics
                                 .getMin());
        System.out.println("The string representation is");
        System.out.println(doubleSummaryStatistics
                               .toString());
    }
}
```

**输出：**

```
The count of values is 10
The average of values is 10468.29537
The sum of values is 104682.9537
The maximum of values is 45664.7
The minimum of values is 0.0
The string representation is
DoubleSummaryStatistics{count=10, sum=104682.953700, min=0.000000, average=10468.295370, max=45664.700000}
```

**参考：**[https://docs.oracle.com/javase/8/docs/api/java/util/DoubleSummaryStatistics.html](https://docs.oracle.com/javase/8/docs/api/java/util/DoubleSummaryStatistics.html)