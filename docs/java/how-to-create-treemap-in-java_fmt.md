# 如何用 Java 创建树形图？

> 原文：[https://www.geeksforgeeks.org/how-to-create-treemap-in-java/](https://www.geeksforgeeks.org/how-to-create-treemap-in-java/)

Java 中的 [`TreeMap`](https://www.geeksforgeeks.org/treemap-in-java/) 是用来实现 [`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口和 [`NavigableMap`](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 接口以及 [`AbstractMap`](https://www.geeksforgeeks.org/abstract-classes-in-java/) 类的。`Map` 根据其键的自然顺序进行排序，或者通过 `Map` 创建时提供的 [`Comparator`](https://www.geeksforgeeks.org/comparator-interface-java/) 进行排序，具体取决于使用的构造函数。

要创建 `TreeMap`，我们可以使用 `Map` 类或 `TreeMap` 类。

## 示例1：创建空TreeMap

```java
// Java program demonstrate how to create a TreeMap

import java.util.*;

class GFG {

    public static void main(String[] args)
    {
        // Declaring a treemap
        TreeMap<Integer, String> map;

        // Creating an empty TreeMap
        map = new TreeMap<Integer, String>();

        System.out.println("TreeMap successfully"
                           + " created");
    }
}
```

**Output**

```
TreeMap successfully created
```

## 示例2：创建并添加元素到TreeMap

```java
// Java program demonstrate how to create and add elements
// to TreeMap

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating an empty TreeMap using Map interface
        Map<Integer, String> map = new TreeMap<>();

        System.out.println("TreeMap successfully"
                           + " created");

        // Adding elements
        map.put(1, "Geeks");
        map.put(2, "for");
        map.put(3, "Geeks");

        // Printing TreeMap
        System.out.println("TreeMap: " + map);
    }
}
```

**Output**

```
TreeMap successfully created
TreeMap: {1=Geeks, 2=for, 3=Geeks}
```