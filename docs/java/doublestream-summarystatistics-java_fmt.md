# Java 中的双流摘要统计()

> 原文: [https://www.geeksforgeeks.org/doublestream-summarystatistics-java/](https://www.geeksforgeeks.org/doublestream-summarystatistics-java/)

`DoubleStream.summaryStatistics()` 返回一个 `DoubleSummaryStatistics`，描述了关于该流元素的各种汇总数据，如双流中元素的数量计数、双流中所有元素的平均值、双流中的最小和最大元素等。这是一个终端操作，也就是说，它可能穿越河流产生结果或副作用。

## 语法:

```java
DoubleSummaryStatistics summaryStatistics()
```

## 参数:

1.  `DoubleSummaryStatistics`: State objects used to collect statistical data (such as count, minimum value, maximum value, sum and average value).

## 返回值:

`DoubleSummaryStatistics summaryStatistics()` 返回一个 `DoubleSummaryStatistics`，描述关于该流元素的各种汇总数据。

## 注:

`DoubleStream.summaryStatistics()` 是归约的特例。归约操作，也称为折叠，获取一系列输入元素，并通过重复应用组合操作将它们组合成单个汇总结果。组合运算可以是求一组数的和或最大值。

## 示例:

使用 `DoubleStream.summaryStatistics()` 获取给定双流中存在的元素的双流汇总统计。

```java
// Java code for DoubleStream summaryStatistics()
// to get various summary data about the
// elements of the stream.
import java.util.stream.DoubleStream;
import java.util.DoubleSummaryStatistics;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = 
            DoubleStream.of(4.2, 5.3, 6.5, 7.1);

        // Using DoubleStream summaryStatistics()
        DoubleSummaryStatistics summary_data = 
            stream.summaryStatistics();

        // Displaying the various summary data
        // about the elements of the stream
        System.out.println(summary_data);
    }
}
```

输出:

```java
DoubleSummaryStatistics{count=4, sum=23.100000, min=4.200000, average=5.775000, max=7.100000}
```