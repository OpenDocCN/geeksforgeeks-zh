# 返回列表中最大元素的 Java 程序

> 原文: [https://www.geeksforgeeks.org/java-program-to-return-the-largest-element-in-a-list/](https://www.geeksforgeeks.org/java-program-to-return-the-largest-element-in-a-list/)

给定一个[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)，找到其中最大的元素。有多种方法可以解决这个问题，比如遍历列表或者使用各种内置函数。

```
Input  : List = [5, 3, 234, 114, 154]
Output : 234

Input  : List = {10, 20, 4}
Output : 20
```

## 方法 1: 使用 ForEach Loop

1.  创建一个`List`对象并在其中存储多个元素。
2.  创建一个变量并将其初始化为整数最大值。
3.  开始使用`forEach`循环遍历列表中的元素，并将每个元素与该变量进行比较。
4.  如果当前元素大于该变量，则更新该变量。
5.  遍历结束后，打印该变量。

下面是上述方法的实现:

## Java

```java
// Java Program to return the largest element in a List

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create a list
        List<Integer> list = Arrays.asList(5, 3, 234, 114, 154);

        // Initialize max with the first element of the list
        int max = list.get(0);

        // Iterate through the list using forEach loop
        for (Integer i : list) {
            // Compare each element with max
            if (i > max)
                max = i;
        }

        // Print the maximum value
        System.out.println("The maximum value is " + max);
    }
}
```

**输出**

```
The maximum value is 1540
```