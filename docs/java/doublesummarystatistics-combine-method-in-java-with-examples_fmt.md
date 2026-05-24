# Double Summary Statistics

> 原文: [https://www.geeksforgeeks.org/doublesummarystatistics-combine-method-in-java-with-examples/](https://www.geeksforgeeks.org/doublesummarystatistics-combine-method-in-java-with-examples/)

## combine() 方法

Java 中 `DoubleSummaryStatistics` 类的 `combine()` 方法用于将给定的其他 `DoubleSummaryStatistics` 组合到这个 `DoubleSummaryStatistics` 中。

**语法:**

```java
public void combine(DoubleSummaryStatistics otherDoubleSummaryStatistics)
```

**参数:** 此方法接受 `otherDoubleSummaryStatistics` 作为要合并到此 `DoubleSummaryStatistics` 中的参数。

**返回值:** 这个方法不返回任何东西。

**异常:** 如果 `otherDoubleSummaryStatistics` 为空，该方法抛出 `NullPointerException`。

**程序:**

```java
// Java program to demonstrate
// the above method

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

        Iterator<Double> iterator = list.listIterator();
        while (iterator.hasNext()) {

            // Add the doubles to the
            // DoubleSummaryStatistics object
            doubleSummaryStatistics
                .accept(iterator.next());
        }

        System.out.println("First DoubleSummaryStatistics: "
                           + doubleSummaryStatistics
                                 .toString());

        DoubleSummaryStatistics otherDoubleSummaryStatistics
            = new DoubleSummaryStatistics();

        List<Double> list1 = new LinkedList<>();
        list1.add(45664.0);
        list1.add(7007.777);
        list1.add(5677.0);
        list1.add(0.0);
        list1.add(45664.7);

        Iterator<Double> iterator1 = list1.listIterator();
        while (iterator1.hasNext()) {

            // Add the doubles to the
            // DoubleSummaryStatistics object
            otherDoubleSummaryStatistics
                .accept(iterator1.next());
        }

        System.out.println("Second DoubleSummaryStatistics: "
                           + otherDoubleSummaryStatistics
                                 .toString());

        System.out.println("Combining both DoubleSummaryStatistics"
                           + " using combine() ");
        doubleSummaryStatistics.combine(otherDoubleSummaryStatistics);

        System.out.println("Combined DoubleSummaryStatistics: "
                           + doubleSummaryStatistics.toString());
    }
}
```

**Output:**

> First DoubleSummaryStatistics:
> DoubleSummaryStatistics{count=5, sum=669.476700, min=45.600000, average=133.895340, max=243.500000}
> Second DoubleSummaryStatistics:
> DoubleSummaryStatistics{count=5, sum=104013.477000, min=0.000000, average=20802.695400, max=45664.700000}
> Combining both DoubleSummaryStatistics using combine()
> Combined DoubleSummaryStatistics:
> DoubleSummaryStatistics{count=10, sum=104682.953700, min=0.000000, average=10468.295370, max=45664.700000}

**参考:** [https://docs.oracle.com/javase/9/docs/api/java/util/DoubleSummaryStatistics.html#combine-java.util.DoubleSummaryStatistics-](https://docs.oracle.com/javase/9/docs/api/java/util/DoubleSummaryStatistics.html#combine-java.util.DoubleSummaryStatistics-)