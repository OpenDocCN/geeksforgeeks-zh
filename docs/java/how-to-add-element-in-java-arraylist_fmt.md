# 如何在 Java 数组列表中添加元素？

> 原文：[https://www.geeksforgeeks.org/how-to-add-element-in-java-arraylist/](https://www.geeksforgeeks.org/how-to-add-element-in-java-arraylist/)

Java [`数组列表`](https://www.geeksforgeeks.org/arraylist-in-java/) 类使用动态数组来存储元素。它就像一个数组，但是没有大小限制。我们可以随时添加或删除元素。因此，它比传统数组灵活得多。

可以使用 `java.util.ArrayList` 类的 `add()` 方法在 Java `ArrayList` 中添加元素。

## 1. `boolean add(Object element)`

作为参数传递的元素被插入到列表的末尾。

### 声明

```java
public boolean add(Object element)
```

### 参数

`element` - 该元素将被添加到列表的末尾。

### 返回值

此方法返回布尔值 `true`。

### 示例

```java
Input:
list.add("A");
list.add("B");
list.add("C");
Output:
list=[A,B,C]

Input:
list.add(1);
list.add(2);
list.add(3);
list.add(4);
Output:
list=[1,2,3,4]
```

给定方法的实现：

## Java 实现

```java
// Java Program to Add Elements to an ArrayList

import java.util.*;

public class GFG {
    public static void main(String args[])
    {
        // Creating an ArrayList of String
        ArrayList<String> list = new ArrayList<String>();

        // Adding elements to the ArrayList
        list.add("A");
        list.add("B");
        list.add("C");
        list.add("D");

        // Printing the ArrayList
        System.out.println("ArrayList: " + list);

        // Adding element at a specific index
        list.add(1, "E");

        // Printing the ArrayList
        System.out.println("ArrayList: " + list);

        // Creating an ArrayList of Integer
        ArrayList<Integer> list2 = new ArrayList<Integer>();

        // Adding elements to the ArrayList
        list2.add(1);
        list2.add(2);
        list2.add(3);
        list2.add(4);

        // Printing the ArrayList
        System.out.println("ArrayList: " + list2);
    }
}
```

### 输出

```
ArrayList: [A, B, C, D]
ArrayList: [A, E, B, C, D]
ArrayList: [1, 2, 3, 4]
```