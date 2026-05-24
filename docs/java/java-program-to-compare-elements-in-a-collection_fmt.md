# 比较集合中元素的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-compare-elements-in-a-collection/](https://www.geeksforgeeks.org/java-program-to-compare-elements-in-a-collection/)

一个`集合`是以单个单位表示的一组个体对象。Java 提供了`集合框架`，定义了几个类和接口，将一组对象表示为一个单元。

## 示例

```
Input : List = [3, 5, 18, 4, 6]
Output:
Min value of our list : 3
max value of our list : 18

Input : List = ['a', 'a', 'a']
Output:
All elements are equal
```

## 方法

1.  从列表中获取输入。
2.  创建两个变量，`minimum`和`maximum`。
3.  使用`Collections.min()`方法将返回值存储在`min`变量中。
4.  使用`Collections.max()`方法将返回值存储在`max`变量中。
5.  如果`minimum`和`maximum`变量相等，则打印元素相等的信息。
6.  否则，打印`minimum`和`maximum`变量。

## 实现

下面是上述方法的实现：

```java
// Java Program to Compare Elements in a Collection
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // List initialization
        List<Integer> l = new ArrayList<>();

        // Add elements in the list
        l.add(3);
        l.add(5);
        l.add(18);
        l.add(4);
        l.add(6);

        // Minimum in the list
        int minimum = Collections.min(l);

        // Maximum in the list
        int maximum = Collections.max(l);

        if (minimum == maximum) {
            System.out.println("All elements are equal");
        }
        else {
            System.out.println("Min value of our list : "
                               + minimum);
            System.out.println("Max value of our list : "
                               + maximum);
        }
    }
}
```

## 输出

```
Min value of our list : 3
Max value of our list : 18
```

## 时间复杂度

`O(N)`，其中`N`为列表长度。