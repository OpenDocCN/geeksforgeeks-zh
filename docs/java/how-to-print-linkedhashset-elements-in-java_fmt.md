# 如何用 Java 打印 LinkedHashSet 元素？

> 原文: [https://www.geeksforgeeks.org/how-to-print-linkedhashset-elements-in-java/](https://www.geeksforgeeks.org/how-to-print-linkedhashset-elements-in-java/)

`LinkedHashSet` 是 `HashSet` 的子类，其中不允许重复，但插入顺序保持不变。元素按照插入的顺序打印。

有几种方法可以打印 `LinkedHashSet` 元素:
*   通过直接打印元素
*   通过使用增强的 for 循环
*   使用 `iterator`
*   使用 `Arrays.toString()`
*   使用对象类的 `toString()` 方法来打印包含自定义类对象的 `LinkedHashSet` 元素。

## 方法一: 简单打印元素到控制台

*   让我们创建一个 `LinkedHashSet` 的例子，向其中添加元素，并简单地将其打印到控制台。
*   一种方法是直接打印集合对象的名称，然后打印 `LinkedHashSet` 的内容。

### Java

```java
// Java program to print the elements of LinkedHashSet

import java.util.*;
class GfG {
    public static void main(String args[])
    {
        // Creating an instance of LinkedHashSet
        LinkedHashSet<String> hs = new LinkedHashSet<>();

        // Adding elements to the LinkedHashSet
        hs.add("Hey");
        hs.add("How");
        hs.add("are");
        hs.add("You");

        // Printing
        System.out.println(hs);
    }
}
```

### 输出

```java
[Hey, How, are, You]
```