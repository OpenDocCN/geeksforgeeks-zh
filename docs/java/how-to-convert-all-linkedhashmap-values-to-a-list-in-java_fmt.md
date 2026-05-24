# 如何用 Java 将所有 LinkedHashMap 值转换成列表？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-all-linkedhashmap-values-to-a-list-in-java/](https://www.geeksforgeeks.org/how-to-convert-all-linkedhashmap-values-to-a-list-in-java/)

任务是将所有 [`LinkedHashMap`](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 值转换为 Java 中的列表。`LinkedHashMap` 是一个映射的实现。[`Map`](https://www.geeksforgeeks.org/map-interface-java-examples/) 和 [`List`](https://www.geeksforgeeks.org/list-interface-java-examples/) 是两种不同的数据结构。映射存储键值对，而列表是元素的有序集合。

使用 [`values()`](https://www.geeksforgeeks.org/hashmap-values-method-in-java/) 方法将链接哈希表的所有值转换为列表。`LinkedHashMap` 类的 `values()` 方法返回地图对象中包含的所有值的 [`Collection`](https://www.geeksforgeeks.org/collection-interface-in-java-with-examples/) 视图。然后，您可以使用此集合将其转换为列表对象。

**语法：**

```java
LinkedHashMap.values()
```

**返回值：** 该方法用于返回包含地图所有值的集合视图。

**例 1：**

## 示例 1

```java
// Java program to Convert all LinkedHashMap values to a
// List

import java.util.ArrayList;
import java.util.LinkedHashMap;
import java.util.List;

public class LinkedHashMapToListExample {

    public static void main(String[] args) {

        // instance of linkedhashmap
        LinkedHashMap<Integer, Integer> lhmap
            = new LinkedHashMap<Integer, Integer>();

        // add mappings
        lhmap.put(1, 11);
        lhmap.put(2, 22);
        lhmap.put(3, 33);

        // convert values to a list
        List<Integer> listValues
            = new ArrayList<Integer>(lhmap.values());

        // print values
        System.out.println("List contains:");
        for (Integer value : listValues) {
            System.out.println(value);
        }
    }
}
```

**输出**

```java
List contains:
11
22
33
```

**例 2：**

## 示例 2

```java
// Java program to Convert all LinkedHashMap values to a
// List

import java.util.ArrayList;
import java.util.LinkedHashMap;
import java.util.List;

public class LinkedHashMapToListExample {

    public static void main(String[] args) {

        // instance of linkedhashmap
        LinkedHashMap<Integer, String> lhmap
            = new LinkedHashMap<Integer, String>();

        // add mappings
        lhmap.put(10, "Geeks");
        lhmap.put(15, "4");
        lhmap.put(20, "Geeks");
        lhmap.put(25, "Welcomes");
        lhmap.put(30, "You");

        // convert values to a list
        List<String> listValues
            = new ArrayList<String>(lhmap.values());

        // print values
        System.out.println("List contains:");
        for (String value : listValues) {
            System.out.println(value);
        }
    }
}
```

**输出**

```java
List contains:
Geeks
4
Geeks
Welcomes
You
```