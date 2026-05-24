# 如何在 Java 中从 LinkedHashSet 获取最后一个元素？

> 原文: [https://www.geeksforgeeks.org/how-to-get-the-last-element-from-linkedhashset-in-java/](https://www.geeksforgeeks.org/how-to-get-the-last-element-from-linkedhashset-in-java/)

[`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 [`HashSet`](https://www.geeksforgeeks.org/hashset-in-java/) 的有序版本，维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。当迭代一个 [`HashSet`](https://www.geeksforgeeks.org/hashset-in-java/) 时，顺序是不可预测的，而 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 让我们按照元素插入的顺序迭代元素。当使用迭代器循环遍历 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 时，元素将按照插入的顺序返回。

**有两种方法可以从 LinkedHashSet 获取最后一个元素:**

1.  通过迭代集合。
2.  通过将 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 转换为数组或列表。

## 方法 1: 通过迭代集合

### 通过迭代 LinkedHashSet

通过迭代 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 从 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 获取最后一个元素，过程分为两部分:

*   首先，制作一个变量 `lastEle`
*   迭代 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 并获取最后一个元素

*示例:*

```java
// Java program to find the last 
// element from LinkedHashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // New empty HashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(10);
        set.add(50);
        set.add(20);

        // Last element
        int lastEle = 0;

        // Iterate LinkedHashSet
        for (int x : set)
        {
            lastEle = x;
        }

        // Print the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Print the last element of the LinkedHashSet
        System.out.println("Last element of LinkedHashSet: "
                           + lastEle);
    }
}
```

**Output**

```java
LinkedHashSet: [10, 20, 30, 50]
Last element of LinkedHashSet: 50
```

## 方法 2: 通过将 LinkedHashSet 转换为数组

要使用数组从 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 获取最后一个元素，该过程分为三个部分:

*   首先，制作一个数组。
*   借助 [`toArray()`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 的方法，将 [`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 转换为数组。
*   使用最后一个索引获取最后一个元素。

*示例:*

```java
// Java program to find the last 
// element from LinkedHashSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // New empty HashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(10);
        set.add(50);
        set.add(20);

        Integer[] elements = new Integer[set.size()];

        // Convert LinkedHashSet to Array
        elements = set.toArray(elements);

        // Get the last element with the help of the index.
        int lastEle = elements[elements.length - 1];

        // Print the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Print the last element of the LinkedHashSet
        System.out.println("Last element of LinkedHashSet: "
                           + lastEle);
    }
}
```

**Output**

```java
LinkedHashSet: [10, 20, 30, 50]
Last element of LinkedHashSet: 50
```