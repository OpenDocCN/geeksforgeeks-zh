# 如何在 Java 中迭代 LinkedList？

> 原文：[`https://www.geeksforgeeks.org/how-to-iterate-linkedlist-in-java/`](https://www.geeksforgeeks.org/how-to-iterate-linkedlist-in-java/)

[`Java 中的 LinkedList`](https://www.geeksforgeeks.org/linked-list-in-java/) 基本上是 `java.util` 包中存在的集合框架的一部分。它是 `LinkedList` 数据结构的实现，在内存中以不连续的方式存储元素。

**迭代链表的五种方法是：**

1.  使用 `for` 循环
2.  使用 `while` 循环
3.  使用增强型 `for` 循环
4.  使用迭代器
5.  使用 `forEach()` 方法

## 方法一：使用 For 循环

```java
// Java program for iterating the LinkedList
// using For loop

import java.util.LinkedList;

public class GFG {
    public static void main(String[] args)
    {

        // Creating a LinkedList of Integer type
        LinkedList<Integer> linkedList = new LinkedList<>();

        // Inserting some Integer values to our LinkedList
        linkedList.add(40);
        linkedList.add(44);
        linkedList.add(80);
        linkedList.add(9);

        // LinkedList after insertions: [40, 44, 80, 9]

        // Calling the function to iterate our LinkedList
        iterateUsingForLoop(linkedList);
    }

    // Function to iterate the LinkedList using a simple for
    // loop
    public static void
    iterateUsingForLoop(LinkedList<Integer> linkedList)
    {

        System.out.print(
            "Iterating the LinkedList using a simple for loop : ");

        for (int i = 0; i < linkedList.size(); i++) {
            System.out.print(linkedList.get(i) + " ");
        }
    }
}
```

**输出**

```java
Iterating the LinkedList using a simple for loop : 40 44 80 9
```