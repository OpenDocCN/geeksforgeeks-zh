# 利用流和过滤器寻找数组中最大奇数的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-find-maximum-odd-number-in-array-using-stream-and-filter/](https://www.geeksforgeeks.org/java-program-to-find-maximum-odd-number-in-array-using-stream-and-filter/)

Java 8 引入了一些很棒的特性，比如流和过滤器，它们极大地简化了任务，比如读取数据和对数据执行最小、最大、求和和条件检查等操作。在这个程序中，我们将借助 Java `Stream` 和 `Filter` 方法从整数列表中获取所有奇数的最大值。

## 使用循环

在没有 `Streams` 的情况下，我们可以通过遍历列表并检查数字是否为奇数来完成给定的任务。如果是真的，我们会检查到现在为止它是否大于最大奇数。

下面是实现的方法：

### Java

```java
// Java program to find maximum odd number in array using stream and filter

import java.util.*;
import java.util.stream.*;

public class GFG {
    public static void main(String[] args)
    {
        // Creating a list of integers
        List<Integer> list = Arrays.asList(12, 15, 17, 18, 21, 23, 25, 28, 30);

        // Using stream and filter to find maximum odd number
        int maxOdd = list.stream()
                         .filter(n -> n % 2 != 0)
                         .max(Integer::compareTo)
                         .orElseThrow();

        // Printing the result
        System.out.println("Largest odd number: " + maxOdd);
    }
}
```

**输出**
```
Largest odd number: 51
```